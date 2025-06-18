# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS. We'll build a table with three pricing tiers: Basic, Pro, and Premium, each with different features and prices.  The styling will be clean and modern, utilizing basic CSS (no preprocessors like Sass or Less, or frameworks like Tailwind).


**Description of the Styling:**

The pricing table will be responsive, adapting to different screen sizes. Each pricing tier will be contained within a card-like element with a subtle shadow.  The headers will be clear and concise, and features will be presented using a bulleted list.  The price will be prominently displayed.  We'll use gradients for a visually appealing effect, though this is optional.


**Full Code:**

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
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  background: linear-gradient(to bottom, #f0f0f0, #e0e0e0); /*Optional Gradient*/
}

.pricing-card h2 {
  background-color: #4CAF50;
  color: white;
  padding: 15px;
  margin: 0;
}

.pricing-card ul {
  list-style: none;
  padding: 15px;
}

.pricing-card li {
  margin-bottom: 10px;
}

.pricing-card .price {
  font-size: 24px;
  font-weight: bold;
  padding: 15px;
  text-align: center;
}
@media (max-width: 768px) {
  .pricing-card {
    width: calc(50% - 40px); /* Adjust for responsiveness */
  }
}

@media (max-width: 480px) {
  .pricing-card {
    width: calc(100% - 40px); /* Adjust for responsiveness */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="pricing-card">
    <h2>Basic</h2>
    <div class="price">$9.99/month</div>
    <ul>
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Basic Support</li>
    </ul>
  </div>
  <div class="pricing-card">
    <h2>Pro</h2>
    <div class="price">$29.99/month</div>
    <ul>
      <li>100GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
  </div>
  <div class="pricing-card">
    <h2>Premium</h2>
    <div class="price">$99.99/month</div>
    <ul>
      <li>Unlimited Storage</li>
      <li>Unlimited Users</li>
      <li>Dedicated Support</li>
    </ul>
  </div>
</div>

</body>
</html>
```


**Explanation:**

The code utilizes flexbox for easy layout management.  Media queries are used to ensure responsiveness.  Classes are used to target specific elements for styling.  The gradient is optional but adds visual appeal.  This example prioritizes simplicity and clarity to teach fundamental CSS concepts.


**Links to Resources to Learn More:**

* **CSS Flexbox:** [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Box Model:** [MDN Web Docs - CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

