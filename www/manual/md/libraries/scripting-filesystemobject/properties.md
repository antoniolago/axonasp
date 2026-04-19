# Properties

## Overview

This page lists properties exposed by the Scripting.FileSystemObject object family. Properties are organized by the sub-object that exposes them.

## FileSystemObject Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Drives | Read | DrivesCollection | Returns a DrivesCollection object containing one Drive entry per available drive on the server. |

## File Properties

A File object is returned by `GetFile` or from the `Files` collection of a Folder.

| Property | Access | Type | Description |
|---|---|---|---|
| Attributes | Read | Integer | Bitmask of file attributes: 1 = ReadOnly, 2 = Hidden, 32 = Archive. |
| DateCreated | Read | Date | The date and time the file was created. |
| DateLastAccessed | Read | Date | The date and time the file was last accessed. |
| DateLastModified | Read | Date | The date and time the file was last modified. |
| Drive | Read | Drive | The Drive object for the drive on which the file resides. |
| Name | Read/Write | String | The file name including its extension. Assigning a new value renames the file within its parent folder. |
| ParentFolder | Read | Folder | The Folder object representing the parent directory of this file. |
| Path | Read | String | The full absolute path to the file. |
| ShortName | Read | String | The short (8.3) file name. On non-Windows hosts this is the same as Name. |
| ShortPath | Read | String | The full short-format path. On non-Windows hosts this is the same as Path. |
| Size | Read | Integer | The size of the file in bytes. |
| Type | Read | String | A description of the file type derived from its extension (for example, "TXT File"). Returns "File" when there is no extension. |

## Folder Properties

A Folder object is returned by `GetFolder`, `CreateFolder`, or from the `SubFolders` collection of another Folder.

| Property | Access | Type | Description |
|---|---|---|---|
| Attributes | Read | Integer | Bitmask of folder attributes: 2 = Hidden, 16 = Directory. |
| DateCreated | Read | Date | The date and time the folder was created. |
| DateLastAccessed | Read | Date | The date and time the folder was last accessed. |
| DateLastModified | Read | Date | The date and time the folder was last modified. |
| Drive | Read | Drive | The Drive object for the drive on which the folder resides. |
| Files | Read | FilesCollection | A collection of File objects for all files directly inside this folder. |
| IsRootFolder | Read | Boolean | Returns True if this folder is the root of its drive; False otherwise. |
| Name | Read/Write | String | The folder name. Assigning a new value renames the folder within its parent directory. |
| ParentFolder | Read | Folder | The Folder object representing the parent directory of this folder. |
| Path | Read | String | The full absolute path to the folder. |
| ShortName | Read | String | The short (8.3) folder name. On non-Windows hosts this is the same as Name. |
| ShortPath | Read | String | The full short-format path. On non-Windows hosts this is the same as Path. |
| Size | Read | Integer | The total size of the folder in bytes, including all files and sub-folders. |
| SubFolders | Read | SubFoldersCollection | A collection of Folder objects for all immediate sub-folders of this folder. |
| Type | Read | String | Always returns "Folder" for Folder objects. |

## TextStream Properties

A TextStream object is returned by `OpenTextFile`, `CreateTextFile`, or `File.OpenAsTextStream`.

| Property | Access | Type | Description |
|---|---|---|---|
| AtEndOfStream | Read | Boolean | Returns True when the read position has reached the end of the stream; False otherwise. |
| Column | Read | Integer | The 1-based column position of the current read/write cursor within the current line. |
| Line | Read | Integer | The 1-based line number of the current read/write cursor position. |

## Drive Properties

A Drive object is returned by `GetDrive` or by the `Drive` property of a File or Folder.

| Property | Access | Type | Description |
|---|---|---|---|
| AvailableSpace | Read | Integer | Bytes available on the drive for the current user. |
| DriveLetter | Read | String | The single-letter drive identifier (for example, "C"). |
| DriveType | Read | Integer | Always returns 2 (Fixed) in the current implementation. |
| FileSystem | Read | String | The file system type string. Returns "NTFS" on Windows; "UnixFS" on other platforms. |
| FreeSpace | Read | Integer | Total free bytes on the drive. |
| IsReady | Read | Boolean | Returns True if the drive is accessible; False otherwise. |
| Path | Read | String | The drive path (for example, "C:" on Windows or "/" on Unix). |
| RootFolder | Read | Folder | The Folder object representing the root directory of this drive. |
| SerialNumber | Read | String | The volume serial number string of the drive. |
| ShareName | Read | String | The network share name for the drive, if applicable. Returns an empty String for local drives. |
| TotalSize | Read | Integer | Total capacity of the drive in bytes. |
| VolumeName | Read | String | The volume label of the drive. |

## Remarks

- Read-only properties do not accept assignment. Attempting to assign a value to a read-only property is silently ignored by the FSO runtime.
- The `Name` property on File and Folder objects is writable and triggers an OS-level rename when assigned.
- TextStream properties (`AtEndOfStream`, `Line`, `Column`) reflect the internal stream state and are updated automatically by read and write operations.
