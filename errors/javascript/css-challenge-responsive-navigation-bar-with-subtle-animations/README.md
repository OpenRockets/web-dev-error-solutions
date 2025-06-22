# 🐞 CSS Challenge:  Responsive Navigation Bar with Subtle Animations


This challenge focuses on creating a responsive navigation bar using CSS (specifically CSS3) that features subtle animation on hover and a smooth transition on smaller screens.  We'll build this without a CSS framework like Tailwind, focusing on core CSS principles.

## Description of the Styling

The navigation bar will be positioned at the top of the page. It will contain a logo on the left and several navigation links on the right.  On larger screens, the links will be displayed inline.  On smaller screens (below a defined breakpoint), the links will be hidden behind a hamburger menu icon. Clicking the icon will toggle the visibility of the links with a smooth slide-down animation.  Each navigation link will have a subtle background highlight on hover.

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
  font-size: 24px;
  font-weight: bold;
}

.nav-links {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.nav-links li {
  margin-left: 20px;
}

.nav-links a {
  text-decoration: none;
  color: white;
  padding: 10px;
  transition: background-color 0.3s ease;
}

.nav-links a:hover {
  background-color: #555;
}

/* Responsive Styles */
@media (max-width: 768px) {
  .nav-links {
    display: none;
    flex-direction: column;
    position: absolute;
    top: 50px;
    left: 0;
    width: 100%;
    background-color: #333;
  }

  .nav-links.active {
    display: flex;
    animation: slideDown 0.3s ease-in-out;
  }

  .nav-links li {
    margin-left: 0;
    width: 100%;
  }

  .nav-links a {
    width: 100%;
    text-align: center;
  }

  .toggle-button {
    display: block;
    cursor: pointer;
  }

  .toggle-button i {
    font-size: 24px;
  }
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
</head>
<body>
<nav>
  <div class="logo">My Logo</div>
  <div class="toggle-button" onclick="toggleNav()">
    <i class="fas fa-bars"></i>
  </div>
  <ul class="nav-links">
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Services</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

<script>
  function toggleNav() {
    document.querySelector('.nav-links').classList.toggle('active');
  }
</script>

</body>
</html>
```

Remember to include Font Awesome for the hamburger icon (`<i class="fas fa-bars"></i>`).  You can link to it via a CDN.  For example:

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" integrity="sha512-9usAa10IRO0HhonpyAIVpjrylPvoDwiPUiKdWk5t3PyolY1cOd4DSE0Ga+ri4AuTroPR5aQvXU9xC6qOPnzFeg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
```


## Explanation

The code uses media queries (`@media`) to adjust the layout based on screen size.  For smaller screens, the navigation links are hidden by default and shown using JavaScript. The `toggleClass` function adds and removes the `active` class, triggering the `slideDown` animation.  The hover effect is achieved using the `transition` property.


## Links to Resources to Learn More

* **CSS3 Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Responsive Web Design:** [Google Web Fundamentals](https://developers.google.com/web/fundamentals/design-and-ux/responsive/)
* **CSS Animations:** [CSS-Tricks Animations](https://css-tricks.com/almanac/properties/a/)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

