# 🐞 CSS Challenge:  Responsive Navigation Bar with Subtle Animations


This challenge focuses on creating a responsive navigation bar that smoothly transitions its appearance on smaller screens and includes subtle hover animations. We'll use CSS3 for styling and animations.  Tailwind CSS could be used to simplify the HTML structure and some of the styling, but for this example, we'll stick with plain CSS for broader applicability.

**Description of the Styling:**

The navigation bar will be a horizontal bar containing several links. On larger screens (above 768px), the links will be displayed inline. On smaller screens, the navigation bar will collapse into a hamburger menu icon that, when clicked, reveals the links in a vertically stacked dropdown menu.  Hovering over links will subtly change their background color.

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

  nav ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
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
    transition: background-color 0.3s ease; /* Smooth transition for hover effect */
  }

  nav li a:hover {
    background-color: #ddd;
    color: black;
  }

  /* Hamburger menu style for smaller screens */
  @media screen and (max-width: 768px) {
    nav li {
      float: none;
    }

    nav li a {
      display: block;
      text-align: left;
    }

    nav ul {
      display: none; /* Hide the navigation links initially */
    }

    nav .hamburger {
      display: block;
      cursor: pointer;
    }
  }


  nav ul.show { /* Style the dropdown menu when open */
    display: block;
  }

  .hamburger {
    display: none;
    background-color: #333;
    color: white;
    padding: 14px 16px;
    border: none;
  }

</style>
</head>
<body>

<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
  <button class="hamburger" onclick="toggleMenu()">&#9776;</button>
</nav>

<script>
function toggleMenu() {
  var x = document.querySelector("nav ul");
  if (x.classList.contains("show")) {
    x.classList.remove("show");
  } else {
    x.classList.add("show");
  }
}
</script>

</body>
</html>
```

**Explanation:**

* The CSS uses media queries (`@media screen and (max-width: 768px)`) to adjust the layout for different screen sizes.
* The hamburger menu is hidden on larger screens and revealed only on smaller screens.  Javascript toggles its visibility.
* CSS transitions provide smooth hover effects.
* The Javascript function `toggleMenu` adds and removes the `show` class to control the visibility of the navigation links on smaller screens.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Media Queries:** [MDN Web Docs - Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **Javascript DOM Manipulation:** [MDN Web Docs - DOM Manipulation](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

