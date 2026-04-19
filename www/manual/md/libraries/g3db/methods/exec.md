# Execute a Non-Query SQL Statement

## Overview

Executes a SQL statement that does not return a row cursor.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set result = db.Exec(sql[, params...])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **sql** | String | Yes | SQL statement to execute. |
| **params** | Any | No | Positional values for statement placeholders. |

## Return Value

- **G3DBResult**: Returned when execution succeeds.
- **Empty**: Returned when connection is not open, SQL is missing, or execution fails.

## Remarks

- Placeholder rewriting is applied for the active driver when required.

## Example

```asp
<%
Option Explicit
Dim db, result
Set db = Server.CreateObject("G3DB")

If db.Open("mysql", "user:pass@tcp(localhost)/db") Then
    Set result = db.Exec("UPDATE users SET active = ? WHERE id = ?", 1, 42)
    If IsEmpty(result) Then Response.Write db.LastError
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Exec`
- **Arguments**: `sql` (String, required), `params...` (Any, optional)
- **Returns**: G3DBResult on success, Empty on failure
