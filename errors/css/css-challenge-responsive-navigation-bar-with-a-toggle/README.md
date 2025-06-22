# 🐞 CSS Challenge:  Responsive Navigation Bar with a Toggle


This challenge focuses on creating a responsive navigation bar that adapts to different screen sizes.  We'll utilize CSS Grid for layout and a checkbox-based toggle for the mobile menu.  This example uses plain CSS; adapting it to Tailwind CSS is straightforward and will be briefly discussed.


**Description of the Styling:**

The navigation bar will consist of a logo on the left, a list of navigation links in the center, and a hamburger menu icon (toggle) on the right for smaller screens. On larger screens, all elements will be displayed inline. When the screen size reduces, the navigation links will be hidden and only the toggle will be visible. Clicking the toggle will reveal the navigation links.


**Full Code (CSS):**

```css
body {
  font-family: sans-serif;
  margin: 0;
}

nav {
  display: grid;
  grid-template-columns: auto 1fr auto; /* Logo, Nav Links, Toggle */
  background-color: #333;
  color: white;
  padding: 1rem;
}

.logo {
  font-size: 1.5rem;
  font-weight: bold;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex; /* Arrange links horizontally */
  justify-content: center; /* Center the links */
}

li {
  margin: 0 1rem;
}

a {
  text-decoration: none;
  color: white;
}

#toggle {
  display: none; /* Hidden on larger screens */
}

#toggle:checked ~ ul {
  display: block; /* Show navigation when checked */
}

#toggle:checked ~ label {
    display: none;
}

#toggle + label {
  display: block; /* Show toggle on smaller screens */
  cursor: pointer;
  padding: 0.5rem;
}

#toggle + label:before {
  content: '\2630'; /* Hamburger icon */
  font-size: 1.5rem;
}

@media (max-width: 768px) {
  nav {
    grid-template-columns: auto auto; /* Logo and Toggle */
  }
  ul {
    display: none; /* Hide navigation links on small screens */
    flex-direction: column; /* Stack links vertically */
  }
  #toggle {
    display: block;
  }
}
```

**HTML Structure (required to accompany the CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
  <nav>
    <div class="logo">My Website</div>
    <input type="checkbox" id="toggle">
    <label for="toggle"></label>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</body>
</html>

```


**Explanation:**

The CSS uses `grid-template-columns` to position the logo, navigation links, and toggle.  Media queries handle the responsive behavior.  A checkbox (`#toggle`) acts as the toggle switch; its checked state controls the visibility of the navigation links. The label is styled to represent the hamburger icon.


**Adapting to Tailwind CSS:**

Tailwind's utility classes make this even simpler. You would replace the CSS with Tailwind classes like `grid grid-cols-[auto_1fr_auto]`, `bg-gray-800 text-white p-4`, `hidden md:block`, and so on.  The core logic of the checkbox toggle remains the same.


**Links to Resources to Learn More:**

* **CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* **CSS Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **Tailwind CSS:** [https://tailwindcss.com/](https://tailwindcss.com/)



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

