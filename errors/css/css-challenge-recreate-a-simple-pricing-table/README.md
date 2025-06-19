# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge involves recreating a clean and responsive pricing table using CSS.  We'll focus on a simple design, suitable for beginners, utilizing standard CSS (no frameworks like Tailwind CSS for this example to keep it accessible).  The goal is to demonstrate basic layout techniques, styling, and responsiveness.

**Description of the Styling:**

The pricing table will consist of three columns representing different pricing tiers (Basic, Pro, Enterprise). Each column will include a title (e.g., "Basic"), a price, a list of features, and a call-to-action button.  The styling will emphasize clean lines, clear visual hierarchy, and responsiveness across different screen sizes.  We'll use a subtle gradient for visual appeal.


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
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive columns */
  grid-gap: 20px;
  padding: 20px;
}

.pricing-column {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
}

.pricing-column h2 {
  color: #333;
  margin-bottom: 10px;
}

.pricing-column p {
  color: #555;
  margin-bottom: 20px;
}

.pricing-column ul {
  list-style: none;
  padding: 0;
}

.pricing-column li {
  margin-bottom: 10px;
}

.pricing-column .price {
  font-size: 24px;
  font-weight: bold;
  color: #007bff; /* Blue price */
}

.pricing-column button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

.pricing-column button:hover {
  background-color: #0069d9;
}

/* Responsive adjustments (optional - for larger screens) */
@media (min-width: 992px) {
  .pricing-table {
    grid-template-columns: repeat(3, 1fr); /* 3 columns on larger screens */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="pricing-column">
    <h2>Basic</h2>
    <p class="price">$9.99/month</p>
    <ul>
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Basic Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-column">
    <h2>Pro</h2>
    <p class="price">$29.99/month</p>
    <ul>
      <li>50GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-column">
    <h2>Enterprise</h2>
    <p class="price">$99.99/month</p>
    <ul>
      <li>Unlimited Storage</li>
      <li>Unlimited Users</li>
      <li>Dedicated Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```

**Explanation:**

The code uses CSS Grid for a responsive layout.  The `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));` line ensures the columns adapt to different screen sizes.  On smaller screens, they stack vertically; on larger screens, they arrange horizontally.  Basic CSS is used for styling elements, including colors, fonts, padding, and shadows.  A media query (`@media (min-width: 992px)`) provides optional adjustments for larger screens.


**Links to Resources to Learn More:**

* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Box Model:** [https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
* **CSS Media Queries:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

