# 🐞 CSS Challenge:  Animated Expanding Card with Tailwind CSS


This challenge involves creating an interactive card that expands on hover, revealing additional content. We'll be using Tailwind CSS for its rapid prototyping capabilities and ease of styling.


## Description of the Styling:

The card will initially be compact, displaying a title and a brief summary. On hover, the card will smoothly expand vertically, revealing a more detailed description.  The animation will be subtle and visually appealing, using Tailwind's transition utilities.  We will also incorporate some basic styling for visual appeal, including rounded corners and shadows.


## Full Code:

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

<div class="container mx-auto p-4">
  <div class="max-w-sm rounded overflow-hidden shadow-lg transition-all duration-300 ease-in-out hover:shadow-2xl hover:scale-105">
    <div class="px-6 py-4">
      <div class="font-bold text-xl mb-2">Card Title</div>
      <p class="text-gray-700 text-base">
        This is a short summary of the card content.  It will expand on hover.
      </p>
    </div>
    <div class="px-6 pt-4 pb-2 hidden transition-all duration-300 ease-in-out hover:block" style="max-height:0;overflow:hidden">
      <p class="text-gray-700 text-base">
        This is the expanded content of the card.  You can add more details here as needed.  This text will smoothly appear on hover.
      </p>
    </div>
  </div>
</div>

</body>
</html>
```


## Explanation:

* **`transition-all duration-300 ease-in-out`**: This Tailwind class applies a smooth transition to all properties that change, with a duration of 300ms and an ease-in-out timing function.
* **`hover:shadow-2xl hover:scale-105`**:  On hover, the shadow becomes more prominent (`shadow-2xl`), and the card scales slightly (`scale-105`).
* **`hidden transition-all duration-300 ease-in-out hover:block`**: The expanded content is initially hidden (`hidden`). On hover, it becomes visible (`block`), and the transition is applied.  `style="max-height:0;overflow:hidden;"` is added to initially collapse the height.
* **Tailwind classes**:  We use Tailwind classes extensively for styling, such as `bg-gray-100`, `max-w-sm`, `rounded`, `overflow-hidden`, `shadow-lg`, `px-6`, `py-4`, `font-bold`, `text-xl`, `text-gray-700`, and `text-base`.


## Links to Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **CSS Transitions and Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **MDN Web Docs - CSS:** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

