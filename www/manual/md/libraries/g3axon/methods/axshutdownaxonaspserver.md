# Shut Down the AxonASP Server

## Overview

Immediately terminates the AxonASP server process. This method requires the shutdown function to be enabled in the configuration file before it can execute.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3AXON.FUNCTIONS")`.

Enable the shutdown function in `config/axonasp.toml`:

```toml
[axfunctions]
enable_axservershutdown_function = true
```

## Syntax

```asp
result = ax.AxShutdownAxonASPServer()
```

## Parameters

This method does not accept any parameters.

## Return Value

- **Boolean `True`**: The shutdown was triggered and the server process will terminate immediately.
- **Boolean `False`**: The `enable_axservershutdown_function` configuration key is `false` or absent. The server continues running.

## Remarks

- **This call is irreversible.** All in-flight requests are immediately cancelled when the server exits.
- Only expose this method in a secured administrative page. Do not make it publicly accessible.
- The method calls `os.Exit` internally. No further code in the current script executes after a `True` return.
- Method names are case-insensitive.

## Example

```asp
<%
Option Explicit
Dim ax, result
Set ax = Server.CreateObject("G3AXON.FUNCTIONS")

result = ax.AxShutdownAxonASPServer()

If result Then
    ' Execution never reaches here — server is terminating.
Else
    Response.Write "Shutdown is not enabled in the configuration."
End If

Set ax = Nothing
%>
```

## API Reference

- **Object**: `G3AXON.FUNCTIONS`
- **Method**: `AxShutdownAxonASPServer`
- **Arguments**: None
- **Returns**: Boolean — `True` if the server terminated; `False` if shutdown is disabled in configuration
