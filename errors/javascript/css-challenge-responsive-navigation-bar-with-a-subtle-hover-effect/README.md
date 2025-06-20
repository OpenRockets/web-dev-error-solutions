# 🐞 CSS Challenge:  Responsive Navigation Bar with a Subtle Hover Effect


This challenge focuses on creating a responsive navigation bar using CSS (specifically CSS3) that features a subtle hover effect on the navigation links.  We'll achieve responsiveness using media queries, and the hover effect will be created using transitions and subtle background changes. This example avoids the use of JavaScript for simplicity.


## Styling Description

The navigation bar will be a horizontal bar fixed to the top of the viewport.  On larger screens, the navigation links will be displayed inline. On smaller screens (mobiles and tablets), the navigation links will collapse into a hamburger menu icon that expands when clicked. The hover effect will subtly change the background color of the links when the cursor hovers over them.


## Full Code


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
  transition: background-color 0.3s ease; /* Add transition for hover effect */
}

.navbar a:hover {
  background-color: #ddd;
  color: black;
}

.navbar a.icon {
  display: none; /* Hide icon on large screens */
}

@media screen and (max-width: 600px) {
  .navbar a:not(:first-child) {display: none;} /* Hide links on small screens */
  .navbar a.icon {
    float: right;
    display: block; /* Show icon on small screens */
  }
}

@media screen and (max-width: 600px) {
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
</style>
</head>
<body>

<div class="navbar" id="myNavbar">
  <a href="#home" class="active">Home</a>
  <a href="#about">About</a>
  <a href="#services">Services</a>
  <a href="#contact">Contact</a>
  <a href="javascript:void(0);" class="icon" onclick="myFunction()">
    <i class="fa fa-bars"></i> <!-- Replace with your hamburger icon -->
  </a>
</div>

<script>
function myFunction() {
  var x = document.getElementById("myNavbar");
  if (x.className === "navbar") {
    x.className += " responsive";
  } else {
    x.className = "navbar";
  }
}
</script>

</body>
</html>
```

## Explanation

* **Basic Styling:** The CSS sets up the basic structure of the navbar, including background color, text color, padding, and hover effects. The `transition` property is crucial for the smooth hover effect.

* **Responsiveness:** Media queries (`@media screen and (max-width: 600px)`) are used to control the layout based on screen size.  On smaller screens, the navigation links are hidden, and a hamburger menu icon is displayed.

* **Hamburger Menu:** The JavaScript function `myFunction()` toggles the `responsive` class on the navbar, which uses CSS to reposition the links vertically when the screen size is small.  Remember to replace `<i class="fa fa-bars"></i>` with actual hamburger menu icon HTML or an image.  You would typically use a font icon library like Font Awesome for this.


## Resources to Learn More

* **CSS3 Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  (A comprehensive resource for learning CSS)
* **Media Queries:** [MDN Web Docs Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) (Learn how to make your websites responsive)
* **CSS Transitions:** [MDN Web Docs CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) (Understand how to create smooth animations with CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

