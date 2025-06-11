# 🐞 CSS Challenge: Responsive Pricing Table


This challenge focuses on creating a responsive pricing table using CSS.  The goal is to build a clean, visually appealing table that adapts seamlessly to different screen sizes. We'll use plain CSS for this example to focus on fundamental layout techniques.


## Description of the Styling

The pricing table will consist of three columns representing different pricing plans (e.g., Basic, Pro, Premium). Each plan will have a title, a price, and a list of features.  The table should be centered horizontally on the page and have clear visual separation between plans.  Responsive design is key – on smaller screens, the table should stack vertically to avoid horizontal scrolling.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Pricing Table</title>
<style>
body {
  font-family: sans-serif;
}

.pricing-table {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive columns */
  grid-gap: 20px;
  text-align: center;
  margin: 20px auto; /* Center the table */
}

.plan {
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
}

.plan h2 {
  margin-top: 0;
}

.plan .price {
  font-size: 2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.plan ul {
  list-style: none;
  padding: 0;
}

.plan li {
  margin-bottom: 5px;
}


/* Media Query for smaller screens */
@media (max-width: 768px) {
  .pricing-table {
    grid-template-columns: 1fr; /* Stack columns vertically */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="plan">
    <h2>Basic</h2>
    <p class="price">$9.99/month</p>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
    </ul>
  </div>
  <div class="plan">
    <h2>Pro</h2>
    <p class="price">$29.99/month</p>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
    </ul>
  </div>
  <div class="plan">
    <h2>Premium</h2>
    <p class="price">$49.99/month</p>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
      <li>Feature 6</li>
    </ul>
  </div>
</div>

</body>
</html>
```


## Explanation

The code uses CSS Grid for layout.  `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));` creates responsive columns.  `auto-fit` ensures columns adjust to the available space, while `minmax(300px, 1fr)` sets a minimum column width of 300px and allows them to grow proportionally to fill the available space. The media query adjusts the layout for smaller screens, stacking the columns vertically.  Styling is added for visual appeal, including borders, shadows, and consistent font sizes.


## Links to Resources to Learn More

* **CSS Grid Layout:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries)
* **Learn CSS:** [freeCodeCamp - Responsive Web Design](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

