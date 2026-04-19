# Use Scripting.FileSystemObject in AxonASP

## Overview

Scripting.FileSystemObject provides access to the server file system from Classic ASP scripts. Use it to create, read, update, and delete files and folders; navigate directory hierarchies; open text streams for reading or writing; and query drive information.

Creating the object returns a root FSO handle. From it you obtain **File**, **Folder**, **TextStream**, and **Drive** sub-objects, each exposing their own methods and properties.

## Prerequisites

- The target path must reside within the server document root or a mapped physical path.
- Write operations require that the server process has the necessary file system permissions on the target path.
- All relative paths are resolved against the document root before being forwarded to the operating system.

## Syntax

```asp
Set fso = Server.CreateObject("Scripting.FileSystemObject")
```

## Return Value

Returns a native FSO object handle. Use `Set` for assignment. Call `Set fso = Nothing` when the object is no longer needed.

## How It Works

The AxonASP runtime resolves all relative paths against the web document root and normalizes path separators for the host operating system before passing them to the OS file API. Closing a TextStream or assigning `Nothing` to a File or Folder handle releases the underlying OS file handle immediately.

The FSO object model is composed of several distinct sub-objects, each returned by methods on the root FSO:

- **File** — Represents a single file entry with metadata properties and stream access.
- **Folder** — Represents a directory with properties, sub-folder and file collections, and a text-file factory.
- **TextStream** — A sequential text I/O stream for reading from or writing to a file.
- **Drive** — Exposes capacity, type, and volume information for one drive.
- **DrivesCollection** — Enumerates all available drives on the server.

## Remarks

- All method and property names are case-insensitive.
- On non-Windows hosts, drive-related properties return normalized values representing the root file system.
- `GetTempName` generates a unique temporary file name in `radXXXXXX.axon.tmp` format and does **not** create the file on disk.
- Attribute values follow classic FSO integer constants: `1` = ReadOnly, `2` = Hidden, `16` = Directory, `32` = Archive.

## Code Example

```asp
<%
Option Explicit
Dim fso, ts, f

Set fso = Server.CreateObject("Scripting.FileSystemObject")

' Write a text file
Set ts = fso.CreateTextFile(Server.MapPath("data/hello.txt"), True)
ts.WriteLine "Hello, World!"
ts.Close
Set ts = Nothing

' Read it back
Set ts = fso.OpenTextFile(Server.MapPath("data/hello.txt"), 1)
Response.Write ts.ReadAll
ts.Close
Set ts = Nothing

' Inspect the file
Set f = fso.GetFile(Server.MapPath("data/hello.txt"))
Response.Write f.Size & " bytes, modified " & f.DateLastModified
Set f = Nothing

Set fso = Nothing
%>
```

