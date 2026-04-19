# ADOX.Catalog Properties

## Overview
This page summarizes properties exposed by ADOX.Catalog in G3Pix AxonASP.

## Properties Reference

| Property | Access | Type | Description |
|---|---|---|---|
| ActiveConnection | Read/Write | Object or String or Empty | Stores the current catalog connection source. Assign an ADODB connection object or a connection string. |
| Tables | Read-only | Object | Returns an ADOX table collection object representing discovered tables and views for ActiveConnection. |

## Remarks
- Property names are case-insensitive.
- Assigning ActiveConnection resets cached Tables metadata.
