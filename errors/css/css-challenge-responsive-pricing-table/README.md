# 🐞 CSS Challenge: Responsive Pricing Table


This challenge focuses on creating a responsive pricing table using CSS.  We'll build a table with three pricing tiers (Basic, Pro, and Premium), each displaying different features and prices. The table should be responsive, adapting gracefully to different screen sizes.  We'll use plain CSS for this example, avoiding any CSS frameworks like Tailwind.

**Description of the Styling:**

The pricing table will be styled with a clean, modern look.  Each pricing tier will be contained within a card-like structure with a clear heading, a list of features, and a prominent price.  We'll use subtle gradients and shadows to add visual appeal.  The table will be horizontally centered and will adapt to smaller screens by stacking the pricing tiers vertically.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Pricing Table</title>
<style>
body {
  font-family: sans-serif;
  background-color: #f4f4f4;
}

.pricing-table {
  display: flex;
  justify-content: center;
  flex-wrap: wrap; /* Allow wrapping on smaller screens */
}

.pricing-card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  margin: 20px;
  padding: 20px;
  width: 300px; /* Adjust as needed */
  min-height: 350px;
  text-align: center;
}

.pricing-card h2 {
  color: #333;
  margin-bottom: 10px;
}

.pricing-card ul {
  list-style: none;
  padding: 0;
}

.pricing-card li {
  margin-bottom: 5px;
}

.pricing-card .price {
  font-size: 24px;
  font-weight: bold;
  color: #007bff;
  margin-bottom: 15px;
}

/* Media query for smaller screens */
@media (max-width: 768px) {
  .pricing-card {
    width: 100%;
    margin-bottom: 20px;
  }
  .pricing-table {
      flex-direction: column; /* Stack cards vertically */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="pricing-card">
    <h2>Basic</h2>
    <p class="price">$9/month</p>
    <ul>
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Basic Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-card">
    <h2>Pro</h2>
    <p class="price">$29/month</p>
    <ul>
      <li>100GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-card">
    <h2>Premium</h2>
    <p class="price">$99/month</p>
    <ul>
      <li>Unlimited Storage</li>
      <li>10 Users</li>
      <li>Dedicated Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```


**Explanation:**

The code uses flexbox for layout. The `.pricing-table` div uses `flex-wrap: wrap` to allow the cards to wrap onto multiple lines on larger screens.  The `@media` query adjusts the layout for smaller screens, setting `flex-direction: column` to stack the cards vertically.  Individual pricing cards are styled with borders, shadows, and padding to create a visually appealing effect.

**Links to Resources to Learn More:**

* **CSS Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **CSS Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Grid (alternative layout method):** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

