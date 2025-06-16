# 🐞 CSS Challenge:  Multi-level Nested Ordered List with Styling


This challenge focuses on styling a multi-level nested ordered list using CSS.  We'll achieve a visually appealing and easily readable hierarchy using indentation and distinct styling for each level.  We'll be utilizing standard CSS for this example, but the principles can be easily adapted to frameworks like Tailwind CSS.

## Description of the Styling

The goal is to create a nested ordered list where each level is visually distinct.  We will use padding and list-style-type to create a clear hierarchy.  The first level will have a larger font size and bolder text. Subsequent levels will be progressively indented and use a different list style type.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Ordered List</title>
<style>
ol {
  list-style-type: decimal; /* Set default list style */
  margin-left: 0; /* Reset default margin */
  padding-left: 20px; /* Add padding for indentation */
}

ol ol {
  list-style-type: lower-alpha; /* Different style for nested lists */
  margin-left: 20px; /* Indent nested lists further */
  font-size: 0.9em; /* Slightly smaller font size */
}

ol ol ol {
    list-style-type: square; /* Different style for deeply nested lists */
    margin-left: 20px; /* Indent even further */
    font-size: 0.8em; /* Even smaller font size */
    font-style: italic; /* Adds italic style for distinction */
}

ol li {
  margin-bottom: 5px; /* Add space between list items */
}

ol > li { /* Style only the top-level list items */
  font-weight: bold; /* Make top-level items bold */
  font-size: 1.1em; /* Make top-level items slightly larger */
}
</style>
</head>
<body>

<h1>Main Topics</h1>
<ol>
  <li>Introduction to Programming</li>
  <li>Data Structures and Algorithms
    <ol>
      <li>Arrays</li>
      <li>Linked Lists
        <ol>
          <li>Singly Linked Lists</li>
          <li>Doubly Linked Lists</li>
        </ol>
      </li>
      <li>Trees</li>
    </ol>
  </li>
  <li>Object-Oriented Programming</li>
</ol>

</body>
</html>
```

## Explanation

The CSS code uses nested selectors (`ol ol`, `ol ol ol`) to target different levels of the nested list. Each level gets a different `list-style-type`, increased indentation using `margin-left`, and potentially adjusted font size and style for better readability.  The `> li` selector targets only the direct children of the `<ol>` element, allowing specific styling of the top-level list items.  Adjust the `margin-left` and `font-size` values to fine-tune the appearance as needed.


## Resources to Learn More

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)  - Learn about different list-style types and how to use them.
* **MDN Web Docs - CSS Selectors:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) -  Understand how CSS selectors work to target specific elements.
* **W3Schools CSS Tutorial:** [https://www.w3schools.com/css/](https://www.w3schools.com/css/) - A comprehensive CSS tutorial covering various aspects of styling web pages.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

