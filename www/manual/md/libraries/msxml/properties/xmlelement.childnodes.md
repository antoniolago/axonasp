# XMLElement.ChildNodes Property

Returns a list of all direct child nodes of this element.

## Access

Read-only.

## Type

XMLNodeList.

## Remarks

- The list contains only direct children, not descendants at deeper levels.
- Returns an empty XMLNodeList if the element has no children.
- Use `Children` for an identical result.

## Code Example

```asp
<%
Dim oXML, oRoot, oList, i
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><a/><b/><c/></root>"
Set oRoot = oXML.DocumentElement
Set oList = oRoot.ChildNodes
For i = 0 To oList.Length - 1
    Response.Write oList.Item(i).NodeName & "<br>"
Next
Set oXML = Nothing
%>
```