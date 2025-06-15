# 🐞 CSS Challenge:  Responsive Navigation Bar with a Hamburger Menu


This challenge focuses on creating a responsive navigation bar that adapts to different screen sizes.  For smaller screens, it utilizes a hamburger menu icon to reveal the navigation links. We'll use CSS Grid for layout and CSS transitions for smooth animations.


## Description of the Styling

The navigation bar will have a fixed width, occupying the full width of the viewport. On larger screens (say, above 768px), the navigation links will be displayed inline.  On smaller screens, the links will be hidden initially, revealed by clicking a hamburger menu icon.  The hamburger menu will transition smoothly to an "X" icon upon clicking.  The overall style will be clean and modern, with subtle animations.


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

  .navbar {
    background-color: #333;
    color: #fff;
    display: grid;
    grid-template-columns: auto 1fr; /* Auto width for the hamburger, rest for links */
    align-items: center;
    padding: 10px;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000; /* Ensure it's on top */
  }

  .hamburger {
    display: none; /* Initially hidden on larger screens */
    cursor: pointer;
    padding: 10px;
  }

  .hamburger span {
    display: block;
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 5px 0;
    transition: all 0.3s ease;
  }

  .hamburger.active span:nth-child(1) {
    transform: rotate(45deg) translate(7px, 7px);
  }

  .hamburger.active span:nth-child(2) {
    opacity: 0;
  }

  .hamburger.active span:nth-child(3) {
    transform: rotate(-45deg) translate(7px, -7px);
  }

  .nav-links {
    display: grid;
    grid-auto-flow: column;
    gap: 20px;
  }

  .nav-link {
    text-decoration: none;
    color: white;
  }

  @media (max-width: 768px) {
    .hamburger {
      display: block;
    }

    .nav-links {
      display: none; /* Hide links on smaller screens */
    }

    .nav-links.active {
      display: grid;
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      background-color: #333;
      grid-auto-flow: row; /* Stack links vertically */
      padding: 10px;

    }
  }
</style>
</head>
<body>
  <nav class="navbar">
    <div class="hamburger" onclick="toggleNav()">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div class="nav-links" id="navLinks">
      <a href="#" class="nav-link">Home</a>
      <a href="#" class="nav-link">About</a>
      <a href="#" class="nav-link">Services</a>
      <a href="#" class="nav-link">Contact</a>
    </div>
  </nav>


  <script>
    function toggleNav() {
      const hamburger = document.querySelector('.hamburger');
      const navLinks = document.getElementById('navLinks');
      hamburger.classList.toggle('active');
      navLinks.classList.toggle('active');
    }
  </script>

</body>
</html>
```

## Explanation

The code uses CSS Grid for flexible layout.  The `@media` query handles responsiveness.  The JavaScript function `toggleNav()` adds and removes the `active` class to control the visibility and animation of the hamburger menu and navigation links.  The CSS transitions create a smooth animation effect.


## Links to Resources to Learn More

* **CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* **CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **Responsive Web Design:** [https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

