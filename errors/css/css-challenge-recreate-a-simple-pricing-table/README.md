# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll leverage CSS Grid for layout and some basic CSS properties for styling.  No frameworks like Tailwind CSS will be used for this example to focus on fundamental CSS principles.

**Description of the Styling:**

The pricing table will consist of three columns representing different pricing plans (Basic, Pro, and Premium). Each plan will have a title, a price, a list of features, and a call to action button.  The styling will emphasize clarity and visual separation between the plans. We'll use subtle gradients and shadows for visual appeal.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Pricing Table</title>
<style>
body {
  font-family: sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f4f4f4;
}

.pricing-table {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive columns */
  grid-gap: 20px;
  background-color: #fff;
  padding: 20px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
}

.plan {
  background-color: #f9f9f9;
  padding: 20px;
  text-align: center;
  border-radius: 5px;
}

.plan h2 {
  color: #333;
  margin-bottom: 10px;
}

.plan .price {
  font-size: 24px;
  font-weight: bold;
  color: #007bff;
  margin-bottom: 15px;
}

.plan ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.plan li {
  margin-bottom: 5px;
}

.plan button {
  background-color: #007bff;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

.plan button:hover {
  background-color: #0069d9;
}
</style>
</head>
<body>
<div class="pricing-table">
  <div class="plan">
    <h2>Basic</h2>
    <p class="price">$9.99/month</p>
    <ul>
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Basic Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Pro</h2>
    <p class="price">$29.99/month</p>
    <ul>
      <li>100GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Premium</h2>
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

The CSS uses `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));` to create a responsive grid.  `auto-fit` allows columns to adjust based on screen size, ensuring optimal layout on different devices.  `minmax(300px, 1fr)` sets a minimum column width of 300px, while `1fr` distributes the remaining space equally among the columns. Other CSS is used for basic styling, ensuring that the elements are visually appealing and easy to read.

**Links to Resources to Learn More:**

* **CSS Grid Layout:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* **MDN CSS Reference:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

