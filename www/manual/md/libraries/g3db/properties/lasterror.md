# LastError Property

## Overview
Returns the latest error message recorded by the G3DB object.

## Prerequisites
```asp
Set db = Server.CreateObject("G3DB")
```

## Syntax
```asp
errText = db.LastError
```

## Return Value
Returns a **String**:
- Error text when an operation fails.
- Empty string when no error is currently stored.

## Remarks
- This property is read-only.
- Same value is returned by `GetError()`.

## Example
```asp
<%
Dim db
Set db = Server.CreateObject("G3DB")

If Not db.Open("mysql", "bad") Then
    Response.Write db.LastError
End If

Set db = Nothing
%>
```

## API Reference
- **Type:** String
- **Access:** Read-only
