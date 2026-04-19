# Prepare a Reusable SQL Statement

## Overview

Creates a prepared SQL statement object bound to the active connection.

## Prerequisites

Instantiate the library with `Server.CreateObject("G3DB")`.

## Syntax

```asp
Set stmt = db.Prepare(sql)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| **sql** | String | Yes | SQL statement to prepare. |

## Return Value

- **G3DBStatement**: Returned when statement preparation succeeds.
- **Empty**: Returned when connection is not open, SQL is missing, or prepare fails.

## Remarks

- Placeholder rewriting is applied before preparation.

## Example

```asp
<%
Option Explicit
Dim db, stmt
Set db = Server.CreateObject("G3DB")

If db.Open("sqlite", "data.db") Then
    Set stmt = db.Prepare("SELECT name FROM users WHERE id = ?")
    If Not IsEmpty(stmt) Then stmt.Close
    db.Close
End If

Set db = Nothing
%>
```

## API Reference

- **Object**: `G3DB`
- **Method**: `Prepare`
- **Arguments**: `sql` (String, required)
- **Returns**: G3DBStatement on success, Empty on failure
