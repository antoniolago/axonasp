# Field.DataFormat Property

Returns the data format object associated with the field.

## Syntax

```asp
fmt = rs.Fields("columnName").DataFormat
```

## Return Value

Empty. In the current G3Pix AxonASP ADODB runtime, this property returns Empty.

## Remarks

- Property names are case-insensitive.
- This property is exposed for compatibility.
- Assignments are not supported in the current implementation.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, fmt

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT name FROM users")
If Not rs.EOF Then
    fmt = rs.Fields("name").DataFormat
    Response.Write "IsEmpty(DataFormat): " & CStr(IsEmpty(fmt))
End If

rs.Close
conn.Close
Set rs = Nothing
Set conn = Nothing
%>
```