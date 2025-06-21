# 🐞 CSS Challenge: Responsive Pricing Table


This challenge involves creating a responsive pricing table using CSS. The table should have three plans (Basic, Pro, and Premium) with different features and prices.  The design should be clean, visually appealing, and adapt seamlessly to different screen sizes. We'll use plain CSS for this example, but the principles can easily be adapted to Tailwind CSS.

## Styling Description

The pricing table will consist of a container with three columns, each representing a plan. Each plan will have a title, a list of features, a price, and a call-to-action button.  We'll use shadows, gradients, and hover effects to enhance the visual appeal.  Responsiveness will be achieved using media queries to adjust the layout for smaller screens, potentially stacking the columns vertically.


## Full Code

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
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap; /* Allow wrapping on smaller screens */
}

.plan {
  background-color: #f0f0f0;
  border-radius: 8px;
  padding: 20px;
  margin: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  width: 300px; /* Adjust as needed */
  text-align: center;
}

.plan h2 {
  color: #333;
}

.plan ul {
  list-style: none;
  padding: 0;
}

.plan li {
  margin-bottom: 10px;
}

.plan .price {
  font-size: 24px;
  font-weight: bold;
  color: #007bff;
}

.plan button {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.plan button:hover {
  background-color: #0069d9;
}

/* Media Query for smaller screens */
@media (max-width: 768px) {
  .pricing-table {
    flex-direction: column; /* Stack columns vertically */
  }
  .plan {
    width: 90%; /* Adjust width for smaller screens */
    margin: 10px auto;
  }
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

## Explanation

The code utilizes flexbox for layout, making it easy to manage the arrangement of the pricing plans.  Media queries ensure responsiveness by changing the flex direction to column on smaller screens.  The CSS provides basic styling for the table, plans, and buttons, including hover effects.  This is a foundational example; further enhancements could include more sophisticated styling, animations, and potentially using a CSS framework like Tailwind CSS to streamline the process.


## Resources to Learn More

* **CSS Flexbox:** [MDN Web Docs - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
* **CSS Media Queries:** [MDN Web Docs - Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
* **Tailwind CSS:** [Tailwind CSS Official Website](https://tailwindcss.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

