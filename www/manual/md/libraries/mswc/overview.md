# Use MSWC Components in G3Pix AxonASP

## Overview
G3Pix AxonASP provides a compatibility surface for legacy MSWC-style components. Each component is exposed through native object dispatch with case-insensitive member names.

## Supported ProgIDs
- MSWC.AdRotator
- MSWC.BrowserType
- MSWC.NextLink
- MSWC.ContentRotator
- MSWC.Counters
- MSWC.Tools
- MSWC.MyInfo
- MSWC.PageCounter
- MSWC.PermissionChecker

## Prerequisites
- Instantiate components with Server.CreateObject using the exact ProgID.
- Ensure referenced files exist when using file-based components such as AdRotator, NextLink, and ContentRotator.
- Enable MSWC page counter configuration before using MSWC.PageCounter.

## How It Works
- Each component has its own method and property surface.
- Unsupported members return Empty.
- Some components read request or server context to produce results.

## Code Example
```asp
<%
Option Explicit

Dim browserType, browserName, canUseCookies
Set browserType = Server.CreateObject("MSWC.BrowserType")

browserName = browserType.Browser
canUseCookies = browserType.Cookies

Response.Write "Browser=" & browserName & " Cookies=" & CStr(canUseCookies)

Set browserType = Nothing
%>
```