# 🐞 CSS Challenge: Responsive Multi-level Nested Navigation Menu


This challenge focuses on creating a responsive, multi-level nested navigation menu using CSS.  The goal is to build a menu that gracefully collapses and expands its sub-menus on smaller screens, offering a clean and intuitive user experience.  We'll utilize standard CSS for this implementation, avoiding any CSS frameworks like Tailwind CSS to emphasize fundamental CSS principles.

## Description of the Styling

The navigation menu will consist of a main navigation bar containing several top-level menu items. Each top-level item can have multiple sub-items, creating a nested structure.  The styling should include:

* **Top-Level Menu:**  A horizontal list of menu items with clear visual separation between them.
* **Sub-Menus:**  Sub-menus should appear on hover (or click on smaller screens) and be visually distinct from the top-level menu.
* **Responsiveness:**  The menu should adapt to different screen sizes, collapsing sub-menus on smaller screens to avoid cluttering the interface.  A hamburger menu icon will be used for smaller screen sizes to toggle the visibility of the menu.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Nested Navigation Menu</title>
<style>
nav {
  background-color: #333;
  overflow: hidden;
}

nav ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

nav li {
  float: left;
}

nav li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

nav li a:hover {
  background-color: #ddd;
  color: black;
}

nav li ul {
  display: none; /* Initially hide sub-menus */
  position: absolute; /* Position sub-menus absolutely */
  background-color: #333;
}

nav li:hover > ul {
  display: block; /* Show sub-menu on hover */
}

/* Responsiveness */
@media screen and (max-width: 600px) {
  nav li {
    float: none; /* Stack menu items vertically */
  }
  nav li ul {
    position: static; /* No longer need absolute positioning */
  }
  nav li:hover > ul { /* Remove hover effect on small screens */
    display: none;
  }
    nav ul{
        display:none;
    }
    nav #menuToggle{
        display:block;
        width:30px;
        height:30px;
        cursor:pointer;
        position:relative;
        background-color:transparent;
        border:none;
    }
    #menuToggle input{
        display:block;
        width:40px;
        height:32px;
        position:absolute;
        top: -7px;
        left: -5px;
        cursor:pointer;
        opacity:0; /* hide this */
    }
    #menuToggle span{
        display:block;
        width: 30px;
        height: 4px;
        margin-bottom: 5px;
        position: relative;
        background: #fff;
        border-radius: 3px;
        z-index: 1;
        transform: rotate(0);
        transition: .25s ease-in-out;
    }
    #menuToggle span:nth-child(2){
        margin-top: -5px;
        width: 20px;
        margin-left: 5px;
    }
    #menuToggle input:checked ~ span{
        transform:rotate(45deg);
        background: #2980b9;
    }
    #menuToggle input:checked ~ span:nth-child(2){
        transform:rotate(-45deg);
        background: #2980b9;
        margin-left: 0px;
    }
    #menuToggle input:checked ~ ul{
        display:block;
    }
}
</style>
</head>
<body>

<nav>
  <input type="checkbox" id="menuToggle">
  <label for="menuToggle"><span></span><span></span><span></span></label>

  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a>
      <ul>
        <li><a href="#">Our Team</a></li>
        <li><a href="#">History</a></li>
      </ul>
    </li>
    <li><a href="#">Services</a>
        <ul>
            <li><a href="#">Service 1</a></li>
            <li><a href="#">Service 2</a></li>
            <li><a href="#">Service 3</a></li>
        </ul>
    </li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>

</body>
</html>
```

## Explanation

The CSS uses a combination of `float`, `position: absolute`, and media queries to achieve the desired effect.  The `display: none` property initially hides the sub-menus. The `:hover` pseudo-class shows the sub-menus when the parent list item is hovered over. Media queries adjust the layout for smaller screens, stacking the menu items vertically and removing the hover effect, thus employing a checkbox for toggling visibility.


## Links to Resources to Learn More

* **MDN Web Docs - CSS Selectors:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)
* **MDN Web Docs - CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* **MDN Web Docs - Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

