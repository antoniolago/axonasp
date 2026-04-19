# Use CreateObject from WScript.Shell

## Overview
Use CreateObject to instantiate another COM-style object through the same runtime path used by Server.CreateObject.

## Syntax

```asp
Set result = shell.CreateObject(progID)
```

## Parameters

- progID (String, required): Programmatic identifier of the object to create, such as G3JSON, Scripting.Dictionary, or WScript.Shell.

## Return Value

Returns an object reference when creation succeeds.

Returns Empty when progID is missing, blank, or object creation fails.

## How It Works

- WScript.Shell.CreateObject delegates to the same backend object factory used by Server.CreateObject.
- The method does not return a Boolean status. Check the returned value with IsObject.

## Remarks

- Method names are case-insensitive.
- Use Set when assigning the returned object reference.

## Example

```asp
<%
Option Explicit

Dim shell, dict
Set shell = Server.CreateObject("WScript.Shell")
Set dict = shell.CreateObject("Scripting.Dictionary")

If IsObject(dict) Then
    dict.Add "engine", "G3Pix AxonASP"
    Response.Write dict.Item("engine")
Else
    Response.Write "CreateObject failed"
End If

Set dict = Nothing
Set shell = Nothing
%>
```

