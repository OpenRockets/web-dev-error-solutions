# 🐞 CSS Challenge:  Responsive Navigation Bar with a Sticky Header


This challenge focuses on creating a responsive navigation bar that sticks to the top of the viewport on scroll. We'll use CSS Grid for layout and leverage media queries for responsiveness.  This example will utilize plain CSS3; adapting it to Tailwind CSS is a straightforward process, as described in the "Further Exploration" section.

**Description of the Styling:**

The navigation bar will consist of a logo on the left and a list of navigation links on the right.  On larger screens, the navigation items will be spaced evenly across the available width. On smaller screens, the navigation items will collapse into a hamburger menu that reveals the links on click.  The entire navigation bar will become sticky once the user scrolls past the top of the viewport.

**Full Code (CSS3):**

```css
/* Styling for the navigation bar */
nav {
  background-color: #333;
  color: white;
  display: grid;
  grid-template-columns: 1fr auto; /* Logo on the left, navigation on the right */
  align-items: center;
  padding: 1rem;
  position: relative; /* Required for sticky positioning */
}

nav h1 {
  margin: 0;
  font-size: 1.5rem;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex; /* Arrange links horizontally */
}

nav li {
  margin-left: 1rem;
}

nav a {
  text-decoration: none;
  color: white;
}

/* Media query for smaller screens - hides the navigation links and shows the hamburger menu */
@media (max-width: 768px) {
  nav ul {
    display: none;
  }

  nav .hamburger {
    display: block;
  }
}

/* Style the hamburger menu */
.hamburger {
  display: none;
  cursor: pointer;
  font-size: 1.5rem;
}

/* Styling for the navigation links when the hamburger menu is active */
.active-menu ul {
  display: block;
  background-color: #333;
  position: absolute;
  top: 100%;
  left: 0;
  width: 100%;
  flex-direction: column; /* Stack links vertically */
  padding: 1rem;
}

/* Sticky Navigation */
nav.sticky {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000; /* Ensure it's on top */
}

/* Basic HTML structure for the navigation bar (you'll need this in your HTML file) */
<nav>
  <h1>My Website</h1>
  <div class="hamburger">&#9776;</div>
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
  const ul = document.querySelector('ul');


  hamburger.addEventListener('click', () => {
    nav.classList.toggle('active-menu');
  })

  window.addEventListener('scroll', () => {
    if (window.scrollY > 0) {
      nav.classList.add('sticky');
    } else {
      nav.classList.remove('sticky');
    }
  });
</script>

```

**Explanation:**

The CSS uses `grid-template-columns` to arrange the logo and navigation links.  Media queries adjust the layout for smaller screens, hiding the navigation links and revealing a hamburger menu. JavaScript is used to toggle the visibility of the navigation links when the hamburger menu is clicked and the `sticky` class is added/removed based on scroll position to make the navigation bar sticky.

**Further Exploration:**

* **Tailwind CSS:**  This design is easily adaptable to Tailwind CSS. You would use Tailwind classes such as `bg-gray-800`, `text-white`, `grid grid-cols-[auto_1fr]`, `flex`, `justify-between`, `sticky top-0`, etc., replacing the custom CSS.  Explore the Tailwind CSS documentation ([https://tailwindcss.com/](https://tailwindcss.com/)) to learn how to translate the styles.
* **CSS Grid Layout:**  Learn more about CSS Grid at the MDN Web Docs ([https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)).
* **Responsive Web Design:** Familiarize yourself with responsive web design principles and media queries ([https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Media_queries](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Media_queries)).

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

