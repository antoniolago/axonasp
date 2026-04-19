# Field.GetChunk Method

Reads a chunk of data from the current field value.

## Syntax

```asp
chunk = fieldObj.GetChunk(length)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `length` | Integer | No | Number of bytes or characters to read. If omitted, reads remaining data. |

## Return Value

String. Returns the chunk data read from the field.

## Remarks

- Method names are case-insensitive.
- Use GetChunk to read long text or binary content in segments.
- Repeated calls return subsequent portions of the field data.
- Reset reading position by reloading the row.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, part

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT notes FROM users WHERE id = 1")
If Not rs.EOF Then
    part = rs.Fields("notes").GetChunk(20)
    Response.Write "Chunk: " & part
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```