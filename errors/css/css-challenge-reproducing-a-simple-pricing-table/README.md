# 🐞 CSS Challenge:  Reproducing a Simple Pricing Table


This challenge focuses on creating a clean and responsive pricing table using CSS.  We'll aim for a design that's visually appealing and adapts well to different screen sizes. While this example doesn't explicitly use Tailwind CSS (to keep the code more concise and easier to understand for beginners), the principles are readily applicable to Tailwind's utility-first approach.

**Description of the Styling:**

The pricing table will consist of three columns representing different pricing plans (e.g., Basic, Pro, Premium). Each column will have a title, a list of features, a price, and a call-to-action button. The styling will include:

* **Visual separation:** Clear visual distinction between plans using borders and padding.
* **Responsiveness:** The table should adapt gracefully to smaller screens, possibly stacking columns vertically.
* **Consistent styling:**  Maintain a consistent look and feel across all plans.
* **Accessibility:** Use clear semantic HTML and sufficient contrast.


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
  justify-content: space-around;
  flex-wrap: wrap; /* Allow wrapping on smaller screens */
}

.plan {
  width: 300px; /* Adjust as needed */
  border: 1px solid #ccc;
  margin: 10px;
  padding: 20px;
  text-align: center;
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
  font-size: 1.5em;
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
    <p class="price">$9/month</p>
    <button>Sign Up</button>
  </div>
  <div class="plan">
    <h2>Pro</h2>
    <ul>
      <li>Feature 1</li>
      <li>Feature 2</li>
      <li>Feature 3</li>
    </ul>
    <p class="price">$19/month</p>
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
    <p class="price">$29/month</p>
    <button>Sign Up</button>
  </div>
</div>

</body>
</html>
```

**Explanation:**

The CSS uses flexbox for layout, making it easy to arrange the columns and handle responsiveness.  Media queries could be added for more fine-grained control over layout at different screen sizes.  The styling is straightforward, focusing on clear visual separation and readability.


**Links to Resources to Learn More:**

* **CSS Flexbox:** [MDN Web Docs - CSS Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Grid:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) (For alternative layout options)
* **Tailwind CSS Documentation:** [Tailwind CSS Official Documentation](https://tailwindcss.com/docs) (To learn how to achieve similar results with Tailwind's utility classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

