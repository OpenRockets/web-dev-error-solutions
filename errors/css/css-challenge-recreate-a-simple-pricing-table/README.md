# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll use standard CSS3 for the styling, focusing on fundamental concepts like flexbox for layout and responsive design principles.  While Tailwind CSS could be used for faster development,  this example sticks to pure CSS3 to illustrate the core concepts.


## Description of the Styling

The pricing table will have three columns representing different pricing tiers: Basic, Pro, and Premium. Each tier will have a title, a list of features, a price, and a call-to-action button.  The styling will emphasize visual clarity and a modern aesthetic. We will aim for responsiveness, ensuring the table adapts well to different screen sizes.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Pricing Table</title>
<style>
body {
  font-family: sans-serif;
}

.pricing-table {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.pricing-column {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 20px;
  margin: 10px;
  width: 300px; /* Adjust as needed for responsiveness */
  box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
}

.pricing-column h2 {
  text-align: center;
  margin-bottom: 10px;
}

.pricing-column ul {
  list-style: none;
  padding: 0;
}

.pricing-column li {
  margin-bottom: 5px;
}

.pricing-column .price {
  font-size: 1.5em;
  font-weight: bold;
  text-align: center;
  margin-top: 10px;
  margin-bottom: 10px;
}

.pricing-column button {
  display: block;
  width: 100%;
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .pricing-column {
    width: 100%;
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="pricing-column">
    <h2>Basic</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
    </ul>
    <div class="price">$9.99/month</div>
    <button>Sign Up</button>
  </div>
  <div class="pricing-column">
    <h2>Pro</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
    </ul>
    <div class="price">$19.99/month</div>
    <button>Sign Up</button>
  </div>
  <div class="pricing-column">
    <h2>Premium</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
      <li>Feature 6</li>
    </ul>
    <div class="price">$29.99/month</div>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```


## Explanation

The code utilizes flexbox for easy horizontal arrangement and responsive adjustments.  The `pricing-table` div uses `flex-wrap: wrap` to allow columns to stack vertically on smaller screens. The `@media` query ensures the columns take up full width on smaller screens.  Each column is styled individually with borders, padding, and shadows for visual appeal.  The styling is straightforward and easy to customize further.


## Resources to Learn More

* **MDN Web Docs CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) – A comprehensive resource for all things CSS.
* **Flexbox Froggy:** [https://flexboxfroggy.com/](https://flexboxfroggy.com/) – A fun and interactive game to learn Flexbox.
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) – A blog and resource site with many articles on CSS techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

