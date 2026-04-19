# Recordset.DataMember Property

Gets or sets the named data member associated with the recordset.

## Syntax

```asp
value = rs.DataMember
rs.DataMember = newValue
```

## Return Value

String. Returns current data member name.

## Remarks

- Property names are case-insensitive.
- Used mainly in bound-data scenarios.
- Often empty for direct SQL recordsets.

## Code Example

```asp
<%
Option Explicit
Dim rs

Set rs = Server.CreateObject("ADODB.Recordset")
rs.DataMember = "Users"
Response.Write rs.DataMember

Set rs = Nothing
%>
```