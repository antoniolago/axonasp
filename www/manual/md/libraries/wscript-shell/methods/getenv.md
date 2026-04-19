# Read an Environment Variable with GetEnv

## Overview
Use GetEnv to read one environment variable from the current process environment.

## Syntax

```asp
value = shell.GetEnv(name)
```

## Parameters

- name (String, required): Environment variable name, such as PATH, TEMP, or USERNAME.

## Return Value

Returns a String containing the variable value when the variable exists.

Returns an empty string when name is missing or when the variable is not defined.

## How It Works

- The method reads directly from the OS process environment seen by AxonASP.
- Missing variables do not raise an error. The method returns an empty string.

## Remarks

- Method names are case-insensitive.
- The alias EnvironmentVariables is also accepted.

## Example

```asp
<%
Option Explicit

Dim shell, pathValue
Set shell = Server.CreateObject("WScript.Shell")

pathValue = shell.GetEnv("PATH")
If pathValue = "" Then
    Response.Write "PATH is not available"
Else
    Response.Write "PATH length: " & Len(pathValue)
End If

Set shell = Nothing
%>
```

