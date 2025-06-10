# 🐞 CSS Challenge:  Responsive Pricing Card with Tailwind CSS


This challenge focuses on creating a responsive pricing card using Tailwind CSS.  The card will display different pricing tiers with clear visual distinctions and adapt smoothly to various screen sizes. We'll leverage Tailwind's utility classes for efficient and rapid development.


## Description of the Styling:

The pricing card will feature three pricing tiers: Basic, Pro, and Premium. Each tier will have:

*   A distinct background color (subtle variations).
*   Clear headings for the tier name.
*   A prominent price display.
*   A bulleted list of features.
*   A call-to-action button.

The layout will be responsive, adapting neatly to smaller screens by stacking elements vertically.


## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pricing Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="container mx-auto px-4 py-8">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

      <div class="bg-blue-100 rounded-lg shadow-md p-6">
        <h2 class="text-2xl font-bold mb-4 text-blue-600">Basic</h2>
        <p class="text-4xl font-bold mb-4 text-blue-700">$9/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>10GB Storage</li>
          <li>1 User</li>
          <li>Basic Support</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

      <div class="bg-green-100 rounded-lg shadow-md p-6">
        <h2 class="text-2xl font-bold mb-4 text-green-600">Pro</h2>
        <p class="text-4xl font-bold mb-4 text-green-700">$29/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>50GB Storage</li>
          <li>5 Users</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

      <div class="bg-purple-100 rounded-lg shadow-md p-6">
        <h2 class="text-2xl font-bold mb-4 text-purple-600">Premium</h2>
        <p class="text-4xl font-bold mb-4 text-purple-700">$99/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>Unlimited Storage</li>
          <li>Unlimited Users</li>
          <li>Dedicated Support</li>
          <li>All Features</li>
        </ul>
        <button class="bg-purple-500 hover:bg-purple-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

    </div>
  </div>

</body>
</html>
```


## Explanation:

The code utilizes Tailwind's grid system (`grid`, `grid-cols`, `gap`) for responsive layout.  Utility classes handle styling efficiently:

*   `bg-*`: Background color.
*   `rounded-lg`: Rounded corners.
*   `shadow-md`: Box shadow.
*   `text-*`: Text color and size.
*   `font-bold`: Bold font weight.
*   `p-*`: Padding.
*   `mb-*`: Margin bottom.
*   `list-*`: List styling.
*   `hover:*`: Hover effects.


## Links to Resources to Learn More:

*   **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  (Official documentation)
*   **Tailwind CSS Playgrounds:** Numerous online playgrounds are available for experimenting with Tailwind classes.  Search for "Tailwind CSS Playground" on your search engine.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

