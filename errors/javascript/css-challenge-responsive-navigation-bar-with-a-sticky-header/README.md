# 🐞 CSS Challenge:  Responsive Navigation Bar with a Sticky Header


This challenge involves creating a responsive navigation bar that sticks to the top of the viewport when the user scrolls down.  We'll use CSS (specifically CSS3) for styling and layout.  No JavaScript will be required.


## Description of the Styling

The navigation bar should be:

* **Visually Appealing:**  Clean design, easy to read, and uses consistent spacing.
* **Responsive:** Adapts seamlessly to different screen sizes (desktops, tablets, and mobile phones).
* **Sticky:** Remains fixed at the top of the viewport once the user scrolls past its initial position.
* **Concise:** Uses efficient CSS for minimal code.

The navigation bar will contain a logo on the left, a list of navigation items in the center, and a button on the right (e.g., "Sign In").  On smaller screens, the navigation items will collapse into a hamburger menu.


## Full Code

```css
/* Basic Styles */
body {
  margin: 0;
  font-family: sans-serif;
}

nav {
  background-color: #333;
  color: #fff;
  padding: 1rem 0;
  position: relative; /* Important for sticky position */
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-logo {
  font-size: 1.5rem;
  font-weight: bold;
}

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
}

.nav-item {
  margin: 0 1rem;
}

.nav-link {
  text-decoration: none;
  color: #fff;
}

.nav-button {
  background-color: #007bff;
  color: #fff;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}


/* Responsive Styles */
@media (max-width: 768px) {
  .nav-list {
    display: none; /* Hide the nav list on smaller screens */
  }

  .nav-toggle {
    display: block; /* Show the hamburger menu button */
  }

  .nav-list.active {
    display: flex;
    flex-direction: column; /* Stack items vertically */
    position: absolute;
    top: 100%;
    left: 0;
    background-color: #333;
    width: 100%;
  }

  .nav-item {
    margin: 0.5rem;
  }

}

/* Sticky Header */
nav.sticky {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 1000; /* Ensure it's on top */
}

/*Add this to show the hamburger icon, you can use any icon library of your choice*/
.nav-toggle {
  display: none;
  cursor: pointer;
}

.nav-toggle span {
  display: block;
  width: 25px;
  height: 3px;
  margin: 5px 0;
  background-color: white;
}

/*Example HTML Structure (you need to adapt this to your project)*/
<nav id="myNav" class="nav">
  <div class="nav-container">
    <div class="nav-logo">My Logo</div>
    <div class="nav-toggle">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <ul class="nav-list">
      <li class="nav-item"><a href="#" class="nav-link">Home</a></li>
      <li class="nav-item"><a href="#" class="nav-link">About</a></li>
      <li class="nav-item"><a href="#" class="nav-link">Services</a></li>
      <li class="nav-item"><a href="#" class="nav-link">Contact</a></li>
    </ul>
    <button class="nav-button">Sign In</button>
  </div>
</nav>

<script>
  const nav = document.getElementById('myNav');
  const toggle = document.querySelector('.nav-toggle');
  const navList = document.querySelector('.nav-list');

  window.addEventListener('scroll', () => {
    if (window.scrollY > 0) {
      nav.classList.add('sticky');
    } else {
      nav.classList.remove('sticky');
    }
  });

  toggle.addEventListener('click', () => {
    navList.classList.toggle('active');
  })
</script>
```


## Explanation

The CSS is divided into sections:

* **Basic Styles:**  Sets up the basic layout, colors, and fonts.
* **Responsive Styles:** Uses media queries (`@media (max-width: 768px)`) to adjust the layout for smaller screens. The navigation list is hidden and a hamburger menu is shown.
* **Sticky Header:**  Uses `position: fixed` to make the navigation bar stick to the top after scrolling past it. `z-index` ensures that it's displayed above other content.
* **Javascript:** This simple script adds sticky functionality and makes the hamburger menu work.  You'll need to add this to your HTML for the code to work correctly.


## Links to Resources to Learn More

* **MDN Web Docs CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/)
* **FreeCodeCamp Responsive Web Design Certification:** [https://www.freecodecamp.org/learn/responsive-web-design/](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

