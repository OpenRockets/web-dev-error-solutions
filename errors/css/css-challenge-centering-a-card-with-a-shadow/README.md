# 🐞 CSS Challenge:  Centering a Card with a Shadow


This challenge focuses on creating a visually appealing card element that is perfectly centered both horizontally and vertically on the page, and includes a subtle box shadow for depth. We'll use CSS Grid for layout simplicity.


**Description of the Styling:**

The goal is to create a card with a light gray background, rounded corners, some padding, a subtle drop shadow, and centered text.  The card itself should be centered on the page, regardless of the viewport size.


**Full Code (CSS only):**

```css
body {
  height: 100vh;
  margin: 0;
  display: grid;
  place-items: center; /* Centers the card both horizontally and vertically */
  background-color: #f4f4f4; /* Light gray background */
}

.card {
  background-color: #fff; /* White card background */
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1); /* Subtle drop shadow */
  padding: 20px;
  text-align: center; /* Center text within the card */
  width: 300px; /* Adjust width as needed */
}

.card h2 {
  margin-bottom: 10px;
}

.card p {
  color: #555; /* Slightly darker gray text */
}
```

**HTML (Example):**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Centered Card</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="card">
    <h2>My Card Title</h2>
    <p>This is some example text for my card.  It's centered both horizontally and vertically on the page.</p>
  </div>
</body>
</html>
```


**Explanation:**

* **`body { display: grid; place-items: center; }`**: This is the key to centering the card.  Setting the `body` to a grid and using `place-items: center;` automatically centers its single child element (the card) both horizontally and vertically.
* **`.card { ... }`**: This styles the card itself with background color, rounded corners (`border-radius`), a box shadow (`box-shadow`), padding, and text alignment.
* **`box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);`**: This creates a subtle drop shadow. The values represent horizontal offset, vertical offset, blur radius, and color respectively.  Adjust these values to change the shadow's appearance.
* **`width: 300px;`**: This sets a fixed width for the card. You can remove this for a more responsive design or adjust it as needed.


**Links to Resources to Learn More:**

* **CSS Grid Layout:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Box Shadow:** [MDN Web Docs - box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)
* **CSS Positioning:** [MDN Web Docs - CSS Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/position)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

