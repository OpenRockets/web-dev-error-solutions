# 🐞 CSS Challenge:  Responsive Pricing Table


This challenge involves creating a responsive pricing table using CSS.  The goal is to design a clean, visually appealing table that adapts seamlessly to different screen sizes. We'll use a combination of CSS Grid and media queries for responsiveness.  This example will use standard CSS3, but the concepts could easily be adapted to Tailwind CSS.


**Description of the Styling:**

The pricing table will have three columns representing different pricing plans (Basic, Premium, Elite). Each plan will have a title, a list of features, a price, and a call-to-action button. The design will utilize clean typography, subtle shadows, and a consistent color scheme to create a professional and user-friendly experience.  The table will be responsive, stacking vertically on smaller screens.

**Full Code:**

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
  padding: 20px;
}

.plan {
  border: 1px solid #ccc;
  padding: 20px;
  text-align: center;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
}

.plan h2 {
  margin-top: 0;
}

.plan ul {
  list-style: none;
  padding: 0;
}

.plan li {
  margin-bottom: 10px;
}

.plan .price {
  font-size: 1.5em;
  font-weight: bold;
  margin-bottom: 10px;
}

.plan button {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

/* Media query for smaller screens */
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
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
    </ul>
    <p class="price">$9/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Premium</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
    </ul>
    <p class="price">$19/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Elite</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
      <li>Feature 6</li>
    </ul>
    <p class="price">$29/month</p>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **CSS Grid:**  The `grid-template-columns` property creates a responsive grid layout. `repeat(auto-fit, minmax(300px, 1fr))` ensures that columns adjust based on screen size, fitting as many as possible with a minimum width of 300px.
* **Media Queries:** The `@media` query targets screens smaller than 768px, changing the grid to stack columns vertically for better mobile viewing.
* **Styling:**  The CSS styles the table elements (headings, lists, buttons, etc.) for visual appeal and consistency.


**Links to Resources to Learn More:**

* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **Learn CSS:** [https://www.freecodecamp.org/learn/responsive-web-design/](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

