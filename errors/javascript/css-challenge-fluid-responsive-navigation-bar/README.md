# 🐞 CSS Challenge:  Fluid, Responsive Navigation Bar


This challenge focuses on creating a fluid and responsive navigation bar using CSS.  The navigation bar should adapt smoothly to different screen sizes, maintaining usability and a clean aesthetic. We'll use plain CSS (no CSS frameworks like Tailwind, Bootstrap, etc.) to demonstrate fundamental CSS principles.

**Description of the Styling:**

The navigation bar will contain a logo on the left and a list of navigation items on the right.  On larger screens, the items will be displayed inline.  As the screen size decreases, the navigation items will stack vertically, revealing a hamburger menu icon for easy access.

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
  overflow: hidden;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

nav li {
  float: left;
}

nav li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav li a:hover {
  background-color: #ddd;
  color: black;
}

/* Responsive design */
@media screen and (max-width: 600px) {
  nav li {
    float: none;
    width: 100%;
  }
  nav li a {
    display: block;
  }
}

/* Hamburger menu style (optional) */
.hamburger {
  display: none;
  cursor: pointer;
  margin-top: 10px;
  margin-right: 10px;
}
.hamburger span {
  display: block;
  height: 3px;
  width: 30px;
  background-color: white;
  margin: 5px;
  transition: all 0.3s ease;
}
.hamburger.active span:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}
.hamburger.active span:nth-child(2) {
  opacity: 0;
}
.hamburger.active span:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

@media screen and (max-width: 600px) {
  .hamburger {
    display: block;
  }
  nav ul {
    display: none;
  }
  nav ul.show {
    display: block;
  }
}
</style>
</head>
<body>

<nav>
  <div class="hamburger">
    <span></span>
    <span></span>
    <span></span>
  </div>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<script>
  const hamburger = document.querySelector(".hamburger");
  const navUl = document.querySelector("nav ul");
  hamburger.addEventListener("click", () => {
    hamburger.classList.toggle("active");
    navUl.classList.toggle("show");
  });
</script>

</body>
</html>
```

**Explanation:**

The CSS utilizes media queries (`@media screen and (max-width: 600px)`) to adjust the layout based on screen size.  On smaller screens, the `float: left;` property is removed from the list items, causing them to stack vertically.  A simple hamburger menu is implemented using CSS transitions for a smooth visual effect.  JavaScript is used to toggle the visibility of the navigation items on smaller screens.


**Links to Resources to Learn More:**

* **MDN Web Docs - CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **MDN Web Docs - Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
* **FreeCodeCamp - Responsive Web Design:** [https://www.freecodecamp.org/learn/responsive-web-design/](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

