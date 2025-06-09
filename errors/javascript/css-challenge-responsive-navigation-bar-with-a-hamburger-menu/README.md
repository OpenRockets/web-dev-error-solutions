# 🐞 CSS Challenge: Responsive Navigation Bar with a Hamburger Menu


This challenge involves creating a responsive navigation bar that adapts to different screen sizes using CSS.  For smaller screens, it will utilize a hamburger menu icon to toggle the visibility of the navigation links.  We'll implement this using pure CSS (no JavaScript).

## Description of the Styling

The navigation bar will have a fixed position at the top of the viewport.  On larger screens (e.g., above 768px), the navigation links will be displayed inline.  On smaller screens, the links will be hidden by default and will be revealed when the hamburger menu is clicked. The hamburger icon itself will be a simple set of three horizontal lines that transform into an "X" upon clicking.  We'll use CSS transitions for smooth animations.

## Full Code (CSS Only)

```css
/* Styles for larger screens */
@media (min-width: 768px) {
  nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background-color: #333;
    padding: 10px 0;
  }

  nav ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
  }

  nav li {
    margin: 0 10px;
  }

  nav a {
    text-decoration: none;
    color: #fff;
    font-weight: bold;
  }
}

/* Styles for smaller screens */
@media (max-width: 768px) {
  nav {
    background-color: #333;
    padding: 10px;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000; /* Ensure it's on top */
  }

  nav ul {
    display: none;
    flex-direction: column;
    text-align: center;
  }

  nav ul li {
    margin: 10px 0;
  }

  .hamburger {
    display: block;
    cursor: pointer;
    width: 30px;
    height: 30px;
    position: relative;
    z-index: 1001;
    margin-right: 10px;
  }

  .hamburger span {
    display: block;
    width: 100%;
    height: 4px;
    background-color: white;
    margin: 5px 0;
    transition: transform 0.3s ease;
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

  nav.active ul {
    display: flex;
  }
}

/*Apply CSS to the body*/
body {
  margin: 0;
}
```

## HTML Structure (Example)

You would need to include this within your HTML file:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Responsive Navigation Bar</title>
  <link rel="stylesheet" href="style.css">
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
    const hamburger = document.querySelector('.hamburger');
    const nav = document.querySelector('nav');

    hamburger.addEventListener('click', () => {
      hamburger.classList.toggle('active');
      nav.classList.toggle('active');
    });
  </script>
</body>
</html>

```

## Explanation

The CSS uses media queries to apply different styles based on screen size.  The hamburger menu is created using three `span` elements styled to look like lines.  The JavaScript (included in the HTML example above) toggles the `active` class on both the hamburger and the navigation, causing the lines to transform and the navigation to appear/disappear.  The `z-index` property ensures the navigation stays on top of other elements.


## Resources to Learn More

* **MDN Web Docs:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - Comprehensive CSS documentation.
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) - A great resource for CSS tutorials and articles.
* **freeCodeCamp:** [https://www.freecodecamp.org/](https://www.freecodecamp.org/) - Offers interactive CSS courses.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

