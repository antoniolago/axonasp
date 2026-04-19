# G3FILEUPLOADER Properties

## Overview
This page summarizes properties exposed by G3FILEUPLOADER in G3Pix AxonASP.

## Properties Reference

| Property | Access | Type | Description |
|---|---|---|---|
| BlockedExtensions | Read-only | Array of String | Gets the current blocked extension set. |
| AllowedExtensions | Read-only | Array of String | Gets the current allowed extension set. |
| MaxFileSize | Read/Write | Integer | Gets or sets the maximum upload size in bytes for each file. |
| PreserveOriginalName | Read/Write | Boolean | Gets or sets whether saved files preserve the original uploaded filename. |
| DebugMode | Read/Write | Boolean | Gets or sets debug mode for uploader behavior. |

## Remarks
- Property names are case-insensitive.
- Use AllowExtension, AllowExtensions, BlockExtension, and BlockExtensions to mutate extension lists.
