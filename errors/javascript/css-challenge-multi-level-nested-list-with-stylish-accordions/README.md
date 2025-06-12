# 🐞 CSS Challenge:  Multi-level Nested List with Stylish Accordions


This challenge focuses on creating a visually appealing multi-level nested list using CSS.  Each list item will be styled as an accordion, allowing users to expand and collapse sub-lists. We'll leverage CSS3 for the styling and animations.


## Description of the Styling:

The goal is to create a nested list where:

* **Top-level list items:**  Have a bold title, a plus (+) icon to indicate collapse/expansion and a background color.
* **Sub-lists:** Are initially hidden and only revealed when the corresponding parent list item is clicked (accordion effect).
* **Indentation:**  Sub-lists are clearly indented to show the hierarchical structure.
* **Transitions:** Smooth transitions should be applied to the height changes during accordion expansion/collapse for a better user experience.
* **Icons:**  Simple plus and minus icons will be used to show the expand/collapse state.


## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<title>Nested List Accordion</title>
<style>
body { font-family: sans-serif; }

.accordion {
  background-color: #f2f2f2;
  cursor: pointer;
  padding: 18px;
  width: 100%;
  border: none;
  text-align: left;
  outline: none;
  transition: 0.4s;
}

.active, .accordion:hover {
  background-color: #ddd;
}

.accordion:after {
  content: '\2795'; /* Unicode for plus sign */
  font-size: 13px;
  color: #777;
  float: right;
  margin-left: 5px;
}

.active:after {
  content: "\2796"; /* Unicode for minus sign */
}

.panel {
  padding: 0 18px;
  background-color: white;
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.2s ease-out;
}

.panel.show {
  max-height: 500px;  /* Adjust as needed */
}

ul {
  list-style: none;
  padding: 0;
}

ul ul {
  margin-left: 20px;
}

.accordion-item {
  margin-bottom: 5px; /* Add space between accordion items */
}

</style>
</head>
<body>

<h2>Nested List Accordion</h2>

<div class="accordion-item">
  <button class="accordion">Chapter 1: Introduction</button>
  <div class="panel">
    <p>Introduction content goes here.</p>
    <ul>
      <li><button class="accordion">Section 1.1: Subsection 1</button>
        <div class="panel">
          <p>Subsection 1.1 content.</p>
        </div>
      </li>
      <li><button class="accordion">Section 1.2: Subsection 2</button>
        <div class="panel">
          <p>Subsection 1.2 content.</p>
          <ul>
            <li><button class="accordion">Subsection 1.2.1</button>
            <div class="panel">
              <p>Subsection 1.2.1 Content</p>
            </div>
            </li>
          </ul>
        </div>
      </li>
    </ul>
  </div>
</div>


<script>
var acc = document.getElementsByClassName("accordion");
var i;

for (i = 0; i < acc.length; i++) {
  acc[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var panel = this.nextElementSibling;
    if (panel.style.maxHeight) {
      panel.style.maxHeight = null;
    } else {
      panel.style.maxHeight = panel.scrollHeight + "px";
    }
  });
}
</script>

</body>
</html>
```

## Explanation:

The HTML structures the nested list using `<ul>` and `<li>` elements.  Each list item contains an accordion button (`<button class="accordion">`) and a panel (`<div class="panel">`) to hold the content.  JavaScript toggles the `active` class and controls the `maxHeight` of the panel to create the accordion effect.  CSS handles the styling, including background colors, transitions, and the plus/minus icons using Unicode characters.


## Links to Resources to Learn More:

* **CSS3 Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Accordions:** Search for "CSS accordion tutorial" on YouTube or your preferred learning platform.  Many tutorials offer different approaches.
* **Unicode Characters:** [Unicode Character Table](https://unicode-table.com/en/) (For the plus and minus signs)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

