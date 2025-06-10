# 🐞 CSS Challenge:  Animated Expanding Card with Tailwind CSS


This challenge involves creating an interactive card that expands when hovered over, revealing more content. We'll use Tailwind CSS for its rapid prototyping capabilities and ease of styling.


## Description of the Styling

The card will initially display a concise title and a small image.  On hover, the card will smoothly expand vertically, revealing a more detailed description and possibly additional elements. We'll utilize Tailwind's transition and transform utilities for the animation.  The card will maintain a clean, modern aesthetic.


## Full Code


```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Expanding Card</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-8">
  <div class="max-w-sm bg-white rounded-lg shadow-md overflow-hidden md:max-w-xl">
    <div class="relative h-48 w-full" style="background-image:url('https://source.unsplash.com/random/500x300'); background-size:cover;">
      <div class="absolute bottom-0 p-4 bg-gray-800 bg-opacity-50 text-white text-lg font-bold w-full">
          Card Title
      </div>
    </div>
    <div class="p-6">
      <div class="mb-2 text-xl font-bold">Card Title</div>
      <p class="text-gray-700 text-base hidden transition-all duration-300 ease-in-out max-h-0 overflow-hidden group-hover:max-h-48 group-hover:block">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Nulla nec purus feugiat, molestie ipsum et, consequat nibh.  Sed et ante vitae elit iaculis lacinia.  Donec sed odio dui.  Nulla facilisi.
      </p>

      <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded hidden group-hover:block">Learn More</button>
    </div>
  </div>
</div>


</body>
</html>
```

## Explanation

* **`container mx-auto p-8`:** Centers the card and adds padding.
* **`max-w-sm bg-white rounded-lg shadow-md overflow-hidden`:** Sets the card's maximum width, background, rounded corners, shadow, and prevents content overflow.
* **`relative h-48 w-full` (Image container):**  Creates a relative positioned container for the image.  The image is set as a background for a better visual effect.
* **`absolute bottom-0 p-4` (Title overlay):** Positions the title absolutely at the bottom of the image container.
* **`hidden transition-all duration-300 ease-in-out max-h-0 overflow-hidden group-hover:max-h-48 group-hover:block`:** This is the crucial part for the animation.  `hidden` hides the description initially, `transition-all` applies transitions to all properties, `duration-300` sets the animation speed, `ease-in-out` defines the easing, `max-h-0` sets the initial height to zero, `overflow-hidden` hides content outside the set height, and `group-hover` applies styles on hover, changing `max-h` to reveal the content.
* **`group-hover:block`:** Shows the "Learn More" button on hover.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **CSS Transitions and Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Group Selectors:** [https://developer.mozilla.org/en-US/docs/Web/CSS/:is/:where/:has](https://developer.mozilla.org/en-US/docs/Web/CSS/:is/:where/:has) (For understanding `group-hover`)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

