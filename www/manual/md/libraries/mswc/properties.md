# MSWC Properties

## Overview
This page summarizes property members exposed by MSWC compatibility components in G3Pix AxonASP.

## Properties Reference

| Component | Property | Access | Type | Description |
|---|---|---|---|---|
| MSWC.AdRotator | Border | Read/Write | Integer | Border value used in generated image HTML. Default is -1, which uses schedule-file border metadata. |
| MSWC.AdRotator | Clickable | Read/Write | Boolean | Controls whether generated advertisement HTML is wrapped in anchor tags. |
| MSWC.AdRotator | TargetFrame | Read/Write | String | Target frame name used when clickable advertisements are rendered. |
| MSWC.BrowserType | Browser | Read-only | String | Detected browser label, such as IE, Edge, Chrome, Firefox, Safari, or Unknown. |
| MSWC.BrowserType | Version | Read-only | String | Browser version string. Current compatibility default is 0.0. |
| MSWC.BrowserType | MajorVer | Read-only | String | Browser major version string. Current compatibility default is 0. |
| MSWC.BrowserType | MinorVer | Read-only | String | Browser minor version string. Current compatibility default is 0. |
| MSWC.BrowserType | Frames | Read-only | Boolean | Indicates frame support based on detected user agent heuristics. |
| MSWC.BrowserType | Tables | Read-only | Boolean | Indicates HTML table support. |
| MSWC.BrowserType | Cookies | Read-only | Boolean | Indicates cookie support. |
| MSWC.BrowserType | BackgroundSounds | Read-only | Boolean | Indicates background sound support. |
| MSWC.BrowserType | VBScript | Read-only | Boolean | Indicates VBScript support. |
| MSWC.BrowserType | JavaScript | Read-only | Boolean | Indicates JavaScript support. |
| MSWC.BrowserType | JavaApplets | Read-only | Boolean | Indicates Java applet support. |
| MSWC.BrowserType | ActiveXControls | Read-only | Boolean | Indicates ActiveX control support. |
| MSWC.BrowserType | CDF | Read-only | Boolean | Indicates CDF support. |
| MSWC.MyInfo | AnyCustomProperty | Read-only | String or Empty | Returns one property value loaded from MyInfo.xml when the property key exists, otherwise Empty. |

## Remarks
- Property names are case-insensitive.
- Unsupported property names resolve through component dispatch and may return Empty.
