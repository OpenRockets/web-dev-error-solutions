# 🐞 CSS Challenge:  Animated Gradient Button with Tailwind CSS


This challenge involves creating an attractive button with an animated gradient background using Tailwind CSS. The button will have a smooth transition between two colors when hovered over.  This example uses Tailwind CSS for rapid styling, but the core concept can be adapted to plain CSS3.


**Description of the Styling:**

The button will be rectangular with rounded corners.  The background will be a linear gradient transitioning from a teal color to a light blue color. On hover, the gradient will reverse, smoothly transitioning from light blue to teal.  The text within the button will be white, ensuring good contrast against the background gradients.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animated Gradient Button</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">
  <div class="flex justify-center items-center h-screen">
    <button class="bg-gradient-to-r from-teal-500 to-blue-200 hover:bg-gradient-to-l hover:from-blue-200 hover:to-teal-500 text-white font-bold py-2 px-6 rounded-lg transition duration-300 ease-in-out">
      Click Me!
    </button>
  </div>
</body>
</html>
```

**Explanation:**

* **`bg-gradient-to-r from-teal-500 to-blue-200`**: This applies a linear gradient from teal-500 (a dark teal) to blue-200 (a light blue), with the gradient going from left to right (`to-r`).
* **`hover:bg-gradient-to-l hover:from-blue-200 hover:to-teal-500`**: This sets the styles for the hover effect.  `to-l` reverses the gradient direction, and the `from` and `to` values are swapped to create the animation.
* **`text-white font-bold py-2 px-6 rounded-lg`**: This styles the text (white, bold), padding, and rounded corners.
* **`transition duration-300 ease-in-out`**: This adds a smooth transition with a duration of 300 milliseconds and an ease-in-out timing function.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  (Excellent resource for learning all about Tailwind CSS utility classes)
* **CSS Gradients:** [https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient) (Mozilla Developer Network documentation on CSS gradients)
* **CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) (Mozilla Developer Network documentation on CSS transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

