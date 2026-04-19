# Methods

## Overview

This page lists all methods exposed by the root Scripting.FileSystemObject handle. Methods that return sub-objects (File, Folder, TextStream, Drive) require `Set` for assignment.

## FileSystemObject Methods

| Method | Returns | Description |
|---|---|---|
| BuildPath(path, name) | String | Concatenates a path and a file name using the OS path separator. |
| CopyFile(source, destination [, overwrite]) | Empty | Copies one file to the destination path. Overwrites by default. |
| CopyFolder(source, destination [, overwrite]) | Empty | Recursively copies a folder tree to the destination path. Overwrites by default. |
| CreateFolder(folderspec) | Folder | Creates the specified folder (and any missing parent folders) and returns a Folder object. |
| CreateTextFile(filename [, overwrite]) | TextStream | Creates a new file opened for writing and returns a TextStream. If overwrite is False and the file exists, returns Empty. |
| DeleteFile(filespec) | Empty | Deletes the specified file. Raises error 53 (File not found) or error 70 (Permission denied) on failure. |
| DeleteFolder(folderspec) | Empty | Deletes the specified folder and all its contents. Raises error 76 (Path not found) or error 70 on failure. |
| DriveExists(drivespec) | Boolean | Returns True if the specified drive or drive path exists; False otherwise. |
| FileExists(filespec) | Boolean | Returns True if the specified file exists; False otherwise. |
| FolderExists(folderspec) | Boolean | Returns True if the specified folder exists; False otherwise. |
| GetAbsolutePathName(pathspec) | String | Returns the fully resolved absolute path for the given relative or partial path. Returns an empty String if the path cannot be resolved. |
| GetBaseName(pathspec) | String | Returns the base file name without its extension. |
| GetDrive(drivespec) | Drive | Returns a Drive object for the specified drive letter or path. Returns Empty if the drive name cannot be determined. |
| GetDriveName(pathspec) | String | Returns the drive letter or identifier extracted from a path. Returns an empty String if not applicable. |
| GetExtensionName(pathspec) | String | Returns the file extension without the leading period. Returns an empty String if there is no extension. |
| GetFile(filespec) | File | Returns a File object for the specified file path. Raises error 53 if the file does not exist. |
| GetFileName(pathspec) | String | Returns the last path component, including the extension. Returns an empty String if the path is empty. |
| GetFileVersion(filespec) | String | Returns the version resource string of the specified file. Returns "1.0.0.0" if no version information is available. |
| GetFolder(folderspec) | Folder | Returns a Folder object for the specified folder path. Raises error 76 if the folder does not exist. |
| GetParentFolderName(pathspec) | String | Returns the parent directory path of the given path. Returns an empty String if there is no parent. |
| GetSpecialFolder(foldertype) | String | Returns the path of a special system folder: 0 = Windows directory, 1 = System32, 2 = Temp directory. |
| GetStandardStream(standardStreamType) | TextStream | Returns a TextStream for stdin (0), stdout (1), or stderr (2). Raises error 5 for any other stream type. |
| GetTempName() | String | Returns a unique temporary file name in `radXXXXXX.axon.tmp` format. Does not create the file on disk. |
| MoveFile(source, destination) | Empty | Moves a file from source to destination. |
| MoveFolder(source, destination) | Empty | Moves a folder from source to destination. |
| OpenTextFile(filename [, iomode [, create]]) | TextStream | Opens a text file and returns a TextStream. iomode: 1 = ForReading, 2 = ForWriting, 8 = ForAppending. |

## Remarks

- Use `Set` when assigning the return value of any method that returns a File, Folder, TextStream, or Drive object.
- Mutating methods (Delete, Move, Copy) silently ignore operations when the source or destination path cannot be resolved, unless a VBScript error is explicitly raised by the runtime.
- `On Error Resume Next` is the standard guard for file operations that may fail at runtime.
