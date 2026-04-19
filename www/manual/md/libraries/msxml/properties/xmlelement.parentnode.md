# XMLElement.ParentNode Property

Returns the parent element of this node.

## Access

Read-only.

## Type

XMLElement or Null.

## Remarks

- Returns Null if this node is the document root or has not been attached to a tree.

## Code Example

```asp
<%
Dim oXML, oChild
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<root><section><item>Test</item></section></root>"
Set oChild = oXML.SelectSingleNode("//item")
If Not IsNull(oChild.ParentNode) Then
    Response.Write "Parent: " & oChild.ParentNode.NodeName
End If
Set oXML = Nothing
%>
```