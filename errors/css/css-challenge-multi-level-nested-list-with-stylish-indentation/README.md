# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Indentation


This challenge focuses on styling a multi-level nested list using CSS to create a visually appealing and easily navigable hierarchy. We'll achieve this using CSS3 properties, specifically focusing on list-style, padding, and margins to create a clear visual representation of the nested structure.


## Description of the Styling:

The goal is to style an unordered list with nested lists to represent a hierarchical structure, such as a file system or an outline.  The styling should clearly indicate the level of nesting through visual cues like indentation and different list markers. We'll aim for a clean, modern look.  Each nested level will be indented further to the right, with different list markers to visually distinguish them.


## Full Code (CSS):

```css
ul {
  list-style-type: none; /* Remove default bullet points */
  padding-left: 0; /* Remove default padding */
}

ul li {
  margin-bottom: 5px; /* Add some spacing between list items */
}

ul ul {
  padding-left: 20px; /* Indent nested lists */
}

ul li::before {
  content: "• "; /* Add a custom bullet point */
  display: inline-block;
  width: 1em; /* Adjust width as needed */
}

ul ul li::before {
  content: "– "; /* Different bullet for nested lists */
}

ul ul ul li::before {
  content: "◦ "; /* And another for the third level*/
}


/*Optional Styling for a more visually appealing look*/
body {
  font-family: sans-serif;
}

ul li {
  color: #333;
}

ul ul li {
  color: #555;
}

ul ul ul li {
  color: #777;
}

```

## Full Code (HTML):

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Example</title>
<link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>

<ul>
  <li>Item 1</li>
  <li>Item 2
    <ul>
      <li>Subitem 2.1</li>
      <li>Subitem 2.2
        <ul>
          <li>Subsubitem 2.2.1</li>
          <li>Subsubitem 2.2.2</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>Item 3</li>
</ul>

</body>
</html>
```


## Explanation:

* **`list-style-type: none;`**: This removes the default bullet points from the unordered lists.
* **`padding-left: 0;`**: This removes the default left padding from the lists.
* **`ul ul { padding-left: 20px; }`**: This indents nested lists by 20 pixels.  You can adjust this value to control the indentation level.
* **`li::before`**: This pseudo-element adds a custom bullet point before each list item.  We use different content for different nesting levels to visually distinguish them.  The `display: inline-block;` and `width: 1em;` ensure proper spacing.
* The optional styling adds color variations for different nesting levels to further improve readability.


## Links to Resources to Learn More:

* **CSS Lists:** [MDN Web Docs - CSS Lists](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
* **CSS Pseudo-elements:** [MDN Web Docs - CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **Understanding CSS Selectors:**  [Various Tutorials available online - search "CSS Selectors tutorial"]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

