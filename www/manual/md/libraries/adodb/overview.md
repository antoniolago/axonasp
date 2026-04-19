# ADODB Library

The ADODB library provides database connectivity and data manipulation through Connection, Recordset, Command, and supporting objects. Use these objects to execute SQL queries, manage transactions, and perform CRUD operations on any ODBC- or OLE DB-compatible database.

## Supported Objects

- **Connection** — Manages database connections, executes SQL commands, begins transactions, and retrieves database schema information.
- **Recordset** — Represents a result set of rows and columns, with support for navigation, editing, deletion, and persistence.
- **Command** — Encapsulates SQL statements and stored procedure calls with parameter support.
- **Error** — Represents a single database error within the Errors collection.
- **Field** — Represents a single column within a Fields collection, including its metadata and value.
- **Parameter** — Represents a single SQL parameter within the Parameters collection.

## Supported ProgIDs

| ProgID | Object |
|---|---|
| `ADODB.Connection` | Database connection |
| `ADODB.Recordset` | Query result set |
| `ADODB.Command` | SQL statement or stored procedure |
| `ADODBOLE.Connection` | OLE DB connection (compatibility alias) |

## Prerequisites

None. No external installation is required beyond a valid ODBC driver or provider for your target database.

## How It Works

Create a Connection object, configure its ConnectionString with the provider and data source, then call Open. Use the Connection to execute queries via the Execute method or bind it to Command and Recordset objects. Navigate Recordset rows using MoveNext, MoveFirst, MoveLast, MovePrevious, or the Seek method. Modify rows with AddNew, Update, and Delete. Wrap multiple operations in explicit BeginTrans/CommitTrans blocks for transaction safety.

## Code Example

```asp
<%
Option Explicit
Dim conn, rs

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver={SQLite3};Data Source=" & Server.MapPath("./db.sqlite")
conn.Open

Set rs = conn.Execute("SELECT * FROM users")
Do While Not rs.EOF
    Response.Write rs.Fields("name").Value & "<br>"
    rs.MoveNext
Loop
rs.Close
conn.Close

Set rs = Nothing
Set conn = Nothing
%>
```