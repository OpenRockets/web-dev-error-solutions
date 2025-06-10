# 🐞 CSS Challenge:  Animated Expanding Card with Tailwind CSS


This challenge focuses on creating an animated card that expands on hover, revealing more information. We'll use Tailwind CSS for rapid styling and smooth transitions.  This example leverages Tailwind's utility classes for a concise and efficient solution.


## Description of the Styling

The card will be initially compact, displaying only a title and a small image. On hover, the card smoothly expands vertically, revealing a longer description and a "Learn More" button.  The animation will be subtle and user-friendly.  We'll utilize Tailwind's transition and transform properties for the animation.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Expanding Card</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

  <div class="container mx-auto p-8">
    <div class="max-w-sm bg-white rounded-lg shadow-md overflow-hidden transition duration-300 ease-in-out transform hover:scale-105">
      <img class="w-full h-48 object-cover" src="https://via.placeholder.com/350x150" alt="Card Image">
      <div class="p-4">
        <h2 class="text-xl font-bold text-gray-800 mb-2">Card Title</h2>
        <p class="text-gray-600 text-sm hidden transition-all duration-300 h-0 overflow-hidden group-hover:h-auto group-hover:text-base">
          This is a longer description of the card content.  It will only appear when the user hovers over the card.  This allows for a clean and uncluttered initial view.  You can customize the content to your liking!
        </p>
        <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded hidden transition-all duration-300 group-hover:block">Learn More</button>
      </div>
    </div>
  </div>

</body>
</html>
```

## Explanation

* **`container mx-auto p-8`:** Centers the card horizontally and adds padding.
* **`max-w-sm`:** Sets a maximum width for the card.
* **`bg-white rounded-lg shadow-md`:** Styles the card with a white background, rounded corners, and a shadow.
* **`overflow-hidden`:** Prevents the content from overflowing.
* **`transition duration-300 ease-in-out transform hover:scale-105`:**  Adds a smooth scaling transition on hover.
* **`hidden transition-all duration-300 h-0 overflow-hidden group-hover:h-auto group-hover:text-base`:** This hides the description initially.  `group-hover` applies styles when hovering over the parent (.group) div, revealing the description on hover and increasing font size.
* **`hidden transition-all duration-300 group-hover:block`:** This hides the button initially and displays it on hover.

## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **MDN Web Docs (CSS Transitions):** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **MDN Web Docs (CSS Transforms):** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

