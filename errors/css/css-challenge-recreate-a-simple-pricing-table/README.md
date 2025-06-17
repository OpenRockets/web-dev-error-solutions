# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS. We'll use standard CSS (no Tailwind) to achieve this, demonstrating fundamental CSS layout and styling techniques. The goal is to build a table with three pricing plans, each clearly displaying its features, price, and a call-to-action button.  The table should be responsive, adapting gracefully to different screen sizes.


**Description of the Styling:**

The pricing table will consist of a container element holding three individual plan boxes. Each plan box will have a header with the plan name, a list of features, the price, and a button. We'll use flexbox for layout and ensure clear visual separation between plans with appropriate padding and borders.  A subtle gradient background will add visual interest.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Pricing Table</title>
<style>
body {
  font-family: sans-serif;
  background-color: #f4f4f4;
}

.pricing-table {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 20px;
  padding: 20px;
}

.plan {
  background: linear-gradient(to bottom, #e6f7ff, #ffffff);
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  width: 300px;
  padding: 20px;
  text-align: center;
  margin-bottom:20px;
}

.plan h2 {
  color: #333;
  margin-bottom: 10px;
}

.plan ul {
  list-style: none;
  padding: 0;
}

.plan li {
  margin-bottom: 5px;
}

.plan .price {
  font-size: 24px;
  font-weight: bold;
  color: #28a745;
  margin-bottom: 10px;
}

.plan button {
  background-color: #28a745;
  color: white;
  border: none;
  padding: 10px 20px;
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
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Email Support</li>
    </ul>
    <p class="price">$9/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Premium</h2>
    <ul>
      <li>50GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
    <p class="price">$49/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Enterprise</h2>
    <ul>
      <li>Unlimited Storage</li>
      <li>Unlimited Users</li>
      <li>Dedicated Support</li>
    </ul>
    <p class="price">$99/month</p>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```


**Explanation:**

The code utilizes flexbox for easy horizontal and vertical arrangement of the pricing plans.  Media queries are included to ensure responsiveness, making the table adapt to smaller screens by stacking the plans vertically.  Classes are used for clear styling separation, making the code maintainable and readable.


**Links to Resources to Learn More:**

* **CSS Flexbox:** [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Grid Layout (Alternative Layout):** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

