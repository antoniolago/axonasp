# ServerXMLHTTP.ResponseXML Property

Returns the response body parsed as an XML document.

## Access

Read-only.

## Type

DOMDocument (if the response is valid XML) or String (if parsing fails).

## Remarks

- Available after `Send` completes (`ReadyState = 4`).
- If the response body is valid XML, a fully populated DOMDocument object is returned. You can call `SelectSingleNode`, `GetElementsByTagName`, and access `DocumentElement` on it.
- If the response body cannot be parsed as XML, the raw response text is returned as a String.
- Returns an empty String if no response has been received.

## Code Example

```asp
<%
Dim oHTTP, oXML, oNode
Set oHTTP = Server.CreateObject("MSXML2.ServerXMLHTTP")
oHTTP.Open "GET", "https://example.com/feed.xml", False
oHTTP.Send
If oHTTP.Status = 200 Then
    Set oXML = oHTTP.ResponseXML
    Set oNode = oXML.SelectSingleNode("//title")
    If Not IsNull(oNode) Then
        Response.Write oNode.Text
    End If
End If
Set oHTTP = Nothing
%>
```