# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordions


This challenge focuses on creating a multi-level nested list that uses accordions to reveal and hide sub-items. We'll achieve this using CSS and leverage the power of the `details` and `summary` elements for a semantic and accessible solution.  No JavaScript will be required.


**Description of the Styling:**

The styling aims for a clean and modern look.  We'll use a simple, flat design with subtle color accents to highlight the different levels of the list. Accordion headers will be clearly distinguishable, and the content within each accordion will be neatly indented for readability.  We'll use a combination of CSS selectors to target specific elements and levels within the nested list structure.


**Full Code (CSS):**

```css
/* Basic Styling */
body {
  font-family: sans-serif;
  line-height: 1.6;
}

details {
  margin-bottom: 1rem;
  border: 1px solid #ddd;
  border-radius: 4px;
  overflow: hidden; /* Prevents summary content from overflowing */
}

summary {
  background-color: #f2f2f2;
  padding: 10px;
  cursor: pointer;
  font-weight: bold;
}

summary::-webkit-details-marker {
  display: none; /* Remove default marker */
}

details[open] summary {
  background-color: #e0e0e0; /* Highlight open accordions */
}


/* Nested List Styling */
ul {
  list-style: none;
  padding-left: 20px;
}

li {
  margin-bottom: 0.5rem;
}

ul ul {
  padding-left: 40px;
}

/* Additional styling for better visual hierarchy (optional) */
ul ul li summary {
  font-weight: normal; /* Sub-level summaries less prominent */
  font-style: italic;
}
```

**Full Code (HTML):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Accordion</title>
<link rel="stylesheet" href="style.css">
</head>
<body>

<details>
  <summary>Level 1 Item 1</summary>
  <ul>
    <li>Level 2 Item 1.1</li>
    <li>Level 2 Item 1.2
      <ul>
        <li>Level 3 Item 1.2.1</li>
        <li>Level 3 Item 1.2.2</li>
      </ul>
    </li>
  </ul>
</details>

<details>
  <summary>Level 1 Item 2</summary>
  <ul>
    <li>Level 2 Item 2.1</li>
    <li>Level 2 Item 2.2</li>
  </ul>
</details>

</body>
</html>
```


**Explanation:**

*   The `details` and `summary` elements provide the core functionality for the accordions.
*   CSS is used to style the accordions, including background colors, padding, and markers.
*   Nested `<ul>` and `<li>` elements create the multi-level list structure.
*   CSS selectors target different levels of the list to provide visual hierarchy.
*   The `:webkit-details-marker` pseudo-element removes the default browser marker from the summary.  You may need to add similar rules for other browsers if necessary (e.g., `::-moz-details-marker`).


**Links to Resources to Learn More:**

*   **MDN Web Docs - `details` and `summary` elements:** [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
*   **CSS-Tricks - Introduction to CSS Selectors:** [https://css-tricks.com/almanac/selectors/](https://css-tricks.com/almanac/selectors/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

