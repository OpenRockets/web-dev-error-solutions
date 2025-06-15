# 🐞 CSS Challenge:  A Responsive Pricing Card with Tailwind CSS


This challenge involves creating a responsive pricing card using Tailwind CSS. The card will feature a title, a price, a list of features, and a call-to-action button.  The design will be clean, modern, and adapt seamlessly to different screen sizes.


## Styling Description

The pricing card will utilize a clean and modern aesthetic.  It will be contained within a card-like structure with rounded corners and a subtle shadow. The title will be prominent, the price will be clearly displayed, and the feature list will be easily scannable. The call-to-action button will have a contrasting color to draw attention.  The card will respond gracefully to different screen sizes, maintaining its visual appeal on both desktop and mobile.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com"></script>
  <title>Pricing Card</title>
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-8">
  <div class="max-w-sm bg-white rounded-lg shadow-md p-6">
    <h2 class="text-2xl font-bold mb-4 text-gray-800">Premium Plan</h2>
    <p class="text-4xl font-bold text-blue-500 mb-4">$99<span class="text-xl">/month</span></p>
    <ul class="list-disc list-inside mb-6 text-gray-600">
      <li>Unlimited users</li>
      <li>10GB storage</li>
      <li>Priority support</li>
      <li>Customizable branding</li>
    </ul>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      Get Started
    </button>
  </div>
</div>

</body>
</html>
```


## Explanation

* **`container mx-auto p-8`**: This centers the card on the page and adds padding.
* **`max-w-sm`**: Limits the maximum width of the card for better responsiveness.
* **`bg-white rounded-lg shadow-md p-6`**: Sets the background color, rounded corners, shadow, and padding for the card.
* **Tailwind Classes for Typography**:  Tailwind's utility classes (`text-2xl`, `font-bold`, etc.) are used for styling the text elements.
* **`list-disc list-inside`**: Styles the unordered list.
* **Button Styling**:  The button uses Tailwind classes for background color, hover effect, text color, padding, and rounded corners.


## Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) -  The official Tailwind CSS documentation is an excellent resource for learning about all the available utility classes and customizing your Tailwind setup.
* **Tailwind CSS Cheat Sheet:**  A quick reference guide for common Tailwind CSS classes can be found through a web search (many are available).
* **Learn CSS (general):**  For a broader understanding of CSS, resources like freeCodeCamp ([https://www.freecodecamp.org/](https://www.freecodecamp.org/)) or Codecademy ([https://www.codecademy.com/](https://www.codecademy.com/)) offer interactive CSS courses.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

