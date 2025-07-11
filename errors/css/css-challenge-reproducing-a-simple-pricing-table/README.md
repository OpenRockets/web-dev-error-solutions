# 🐞 CSS Challenge:  Reproducing a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll leverage standard CSS (no Tailwind this time) to build a table with three pricing plans, each highlighting key features and prices. The goal is to achieve a visually appealing layout that adapts well to different screen sizes.


**Description of the Styling:**

The pricing table will have a card-like appearance with rounded corners, subtle shadows, and a clear separation between the pricing plans. Each plan will be contained within a separate column, with headings for plan name, price, and features.  We will use a consistent color palette and appropriate typography for readability. Responsiveness will be achieved using media queries to adjust column widths and potentially layout at smaller screen sizes.


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
  justify-content: space-around;
  padding: 20px;
}

.plan {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  padding: 20px;
  margin: 10px;
  width: 300px; /* Adjust as needed */
  text-align: center;
}

.plan h2 {
  margin-bottom: 10px;
}

.plan .price {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 15px;
}

.plan ul {
  list-style: none;
  padding: 0;
}

.plan li {
  margin-bottom: 5px;
}


@media (max-width: 768px) {
  .pricing-table {
    flex-direction: column; /* Stack plans vertically on smaller screens */
  }
  .plan {
    width: 90%; /* Occupy most of the width on smaller screens */
    margin: 10px auto; /* Center the plans */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="plan">
    <h2>Basic</h2>
    <div class="price">$9.99/month</div>
    <ul>
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Basic Support</li>
    </ul>
  </div>
  <div class="plan">
    <h2>Premium</h2>
    <div class="price">$29.99/month</div>
    <ul>
      <li>100GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
  </div>
  <div class="plan">
    <h2>Enterprise</h2>
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

The code utilizes flexbox for easy layout management.  The `pricing-table` div uses `flex-wrap: wrap` to allow plans to wrap onto the next line if necessary.  Media queries are employed to adjust the layout for smaller screens, switching to a vertical stack.  Classes like `plan`, `price`, and others are used for styling individual components.  The CSS focuses on visual appeal, responsiveness, and semantic clarity.


**Links to Resources to Learn More:**

* **CSS Flexbox:** [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - CSS Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **CSS Grid (alternative layout method):** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

