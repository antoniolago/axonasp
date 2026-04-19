# ADODB Methods Reference

## Connection Methods

| Method | Returns | Description |
|---|---|---|
| Open | Empty | Establishes a connection to a database using the configured ConnectionString. |
| Close | Empty | Closes the database connection. |
| Execute | Recordset, Integer, or Empty | Executes a SQL statement. Returns a Recordset for queries (SELECT, SHOW, PRAGMA), an Integer row count for modifications (INSERT, UPDATE, DELETE), or Empty on failure. |
| BeginTrans | Integer | Begins a transaction. Returns 1 on success, 0 on failure. |
| CommitTrans | Empty | Commits the current transaction. |
| RollbackTrans | Empty | Rolls back the current transaction. |
| OpenSchema | Recordset | Returns a Recordset containing database schema information (tables, columns, indexes, views, procedures, or foreign keys). |
| Cancel | Empty | Cancels the current operation (no-op in current runtime). |

## Recordset Methods

| Method | Returns | Description |
|---|---|---|
| Open | Empty | Opens a result set from a SQL statement or Connection. Optionally sets CursorType, LockType, and other parameters. |
| Close | Empty | Closes the result set and releases database resources. |
| MoveNext | Empty | Moves to the next row. EOF becomes true if no next row exists. |
| MovePrevious | Empty | Moves to the previous row. BOF becomes true if no previous row exists. |
| MoveFirst | Empty | Moves to the first row. |
| MoveLast | Empty | Moves to the last row. |
| Move | Empty | Moves forward or backward by the specified row offset. |
| Cancel | Empty | Cancels the current operation (no-op in current runtime). |
| CancelBatch | Empty | Cancels pending batch updates (no-op in current runtime). |
| CancelUpdate | Empty | Cancels pending row updates not yet committed. |
| Find | Empty | Locates and moves to the first row matching the criteria (format: `field = value`). |
| NextRecordset | Recordset or Nothing | Returns the next result set if the command produced multiple result sets, or Nothing if no additional result set exists. |
| Clone | Recordset | Creates an independent copy of the current Recordset with the same structure. |
| CompareBookmarks | Integer | Compares two bookmarks. Returns -1 (first is less), 0 (equal), or 1 (first is greater). |
| AddNew | Empty | Adds a new empty row to the Recordset in memory. Follow with Update to persist. |
| Update | Empty | Persists the current row to the database (after AddNew or field modifications). |
| Delete | Empty | Deletes the current row. |
| GetRows | Array or Empty | Returns a 2D array of the entire result set (columns first, then rows). Empty if Recordset is closed or empty. |
| GetString | String | Returns the entire result set as a tab-separated string with newline row delimiters. |
| Requery | Empty | Re-executes the original query to refresh the Recordset. |
| Resync | Empty | Refreshes the current row data from the database (no-op in current runtime). |
| Save | Empty | Writes the Recordset to a file or ADODB.Stream object in XML format. |
| Seek | Empty | Positions the current row by searching the index. Requires the current Recordset to have an Index property set. |
| Supports | Boolean | Returns true if the Recordset supports the specified feature (e.g., bookmarks, seeking). |
| UpdateBatch | Empty | Applies all pending batch updates to the database (no-op in current runtime). |

## Command Methods

| Method | Returns | Description |
|---|---|---|
| Execute | Recordset, Integer, or Empty | Executes the SQL statement in CommandText. Returns a Recordset for queries, an Integer row count for modifications, or Empty on failure. Use Connection.Execute for simplified direct execution. |
| CreateParameter | Parameter | Creates a Parameter object with the specified data type, direction (in/out), size, and value. |
| Cancel | Empty | Cancels the current operation (no-op in current runtime). |

## Collection Methods

| Object | Method | Returns | Description |
|---|---|---|---|
| Errors | Count | Integer | Returns the number of errors in the collection. |
| Errors | Item | Error or Empty | Returns the error at the specified index, or Empty if out of range. |
| Errors | Clear | Empty | Clears all errors from the collection. |
| Fields | Append | Empty | Adds a new Field definition to the collection (schema design). |
| Fields | Item | Field | Returns the Field at the specified index or by name. |
| Fields | Count | Integer | Returns the number of fields in the collection. |
| Field | AppendChunk | Empty | Appends binary or text data to a Blob field. |
| Field | GetChunk | String | Retrieves a chunk of binary or text data from a Blob field. |
| Parameters | Append | Empty | Adds a Parameter to the command's parameter collection. |
| Parameters | Count | Integer | Returns the number of parameters in the collection. |

## Code Example

```asp
<%
Option Explicit
Dim conn, rs, parms, affected

Set conn = Server.CreateObject("ADODB.Connection")
conn.ConnectionString = "Driver=sqlite;Data Source=" & Server.MapPath("./data/app.db")
conn.Open

affected = conn.Execute("UPDATE users SET active = 1 WHERE active = 0")
Response.Write "Rows updated: " & CStr(affected) & "<br>"

Set rs = conn.Execute("SELECT id, name FROM users")
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

