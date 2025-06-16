# 🐞 CSS Challenge:  Building a Responsive Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll leverage CSS Grid for layout and some basic CSS3 properties for styling. No external frameworks like Tailwind are used to focus on fundamental CSS skills.

**Description of the Styling:**

The pricing table will feature three pricing plans (Basic, Pro, Enterprise). Each plan will have a distinct color block for visual separation.  The table should be responsive, adapting gracefully to different screen sizes.  We aim for a clean, modern aesthetic.

**Full Code:**

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
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive columns */
  grid-gap: 20px;
  padding: 20px;
}

.plan {
  border: 1px solid #ccc;
  padding: 20px;
  text-align: center;
}

.plan h2 {
  margin-top: 0;
}

.plan .price {
  font-size: 2em;
  font-weight: bold;
  color: #333;
}

.plan.basic {
  background-color: #f0f0f0;
}

.plan.pro {
  background-color: #e0f7fa;
}

.plan.enterprise {
  background-color: #e0e0e0;
}

.plan ul {
  list-style: none;
  padding: 0;
}

.plan li {
  margin-bottom: 10px;
}

/* Responsive adjustments (optional - adjust breakpoints as needed) */
@media (max-width: 768px) {
  .pricing-table {
    grid-template-columns: 1fr; /* Stack plans vertically on smaller screens */
  }
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="plan basic">
    <h2>Basic</h2>
    <p class="price">$9/month</p>
    <ul>
      <li>10GB Storage</li>
      <li>1 User</li>
      <li>Basic Support</li>
    </ul>
  </div>
  <div class="plan pro">
    <h2>Pro</h2>
    <p class="price">$49/month</p>
    <ul>
      <li>100GB Storage</li>
      <li>5 Users</li>
      <li>Priority Support</li>
    </ul>
  </div>
  <div class="plan enterprise">
    <h2>Enterprise</h2>
    <p class="price">$99/month</p>
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

1. **HTML Structure:**  The HTML uses simple divs to structure the pricing table and individual plans.  Classes (`basic`, `pro`, `enterprise`) are used for styling.

2. **CSS Grid:** The `.pricing-table` uses `display: grid` and `grid-template-columns` to create a responsive grid layout.  `repeat(auto-fit, minmax(300px, 1fr))` allows the columns to adjust based on screen size.  `grid-gap` adds spacing between plans.

3. **CSS Styling:**  Individual plan styles are applied using classes.  Background colors differentiate plans.  Media queries handle responsive adjustments (stacking plans vertically on smaller screens).

**Links to Resources to Learn More:**

* **CSS Grid Layout:**  [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Media Queries:** [MDN Web Docs - Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **General CSS Tutorials:** [FreeCodeCamp - Responsive Web Design](https://www.freecodecamp.org/learn/responsive-web-design/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

