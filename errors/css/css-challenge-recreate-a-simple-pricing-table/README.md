# 🐞 CSS Challenge: Recreate a Simple Pricing Table


This challenge involves creating a clean and responsive pricing table using CSS.  We'll focus on a straightforward design to highlight fundamental CSS concepts.  This example uses standard CSS3; adapting it to Tailwind CSS is a straightforward exercise left for the reader (explained briefly below).

## Description of the Styling

The pricing table will consist of three columns representing different pricing plans (Basic, Pro, and Premium). Each column will have a title, a list of features, a price, and a call-to-action button.  The design will emphasize visual separation between plans using borders and padding.  We'll aim for a clean, modern look with a responsive layout that adapts to different screen sizes.

## Full Code (CSS3)

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
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive grid */
  grid-gap: 20px;
}

.plan {
  border: 1px solid #ccc;
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
  font-size: 1em;
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

## Explanation

The code utilizes CSS Grid for a responsive layout.  `grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));` ensures the columns adapt to different screen sizes.  Classes like `.plan` style individual pricing plans, while other classes target specific elements within each plan (e.g., `.price`, `button`).  The use of semantic HTML elements like `ul` and `li` improves accessibility.

## Tailwind CSS Adaptation

Adapting this to Tailwind CSS would involve replacing the custom CSS classes with corresponding Tailwind utility classes.  For example:

* `.pricing-table` could become  `grid grid-cols-1 md:grid-cols-3 gap-4`.
* `.plan` could become `border border-gray-300 p-4 text-center`.
* `.price` could become `text-xl font-bold mb-2`.
* `.plan h2` could become `text-2xl font-semibold mb-2`.
* The button styling would be achieved using Tailwind's button utilities.


## Resources to Learn More

* **CSS Grid Layout:** [MDN Web Docs - CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
* **CSS Basics:** [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Tailwind CSS:** [Tailwind CSS Documentation](https://tailwindcss.com/docs)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

