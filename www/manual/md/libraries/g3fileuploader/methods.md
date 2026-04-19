# G3FILEUPLOADER Methods

## Overview
This page summarizes methods exposed by G3FILEUPLOADER in G3Pix AxonASP for upload validation, processing, and metadata inspection.

## Methods Reference

| Method | Returns | Description |
|---|---|---|
| BlockExtension | Empty | Adds one extension to the blocked list. |
| AllowExtension | Empty | Adds one extension to the allowed list. |
| BlockExtensions | Empty | Adds multiple extensions to the blocked list from a comma-separated string. |
| AllowExtensions | Empty | Adds multiple extensions to the allowed list from a comma-separated string. |
| SetUseAllowedOnly | Empty | Enables or disables allow-list-only validation mode. |
| Process | Dictionary or Empty | Processes one uploaded file and returns a dictionary with success flag, names, size, MIME type, and error message. Returns Empty when required arguments are missing. |
| Save | Dictionary or Empty | Alias of Process. |
| ProcessAll | Array of Dictionary | Processes all uploaded files and returns one result dictionary per file. |
| SaveAll | Array of Dictionary | Alias of ProcessAll. |
| GetFileInfo | Dictionary or Empty | Returns metadata for one uploaded form field. Returns Empty when request context is unavailable. |
| GetAllFilesInfo | Array of Dictionary | Returns metadata for all uploaded files in the current multipart request. |
| Form | String or Empty | Gets a multipart form field value by name. Returns Empty when not found. |
| FormValue | String or Empty | Alias of Form. |
| IsValidExtension | Boolean | Validates whether an extension is currently allowed under configured rules. |

## Remarks
- Method names are case-insensitive.
- Result dictionaries include IsSuccess and ErrorMessage keys for operation status.
