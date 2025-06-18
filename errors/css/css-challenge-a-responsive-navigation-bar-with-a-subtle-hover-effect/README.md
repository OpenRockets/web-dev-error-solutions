# 🐞 CSS Challenge:  A Responsive Navigation Bar with a Subtle Hover Effect


This challenge involves creating a responsive navigation bar using CSS (specifically, we'll utilize CSS3 properties for a smooth, modern feel).  The navigation bar should adapt smoothly to different screen sizes and feature a subtle hover effect on the menu items. We'll target a clean, minimalist aesthetic.

**Description of the Styling:**

The navigation bar will be positioned at the top of the page. It will have a dark background color and light-colored text.  On hover, the menu items will change background color slightly and the text will become bolder to provide clear visual feedback.  The responsiveness will ensure the navigation bar collapses into a hamburger menu icon on smaller screens.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Navigation Bar</title>
<style>
body {
  margin: 0;
  font-family: sans-serif;
}

nav {
  background-color: #333;
  overflow: hidden;
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  text-align: center;
}

nav li {
  display: inline-block;
  margin: 0 10px;
}

nav a {
  display: block;
  padding: 15px 20px;
  text-decoration: none;
  color: #fff;
}

nav a:hover {
  background-color: #555;
  font-weight: bold;
}

/* Responsive styles */
@media screen and (max-width: 600px) {
  nav ul {
    text-align: left;
  }
  nav li {
    display: block;
    margin: 0;
  }
  nav a {
      display: block;
      padding: 10px;
      text-align: left;
  }
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
</nav>

</body>
</html>
```

**Explanation:**

* **Basic Styling:**  We set up basic styles for the body, navigation bar (`nav`), unordered list (`ul`), list items (`li`), and links (`a`).  The `text-align: center;` centers the menu items on larger screens.
* **Hover Effect:** The `:hover` pseudo-class is used to style the links when the mouse hovers over them, changing the background color and font weight.
* **Responsive Design:** The `@media` query targets screens with a maximum width of 600 pixels. Inside this query, we change the display of list items to `block` to stack them vertically, creating a more mobile-friendly menu.


**Links to Resources to Learn More:**

* **CSS3 Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) -  A comprehensive resource for learning CSS.
* **Responsive Web Design Basics:** [Google Web Fundamentals](https://developers.google.com/web/fundamentals/design-and-ux/responsive/) - Learn about creating websites that adapt to different screen sizes.
* **CSS Selectors:** [Understanding CSS Selectors](https://www.w3schools.com/cssref/css_selectors.asp) -  Mastering CSS selectors is crucial for effective styling.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

