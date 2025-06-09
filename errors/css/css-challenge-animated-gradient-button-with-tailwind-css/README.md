# 🐞 CSS Challenge:  Animated Gradient Button with Tailwind CSS


This challenge focuses on creating an attractive and animated gradient button using Tailwind CSS. The button will feature a smooth color transition on hover, utilizing Tailwind's utility classes for efficient styling.

**Description of the Styling:**

The button will be a rectangular shape with rounded corners.  The background will be a linear gradient transitioning between two colors. On hover, the gradient's colors will shift subtly, creating an animation effect.  The text within the button will be white, ensuring good contrast against the gradient background.  We'll aim for a modern and clean aesthetic.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animated Gradient Button</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

<div class="flex justify-center items-center h-screen">
  <button class="bg-gradient-to-r from-blue-500 to-purple-500 hover:from-pink-500 hover:to-orange-500 text-white font-bold py-2 px-4 rounded-lg shadow-lg transition duration-300 ease-in-out">
    Click Me!
  </button>
</div>

</body>
</html>
```

**Explanation:**

* **`bg-gradient-to-r from-blue-500 to-purple-500`**: This sets the background to a linear gradient going from blue (#2563eb) to purple (#a855f7).  `to-r` specifies the gradient direction as right-to-left.
* **`hover:from-pink-500 hover:to-orange-500`**: This uses Tailwind's hover pseudo-class to modify the gradient on hover.  The gradient changes to pink (#ec4899) to orange (#fb923c).
* **`text-white`**: Sets the text color to white.
* **`font-bold py-2 px-4 rounded-lg shadow-lg`**:  These classes control the font weight, padding, border radius, and shadow, giving the button a more polished look.
* **`transition duration-300 ease-in-out`**: This adds a smooth transition effect to the hover animation, making the color change gradual over 300 milliseconds.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  (Official documentation, excellent resource for all things Tailwind)
* **CSS Gradients:** [https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient) (MDN documentation on CSS gradients)
* **CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) (MDN documentation on CSS transitions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

