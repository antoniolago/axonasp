# Run a Command with Exec

## Overview
Use Exec to start a process and interact with it through a process object that exposes output streams and status information.

## Syntax

```asp
Set execObj = shell.Exec(command)
```

## Parameters

- command (String, required): Command line to execute.

## Return Value

Returns an object reference that represents the running process when process startup succeeds.

Returns Empty when command is missing, blank, or process startup fails.

## How It Works

- On Windows, AxonASP runs the command through cmd.exe /c.
- The returned process object exposes members such as StdOut, StdErr, Status, ExitCode, and ProcessID.

## Remarks

- Method names are case-insensitive.
- Use Set when assigning the returned process object.
- Exec starts asynchronously. Use process state members to track completion.

## Example

```asp
<%
Option Explicit

Dim shell, execObj
Set shell = Server.CreateObject("WScript.Shell")
Set execObj = shell.Exec("echo AxonASP")

If IsObject(execObj) Then
    execObj.WaitUntilDone 5000
    Response.Write "ExitCode=" & execObj.ExitCode
Else
    Response.Write "Exec failed"
End If

Set execObj = Nothing
Set shell = Nothing
%>
```

