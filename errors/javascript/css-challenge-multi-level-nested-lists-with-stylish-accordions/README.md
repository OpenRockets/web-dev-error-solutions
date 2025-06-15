# 🐞 CSS Challenge:  Multi-level Nested Lists with Stylish Accordions


This challenge focuses on styling nested lists to create an accordion-like effect using only CSS.  Each top-level list item will act as an accordion header, revealing or hiding its sub-levels when clicked. We'll achieve this without JavaScript, relying solely on CSS's `:target` pseudo-class and sibling selectors.  We'll aim for a clean and modern look.  This example utilizes standard CSS but could easily be adapted to Tailwind CSS by replacing the specific CSS properties with their Tailwind equivalents (e.g., `background-color` with `bg-gray-200`).

**Description of the Styling:**

The styling includes:

* **Accordion Headers:**  Each top-level list item (`<li>`) will have a distinct background color and padding.  On hover, the background will slightly darken.  A plus (+) or minus (-) symbol will indicate the open/closed state.
* **Accordion Content:** Nested lists (`<ul>`) will initially be hidden.  When the corresponding header is clicked, the nested list will become visible.
* **Visual Hierarchy:**  Proper indentation and styling will ensure a clear visual hierarchy between levels of the list.

**Full Code (CSS):**

```css
ul {
  list-style: none;
  padding: 0;
  margin-bottom: 1rem;
}

li {
  cursor: pointer;
  padding: 0.8rem 1.2rem;
  border-bottom: 1px solid #ddd;
  transition: background-color 0.3s ease; /* smooth transition for hover effect */
}

li:hover {
  background-color: #f0f0f0;
}

li > ul {
  display: none;
  margin-left: 20px;
}

li > ul:target { /* This is the key - show content when the UL is the target */
  display: block;
}

li::before {
  content: "+ "; /* Default plus symbol */
  margin-right: 0.5rem;
}

li[aria-expanded="true"]::before {
  content: "- "; /* Change to minus when expanded */
}


li:has(>ul):focus-within, li:has(>ul:target) { /* Keep header visible on open */
  background-color: #f0f0f0;
}

a{
  text-decoration: none;
  color: inherit;
}

```

**Full Code (HTML):**

```html
<ul>
  <li><a href="#sublist1">Item 1</a>
    <ul id="sublist1">
      <li>Subitem 1.1</li>
      <li>Subitem 1.2</li>
    </ul>
  </li>
  <li><a href="#sublist2">Item 2</a>
    <ul id="sublist2">
      <li>Subitem 2.1</li>
      <li>Subitem 2.2</li>
      <li>Subitem 2.3</li>
    </ul>
  </li>
  <li><a href="#sublist3">Item 3</a>
    <ul id="sublist3">
      <li>Subitem 3.1</li>
      <li>Subitem 3.2 <a href="#sublist3-1">Subitem 3.2.1</a>
      <ul id="sublist3-1">
        <li>Sub-Subitem 3.2.1.1</li>
      </ul>
      </li>
    </ul>
  </li>
</ul>
```

**Explanation:**

* The core logic relies on the `:target` pseudo-class.  Each nested `<ul>` has a unique ID, and the corresponding `<li>`'s `<a>` tag's `href` attribute points to this ID.  When the `<li>` is clicked, the browser navigates to the ID, revealing the nested list. The `display: none;` and `display: block;` control visibility.
* The `::before` pseudo-element adds the plus/minus symbol, dynamically changing based on whether the list is expanded.  This is controlled by setting the `aria-expanded` attribute dynamically in JavaScript (not shown here, as we are focusing on CSS solution).  A JavaScript improvement would smoothly handle the opening/closing and update the `aria-expanded` accordingly.
* The `:has` and `focus-within` are included to manage cases of nested lists.


**Resources to Learn More:**

* **CSS Selectors:**  MDN Web Docs: [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* **CSS Pseudo-classes:** MDN Web Docs: [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **CSS Transitions:** MDN Web Docs: [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **Understanding ARIA Attributes:** [https://www.w3.org/WAI/intro/aria](https://www.w3.org/WAI/intro/aria)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

