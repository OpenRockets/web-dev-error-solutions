# 🐞 CSS Challenge:  A Responsive Navigation Bar with a Subtle Hover Effect


This challenge focuses on creating a responsive navigation bar using CSS (specifically CSS3).  The navigation bar will adapt to different screen sizes and feature a subtle hover effect on the menu items.  We'll use plain CSS for this example; Tailwind CSS would simplify the process, but this example focuses on fundamental CSS concepts.

**Description of the Styling:**

The navigation bar will be positioned at the top of the page and will contain several menu items. On larger screens, the menu items will be displayed horizontally.  On smaller screens (mobile), the menu will become a hamburger menu that reveals the menu items upon click.  Each menu item will have a subtle background highlight on hover.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<style>
nav {
  background-color: #333;
  overflow: hidden;
}

nav a {
  float: left;
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav a:hover {
  background-color: #ddd;
  color: black;
}

/* Responsive Navigation Bar */
@media screen and (max-width: 600px) {
  nav a {
    float: none;
    display: block;
  }
}

/*Hamburger Menu Style (Optional, for more advanced design)*/
.hamburger {
  display: none; /* Hidden by default */
  cursor: pointer;
  float: right;
  padding: 14px 16px;
  user-select: none;
}

.hamburger:hover {
  background-color: #ddd;
}

@media screen and (max-width: 600px) {
  .hamburger {
    display: block; /* Show hamburger on smaller screens */
  }
  nav a {
    display: none; /* Hide menu items on smaller screens initially */
  }
}
/*Show/Hide menu items when hamburger is clicked*/

.responsive {
    display: block;
}

</style>
</head>
<body>

<nav>
<div class="hamburger" onclick="toggleMenu()">&#9776;</div>  <!--Hamburger Icon-->
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Services</a>
  <a href="#">Contact</a>
</nav>


<script>
function toggleMenu() {
    var x = document.getElementById("myLinks");
    if (x.style.display === "block") {
      x.style.display = "none";
    } else {
      x.style.display = "block";
    }
}
</script>

</body>
</html>
```

**Explanation:**

* **Basic Styling:** The initial styles set up the navigation bar's background color,  float the menu items to the left, and style the links.
* **Hover Effect:** The `:hover` pseudo-class adds a subtle highlight on mouse hover.
* **Responsive Design (`@media` query):**  The `@media screen and (max-width: 600px)`  query targets screens smaller than 600px wide. It removes the float from menu items and stacks them vertically.  The  hamburger menu is displayed, and the menu items are initially hidden. The JavaScript function `toggleMenu()` is used to show/hide these items.
* **Hamburger Menu:** A simple hamburger icon (&#9776;) is added.  It's hidden on larger screens and displayed on smaller screens.


**Links to Resources to Learn More:**

* **CSS Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Responsive Web Design:** [Responsive Web Design Basics](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
* **CSS Selectors:** [Understanding CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

