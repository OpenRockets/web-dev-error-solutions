# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll utilize standard CSS (no framework like Tailwind is used for this example, to emphasize core CSS concepts), aiming for a visually appealing layout suitable for displaying different pricing plans.  The goal is to demonstrate mastery of flexbox and basic styling techniques.


## Styling Description

The pricing table will consist of three columns representing different pricing plans (Basic, Pro, Premium). Each column will contain the plan name, a list of features, the price, and a call-to-action button.  We will use a responsive design to ensure the table adapts gracefully to different screen sizes.  The overall style will be clean and modern, using a subtle color palette.


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

.plan {
  width: 300px;
  margin: 20px;
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 20px;
  text-align: center;
  box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
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
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

.plan button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  border-radius: 5px;
  cursor: pointer;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .plan {
    width: 100%;
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
    </ul>
    <p class="price">$9.99/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Pro</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
    </ul>
    <p class="price">$19.99/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Premium</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
      <li>Feature 4</li>
    </ul>
    <p class="price">$29.99/month</p>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```


## Explanation

The code utilizes flexbox for easy layout management.  The `.pricing-table` div uses `flex-wrap: wrap` to allow the columns to wrap onto multiple lines on smaller screens.  Individual plans are styled with consistent padding, borders, and shadows.  Media queries handle responsiveness, making the table adjust to different screen sizes. The CSS is well-commented to improve understanding.


## Links to Resources to Learn More

* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - Comprehensive resource for all things CSS.
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) -  A great website for CSS tutorials and articles.
* **FreeCodeCamp:** [https://www.freecodecamp.org/](https://www.freecodecamp.org/) - Offers interactive CSS learning paths.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

