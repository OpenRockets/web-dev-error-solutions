# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge involves creating a clean and responsive pricing table using CSS.  We'll focus on a straightforward design, easily adaptable to different styles and complexity levels.  This example uses plain CSS, but could be easily adapted to use Tailwind CSS (see notes below).


**Description of the Styling:**

The pricing table will contain three columns representing different pricing plans (Basic, Pro, and Premium). Each column will include a plan name, a price, a list of features, and a call-to-action button. The table will be responsive, adapting its layout to different screen sizes.  We'll aim for a clean, modern aesthetic with clear visual hierarchy.

**Full Code (CSS):**

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
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
  padding: 20px;
}

.pricing-plan {
  border: 1px solid #ccc;
  padding: 20px;
  text-align: center;
}

.pricing-plan h2 {
  margin-top: 0;
}

.pricing-plan .price {
  font-size: 2em;
  font-weight: bold;
  margin-bottom: 10px;
}

.pricing-plan ul {
  list-style: none;
  padding: 0;
}

.pricing-plan ul li {
  margin-bottom: 5px;
}

.pricing-plan button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 10px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 10px 0;
  cursor: pointer;
  border-radius: 5px;
}
</style>
</head>
<body>

<div class="pricing-table">
  <div class="pricing-plan">
    <h2>Basic</h2>
    <p class="price">$9/month</p>
    <ul>
      <li>1 User</li>
      <li>5 GB Storage</li>
      <li>Basic Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-plan">
    <h2>Pro</h2>
    <p class="price">$49/month</p>
    <ul>
      <li>5 Users</li>
      <li>50 GB Storage</li>
      <li>Priority Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
  <div class="pricing-plan">
    <h2>Premium</h2>
    <p class="price">$99/month</p>
    <ul>
      <li>Unlimited Users</li>
      <li>Unlimited Storage</li>
      <li>Dedicated Support</li>
    </ul>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```


**Explanation:**

The CSS uses `grid` for layout, making it responsive and easy to manage.  Classes are used to target specific elements, allowing for easy styling modifications.  The `auto-fit` keyword in `grid-template-columns` ensures the columns adjust to the available space.  Each plan is contained within a `div` with the class `pricing-plan`.  This structure allows for clean separation of concerns and easy maintenance.


**Adapting to Tailwind CSS:**

Tailwind CSS would simplify this further.  Instead of writing custom CSS, you'd use Tailwind's utility classes. For example:

```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-4 p-4">
  <!-- Pricing plan divs using Tailwind classes here -->
</div>
```


**Links to Resources to Learn More:**

* **CSS Grid:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **Tailwind CSS:** [https://tailwindcss.com/](https://tailwindcss.com/)
* **Responsive Web Design:** [https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

