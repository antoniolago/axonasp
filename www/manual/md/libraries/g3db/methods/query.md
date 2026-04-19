# Execute a Query and Return a Result Set

## Overview

Executes a SQL query and returns a forward-only G3DBResultSet object.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set rs = db.Query(sql[, params...])
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **sql** | String | Yes | SQL query text. |
| **params** | Any | No | Positional values for query placeholders. |

## Return Value

- **G3DBResultSet**: Returned when query execution succeeds.
- **Empty**: Returned when connection is not open, SQL is missing, or query execution fails.

## Remarks

- Close the result set when processing is complete.

## Example

```asp
<%
Option Explicit
Dim db, rs
Set db = Server.CreateObject("G3DB")

If db.Open("mysql", "user:pass@tcp(localhost)/db") Then
    Set rs = db.Query("SELECT id FROM users WHERE active = ?", 1)
    If Not IsEmpty(rs) Then rs.Close
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Query`
- **Arguments**: `sql` (String, required), `params...` (Any, optional)
- **Returns**: G3DBResultSet on success, Empty on failure
