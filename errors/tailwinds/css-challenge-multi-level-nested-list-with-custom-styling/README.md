# 🐞 CSS Challenge:  Multi-level Nested List with Custom Styling


This challenge focuses on styling a multi-level nested list using CSS, aiming for a visually appealing and easily navigable hierarchy. We'll use standard CSS (no Tailwind CSS for this example to showcase fundamental CSS principles).  The goal is to create a nested list that clearly distinguishes between different levels of nesting, using indentation, different markers, and color variations.


**Description of the Styling:**

The styling will achieve the following:

* **Level 1:**  Bold, larger font size, dark blue color, square bullet points.
* **Level 2:** Italicized, slightly smaller font size,  medium blue color, circular bullet points.
* **Level 3:** Normal font style, smallest font size, light blue color, disc bullet points.
* **Indentation:** Each level will be indented to clearly show the hierarchy.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Styling</title>
<style>
ul {
  list-style-type: square; /* Default for level 1 */
  font-size: 18px;
  color: darkblue;
  padding-left: 20px; /* Initial indentation */
}

ul ul {
  list-style-type: circle; /* Level 2 */
  font-size: 16px;
  font-style: italic;
  color: mediumblue;
  padding-left: 30px; /* Increased indentation */
}

ul ul ul {
  list-style-type: disc; /* Level 3 */
  font-size: 14px;
  color: lightblue;
  padding-left: 40px; /* Increased indentation */
}

ul li {
    margin-bottom: 5px; /* Add some spacing between list items */
}

ul li strong {
    font-weight: bold; /* Make the level 1 text bolder */
}

</style>
</head>
<body>

<h1>My Nested List</h1>

<ul>
  <li><strong>Item 1:</strong>  This is the first item at level 1</li>
  <li><strong>Item 2:</strong> This is another item at level 1
    <ul>
      <li>Item 2.1: This is a sub-item of Item 2.</li>
      <li>Item 2.2: Another sub-item of Item 2.
        <ul>
          <li>Item 2.2.1: A sub-sub-item.</li>
          <li>Item 2.2.2: Another sub-sub-item.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li><strong>Item 3:</strong> This is a third item at level 1.</li>
</ul>

</body>
</html>
```


**Explanation:**

The CSS uses nested selectors (`ul ul`, `ul ul ul`) to target different levels of the nested list.  Each nested `ul`  gets a different list-style-type, font size, color, and increased indentation using `padding-left`.  The `li` selector adds margin to improve spacing.  We also use `strong` to reinforce the bold style for the top level items.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)
* **W3Schools - CSS Lists:** [https://www.w3schools.com/css/css_lists.asp](https://www.w3schools.com/css/css_lists.asp)
* **CSS Tricks - List Styles:** (Search for relevant articles on CSS Tricks website)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

