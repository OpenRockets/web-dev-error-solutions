# 🐞 CSS Challenge: Responsive Navigation Bar with Subtle Animations


This challenge focuses on creating a responsive navigation bar using CSS (specifically CSS3) that incorporates smooth hover animations and adapts seamlessly to different screen sizes. We'll utilize a simple, clean design, focusing on the practical application of CSS properties for layout and animation.  No JavaScript is needed.

**Description of the Styling:**

The navigation bar will consist of a logo on the left and a list of navigation links on the right.  On larger screens, the links will be displayed inline.  On smaller screens (mobile), the links will be hidden behind a hamburger menu icon, revealed upon clicking.  Hovering over navigation links will subtly animate the background color.

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
  color: #fff;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
}

.nav-links {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.nav-links li {
  margin-left: 1rem;
}

.nav-links a {
  text-decoration: none;
  color: #fff;
  padding: 0.5rem 1rem;
  transition: background-color 0.3s ease; /* Smooth transition for hover effect */
}

.nav-links a:hover {
  background-color: rgba(255, 255, 255, 0.2); /* Subtle background change on hover */
}


/* Responsive Styles for smaller screens */
@media (max-width: 768px) {
  .nav-links {
    display: none; /* Hide links on smaller screens */
  }

  .hamburger {
    display: block; /* Show hamburger menu icon */
    cursor: pointer;
  }

  .hamburger span {
    display: block;
    height: 3px;
    width: 25px;
    margin: 5px 0;
    background-color: white;
    transition: all 0.3s;
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

  .nav-links.active {
    display: flex;
    flex-direction: column; /* Stack links vertically on mobile */
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #333;
    width: 100%;
  }

  .nav-links.active li{
      margin: 0;
      width: 100%;
  }

  .nav-links.active a{
    text-align: center;
    width: 100%;
    display: block;
  }
}
</style>
</head>
<body>
<nav>
  <div class="logo">My Website</div>
  <div class="hamburger" onclick="toggleMenu()">
    <span></span>
    <span></span>
    <span></span>
  </div>
  <ul class="nav-links">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<script>
function toggleMenu() {
  const hamburger = document.querySelector(".hamburger");
  const navLinks = document.querySelector(".nav-links");
  hamburger.classList.toggle("active");
  navLinks.classList.toggle("active");
}
</script>
</body>
</html>
```

**Explanation:**

The code uses CSS flexbox for easy layout management.  Media queries handle the responsiveness.  The hamburger menu is implemented using a simple CSS animation on the three spans representing the menu icon. JavaScript is minimally used to toggle the class for showing/hiding the mobile menu.  Hover effects utilize CSS transitions for smoothness.

**Links to Resources to Learn More:**

* **CSS Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **CSS Media Queries:** [https://www.w3schools.com/cssref/css3_pr_mediaquery.asp](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)
* **CSS Transitions:** [https://www.w3schools.com/cssref/css3_pr_transition.asp](https://www.w3schools.com/cssref/css3_pr_transition.asp)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

