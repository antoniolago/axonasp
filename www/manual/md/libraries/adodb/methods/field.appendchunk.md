# Field.AppendChunk Method

Appends binary or text chunk data to the current field value.

## Syntax

```asp
fieldObj.AppendChunk data
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `data` | String or Byte Array | Yes | Chunk data appended to the target field. |

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- AppendChunk is commonly used for long text and binary fields.
- Multiple AppendChunk calls append data sequentially.
- Call `Recordset.Update` to persist appended data.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT * FROM users WHERE id = 1")
If Not rs.EOF Then
    rs.Fields("notes").AppendChunk " First chunk."
    rs.Fields("notes").AppendChunk " Second chunk."
    rs.Update
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```