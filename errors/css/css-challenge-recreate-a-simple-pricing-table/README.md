# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll use plain CSS (no frameworks like Tailwind) to emphasize fundamental CSS concepts. The goal is to build a table with three pricing plans: Basic, Pro, and Premium, each showcasing different features and prices.  The design should be visually appealing and easily adaptable to different screen sizes.


## Styling Description

The pricing table will have a clean, modern look. Each plan will be contained within a separate card with a distinct background color.  The table will be responsive, adjusting its layout seamlessly for various screen sizes.  We'll use clear typography and consistent spacing to improve readability.


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

.pricing-card {
  width: 300px;
  margin: 20px;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.pricing-card.basic {
  background-color: #f0f0f0;
}

.pricing-card.pro {
  background-color: #e0f7fa;
}

.pricing-card.premium {
  background-color: #e0f2f7;
}

.pricing-card h2 {
  margin-top: 0;
}

.pricing-card ul {
  list-style: none;
  padding: 0;
}

.pricing-card li {
  margin-bottom: 10px;
}

.pricing-card .price {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 10px;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .pricing-card {
    width: calc(50% - 40px);
  }
}

@media (max-width: 480px) {
  .pricing-card {
    width: calc(100% - 40px);
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="pricing-card basic">
    <h2>Basic</h2>
    <p class="price">$9.99/month</p>
    <ul>
      <li>10GB Storage</li>
      <li>Basic Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-card pro">
    <h2>Pro</h2>
    <p class="price">$19.99/month</p>
    <ul>
      <li>50GB Storage</li>
      <li>Priority Support</li>
      <li>Advanced Features</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-card premium">
    <h2>Premium</h2>
    <p class="price">$49.99/month</p>
    <ul>
      <li>Unlimited Storage</li>
      <li>Dedicated Support</li>
      <li>All Features</li>
    </ul>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```


## Explanation

The code utilizes flexbox for easy layout management. The `pricing-table` div uses `flex-wrap: wrap` to handle different screen sizes, and media queries further refine the layout for smaller screens.  Each pricing card is styled individually using classes, allowing for customized colors and content.  The use of semantic HTML elements enhances accessibility.


## Resources to Learn More

* **MDN Web Docs CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  - Comprehensive guide to CSS.
* **Flexbox Froggy:** [https://flexboxfroggy.com/](https://flexboxfroggy.com/) - Interactive game to learn Flexbox.
* **CSS-Tricks:** [https://css-tricks.com/](https://css-tricks.com/) - Articles and tutorials on various CSS techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

