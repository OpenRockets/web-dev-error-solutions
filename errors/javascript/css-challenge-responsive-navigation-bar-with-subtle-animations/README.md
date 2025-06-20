# 🐞 CSS Challenge:  Responsive Navigation Bar with Subtle Animations


This challenge focuses on creating a responsive navigation bar using CSS.  The navigation bar will adapt smoothly to different screen sizes and incorporate subtle animations for a more engaging user experience. We'll be using plain CSS3 for this example, avoiding any CSS frameworks like Tailwind for a more fundamental understanding.

**Description of the Styling:**

The navigation bar will consist of a logo on the left, a list of navigation links in the center, and a "Contact" button on the right. On larger screens, all elements will be displayed horizontally. As the screen size decreases, the navigation links will collapse into a hamburger menu icon that expands on click.  A subtle fade-in animation will accompany the appearance of the hamburger menu and its items.


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
  padding: 10px 0;
  position: relative; /* Needed for absolute positioning of hamburger menu */
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 960px;
  margin: 0 auto; /* Center the nav container */
}

.logo {
  font-size: 1.5em;
  font-weight: bold;
  margin-right: 20px;
}

.nav-links {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.nav-links li {
  margin-right: 20px;
}

.nav-links a {
  color: white;
  text-decoration: none;
}


/* Hamburger Menu Styles */
.hamburger {
  display: none;
  cursor: pointer;
  padding: 10px;
}

.bar {
  display: block;
  width: 25px;
  height: 3px;
  background-color: white;
  margin: 5px auto;
  transition: background-color 0.3s; /* Add transition for smoother animation */
}


/* Responsive styles */
@media (max-width: 768px) {
  .nav-links {
    display: none; /* Hide nav links on smaller screens */
    position: absolute; /* Position it off screen */
    top: 100%; /* Below the nav bar */
    left: 0;
    width: 100%;
    flex-direction: column; /* Stack links vertically */
    background-color: #333;
    opacity: 0; /* Initially hidden */
    transition: opacity 0.3s ease-in-out; /* Add transition for fade-in animation */
  }

  .nav-links.active {
    opacity: 1; /* Show when active */
  }

  .nav-links li {
    margin: 10px 0;
    text-align: center;
  }

  .hamburger {
    display: block; /* Show hamburger menu on smaller screens */
  }
}

/* Animations for hover effect on menu*/
.nav-links li a:hover {
    transform: scale(1.1);
    transition: 0.2s;
    color: lightblue;

}

</style>
</head>
<body>
<nav>
  <div class="nav-container">
    <div class="logo">My Website</div>
    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
    <div class="hamburger" onclick="toggleNav()">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
    </div>
  </div>
</nav>

<script>
function toggleNav() {
  const navLinks = document.querySelector('.nav-links');
  navLinks.classList.toggle('active');
}
</script>

</body>
</html>
```

**Explanation:**

* The base styles create a simple navigation bar with a flexbox layout for easy horizontal alignment.
* Media queries are used to handle responsiveness.  On smaller screens, the `nav-links` are hidden initially and displayed using JavaScript's `classList.toggle('active')`.
* The hamburger menu is hidden on larger screens and revealed on smaller screens.
* JavaScript's `toggleNav()` function manages the display of the navigation links.
* CSS transitions provide smooth animations for the hamburger menu and the nav links.

**Resources to Learn More:**

* **CSS Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **CSS Media Queries:** [https://www.w3schools.com/cssref/css3_pr_mediaquery.asp](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)
* **CSS Transitions and Animations:** [https://www.w3schools.com/css/css3_transitions.asp](https://www.w3schools.com/css/css3_transitions.asp) and [https://www.w3schools.com/css/css3_animations.asp](https://www.w3schools.com/css/css3_animations.asp)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

