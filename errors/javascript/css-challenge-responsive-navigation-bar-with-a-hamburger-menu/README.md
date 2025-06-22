# 🐞 CSS Challenge:  Responsive Navigation Bar with a Hamburger Menu


This challenge involves creating a responsive navigation bar that adapts to different screen sizes using CSS.  For smaller screens, a hamburger menu will be used to reveal the navigation links. We will use plain CSS3 for this example, avoiding any CSS frameworks like Tailwind CSS to focus on fundamental concepts.

**Description of the Styling:**

The navigation bar will be a fixed-width element centered horizontally. On larger screens (above 768px), the navigation links will be displayed inline.  On smaller screens, the navigation links will be hidden by default, and a hamburger icon will be visible. Clicking the hamburger icon will toggle the visibility of the navigation links.

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

.navbar {
  background-color: #333;
  overflow: hidden;
}

.navbar a {
  float: left;
  display: block;
  color: white;
  text-align: center;
  padding: 14px 20px;
  text-decoration: none;
}

.navbar a:hover {
  background-color: #ddd;
  color: black;
}

.navbar .hamburger {
  display: none; /* Hidden on larger screens */
  cursor: pointer;
  float: right;
  padding: 14px 20px;
}

.navbar .hamburger span {
  display: block;
  height: 2px;
  width: 25px;
  background-color: white;
  margin: 5px 0;
}

/* Style for smaller screens */
@media screen and (max-width: 768px) {
  .navbar a:not(:first-child) {
    display: none;
  }

  .navbar .hamburger {
    display: block;
  }

  .navbar.active a:not(:first-child){
    display: block;
  }
}

/* JavaScript to toggle the menu */
</style>
</head>
<body>

<div class="navbar" id="myNavbar">
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Services</a>
  <a href="#">Contact</a>
  <div class="hamburger" onclick="toggleNavbar()">
    <span></span>
    <span></span>
    <span></span>
  </div>
</div>

<script>
function toggleNavbar() {
  document.getElementById("myNavbar").classList.toggle("active");
}
</script>

</body>
</html>
```

**Explanation:**

* **CSS:** We use `float` for horizontal alignment of links, `display: none;`  to hide elements, and `@media` queries for responsive design.  The hamburger menu is styled with spans to create the three-line effect.
* **JavaScript:**  A simple JavaScript function toggles the `active` class on the navbar, which changes the display style of the navigation links using CSS.

**Links to Resources to Learn More:**

* **CSS Media Queries:** [https://www.w3schools.com/cssref/css3_pr_mediaquery.asp](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)
* **CSS Flexbox (alternative layout method):** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **CSS Grid (another alternative layout method):** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

