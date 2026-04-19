# Run a Command with Run

## Overview
Use Run to execute a command line and receive an Integer status code.

## Syntax

```asp
exitCode = shell.Run(command, windowStyle, waitOnReturn)
```

## Parameters

- command (String, required): Command line to execute.
- windowStyle (Integer, optional): Accepted for compatibility. Current AxonASP runtime does not apply this value.
- waitOnReturn (Boolean, optional): When True, waits for process completion before returning. Default is True.

## Return Value

Returns Integer 0 when command start succeeds and either:
- the process finishes successfully when waitOnReturn is True, or
- the process starts successfully when waitOnReturn is False.

Returns an Integer greater than 0 when waitOnReturn is True and the process exits with a non-zero exit code.

Returns Integer -1 when command is missing, blank, or process startup fails.

## How It Works

- On Windows, AxonASP executes the command through cmd.exe /c.
- On non-Windows environments, AxonASP executes through sh -c.

## Remarks

- Method names are case-insensitive.
- Run does not return process output. Use Exec when you need StdOut or StdErr streams.

## Example

```asp
<%
Option Explicit

Dim shell, code
Set shell = Server.CreateObject("WScript.Shell")

code = shell.Run("cmd /c echo G3Pix AxonASP", 0, True)
Response.Write "Run returned: " & code

Set shell = Nothing
%>
```

