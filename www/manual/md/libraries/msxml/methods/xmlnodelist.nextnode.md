# XMLNodeList.NextNode Method

Returns the next node in a forward-only iteration over the list.

## Syntax

```asp
Set oNode = oList.NextNode()
```

## Parameters

None.

## Return Value

XMLElement. The next node in iteration order. Returns Null when all nodes have been visited.

## Remarks

- The iterator position is maintained internally within the XMLNodeList object.
- Method names are case-insensitive.

## Code Example

```asp
<%
Dim oXML, oList, oNode
Set oXML = Server.CreateObject("MSXML2.DOMDocument")
oXML.LoadXML "<items><item>A</item><item>B</item><item>C</item></items>"
Set oList = oXML.GetElementsByTagName("item")
Set oNode = oList.NextNode()
Do While Not IsNull(oNode)
    Response.Write oNode.Text & "<br>"
    Set oNode = oList.NextNode()
Loop
Set oXML = Nothing
%>
```