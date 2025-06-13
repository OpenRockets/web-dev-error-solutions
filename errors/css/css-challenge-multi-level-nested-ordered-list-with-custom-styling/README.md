# 🐞 CSS Challenge:  Multi-level Nested Ordered List with Custom Styling


This challenge involves styling a multi-level nested ordered list to achieve a visually appealing and hierarchical representation of information using CSS.  We'll use CSS3 for styling, focusing on list-style properties and selectors to customize the appearance.


**Description of the Styling:**

The goal is to create a nested ordered list where each level is visually distinct.  We'll achieve this by:

*   Changing the default list markers (numbers) to custom characters.
*   Indenting each nested level.
*   Using different colors and fonts for different levels to enhance readability and hierarchy.
*   Adding background colors to highlight sections.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Ordered List</title>
<style>
ol {
  list-style-type: none; /* Remove default numbering */
  counter-reset: item; /* Initialize a counter */
  padding: 0;
  margin: 0;
}

ol li {
  counter-increment: item; /* Increment the counter for each item */
  margin-bottom: 10px;
}

ol li::before {
  content: counter(item) ". "; /* Custom marker */
  font-weight: bold;
  color: #333;
  margin-right: 10px;
}

ol ol {
  margin-left: 20px; /* Indentation for nested lists */
}

ol ol li::before {
  content: counter(item, lower-alpha) ". "; /* Nested list marker: lowercase letters */
  color: #555;
}

ol ol ol {
  margin-left: 40px; /* Indentation for nested nested lists */
}

ol ol ol li::before {
  content: counter(item, lower-roman) ". "; /* Nested nested list marker: lowercase roman */
  color: #777;
}

ol li {
  padding-left: 10px;
  background-color: #f8f8f8;
  border-left: 5px solid #ddd;
}
ol ol li {
  background-color: #f0f0f0;
  border-left: 5px solid #ccc;
}
ol ol ol li {
  background-color: #e8e8e8;
  border-left: 5px solid #bbb;
}

</style>
</head>
<body>

<h1>Nested Ordered List Example</h1>

<ol>
  <li>Item 1
    <ol>
      <li>Sub-item 1.1</li>
      <li>Sub-item 1.2
        <ol>
          <li>Sub-sub-item 1.2.1</li>
          <li>Sub-sub-item 1.2.2</li>
        </ol>
      </li>
      <li>Sub-item 1.3</li>
    </ol>
  </li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>

</body>
</html>
```


**Explanation:**

The CSS uses the `counter-reset` and `counter-increment` properties to create custom numbering.  The `::before` pseudo-element adds the custom markers before each list item.  Different selectors (`ol`, `ol ol`, `ol ol ol`) target different nesting levels allowing for unique styling for each level (indentation, color, marker).  Background colors and border styles further improve visual distinction.


**Links to Resources to Learn More:**

*   **MDN Web Docs - CSS Counters:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters)
*   **CSS-Tricks - List Styles:** [https://css-tricks.com/almanac/properties/l/list-style/](https://css-tricks.com/almanac/properties/l/list-style/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

