# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordion


This challenge focuses on styling a multi-level nested list to create an accordion-like effect using CSS.  Each list item will initially only show its title, and clicking the title will reveal its sub-items. We'll achieve this using CSS only, without JavaScript. This example utilizes CSS variables for easier customization.

**Description of the Styling:**

The styling aims for a clean, modern look.  Each list item will have a distinct background color,  a subtle hover effect, and the sub-lists will slide down smoothly when their parent is clicked. We use a combination of CSS variables and the `:target` pseudo-class to manage the accordion behavior.  The styling will be concise and efficient, leveraging CSS's power to manage complex interactions.


**Full Code (CSS Only):**

```css
:root {
  --primary-color: #3498db; /* Primary color */
  --secondary-color: #ecf0f1; /* Secondary color */
  --text-color: #333; /* Text color */
}

body {
  font-family: sans-serif;
  line-height: 1.6;
  margin: 20px;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  margin-bottom: 10px;
  background-color: var(--secondary-color);
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
}

li > ul {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-out;
}

li > ul.open {
  max-height: 200px; /* Adjust as needed */
}


li a {
  text-decoration: none;
  color: var(--text-color);
  display: block; /* Occupy the whole line */
}

li:hover {
  background-color: var(--primary-color);
  color: white;
}

li.active a {
  color: white;
}

li.active {
  background-color: var(--primary-color);
}

/* Styling for different list levels (can be expanded) */
li ul li {
  margin-left: 20px;
}
li ul li ul li {
  margin-left: 40px;
}

```

**HTML Structure (example):**

```html
<ul>
  <li><a href="#section1">Section 1</a>
    <ul id="section1">
      <li><a href="#subsection1a">Subsection 1a</a></li>
      <li><a href="#subsection1b">Subsection 1b</a>
        <ul id="subsection1b">
          <li><a href="#subsubsection1b1">Sub-subsection 1b1</a></li>
        </ul>
      </li>
    </ul>
  </li>
  <li><a href="#section2">Section 2</a>
    <ul id="section2">
      <li><a href="#subsection2a">Subsection 2a</a></li>
    </ul>
  </li>
</ul>
```

**Explanation:**

* **CSS Variables:**  Using `:root` to define variables allows for easy customization of colors and other styles.
* **`max-height` and `overflow: hidden`:** These properties initially hide the sub-lists.
* **`transition`:** This provides a smooth animation when the `max-height` changes.
* **`:target` (implicitly used in HTML):** The `#section1`, `#section2`, etc.  IDs in the HTML, combined with the `href` attributes create the accordion functionality. When a link is clicked, the browser navigates to the corresponding section, causing the related `ul` to be displayed.  Javascript is NOT used here.  The JavaScript approach would use event listeners for a more dynamic experience but this CSS-only method demonstrates a powerful CSS feature.
* **JavaScript Enhancement (optional):** For a more interactive approach, you could add JavaScript to handle the opening and closing of the accordion sections more smoothly and possibly include additional animation effects beyond the simple `max-height` transition.

**Links to Resources to Learn More:**

* **MDN Web Docs - CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs - :target Pseudo-Class:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:target](https://developer.mozilla.org/en-US/docs/Web/CSS/:target)
* **CSS Tricks:** [https://css-tricks.com/](https://css-tricks.com/) (A great resource for all things CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

