# Recordset.CompareBookmarks Method

Compares two bookmark positions from the same recordset.

## Syntax

```asp
comparison = rs.CompareBookmarks(bookmark1, bookmark2)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `bookmark1` | Variant | Yes | First bookmark value. |
| `bookmark2` | Variant | Yes | Second bookmark value. |

## Return Value

Integer. Returns `-1` when `bookmark1` is before `bookmark2`, `0` when both point to the same row, and `1` when `bookmark1` is after `bookmark2`.

## Remarks

- Method names are case-insensitive.
- Both bookmarks must come from the same recordset cursor context.
- Invalid bookmarks raise runtime errors.
- Use this method for cursor position logic without moving the active row.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, bm1, bm2, cmp

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
If Not rs.EOF Then
    bm1 = rs.Bookmark
    rs.MoveNext
    If Not rs.EOF Then
        bm2 = rs.Bookmark
        cmp = rs.CompareBookmarks(bm1, bm2)
        Response.Write "Compare result: " & CStr(cmp)
    End If
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```