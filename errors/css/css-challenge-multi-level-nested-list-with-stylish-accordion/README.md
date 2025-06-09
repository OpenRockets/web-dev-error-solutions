# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordion


This challenge focuses on creating a visually appealing multi-level nested list using CSS, specifically leveraging the power of CSS3's `:target` pseudo-class to implement an accordion effect for expanding and collapsing nested list items. We'll utilize basic CSS properties without any CSS frameworks like Tailwind.


**Description of the Styling:**

The goal is to style a nested unordered list (ul) to resemble an accordion.  When a parent list item is clicked, its immediate children (the next level of the list) should slide down (or up) revealing (or hiding) its content. We'll achieve this using a combination of the `:target` pseudo-class, transitions, and clever manipulation of height and overflow.  The styling will include distinct visual cues for opened and closed list items, such as different icons and background colors.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Accordion</title>
<style>
body { font-family: sans-serif; }
ul { list-style: none; padding: 0; }
li { 
  margin-bottom: 10px;
  cursor: pointer;
}
li > ul {
  display: none; /* Initially hide nested lists */
  overflow: hidden; /* Hide content when closed */
  transition: max-height 0.3s ease-out; /* Add smooth transition */
  max-height: 0; /* Initially zero height */
}

li > ul:target {  /* Show the nested list when its parent is the target */
  display: block;
  max-height: 500px; /* Adjust as needed */
}

li a {
    display: block;
    padding: 10px;
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    text-decoration: none;
    color: #333;
}

li a::before {
    content: "\25BC"; /* Unicode for a down arrow */
    margin-right: 5px;
}

li a[href^="#"]:target::before {
    content: "\25B2"; /* Unicode for an up arrow */
}
</style>
</head>
<body>

<h1>Nested List Accordion</h1>

<ul>
  <li><a href="#item1">Item 1</a>
    <ul id="item1">
      <li><a href="#item1-1">Sub-item 1.1</a></li>
      <li><a href="#item1-2">Sub-item 1.2</a></li>
    </ul>
  </li>
  <li><a href="#item2">Item 2</a>
    <ul id="item2">
      <li><a href="#item2-1">Sub-item 2.1</a></li>
      <li><a href="#item2-2">Sub-item 2.2</a></li>
      <li><a href="#item2-3">Sub-item 2.3</a>
        <ul id="item2-3">
            <li><a href="#">Sub-Sub-item 2.3.1</a></li>
        </ul>
      </li>
    </ul>
  </li>
  <li><a href="#item3">Item 3</a></li>
</ul>

</body>
</html>
```


**Explanation:**

1. **HTML Structure:**  A nested unordered list (`<ul>`) forms the basis.  Each `<li>` element represents a list item, and `id` attributes are crucial for the `:target` selector.
2. **CSS Styling:**
   - Basic styles set up the overall appearance.
   - `li > ul` hides nested lists initially (`display: none`). `overflow: hidden` prevents content from spilling out, and `transition` adds smooth animation. `max-height: 0` keeps them initially collapsed.
   - `li > ul:target` is the key: When an `id` matches the fragment identifier in the `href` of an `<a>` tag (e.g., clicking on "Item 1" makes "#item1" the target), the nested list is displayed (`display: block`) and its `max-height` is set to allow the content to show.
   - Arrow icons (`::before` pseudo-element) dynamically change based on whether the section is open or closed.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS :target:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **Understanding CSS Pseudo-classes:** Search for tutorials on CSS pseudo-classes and selectors.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

