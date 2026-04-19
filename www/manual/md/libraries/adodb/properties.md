# ADODB Properties Reference

## Connection Properties

| Property | Access | Type | Description |
|---|---|---|---|
| ConnectionString | Read/Write | String | Full provider connection string (e.g., `Driver={SQLite3};Data Source=app.db`). |
| State | Read | Integer | Connection state: 0 (closed), 1 (open). |
| Mode | Read/Write | Integer | Access mode for the connection. |
| Provider | Read/Write | String | Provider name (e.g., sqloledb, msdasql). |
| Version | Read | String | Version string for compatibility reporting. |
| CommandTimeout | Read/Write | Integer | Default timeout in seconds for command execution. |
| ConnectionTimeout | Read/Write | Integer | Timeout in seconds for establishing the connection. |
| CursorLocation | Read/Write | Integer | Cursor location: 1 (server-side), 3 (client-side). |
| DefaultDatabase | Read/Write | String | Default database or catalog name. |
| IsolationLevel | Read/Write | Integer | Transaction isolation level. |
| Errors | Read | Object | Errors collection containing all errors from the last failed operation. |

## Recordset Properties

| Property | Access | Type | Description |
|---|---|---|---|
| EOF | Read | Boolean | True when cursor is positioned after the last row. |
| BOF | Read | Boolean | True when cursor is positioned before the first row. |
| State | Read | Integer | Recordset state: 0 (closed), 1 (open). |
| RecordCount | Read | Integer | Number of rows currently materialized in memory. |
| Fields | Read | Object | Fields collection representing the current column schema. |
| AbsolutePage | Read/Write | Integer | Current page index (used with PageSize). |
| PageCount | Read | Integer | Total page count based on RecordCount and PageSize. |
| PageSize | Read/Write | Integer | Number of rows per page. |
| AbsolutePosition | Read/Write | Integer | One-based position of the current row. |
| Bookmark | Read/Write | Variant | Bookmark value for the current row (use with Seek). |
| ActiveCommand | Read/Write | Object | Associated Command object that produced this Recordset. |
| CacheSize | Read/Write | Integer | Number of rows to cache locally (minimum effective value is 1). |
| DataMember | Read/Write | String | Data member name for complex data sources. |
| EditMode | Read | Integer | Current edit mode: 0 (not editing), 1 (edit), 2 (add new). |
| Filter | Read/Write | String | Filter clause to restrict visible rows (format: `field = value`). |
| Index | Read/Write | String | Indexed field expression for Seek operations. |
| MarshalOptions | Read/Write | Integer | Options for marshaling data. |
| MaxRecords | Read/Write | Integer | Maximum number of rows to materialize from the source. |
| Sort | Read/Write | String | Sort order for rows (format: `field ASC` or `field DESC`). |
| Source | Read/Write | String or Object | SQL source text or Command object to execute. |
| Status | Read/Write | Integer | Status of the current record. |
| ActiveConnection | Write | Object | Connection object used by Open and persistence methods. |
| CursorType | Write | Integer | Cursor type: 0 (forward), 1 (keyset), 2 (dynamic), 3 (static). |
| LockType | Write | Integer | Lock type: 1 (read-only), 2 (pessimistic), 3 (optimistic), 4 (batch). |
| CursorLocation | Write | Integer | Overrides connection cursor location for this Recordset. |

## Command Properties

| Property | Access | Type | Description |
|---|---|---|---|
| ActiveConnection | Read/Write | Object | Connection object used for Execute. |
| CommandText | Read/Write | String | SQL statement or stored procedure name. |
| CommandType | Read/Write | Integer | Command type: 1 (text), 2 (table), 4 (stored procedure). |
| CommandTimeout | Read/Write | Integer | Timeout in seconds for command execution. |
| Prepared | Read/Write | Boolean | Whether the command should be prepared before execution. |
| Parameters | Read | Object | Parameters collection for the command. |

## Error Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Number | Read | Integer | HRESULT-compatible error number. |
| Description | Read | String | Human-readable error message. |
| Source | Read | String | Member name or function that raised the error. |
| SQLState | Read | String | SQL state code when available. |

## Errors Collection Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Count | Read | Integer | Number of errors in the collection. |
| Item | Read | Object | Access individual Error objects by index. |

## Field Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Value | Read/Write | Variant | Current field value. |
| Name | Read | String | Field name from the query schema. |
| Type | Read | Integer | Field data type code. |
| DefinedSize | Read | Integer | Declared maximum size of the field. |
| Attributes | Read | Integer | Field attribute flags (nullable, auto-increment, etc.). |
| NumericScale | Read/Write | Integer | Number of decimal places for numeric fields. |
| ActualSize | Read | Integer | Actual length in characters of the current value. |
| DataFormat | Read | Empty | Returns Empty in current runtime. |
| OriginalValue | Read | Variant | Original value before modification (mirrors current value in current runtime). |
| Precision | Read | Integer | Number of significant digits for numeric fields. |
| Status | Read | Integer | Field status (inherited from Recordset status). |
| UnderlyingValue | Read | Variant | Database value before local modifications (mirrors current value in current runtime). |

## Fields Collection Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Count | Read | Integer | Number of fields in the Recordset schema. |
| Item | Read | Object | Access individual Field objects by index or name. |

## Parameter Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Name | Read/Write | String | Parameter name (used in parameterized queries). |
| Value | Read/Write | Variant | Parameter value to pass to the SQL command. |
| Type | Read/Write | Integer | Parameter data type. |
| Direction | Read/Write | Integer | Parameter direction: 1 (input), 2 (output), 4 (input-output). |
| Size | Read/Write | Integer | Maximum parameter size in bytes. |

## Parameters Collection Properties

| Property | Access | Type | Description |
|---|---|---|---|
| Count | Read | Integer | Number of parameters in the collection. |
| Item | Read | Object | Access individual Parameter objects by index or name. |


