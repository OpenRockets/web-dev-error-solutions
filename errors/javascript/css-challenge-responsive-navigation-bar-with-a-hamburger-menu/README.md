# 🐞 CSS Challenge:  Responsive Navigation Bar with a Hamburger Menu


This challenge involves creating a responsive navigation bar that adapts to different screen sizes using CSS.  For smaller screens, it will collapse into a hamburger menu icon that reveals the navigation links when clicked. We'll use plain CSS (no Tailwind or other frameworks) for this example, to keep the core concepts clear.


**Description of the Styling:**

The navigation bar will contain a logo on the left and a list of navigation links on the right.  On larger screens (e.g., above 768px), the logo and links will be displayed inline.  On smaller screens, the links will be hidden by default and revealed when the hamburger menu icon is clicked.  The styling will include appropriate padding, margins, and colors to ensure a visually appealing design.  The hamburger menu will be implemented using a simple checkbox and associated CSS.

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

.navbar {
  background-color: #333;
  overflow: hidden;
}

.navbar a {
  float: left;
  display: block;
  color: white;
  text-align: center;
  padding: 14px 20px;
  text-decoration: none;
}

.navbar a:hover {
  background-color: #ddd;
  color: black;
}

.navbar .icon {
  display: none;
}

.navbar .icon:hover {
    cursor: pointer;
}

@media screen and (max-width: 768px) {
  .navbar a:not(:first-child) {display: none;}
  .navbar a.icon {
    float: right;
    display: block;
  }
}

@media screen and (max-width: 768px) {
  .navbar.responsive {position: relative;}
  .navbar.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .navbar.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}


/* Add styles for the checked input to show the menu */
input[type="checkbox"]:checked ~ .navbar a {
    display: block;
}
</style>
</head>
<body>

<div class="navbar">
    <a href="#home">Logo</a>
  <input type="checkbox" id="check">
  <label for="check" class="icon">&#9776;</label>
  <a href="#news">News</a>
  <a href="#contact">Contact</a>
  <a href="#about">About</a>
</div>

<script>
    const checkbox = document.getElementById('check');
    checkbox.addEventListener('change', function() {
        document.querySelector('.navbar').classList.toggle('responsive');
    });
</script>

</body>
</html>
```

**Explanation:**

* **HTML Structure:**  A simple `<nav>` element contains the logo and links.  A checkbox is used as a toggle for the hamburger menu.
* **CSS for Large Screens:**  The `float: left` property aligns the logo and links horizontally.
* **CSS for Small Screens:**  Media queries are used to hide the links and show the hamburger icon (`.icon`) on smaller screens.  The `display: none` and `display: block` properties control the visibility of elements. The `responsive` class is toggled using Javascript when the checkbox is clicked.
* **Javascript:**  A small script toggles the `responsive` class on the navbar when the checkbox state changes, revealing/hiding the menu items.  This is optional, you could implement this purely with CSS using the `:target` pseudo-class, but Javascript offers more flexibility.

**Links to Resources to Learn More:**

* **CSS Media Queries:** [MDN Web Docs - Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Floats:** [MDN Web Docs - CSS Floats](https://developer.mozilla.org/en-US/docs/Web/CSS/float)
* **CSS Display Property:** [MDN Web Docs - CSS Display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

