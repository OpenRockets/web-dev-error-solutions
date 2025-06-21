# 🐞 CSS Challenge:  Responsive Pricing Table


This challenge focuses on creating a responsive pricing table using CSS. We'll aim for a clean, modern design that adapts well to different screen sizes.  This example uses plain CSS;  a Tailwind CSS version could be created with similar structure but using Tailwind's utility classes.


## Description of the Styling

The pricing table will feature three plans (Basic, Pro, and Premium) each with a title, a list of features, a price, and a call-to-action button.  The design will emphasize clear visual separation between plans, using cards or similar structures.  Responsiveness will be key, ensuring the table gracefully adapts from desktop to mobile views.


## Full Code (CSS)

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
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.plan {
  width: 300px;
  margin: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
  overflow: hidden;
}

.plan-header {
  background-color: #f0f0f0;
  padding: 20px;
  text-align: center;
}

.plan-title {
  font-size: 1.2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.plan-price {
  font-size: 1.5em;
  font-weight: bold;
  color: #333;
  margin-bottom: 20px;
}

.plan-features {
  padding: 20px;
  list-style: none;
}

.plan-features li {
  margin-bottom: 10px;
}

.plan-button {
  background-color: #4CAF50;
  color: white;
  padding: 15px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 1em;
  border-radius: 5px;
  margin: 20px 0;
  width: 100%;
  box-sizing: border-box; /* Include padding and border in element's total width and height */
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .plan {
    width: calc(50% - 40px); /* Adjust width for smaller screens */
  }
}

@media (max-width: 480px) {
  .plan {
    width: calc(100% - 40px); /* Full width on smaller screens */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="plan">
    <div class="plan-header">
      <h2 class="plan-title">Basic</h2>
      <p class="plan-price">$9.99/month</p>
    </div>
    <ul class="plan-features">
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
    </ul>
    <a href="#" class="plan-button">Sign Up</a>
  </div>
  <div class="plan">
    <div class="plan-header">
      <h2 class="plan-title">Pro</h2>
      <p class="plan-price">$29.99/month</p>
    </div>
    <ul class="plan-features">
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
    </ul>
    <a href="#" class="plan-button">Sign Up</a>
  </div>
  <div class="plan">
    <div class="plan-header">
      <h2 class="plan-title">Premium</h2>
      <p class="plan-price">$49.99/month</p>
    </div>
    <ul class="plan-features">
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
      <li>Feature 5</li>
      <li>Feature 6</li>
    </ul>
    <a href="#" class="plan-button">Sign Up</a>
  </div>
</div>

</body>
</html>
```

## Explanation

The CSS uses flexbox for layout, making it easy to arrange the plans horizontally and wrap them to new lines on smaller screens. Media queries handle responsiveness, adjusting the width of the plans based on screen size.  The styling emphasizes clear visual hierarchy and readability.


## Links to Resources to Learn More

* **CSS Flexbox:** [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Grid Layout (Alternative):** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

