# 🐞 CSS Challenge:  Multi-level Nested Ordered List with Styling


This challenge focuses on styling a multi-level nested ordered list using CSS. We'll create a visually appealing and easily readable list with different styles for each level of nesting.  We'll achieve this using standard CSS properties, demonstrating control over list indentation, marker styles, and font variations.  No frameworks like Tailwind are used to keep the focus on core CSS concepts.


**Description of the Styling:**

The goal is to create a nested ordered list where:

* The top-level list items have a larger font size and bold text.
* Each nested level indents further to the right.
* Each level uses a different list marker style (e.g., decimal, lower-alpha, etc.).
* List items have sufficient spacing between them for readability.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Ordered List</title>
<style>
ol {
  list-style-type: decimal; /* Top level uses decimal */
  margin-left: 20px; /* Indentation for top level */
  font-size: 1.2em; /* Larger font size for top level */
  font-weight: bold; /* Bold for top level */
}

ol ol {
  list-style-type: lower-alpha; /* Second level uses lower-alpha */
  margin-left: 40px; /* Increased indentation for nested levels */
  font-size: 1em; /* Smaller font size for nested levels */
  font-weight: normal;
}

ol ol ol {
  list-style-type: upper-roman; /* Third level uses upper-roman */
  margin-left: 60px; /* Further indentation */
  font-size: 0.9em;
}

li {
  margin-bottom: 0.5em; /* Spacing between list items */
}
</style>
</head>
<body>

<h1>My Nested List</h1>

<ol>
  <li>Item 1
    <ol>
      <li>Subitem 1.1
          <ol>
              <li>Sub-subitem 1.1.1</li>
              <li>Sub-subitem 1.1.2</li>
          </ol>
      </li>
      <li>Subitem 1.2</li>
    </ol>
  </li>
  <li>Item 2
    <ol>
      <li>Subitem 2.1</li>
      <li>Subitem 2.2</li>
    </ol>
  </li>
  <li>Item 3</li>
</ol>

</body>
</html>
```

**Explanation:**

The CSS code uses nested selectors (`ol ol`, `ol ol ol`) to target different levels of the nested list.  Each level's styling is adjusted individually.  `list-style-type` controls the marker style, `margin-left` handles indentation, and `font-size` and `font-weight` manage text appearance.  The `li` selector adds spacing between list items for improved readability.  You can adjust the values for `margin-left` and font sizes to fine-tune the layout to your preference.


**Resources to Learn More:**

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)  (Comprehensive guide to CSS list styling)
* **CSS-Tricks - Lists:** [https://css-tricks.com/almanac/selectors/list/](https://css-tricks.com/almanac/selectors/list/) (Helpful CSS list techniques and examples)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

