# 🐞 CSS Challenge:  Responsive Navigation Bar with a Dark Mode Toggle


This challenge focuses on creating a responsive navigation bar that adapts to different screen sizes and includes a toggle for switching between light and dark mode. We'll use CSS3 for styling and leverage media queries for responsiveness.  No external libraries like Tailwind CSS are used to emphasize core CSS concepts.


**Description of the Styling:**

The navigation bar will be positioned at the top of the page and contain a logo on the left and navigation links on the right. On larger screens, the links will be displayed inline. On smaller screens (mobile), the links will be hidden behind a hamburger menu icon that, when clicked, reveals the links in a dropdown menu.  A dark mode toggle will be present, allowing users to switch between a light and dark theme.  The styling will be clean and modern.


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
  padding: 0;
  transition: background-color 0.3s ease; /* Smooth transition for dark mode */
}

.navbar {
  background-color: #f2f2f2; /* Light mode background */
  overflow: hidden;
  position: fixed;
  top: 0;
  width: 100%;
}

.navbar a {
  float: left;
  display: block;
  color: #333;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.navbar a:hover {
  background-color: #ddd;
  color: black;
}

.navbar-right {
  float: right;
}


/* Hamburger Menu */
.hamburger {
  display: none;
  cursor: pointer;
  float: right;
  padding: 14px 16px;
}

.hamburger span {
  display: block;
  height: 2px;
  width: 25px;
  background-color: #333;
  margin: 5px 0;
  transition: all 0.3s ease;
}

.hamburger.active span:nth-child(1) {
  transform: translateY(8px) rotate(45deg);
}

.hamburger.active span:nth-child(2) {
  opacity: 0;
}

.hamburger.active span:nth-child(3) {
  transform: translateY(-8px) rotate(-45deg);
}


/* Responsive Styles */
@media screen and (max-width: 600px) {
  .navbar a:not(:first-child) { display: none; }
  .hamburger { display: block; }
}

@media screen and (max-width: 600px) {
    .navbar-right {
        display:none;
    }
    .navbar-responsive {
        display: block;
    }
}

.navbar-responsive {
    display: none;
}

.navbar-responsive ul {
    list-style: none;
    padding: 0;
    margin: 0;
    background-color: #f2f2f2;
}
.navbar-responsive li {
    padding: 10px;
    border-bottom: 1px solid #ddd;
}
.navbar-responsive li a {
    text-decoration: none;
    color: #333;
}

/* Dark Mode */
.dark-mode {
  background-color: #333;
  color: #f2f2f2;
}

.dark-mode .navbar a {
  color: #f2f2f2;
}

.dark-mode .navbar a:hover {
  background-color: #555;
  color: #fff;
}

.dark-mode .hamburger span {
  background-color: #f2f2f2;
}

.dark-mode .navbar-responsive ul{
    background-color: #333;
}
.dark-mode .navbar-responsive li a{
    color: #fff;
}
</style>
</head>
<body>

<div class="navbar">
  <a href="#" class="logo">Logo</a>
  <div class="navbar-right">
  <a href="#">Link 1</a>
  <a href="#">Link 2</a>
  <a href="#">Link 3</a>
  </div>
  <div class="hamburger" onclick="toggleMenu()">
    <span></span>
    <span></span>
    <span></span>
  </div>
  <div class="navbar-responsive">
    <ul>
        <li><a href="#">Link 1</a></li>
        <li><a href="#">Link 2</a></li>
        <li><a href="#">Link 3</a></li>
    </ul>
</div>
  <button onclick="toggleDarkMode()">Toggle Dark Mode</button>
</div>

<script>
function toggleMenu() {
  const hamburger = document.querySelector('.hamburger');
  const navbarResponsive = document.querySelector('.navbar-responsive');
  hamburger.classList.toggle('active');
  navbarResponsive.classList.toggle('active');
}

function toggleDarkMode() {
  document.body.classList.toggle('dark-mode');
}
</script>

</body>
</html>
```

**Explanation:**

The CSS utilizes media queries to handle responsiveness. The JavaScript functions `toggleMenu()` and `toggleDarkMode()` control the hamburger menu and dark mode toggle respectively.  The `dark-mode` class is applied to the body to switch the theme.  The code is well-commented to make it easy to understand.


**Links to Resources to Learn More:**

* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **MDN Web Docs (JavaScript):** [https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* **CSS Tricks:** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

