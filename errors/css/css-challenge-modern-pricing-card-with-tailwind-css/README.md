# 🐞 CSS Challenge:  Modern Pricing Card with Tailwind CSS


This challenge focuses on creating a clean and modern pricing card using Tailwind CSS. The goal is to build a visually appealing card that clearly displays pricing information and encourages user engagement.  We'll leverage Tailwind's utility classes for rapid development and consistent styling.

## Description of the Styling:

The pricing card will feature:

* A clean, rectangular design.
* A subtle background gradient.
* Clear headings for plan name and price.
* A bulleted list of included features.
* A prominent call-to-action button.
* Responsive design to adapt to different screen sizes.

## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pricing Card</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

<div class="max-w-sm mx-auto bg-gradient-to-r from-blue-500 to-purple-500 rounded-lg shadow-lg p-6 my-10">
  <h2 class="text-white text-2xl font-bold mb-4">Pro Plan</h2>
  <p class="text-white text-4xl font-bold mb-4">$99<span class="text-lg">/month</span></p>
  <ul class="text-white mb-6">
    <li>&#8226; 100GB Storage</li>
    <li>&#8226; Unlimited Bandwidth</li>
    <li>&#8226; 24/7 Support</li>
    <li>&#8226; Priority Access</li>
  </ul>
  <button class="bg-white text-purple-500 hover:bg-purple-100 py-2 px-4 rounded-lg text-lg font-medium">Get Started</button>
</div>

</body>
</html>
```


## Explanation:

* **`bg-gradient-to-r from-blue-500 to-purple-500`**: This applies a linear gradient background from blue to purple.
* **`rounded-lg`**:  Rounds the corners of the card.
* **`shadow-lg`**: Adds a large box shadow for depth.
* **`text-white`**: Sets text color to white for contrast against the background.
* **`text-2xl`, `text-4xl`, `text-lg`**:  Control the text size using Tailwind's pre-defined sizes.
* **`font-bold`**:  Makes the text bold.
* **`mb-4`, `mb-6`**: Adds margin at the bottom for spacing.
* **`hover:bg-purple-100`**: Changes the button background on hover.
* **`max-w-sm mx-auto`**: Limits the card's width and centers it horizontally.


## Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) – The official Tailwind CSS documentation is an excellent resource for learning about all the available utility classes and customizing your setup.
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS Cheat Sheet" on Google – Many helpful cheat sheets are available online to quickly look up classes.
* **Learn CSS Grid:**  If you want to improve your layout skills further, look into CSS Grid.  Numerous tutorials are available online.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

