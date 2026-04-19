# MSWC Methods

## Overview
This page summarizes methods exposed by MSWC compatibility components in G3Pix AxonASP.

## Methods Reference

| Component | Method | Returns | Description |
|---|---|---|---|
| MSWC.AdRotator | GetAdvertisement(scheduleFile) | String | Returns generated advertisement HTML. Returns an empty string when no argument is provided or no entries are available. |
| MSWC.NextLink | GetListCount(listFile) | Integer or Empty | Returns the number of entries in the link list. Returns Empty when listFile is missing. |
| MSWC.NextLink | GetListIndex(listFile) | Integer or Empty | Returns the current 1-based index that matches the executing page URL. Returns Empty when listFile is missing. |
| MSWC.NextLink | GetNextDescription(listFile) | String or Empty | Returns the description of the next entry. Returns Empty when listFile is missing. |
| MSWC.NextLink | GetNextURL(listFile) | String or Empty | Returns the URL of the next entry. Returns Empty when listFile is missing. |
| MSWC.NextLink | GetPreviousDescription(listFile) | String or Empty | Returns the description of the previous entry. Returns Empty when listFile is missing. |
| MSWC.NextLink | GetPreviousURL(listFile) | String or Empty | Returns the URL of the previous entry. Returns Empty when listFile is missing. |
| MSWC.NextLink | GetNthDescription(listFile, index) | String or Empty | Returns the description of the specified 1-based entry. Returns Empty when required arguments are missing. |
| MSWC.NextLink | GetNthURL(listFile, index) | String or Empty | Returns the URL of the specified 1-based entry. Returns Empty when required arguments are missing. |
| MSWC.ContentRotator | ChooseContent(contentFile) | String or Empty | Returns one selected content block using weight rules. Returns Empty when contentFile is missing. |
| MSWC.ContentRotator | GetAllContent(contentFile) | String or Empty | Returns all content blocks joined by separator markup. Returns Empty when contentFile is missing. |
| MSWC.Counters | Get(name) | Integer or Empty | Returns the current counter value or 0 when the counter does not exist. Returns Empty when name is missing. |
| MSWC.Counters | Increment(name) | Integer or Empty | Increments and returns the counter value. Returns Empty when name is missing. |
| MSWC.Counters | Remove(name) | Empty | Removes one counter key. Returns Empty. |
| MSWC.Counters | Set(name, value) | Empty | Sets one counter value when arguments are provided. Returns Empty. |
| MSWC.Tools | FileExists(path) | Boolean | Returns True when the mapped file exists, otherwise False. |
| MSWC.Tools | Owner(path) | String | Returns the resolved owner name for the mapped file path, or an empty string when unavailable. |
| MSWC.Tools | PluginExists(name) | Boolean | Returns False. |
| MSWC.Tools | ProcessForm(...) | Empty | Returns Empty. |
| MSWC.MyInfo | URL(index) | String or Empty | Returns URL-indexed value from MyInfo.xml, such as URL1 or URL2. Returns Empty when not found or argument is missing. |
| MSWC.MyInfo | URLWords(index) | String or Empty | Returns URLWords-indexed value from MyInfo.xml, such as URLWords1. Returns Empty when not found or argument is missing. |
| MSWC.PageCounter | Hits([path]) | Integer or Empty | Returns hit count for path or current script URL. Returns 0 when no path is resolved. Returns Empty when the component is disabled. |
| MSWC.PageCounter | PageHit() | Integer or Empty | Increments and returns hit count for the current script URL. Returns 0 when no path is resolved. Returns Empty when the component is disabled. |
| MSWC.PageCounter | Reset([path]) | Empty | Removes page counter state for path or current script URL. Returns Empty. |
| MSWC.PermissionChecker | HasAccess(path) | Boolean or Empty | Returns True when the mapped path is readable by the process, otherwise False. Returns Empty when path is missing. |

## Remarks
- Method names are case-insensitive.
- Methods that return Empty indicate missing required arguments or unsupported operation context for that call path.
