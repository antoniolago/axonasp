# WScript.Shell Methods

## Overview
This page summarizes core methods exposed by the WScript.Shell library in G3Pix AxonASP.

## Methods Reference

| Method | Returns | Description |
|---|---|---|
| Run(command [, windowStyle] [, waitOnReturn]) | Integer | Executes a command line. Returns 0 on successful start and successful completion, non-zero process exit code when waitOnReturn is True and the process fails, or -1 when command is missing, empty, or startup fails. |
| Exec(command) | Object or Empty | Starts a process asynchronously and returns a process object with stream and status members. Returns Empty when command is missing, empty, or startup fails. |
| CreateObject(progID) | Object or Empty | Creates an object using the AxonASP object factory. Returns an object reference on success, or Empty when progID is missing, empty, or object creation fails. |
| GetEnv(name) | String | Returns the value of one environment variable. Returns an empty string when name is missing or the variable does not exist. |
| ExpandEnvironmentStrings(inputText) | String | Expands percent-delimited environment placeholders such as %PATH%. Returns an empty string when inputText is missing. Unknown placeholders are preserved. |

## Remarks

- Method names are case-insensitive.
- Use Set for object-returning methods such as Exec and CreateObject.
