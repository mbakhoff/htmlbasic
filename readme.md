# HTML Basics

HTML (*Hypertext Markup Language*) describes the structure of a web page semantically - it defines *what* the web page contains, but not how it looks.
Closely related to HTML is CSS (*Cascading Style Sheets*) which define how the page is rendered (layout, appearance).

HTML pages are regular text files that follow the HTML syntax. 
Each html page contains the *html*, *head* and the *body* element. 
The *head* element can contain useful metadata such as page title and links to scripts or css files.
The *body* element defines the contents of the page. 

Elements are components of a HTML page consisting of a start tag and an end tag. 
For example, to create a paragraph, we would use a start tag `<p>`, followed by the content of the paragraph, followed by an end tag `</p>`.
The text between the angular brackets of the tag is the tag name (`p` for paragraph, `img` for image, `tr` for table row, etc.)
When an element has no content, then the start tag and end tag can be combined: `<img />`
Most elements can contain other elements. 
For example, a paragraph element can contain an image element. 

Each element can have attributes. 
Attributes are key-value pairs that can contains extra information for the element. 
For example, an `<img>` tag must contain a *src* attribute, which contains a link to the image that should be displayed.
The attributes are placed in the start tag of the element: `<img src="some-image.png" />`. 

Lets looks at an example: 
```html
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Hello page title</title>
</head>
<body>

<h1>Hello heading</h1>

<p>
  hello paragraph
  <span>hello span</span>
  <img src="html5.png" height="32px" width="32px" alt="html5 logo" />
  goodbye paragraph
</p>

<div>
  start div
  <div>
    start subdiv
    <span>nested span</span>
    end subdiv
  </div>
  end div
</div>

<!-- this is a comment -->

</body>
</html>
```

This is how it looks like in a browser:

<div>
  <h5>Hello heading</h5>
  <p>
    hello paragraph
    <span>hello span</span>
    <img src="https://www.w3.org/html/logo/downloads/HTML5_Logo_512.png" height="32px" width="32px" alt="html5 logo" />
    goodbye paragraph
  </p>
  <div>
    start div
    <div>
      start subdiv
      <span>nested span</span>
      end subdiv
    </div>
    end div
  </div>
</div>

## Inspect it

Press `F12` to toggle your browser's developer tools. 
Try to select different elements on the page. 

* Firefox https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Select_an_element
* Chrome https://developers.google.com/web/tools/chrome-devtools/inspect-styles/

# HTML layouts 101

The web browser is responsible for rendering html pages.
It must find a place on the screen for (most) HTML elements.
The placement of the an element depends on its type (tag name).
Additionally, the default placement and rendering can be overridden using css rules.
 
Most elements are displayed using either **block**, **inline** or **none** mode.
**Inline** elements are rendered left-to-right (placed next to each other). 
Examples of inline elements are `<span>`, `<img>` and `<input>`.
**Block** elements are rendered top-to-bottom (placed below each other).
Examples of block elements are `<p>`, `<div>` and `<h1>`.
Elements with the **none** mode are not rendered on the screen.
Special rules apply for tables, lists and some other elements.  

Another important concept is the box model. 
In a document, each element is represented as a rectangular box.
Each box has a margin, border and padding, which can be overriden using css rules. 

Please read now: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model

Use the `F12` developer tools to inspect the margins and paddings of different elements.

# CSS rules 101

CSS rules can be used to change the display mode, paddings, margins, fonts and sizes of elements in the HTML page.
To apply a rule, a target must first be "selected": 

* Select by element *id* attribute. For example `<div id="sampleId">` can be selected with`#sampleId`.
* Select by element *class* attribute. For example `<div class="sampleClass1 sampleClass2">` can be selected with`.sampleClass1`.

What's the difference between id and class? 
An element can have up to one id, which must be unique in the page. 
An element can have several classes which can be shared between different elements.

When a rule is applied to an element, then it's also inherited by all other elements inside that element.
The child elements can have their own rules that override the rules of their parent.

CSS rules must be placed in a separate file and linked from the HTML *head*.
The simplified format of the file is `selector { rule; }`.

Some examples: 
```css
.sampleClass1 {
  font-weight: bold;
}

.sampleClass2 {
  font-weight: bolder;
}
```

```css
#sampleId {
  color: red;
  text-align: center;
  padding-top: 10px;
}

.sampleClass1,
.sampleClass2 {
  font-weight: bold;
}
```

The CSS file must be linked to the page using the link tag: `<link rel="stylesheet" href="styles-file-name.css">` 

The main complexity is knowing all the useful css properties that you can override and using them in the right place.

# Useful CSS properties

| Property | Description |
| --- | --- |
| [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display) | specifies the type of rendering box used for an element |
| [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) | sets the padding space on all sides of an element |
| [margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) | sets the margin for all four sides of an element |
| [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border) | shorthand property for setting all individual border property values |
| [height](https://developer.mozilla.org/en-US/docs/Web/CSS/height) | specifies the height of the content area of an element |
| [width](https://developer.mozilla.org/en-US/docs/Web/CSS/width) | specifies the width of the content area of an element |
| [float](https://developer.mozilla.org/en-US/docs/Web/CSS/float) | specifies that an element should be placed along the left or right side of its container, where text and inline elements will wrap around it |
| [color](https://developer.mozilla.org/en-US/docs/Web/CSS/color) | sets the foreground color of an element's text content, and its decorations |
| [font-size](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size) | specifies the size of the font |
| [font-weight](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight) | specifies the weight of the font (boldness) |
| [text-decoration](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) | used to draw a line under, over, or through some text |
| [text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) | describes how inline content like text is aligned in its parent block element |

See all the properties at: https://developer.mozilla.org/en-US/docs/Web/CSS/Reference 

# Useful HTML tags

| Tag | Description |
| --- | --- |
| [a](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) | creates a hyperlink to other web pages, files, locations |
| [span](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span) | generic inline container for phrasing content |
| [p](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p) | represents a paragraph of text |
| [div](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) | generic container for flow content |
| [h1-h6](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements) | section headings |
| [img](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) | represents an image in the document |
| [form](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) | represents a document section that contains interactive controls to submit information to a web server |
| [input](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) | used to create interactive controls for web-based forms |
| [label](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) | represents a caption for an item in a user interface |
| [select](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) | represents a control that provides a menu of options |
| [ol](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) | represents an ordered list of items, typically rendered as a numbered list |
| [ul](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) | represents an unordered list of items, typically rendered as a bulleted list |
| [li](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) | used to represent an item in a list |
| [table](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table) | represents tabular data — that is, information expressed via a two-dimensional data table |
| [tr](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tr) | defines a row of cells in a table |
| [td](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td) | defines a cell of a table that contains data |

See all the elements at: https://developer.mozilla.org/en-US/docs/Web/HTML

# Pro tips

* avoid hard coded heigth/width sizes in pixels (`width: 100px;`). use percentages instead: `width: 10%;`
* whitespace is collapsed. usually you should use paddings and margins. use `<br/>` for line breaks, but not for vertical spacing.
* css is simple, but not easy. don't give up.

# Run the example

Clone this repository and run `mvn jetty:run`. 
Open the page: [http://localhost:8080/](http://localhost:8080/).
You could also bypass the web server and directly open src/main/webapp/index.html in your browser.