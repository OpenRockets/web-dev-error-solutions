# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS.  The table will feature three pricing plans (Basic, Pro, and Enterprise) with different features and prices, adapting gracefully to various screen sizes.  The styling will emphasize clarity, readability, and a modern aesthetic.

**Description of the Styling:**

The pricing table will consist of three cards, each representing a pricing plan.  These cards will be arranged horizontally on larger screens and stacked vertically on smaller screens thanks to Tailwind's responsive modifiers.  Each card will include:

* A clear title (Basic, Pro, Enterprise)
* A prominent price displayed prominently.
* A bulleted list of features.
* A call to action button ("Choose Plan").

The styling will use Tailwind's pre-defined classes for spacing, typography, colors, and responsiveness to ensure efficient and consistent styling. We'll aim for a clean and modern look, using a subtle color palette and clear visual hierarchy.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Pricing Table</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="container mx-auto px-4 py-8">
    <h2 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

      <!-- Basic Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Basic</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$9/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>10GB Storage</li>
          <li>1 User</li>
          <li>Basic Support</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Pro Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Pro</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$49/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>100GB Storage</li>
          <li>5 Users</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Enterprise Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Enterprise</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$99/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>Unlimited Storage</li>
          <li>Unlimited Users</li>
          <li>Dedicated Support</li>
          <li>All Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

    </div>
  </div>

</body>
</html>
```

**Explanation:**

The code utilizes Tailwind's utility-first approach.  Classes like `grid`, `grid-cols`, `gap`, `bg-white`, `rounded-lg`, `shadow-md`, `text-xl`, `font-bold`, and many others are used to quickly style the elements.  Responsive design is achieved using the `md:grid-cols-3` modifier, which changes the layout to three columns on medium-sized screens and above.  Hover effects are easily added using `hover:bg-blue-700`.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)  -  The official Tailwind CSS documentation is an excellent resource for learning about all its features and utility classes.
* **Tailwind CSS Cheat Sheet:** [Many available online, search "Tailwind CSS cheatsheet"] -  A cheat sheet can be helpful for quickly referencing available classes.
* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) -  Understanding CSS Grid is crucial for creating responsive layouts efficiently.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

