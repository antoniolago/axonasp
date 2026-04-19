# MSXML2 Library

The MSXML2 library provides HTTP client and XML Document Object Model (DOM) support for Classic ASP pages. It exposes five cooperating objects â€” **ServerXMLHTTP**, **DOMDocument**, **XMLNodeList**, **XMLElement**, and **ParseError** â€” that together allow pages to issue HTTP requests, parse XML, traverse document trees, and evaluate XPath expressions.

## Supported ProgIDs

| ProgID | Object |
|---|---|
| `MSXML2.ServerXMLHTTP` | HTTP client |
| `MSXML2.DOMDocument` | XML document |
| `MSXML2.DOMDocument.3.0` | XML document (versioned alias) |
| `MSXML2.DOMDocument.6.0` | XML document (versioned alias) |
| `Microsoft.XMLDOM` | XML document (legacy alias) |

## Prerequisites

No additional installation is required. The library is built into AxonASP.

## Object Model

**ServerXMLHTTP** â€” Sends HTTP requests and exposes the response as text, XML, or raw bytes. Create with `Server.CreateObject("MSXML2.ServerXMLHTTP")`.

**DOMDocument** â€” Parses an XML string or URL into a traversable document tree. Supports XPath queries via `SelectSingleNode` and `SelectNodes`. Create with one of the DOMDocument ProgIDs.

**XMLNodeList** â€” An indexed, iterable list of `XMLElement` nodes returned by `GetElementsByTagName`, `SelectNodes`, `ChildNodes`, or `Children`.

**XMLElement** â€” A single node in the document tree. Exposes the node name, value, attributes, and child collection, and supports XPath traversal.

**ParseError** â€” Returned by `DOMDocument.ParseError`. Always present; check `ErrorCode = 0` to confirm successful parsing.

## Remarks

- All method and property names are case-insensitive.
- `DOMDocument.Async` is accepted for compatibility but synchronous behaviour is always used.
- XPath support covers child/descendant axes, attribute predicates, position predicates, `contains()`, `starts-with()`, `not()`, `and`, `or`, namespace prefixes via `SelectionNamespaces`, and the `//` shorthand.

## Code Examples

**Send an HTTP GET request and read the response:**

```asp
<%
Dim oHTTP
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/api/data", False
oHTTP.Send
If oHTTP.Status = 200 Then
    Response.Write oHTTP.ResponseText
End If
Set oHTTP = Nothing
%>
```

**Load and query an XML document:**

```asp
<%
Dim oXML, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
If oXML.LoadXML("<root><item id='1'>Alpha</item><item id='2'>Beta</item></root>") Then
    Set oNode = oXML.SelectSingleNode("//item[@id='2']")
    If Not IsNull(oNode) Then
        Response.Write oNode.Text
    End If
End If
Set oXML = Nothing
%>
```