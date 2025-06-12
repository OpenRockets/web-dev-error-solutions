# 🐞 CSS Challenge:  Multi-Level Nested Ordered List with Styling


This challenge focuses on styling a multi-level nested ordered list using CSS.  We'll achieve a visually appealing and easily readable hierarchy using indentation and varying list marker styles.  We'll also explore how to target specific list levels using CSS selectors. This example uses plain CSS, but the concepts are easily transferable to frameworks like Tailwind CSS.


## Description of the Styling

The goal is to create a nested ordered list where:

* The top-level list items use a larger, bolder font size and a different marker style (e.g., a Roman numeral).
* Subsequent levels use progressively smaller font sizes and different marker styles (e.g., uppercase letters, then numbers).
* Each level is indented to clearly show the hierarchy.
* The list has appropriate spacing and padding for readability.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested Ordered List</title>
<style>
ol {
  list-style-type: upper-roman; /* Top level: Uppercase Roman numerals */
  font-size: 1.2em;
  font-weight: bold;
  margin-left: 0; /* Reset default margin */
  padding-left: 2em; /* Add padding for indentation */
}

ol ol {
  list-style-type: upper-alpha; /* Second level: Uppercase letters */
  font-size: 1em;
  margin-left: 2em; /* Increase indentation */
  padding-left: 1.5em;
}

ol ol ol {
  list-style-type: decimal; /* Third level: Numbers */
  font-size: 0.9em;
  margin-left: 2em;
  padding-left: 1em;
}
</style>
</head>
<body>

<h1>Nested List Example</h1>

<ol>
  <li>First Level Item 1</li>
  <li>First Level Item 2
    <ol>
      <li>Second Level Item 1</li>
      <li>Second Level Item 2
        <ol>
          <li>Third Level Item 1</li>
          <li>Third Level Item 2</li>
        </ol>
      </li>
    </ol>
  </li>
  <li>First Level Item 3</li>
</ol>

</body>
</html>
```


## Explanation

The CSS uses nested selectors to target each level of the ordered list.  `ol` styles the top-level list. `ol ol` targets lists nested within other lists (the second level), and so on.  We use the `list-style-type` property to change the marker style for each level. `font-size` and `margin-left` control the visual hierarchy.  Adjusting padding and margins fine-tunes the spacing.

## Resources to Learn More

* **MDN Web Docs - CSS Lists:** [https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type](https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type)  (Comprehensive guide to styling lists in CSS)
* **CSS-Tricks - List Styles:** [https://css-tricks.com/almanac/properties/l/list-style/](https://css-tricks.com/almanac/properties/l/list-style/) (Practical examples and explanations)
* **W3Schools - CSS Lists:** [https://www.w3schools.com/css/css_list.asp](https://www.w3schools.com/css/css_list.asp) (Beginner-friendly tutorial)



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

