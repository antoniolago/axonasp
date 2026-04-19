# Connection.Cancel Method

Cancels the current connection operation.

## Syntax

```asp
conn.Cancel
```

## Parameters

No parameters.

## Return Value

Empty. The method does not return a value.

## Remarks

- Method names are case-insensitive.
- In the current G3Pix AxonASP ADODB implementation, this method is a compatibility no-op.
- Use this method only when porting legacy scripts that call Connection.Cancel.
- The method does not close the connection.

## Code Example

```asp
<%
Option Explicit
Dim conn

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

' Compatibility no-op in current runtime.
conn.Cancel

Response.Write "Connection.Cancel executed" & "<br>"
Response.Write "Connection state: " & CStr(conn.State)

conn.Close
Set conn = Nothing
%>
```