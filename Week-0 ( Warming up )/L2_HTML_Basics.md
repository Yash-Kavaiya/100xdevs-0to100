# HTML 🌐

HTML (HyperText Markup Language) defines the structure of your websites. It is the backbone of web development, providing the basic structure and content of web pages.

## Tags 🏷️

HTML tags are the building blocks used to structure content on web pages. They are elements enclosed in angle brackets (`< >`) that define the structure and layout of the content within a webpage. Tags are composed of an opening tag, content, and a closing tag.

### Popular HTML Tags 🔖

Here are some of the most popular HTML tags:

| Tag | Description |
|-----|-------------|
| `<html>` | Defines the root of an HTML document. |
| `<head>` | Contains meta-information about the HTML document, such as title, metadata, links to stylesheets, etc. |
| `<title>` | Sets the title of the HTML document, which appears in the browser's title bar or tab. |
| `<body>` | Contains the main content of the HTML document visible to users. |
| `<h1>` to `<h6>` | Headings used to define different levels of headings, with `<h1>` being the highest level and `<h6>` the lowest. |
| `<p>` | Defines a paragraph of text. |
| `<a>` | Creates hyperlinks to other web pages or resources. |
| `<img>` | Embeds an image in the webpage. |
| `<ul>` | Defines an unordered list. |
| `<ol>` | Defines an ordered list. |
| `<li>` | Defines list items within `<ul>` or `<ol>` lists. |
| `<div>` | Defines a division or a section in an HTML document, used for layout and grouping content. |
| `<span>` | Inline element used for styling or grouping text. |
| `<table>` | Defines a table. |
| `<tr>` | Defines a table row. |
| `<td>` | Defines a table cell. |

### `<div>` vs. `<span>` 📐

`<div>` and `<span>` are both HTML elements used for structuring and styling content, but they have different characteristics and purposes:

| Element | Description |
|---------|-------------|
| `<div>` | **Block-level Element**: `<div>` is a block-level element, meaning it typically starts on a new line and takes up the full width available by default. **Grouping Content**: It is commonly used to group and divide sections of content on a web page. It's often used for layout purposes and helps in structuring the layout of a webpage. **Allows Block Elements**: `<div>` can contain other block-level and inline elements, including other `<div>` elements, headings, paragraphs, lists, etc. |
| `<span>` | **Inline Element**: `<span>` is an inline-level element, meaning it does not start on a new line and takes up only the necessary width. **Styling and Inline Markup**: It is often used to apply styles or markup to a specific part of text within a larger block of content without affecting the layout. **Allows Inline Elements**: `<span>` can contain other inline elements, such as text, images, links, etc. |

### `<table>` 📊

- `<table>`: Defines an HTML table used to display data in rows and columns.
- It is a structural element used to organize and present tabular data.
- Consists of `<tr>` (table row), `<td>` (table cell), and `<th>` (table header cell) elements to define the structure of rows and columns.
- Tables should be used for presenting data in a structured format, not for layout purposes. Their usage for layout is discouraged in modern web development due to accessibility and responsive design concerns.

In summary, `<div>` and `<span>` serve different purposes in structuring and styling content, while `<table>` is specifically meant for organizing and displaying tabular data on a webpage.

## Attributes 🔍

Attributes are additional properties that can be added to HTML elements to provide extra information about the element. They are added within the start tag of an HTML element and consist of a name and a value, separated by an equals sign (`=`), and are enclosed in double quotes (`"`) or single quotes (`'`). Attributes provide metadata or configuration settings for the element and help define its behavior, appearance, or functionality.

### Purposes of Attributes 🛠️

1. **Setting Values**: Attributes can assign values to elements. For instance, the `src` attribute in the `<img>` tag specifies the URL of the image to be displayed.

   Example:
   ```html
   <img src="image.jpg" alt="Description of the image">
   ```

2. **Providing Information**: Attributes like `id`, `class`, or `title` are used to provide information about an element. The `id` attribute uniquely identifies an element within a document, while the `class` attribute allows elements to be grouped together for styling or scripting purposes.

   Example:
   ```html
   <p id="uniqueID" class="styled-paragraph" title="This is a paragraph">Some text here</p>
   ```

3. **Defining Behavior**: Attributes like `href` in the `<a>` tag or `action` in the `<form>` tag define where a link should go or where form data should be sent when submitted.

   Example:
   ```html
   <a href="https://www.example.com">Link Text</a>
   <form action="/submit-form" method="post">
       <!-- Form elements -->
   </form>
   ```

4. **Custom Attributes**: It's also possible to create custom attributes for scripting purposes. While these are not recognized by HTML standards, they can be used with JavaScript or other scripting languages.

   Example:
   ```html
   <button data-custom="someValue">Click me</button>
   ```

HTML attributes vary depending on the HTML element and define various aspects like dimensions, colors, behaviors, links, etc. They play a crucial role in providing additional information and functionality to HTML elements, contributing to the overall structure and behavior of a web page.
