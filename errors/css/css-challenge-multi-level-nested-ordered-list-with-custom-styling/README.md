# 🐞 CSS Challenge:  Multi-level Nested Ordered List with Custom Styling


This challenge focuses on styling a multi-level nested ordered list using CSS. We'll create a visually appealing and easy-to-read nested list with custom styling, demonstrating the use of list-style-type, padding, margins, and pseudo-elements to enhance readability and aesthetics.  We'll leverage standard CSS for broad applicability.


## Description of the Styling:

The goal is to create a nested ordered list where each level is visually distinct.  We will achieve this by:

* Using different list-style-types for each level (e.g., decimal, lower-alpha, lower-roman).
* Indenting subsequent levels using padding.
* Adding a subtle background color to alternate list items for improved readability.
* Using pseudo-elements (`:before`) to add custom markers for list items instead of relying on default browser styles.


## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Ordered List</title>
<style>
ol {
  list-style: none; /* Remove default list markers */
  padding-left: 0; /* Remove default padding */
}

ol ol {
  padding-left: 20px; /* Indent nested lists */
}

ol li {
  counter-increment: item; /* Increment counter for each item */
  margin-bottom: 5px;
}

ol li::before {
  content: counter(item) ". "; /* Add custom list marker */
  counter-reset: subitem; /* Reset subitem counter for each item */
  font-weight: bold;
}

ol ol li {
  counter-increment: subitem; /* Increment sub-item counter */
  counter-reset: subsubitem;
}

ol ol li::before {
  content: counter(item) "." counter(subitem) ". ";
  font-weight: bold;
}

ol ol ol li {
    counter-increment: subsubitem;
    content: counter(item) "." counter(subitem) "." counter(subsubitem) ". ";
    font-weight: bold;
}

ol li:nth-child(even) {
  background-color: #f2f2f2; /* Alternate background color */
}

</style>
</head>
<body>

<h1>Nested Ordered List Example</h1>

<ol>
  <li>Item 1
    <ol>
      <li>Sub-item 1.1
        <ol>
          <li>Sub-sub-item 1.1.1</li>
          <li>Sub-sub-item 1.1.2</li>
        </ol>
      </li>
      <li>Sub-item 1.2</li>
    </ol>
  </li>
  <li>Item 2
    <ol>
      <li>Sub-item 2.1</li>
      <li>Sub-item 2.2</li>
    </ol>
  </li>
  <li>Item 3</li>
</ol>

</body>
</html>
```


## Explanation:

The CSS code uses several techniques:

* **`list-style: none;`**: This removes the default bullet points or numbers from the lists.
* **`counter-increment` and `counter-reset`**: These CSS properties allow us to create custom counters for list items at each level, providing unique numbering.
* **`::before` pseudo-element**:  This inserts content before each list item, creating the custom markers using the counter values.
* **`padding-left`**: This indents nested lists to create a visual hierarchy.
* **`:nth-child(even)`**: This selector targets even-numbered list items to apply a background color.


## Links to Resources to Learn More:

* **MDN Web Docs - CSS Counters:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Lists_and_Counters)
* **MDN Web Docs - `::before` and `::after` pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks - Styling Ordered Lists:** [Search "Styling Ordered Lists" on css-tricks.com for various tutorials]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

