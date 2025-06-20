# 🐞 CSS Challenge: Responsive Navigation Bar with a Subtle Hover Effect


This challenge focuses on creating a responsive navigation bar using CSS (specifically, we'll use CSS3 properties and techniques for broader applicability). The navigation bar should smoothly adjust to different screen sizes and feature a subtle hover effect on menu items.


## Styling Description

The navigation bar will be positioned at the top of the page.  It will contain a logo on the left and menu items on the right.  On larger screens, all menu items will be visible. On smaller screens (mobile), the menu items will collapse behind a hamburger menu icon, revealing themselves when the hamburger is clicked.  Hovering over a menu item will slightly increase its font size and change the color of the underline.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<style>
body {
  margin: 0;
  font-family: sans-serif;
}

.navbar {
  background-color: #333;
  overflow: hidden;
}

.navbar a {
  float: left;
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 16px;
}

.navbar a:hover {
  font-size: 17px;
  text-decoration: underline;
  color: #ddd; /* Subtle hover color change */
}

.navbar a.right {
  float: right;
}

/* Responsive Hamburger Menu */
.navbar .icon {
  display: none; /* Hidden on larger screens */
}

@media screen and (max-width: 600px) {
  .navbar a:not(.icon) {
    display: none;
  }

  .navbar .icon {
    display: block;
    position: absolute;
    right: 0;
    top: 0;
    cursor: pointer;
  }
  .navbar a.icon {
    padding: 10px 16px;
    color: white;
  }
  .navbar.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .navbar.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}

/* Hamburger Icon Styling (You can improve this with CSS or an icon font) */
.navbar .icon::before {
  content: "☰";
  font-size: 24px;
}

.navbar.responsive .icon::before {
  content: "✕"; /* Close icon */
}
</style>
</head>
<body>

<div class="navbar" id="myNavbar">
  <a href="#home" class="logo">Logo</a>
  <a href="#news">News</a>
  <a href="#contact">Contact</a>
  <a href="javascript:void(0);" class="icon" onclick="myFunction()">&#9776;</a> 
</div>

<script>
function myFunction() {
  var x = document.getElementById("myNavbar");
  if (x.className === "navbar") {
    x.className += " responsive";
  } else {
    x.className = "navbar";
  }
}
</script>

</body>
</html>
```


## Explanation

* **Basic Structure:** The HTML sets up a basic navigation bar with a logo and links.
* **CSS Styling:** The CSS styles the navigation bar, links, and hover effects.  `float:left` and `float:right` are used for horizontal arrangement.
* **Responsive Design:** Media queries (`@media screen and (max-width: 600px)`) are used to adjust the layout for smaller screens.  The hamburger menu (`class="icon"`) is hidden on larger screens and revealed on smaller screens using Javascript's `myFunction`.
* **Hamburger Menu Functionality:** The JavaScript function `myFunction` toggles the `responsive` class on the navbar, dynamically changing its styles to show or hide the menu items.


## Links to Resources to Learn More

* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **MDN Web Docs (JavaScript):** [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* **CSS Tricks:** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

