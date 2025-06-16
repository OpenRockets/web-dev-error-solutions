# 🐞 CSS Challenge:  Responsive Navigation Bar with a Subtle Hover Effect


This challenge focuses on creating a responsive navigation bar using CSS (specifically CSS3) that features a subtle hover effect on its menu items.  The design aims for a clean, modern look that adapts gracefully to different screen sizes. We'll avoid using a CSS framework like Tailwind for this example to demonstrate fundamental CSS principles.

**Description of the Styling:**

The navigation bar will be positioned at the top of the page.  It will contain a logo on the left and a list of menu items on the right. On larger screens, the menu items will be displayed inline.  On smaller screens (mobile), the menu will collapse into a hamburger menu icon, revealing the menu items on click. The hover effect will involve a slight change in background color and text shadow on mouseover.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
}

nav {
  background-color: #333;
  color: white;
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.5em;
  font-weight: bold;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

li {
  margin-left: 20px;
}

a {
  text-decoration: none;
  color: white;
  padding: 10px;
  transition: background-color 0.3s ease, text-shadow 0.3s ease; /* Smooth transitions */
}

a:hover {
  background-color: #555;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

/* Responsive Styles */
@media (max-width: 768px) {
  ul {
    display: none; /* Hide the menu on smaller screens */
  }

  #menu-toggle {
    display: block;
    cursor: pointer;
    font-size: 1.5em;
  }

  #menu-toggle:checked ~ ul {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background-color: #333;
  }

  #menu-toggle:checked ~ ul li {
      margin: 0;
      width: 100%;
      text-align: center;
  }

  #menu-toggle:checked ~ ul a {
    display: block;
    width: 100%;
  }
}
</style>
</head>
<body>

<nav>
  <div class="logo">My Website</div>
  <input type="checkbox" id="menu-toggle">
  <label for="menu-toggle">☰</label>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

</body>
</html>
```

**Explanation:**

* The code uses flexbox for easy layout management, making it responsive.
* The `@media` query targets screens smaller than 768px and hides the menu, revealing a hamburger menu icon instead.
* A checkbox (`#menu-toggle`) is used to control the menu's visibility. The adjacent sibling selector (`~`) is crucial for connecting the checkbox state to the menu's display.
* CSS transitions provide smooth hover effects.

**Links to Resources to Learn More:**

* **CSS Flexbox:** [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

