# 🐞 CSS Challenge:  Multi-level Nested List with Styling


This challenge focuses on styling a multi-level nested list using CSS. We'll achieve a visually appealing and organized hierarchy using indentation, different markers, and color variations.  We'll use standard CSS3 for this example.

## Description of the Styling

The goal is to create a nested list that clearly distinguishes between different levels.  The top-level list items will use a square marker, the second level will use a circle, and the third level will use a disc.  Each level will have different indentation and text color to further enhance readability.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Styling</title>
<style>
ul {
  list-style-type: square; /* Top-level list style */
  padding-left: 20px; /* Indentation for top level */
}

ul ul {
  list-style-type: circle; /* Second-level list style */
  padding-left: 40px; /* Indentation for second level */
}

ul ul ul {
  list-style-type: disc; /* Third-level list style */
  padding-left: 60px; /* Indentation for third level */
}

ul li {
  margin-bottom: 5px; /* Spacing between list items */
}

ul > li {
  color: #333; /* Top-level list item text color */
}

ul ul > li {
  color: #555; /* Second-level list item text color */
}

ul ul ul > li {
  color: #777; /* Third-level list item text color */
}
</style>
</head>
<body>

<h1>My Nested List</h1>

<ul>
  <li>Item 1
    <ul>
      <li>Sub-item 1.1</li>
      <li>Sub-item 1.2
        <ul>
          <li>Sub-sub-item 1.2.1</li>
          <li>Sub-sub-item 1.2.2</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>Item 2
    <ul>
      <li>Sub-item 2.1</li>
      <li>Sub-item 2.2</li>
    </ul>
  </li>
  <li>Item 3</li>
</ul>

</body>
</html>
```

## Explanation

The CSS code utilizes nested selectors (`ul ul`, `ul ul ul`) to target each level of the nested list specifically.  `list-style-type` property changes the bullet style for each level.  `padding-left` creates the indentation.  We've also added different text colors to each level for better visual distinction and `margin-bottom` for better spacing between list items.


## Resources to Learn More

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)  This provides comprehensive information on CSS list styles and their properties.
* **CSS-Tricks - List Styles:** Search "CSS list styles" on CSS-Tricks for various articles and tutorials on advanced list styling techniques.  (Note:  A direct link is omitted as the best resource on CSS-Tricks is often dynamic.)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

