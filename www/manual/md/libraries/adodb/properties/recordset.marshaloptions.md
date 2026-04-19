# Recordset.MarshalOptions Property

Gets or sets marshaling behavior flags for recordset transport.

## Syntax

```asp
value = rs.MarshalOptions
rs.MarshalOptions = newValue
```

## Return Value

Integer. Returns current marshal options flag.

## Remarks

- Property names are case-insensitive.
- Marshaling behavior can be provider/runtime specific.
- Set before serialization or transport scenarios.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.MarshalOptions = 0
Response.Write CStr(rs.MarshalOptions)

Set rs = Nothing
%>
```