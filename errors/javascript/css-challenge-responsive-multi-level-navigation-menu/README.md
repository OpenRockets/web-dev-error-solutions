# 🐞 CSS Challenge:  Responsive Multi-level Navigation Menu


This challenge involves creating a responsive multi-level navigation menu using CSS (specifically, we'll leverage CSS3 features).  The menu should adapt smoothly to different screen sizes, gracefully collapsing and expanding sub-menus as needed.  We'll aim for a clean, modern aesthetic.

**Description of the Styling:**

The navigation menu will be a horizontal list at larger screen sizes.  Upon shrinking the screen, the menu will become a hamburger menu, revealing the menu items and their sub-menus on click. Sub-menus will appear on hover at larger screen sizes and on click at smaller ones.  We'll use smooth transitions and animations to enhance the user experience.  The styling will include appropriate padding, margins, fonts, and colors for readability and visual appeal.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Multi-level Navigation</title>
<style>
body {
  font-family: sans-serif;
  margin: 0;
}

.nav {
  background-color: #333;
  overflow: hidden;
}

.nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav li {
  float: left;
}

.nav a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.nav a:hover {
  background-color: #ddd;
  color: black;
}

.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {background-color: #ddd;}

.dropdown:hover .dropdown-content {display: block;}

/* Responsive Styles */
@media screen and (max-width: 600px) {
  .nav li {
    float: none;
  }

  .nav a {
    display: block;
  }

  .dropdown-content {
    position: static;
  }

  .dropdown:hover .dropdown-content {
    display: none; /* Hide on hover at smaller screens */
  }
  .nav a.hamburger{
    display: block;
    padding: 10px 20px;
  }
  .nav ul{
    display: none;
  }
  .nav ul.active{
    display: block;
  }
}


</style>
</head>
<body>

<div class="nav">
  <ul>
    <li><a href="#">Home</a></li>
    <li class="dropdown">
      <a href="javascript:void(0)" class="dropbtn">Services</a>
      <div class="dropdown-content">
        <a href="#">Link 1</a>
        <a href="#">Link 2</a>
        <a href="#">Link 3</a>
      </div>
    </li>
    <li class="dropdown">
      <a href="javascript:void(0)" class="dropbtn">About</a>
      <div class="dropdown-content">
        <a href="#">Link 1</a>
        <a href="#">Link 2</a>
      </div>
    </li>
    <li><a href="#">Contact</a></li>
    <a href="javascript:void(0);" class="hamburger" onclick="myFunction()">&#9776;</a>
  </ul>
</div>

<script>
function myFunction() {
  var x = document.querySelector(".nav ul");
  if (x.className.indexOf("active") == -1) {
    x.className += " active";
  } else {
    x.className = x.className.replace(" active", "");
  }
}
</script>

</body>
</html>
```

**Explanation:**

The code utilizes CSS for styling and basic JavaScript for the hamburger menu functionality at smaller screen sizes.  The `@media` query handles responsive behavior.  The dropdown menus use absolute positioning for sub-menus. The Javascript function toggles the visibility of the navigation list on smaller screens using the `active` class.


**Links to Resources to Learn More:**

* **CSS3 Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Responsive Web Design:** [Responsive Web Design Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_design)
* **JavaScript Fundamentals:** [MDN Web Docs JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

