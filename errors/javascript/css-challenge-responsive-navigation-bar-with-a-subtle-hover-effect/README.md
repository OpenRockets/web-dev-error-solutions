# 🐞 CSS Challenge: Responsive Navigation Bar with a Subtle Hover Effect


This challenge focuses on creating a responsive navigation bar using CSS (specifically CSS3).  The navigation bar should adapt smoothly to different screen sizes and include a subtle hover effect on menu items.  We'll achieve responsiveness using media queries and the hover effect with CSS transitions.  This example doesn't use a CSS framework like Tailwind CSS, opting instead for a vanilla CSS approach to illustrate fundamental concepts.


## Styling Description

The navigation bar will be positioned at the top of the page.  It will contain a logo on the left and a list of menu items on the right.  On larger screens, the menu items will be displayed inline.  On smaller screens, the menu items will be hidden by default and revealed via a hamburger menu icon.  The hover effect will subtly change the background color of the menu items on mouseover.

## Full Code

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
  font-weight: bold;
  font-size: 1.2em;
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
  padding: 8px 12px;
  transition: background-color 0.3s ease; /* Smooth transition for hover effect */
}

a:hover {
  background-color: #555;
}

/* Hamburger Menu Style */
.hamburger {
  display: none; /* Hide on larger screens */
  cursor: pointer;
}

.hamburger span {
  display: block;
  width: 25px;
  height: 3px;
  margin: 5px;
  background-color: white;
  transition: all 0.3s ease;
}

/* Responsive Style for smaller screens */
@media (max-width: 768px) {
  ul {
    display: none; /* Hide the menu on smaller screens */
  }

  .hamburger {
    display: block; /* Show hamburger menu on smaller screens */
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

  ul.active {
    display: flex;
    flex-direction: column;
    position: absolute;
    top: 100%;
    left: 0;
    width: 100%;
    background-color: #333;
  }

  ul.active li {
    margin: 0;
    width: 100%;
    text-align: center;
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
  <ul id="nav-menu">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<script>
function toggleMenu() {
  const menu = document.getElementById('nav-menu');
  const hamburger = document.querySelector('.hamburger');
  menu.classList.toggle('active');
  hamburger.classList.toggle('active');
}
</script>

</body>
</html>
```

## Explanation

The code uses CSS flexbox for layout and media queries for responsiveness.  The hamburger menu is implemented using a simple CSS animation and JavaScript to toggle the menu's visibility.  The hover effect is achieved with CSS transitions. The Javascript function `toggleMenu` controls the visibility of the menu on smaller screens.

## Resources to Learn More

* **CSS Flexbox:**  [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

