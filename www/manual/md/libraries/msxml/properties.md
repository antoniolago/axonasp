# MSXML2 Properties

## ServerXMLHTTP Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `ResponseText` | Read | String | The response body decoded as a text string. |
| `ResponseXML` | Read | DOMDocument | The response body parsed as an XML document. Returns a String if the response is not valid XML. |
| `ResponseBody` | Read | Byte Array | The raw response body as a byte array. |
| `Status` | Read | Integer | The HTTP status code (e.g., 200, 404). Returns 0 on a connection error. |
| `StatusText` | Read | String | The full HTTP status line (e.g., `200 OK`). |
| `ReadyState` | Read | Integer | The request lifecycle state: 0 = Uninitialized, 1 = Open, 2 = Sent, 3 = Receiving, 4 = Complete. |
| `Timeout` | Read/Write | Integer | Request timeout in seconds. Default is 30. |

## DOMDocument Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `DocumentElement` | Read | XMLElement | The root element of the parsed document, or Null if the document is empty. |
| `XML` | Read | String | The stored XML source or serialized document tree. |
| `ParseError` | Read | ParseError | The ParseError object from the last load or parse. Check `ErrorCode = 0` for success. |
| `Async` | Read/Write | Boolean | Accepted for compatibility; the implementation always behaves synchronously. Default is False. |
| `ServerHTTPRequest` | Read/Write | Boolean | Controls whether HTTP requests use the server HTTP stack. |
| `ResolveExternals` | Read/Write | Boolean | Controls resolution of external entity references. |
| `ValidateOnParse` | Read/Write | Boolean | Controls DTD validation during parsing. |
| `PreserveWhiteSpace` | Read/Write | Boolean | Controls whether insignificant whitespace is preserved in the DOM tree. |
| `SelectionLanguage` | Read/Write | String | The query language used by `SelectSingleNode` and `SelectNodes`. Default is `XPath`. |
| `SelectionNamespaces` | Read/Write | String | Namespace prefix bindings for XPath queries. Format: `xmlns:prefix='uri'`. |

## XMLNodeList Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `Length` | Read | Integer | The number of nodes in the list. |
| `Count` | Read | Integer | Alias for `Length`. |

## ParseError Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `ErrorCode` | Read | Integer | 0 = no error. Negative values or HTTP status codes indicate parse or load failures. |
| `Reason` | Read | String | A human-readable description of the parse error. |
| `FilePos` | Read | Integer | The byte offset in the source where the error was detected. |
| `Line` | Read | Integer | The 1-based line number in the source where the error was detected. |
| `LinePos` | Read | Integer | The 1-based column position within the error line. |
| `SrcText` | Read | String | The source text that was being parsed when the error occurred. |
| `URL` | Read | String | The URL or file path that was being loaded when the error occurred. |

## XMLElement Properties

| Property | Access | Type | Description |
|---|---|---|---|
| `NodeName` | Read | String | The element tag name or `#text` for text nodes. |
| `NodeValue` | Read/Write | String | The text value of the node. Settable for text and attribute nodes. |
| `Text` | Read/Write | String | The concatenated text content of the element and all its descendants. |
| `XML` | Read | String | The serialized XML markup of this node and its subtree. |
| `Attributes` | Read | Collection | A collection of attribute name/value pairs. |
| `ChildNodes` | Read | XMLNodeList | A list of all direct child nodes. |
| `Children` | Read | XMLNodeList | Alias for `ChildNodes`. |
| `FirstChild` | Read | XMLElement | The first direct child node, or Null if there are no children. |
| `LastChild` | Read | XMLElement | The last direct child node, or Null if there are no children. |
| `ParentNode` | Read | XMLElement | The parent element, or Null if this is the root. |
| `Length` | Read | Integer | The number of direct child nodes. |