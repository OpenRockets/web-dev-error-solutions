# 🐞 CSS Challenge:  Multi-level Nested Accordion


This challenge involves creating a multi-level nested accordion using CSS.  The accordion will allow users to expand and collapse sections, with nested sections expanding and collapsing within their parent sections.  We'll use CSS3 for this implementation, focusing on the `details` and `summary` elements for a semantic and straightforward approach.  No JavaScript is required.


**Description of the Styling:**

The styling aims for a clean, modern look.  Each accordion section will have a distinct header with a plus/minus icon to indicate expansion/collapse. The nested sections will be visually indented to clearly show the hierarchical structure. We will use a simple color palette for readability.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Multi-Level Nested Accordion</title>
<style>
details {
  border: 1px solid #ccc;
  margin-bottom: 10px;
}

summary {
  cursor: pointer;
  padding: 10px;
  background-color: #f0f0f0;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

summary::before {
  content: '+';
  font-weight: bold;
}

summary[aria-expanded="true"]::before {
  content: '-';
}

details[open] summary {
    background-color: #e0e0e0;
}

details details {
  margin-left: 20px;
}
</style>
</head>
<body>

<h1>Main Section</h1>
<details>
  <summary>Section 1</summary>
  <p>Content of Section 1</p>
  <details>
    <summary>Subsection 1.1</summary>
    <p>Content of Subsection 1.1</p>
  </details>
  <details>
    <summary>Subsection 1.2</summary>
    <p>Content of Subsection 1.2</p>
    <details>
      <summary>Subsection 1.2.1</summary>
      <p>Content of Subsection 1.2.1</p>
    </details>
  </details>
</details>

<h1>Another Main Section</h1>
<details>
  <summary>Section 2</summary>
  <p>Content of Section 2</p>
</details>

</body>
</html>
```


**Explanation:**

* We leverage the native HTML5 `<details>` and `<summary>` elements.  These elements provide built-in functionality for accordions without needing JavaScript.
* The CSS styles the appearance of the accordion sections.  The `::before` pseudo-element is used to dynamically add the plus/minus icon based on the `aria-expanded` attribute.
* Nested `<details>` elements create the multi-level structure.  The `margin-left` property provides visual indentation for nested sections.  The styling of `details[open]` summary changes the background color when open.

**Links to Resources to Learn More:**

* **MDN Web Docs - `<details>` element:** [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
* **CSS Tricks - Accordions:**  (Search for "CSS Accordion" on CSS Tricks for many examples and techniques)
* **W3Schools - CSS Selectors:** [https://www.w3schools.com/css/css_selectors.asp](https://www.w3schools.com/css/css_selectors.asp) (Useful for understanding the selectors used in the CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

