# 🐞 CSS Challenge: Responsive Pricing Table


This challenge involves creating a responsive pricing table using CSS.  We'll focus on a clean, modern design adaptable to different screen sizes.  While we could use plain CSS, we'll leverage Tailwind CSS for its rapid development capabilities and utility-first approach.

## Description of the Styling

The pricing table will feature three pricing plans: Basic, Pro, and Premium.  Each plan will have a title, a list of features, a price, and a call-to-action button.  The design will emphasize visual clarity and a consistent layout across different screen sizes (desktop, tablet, and mobile).  Tailwind CSS classes will be used to manage spacing, sizing, colors, and responsiveness.

## Full Code (Tailwind CSS)

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Pricing Table</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

  <div class="container mx-auto px-4 py-10">
    <h1 class="text-3xl font-bold text-center text-gray-800 mb-8">Choose Your Plan</h1>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold text-gray-800 mb-4">Basic</h2>
        <ul class="text-gray-600 mb-6">
          <li>1 User</li>
          <li>10GB Storage</li>
          <li>Basic Support</li>
        </ul>
        <p class="text-2xl font-bold text-green-500 mb-4">$9/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold text-gray-800 mb-4">Pro</h2>
        <ul class="text-gray-600 mb-6">
          <li>5 Users</li>
          <li>50GB Storage</li>
          <li>Priority Support</li>
        </ul>
        <p class="text-2xl font-bold text-green-500 mb-4">$49/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold text-gray-800 mb-4">Premium</h2>
        <ul class="text-gray-600 mb-6">
          <li>Unlimited Users</li>
          <li>Unlimited Storage</li>
          <li>Dedicated Support</li>
        </ul>
        <p class="text-2xl font-bold text-green-500 mb-4">$99/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
    </div>
  </div>

</body>
</html>
```

## Explanation

This code utilizes Tailwind CSS classes to style the pricing table.  `grid` and `grid-cols` are used for responsive layout.  `bg-white`, `rounded-lg`, `shadow-md`, etc., provide styling for the table elements.  Media queries are implicitly handled by Tailwind's responsive modifiers (e.g., `md:grid-cols-3`).  The code is well-structured and easy to understand, thanks to Tailwind's declarative nature.

## Links to Resources to Learn More

* **Tailwind CSS:** [https://tailwindcss.com/](https://tailwindcss.com/) - Official Tailwind CSS documentation.
* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) - MDN documentation on CSS Grid.
* **Responsive Web Design:** [https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design) -  MDN's guide to responsive web design.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

