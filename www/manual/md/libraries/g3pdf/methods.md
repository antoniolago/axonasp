# G3PDF Methods

## Overview
This page summarizes methods exposed by the G3PDF library in G3Pix AxonASP.

## Methods Reference

| Method | Returns | Description |
|---|---|---|
| New | Object | Initializes a new PDF context and returns the same object instance. |
| Init | Object | Alias of New. Initializes a new PDF context and returns the same object instance. |
| Reset | Object | Alias of New. Reinitializes the PDF context and returns the same object instance. |
| AddPage | Boolean | Adds a new page to the current document. |
| Close | Boolean | Finalizes the current document state. |
| Output | Boolean, String, or Null | Emits document output by destination mode: inline/download/file returns Boolean, string mode returns PDF binary string, and generation failures return Null. |
| SetFont | Boolean | Sets active font family, style, and size. |
| SetFontSize | Boolean | Sets active font size. |
| SetTextColor | Boolean | Sets text color using grayscale or RGB values. |
| SetDrawColor | Boolean | Sets stroke color using grayscale or RGB values. |
| SetFillColor | Boolean | Sets fill color using grayscale or RGB values. |
| SetLineWidth | Boolean | Sets line width for draw operations. |
| SetMargins | Boolean | Sets left, top, and optional right page margins. Returns False when required arguments are missing. |
| SetLeftMargin | Boolean | Sets left page margin. |
| SetTopMargin | Boolean | Sets top page margin. |
| SetRightMargin | Boolean | Sets right page margin. |
| SetX | Boolean | Sets the current horizontal cursor position. |
| SetY | Boolean | Sets the current vertical cursor position with optional X reset behavior. |
| SetXY | Boolean | Sets both horizontal and vertical cursor positions. |
| GetX | Double | Returns current horizontal cursor position. |
| GetY | Double | Returns current vertical cursor position. |
| Ln | Boolean | Moves cursor to the next line using optional offset. |
| Cell | Boolean | Writes one cell at the current cursor position. Returns False when required arguments are missing. |
| MultiCell | Boolean | Writes wrapped multi-line text cells. Returns False when required arguments are missing. |
| Write | Boolean | Writes flowing text. Returns False when required arguments are missing. |
| Text | Boolean | Writes text at absolute coordinates. Returns False when required arguments are missing. |
| Line | Boolean | Draws a line segment. Returns False when required arguments are missing. |
| Rect | Boolean | Draws a rectangle with optional style. Returns False when required arguments are missing. |
| Image | Boolean | Places an image at coordinates with optional sizing and link metadata. Returns False when required arguments are missing. |
| AddLink | Integer | Creates an internal link identifier and returns it. |
| SetLink | Boolean | Binds a link identifier to a document location. Returns False when required arguments are missing. |
| Link | Boolean | Creates a clickable rectangle bound to an internal or external link target. Returns False when required arguments are missing. |
| SetTitle | Boolean | Sets document title metadata. |
| SetAuthor | Boolean | Sets document author metadata. |
| SetSubject | Boolean | Sets document subject metadata. |
| SetKeywords | Boolean | Sets document keywords metadata. |
| SetCreator | Boolean | Sets document creator metadata. |
| AliasNbPages | Boolean | Sets the total-page alias token used in content placeholders. |
| SetDisplayMode | Boolean | Sets PDF viewer zoom and page layout mode. |
| SetCompression | Boolean | Enables or disables PDF stream compression. |
| WriteHTML | Boolean | Renders supported HTML markup into the current document. Returns False when HTML input is missing. |
| HTML | Boolean | Alias of WriteHTML. |
| WriteHTMLFile | Boolean | Loads and renders HTML from a file path. Returns False when the argument is missing or file loading fails. |
| HTMLFile | Boolean | Alias of WriteHTMLFile. |
| LoadHTMLFile | Boolean | Alias of WriteHTMLFile. |
| GetPageWidth | Double | Returns current page width in the active unit. |
| GetPageHeight | Double | Returns current page height in the active unit. |
| GetStringWidth | Double | Measures rendered width for a text string in the active font settings. |

## Remarks
- Method names are case-insensitive.
- Alias methods resolve to the same behavior and return contract as their canonical methods.
