# Fields.Item Method

Returns a Field object by index or column name.

## Syntax

```asp
Set fieldObj = rs.Fields.Item(indexOrName)
```

## Parameters

| Parameter | Type | Required | Description |
|---|---|---|---|
| `indexOrName` | Integer or String | Yes | Zero-based field index or exact field name. |

## Return Value

Field. Returns an ADODB.Field object for the requested column.

## Remarks

- Method names are case-insensitive.
- Use index for faster access in tight loops.
- Use name for readable code when column order can change.
- Invalid index or name raises a runtime error.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, fldByIndex, fldByName

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT id, name FROM users")
If Not rs.EOF Then
    Set fldByIndex = rs.Fields.Item(0)
    Set fldByName = rs.Fields.Item("name")
    Response.Write "Field[0]: " & fldByIndex.Value & "<br>"
    Response.Write "Field['name']: " & fldByName.Value
End If

rs.Close
conn.Close
Set fldByName = Nothing
Set fldByIndex = Nothing
Set rs = Nothing
Set conn = Nothing
%>
```