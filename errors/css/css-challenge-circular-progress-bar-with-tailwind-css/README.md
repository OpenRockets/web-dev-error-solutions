# 🐞 CSS Challenge:  Circular Progress Bar with Tailwind CSS


This challenge involves creating a circular progress bar using Tailwind CSS. The bar will visually represent a percentage, dynamically updating its appearance based on a provided value. We'll achieve this using a combination of CSS custom properties (variables), pseudo-elements, and Tailwind's utility classes for efficient styling.


**Description of the Styling:**

The progress bar will be a circle with a background color.  A smaller circle on top will represent the progress, filling a portion of the larger circle based on the percentage value. The percentage value will be displayed inside the progress circle.  We'll leverage Tailwind's responsive design features to ensure it looks good on various screen sizes.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Circular Progress Bar</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<style>
  .progress-ring {
    --progress: 75; /* Adjust this value to change the progress */
    width: 150px;
    height: 150px;
    border-radius: 50%;
    position: relative;
  }

  .progress-ring::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-color: #f0f0f0; /* Background color */
    z-index: 1;
  }

  .progress-ring::after {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) rotate(calc(var(--progress) * 3.6deg)); /* Calculation for rotation */
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-color: #4CAF50; /* Progress color */
    clip-path: polygon(50% 50%, 100% 50%, 100% 0, 50% 0); /* creates a semi-circle */
    z-index: 2;
  }

  .progress-ring span {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 1.2rem;
    color: white;
  }
</style>
</head>
<body class="bg-gray-100 flex justify-center items-center h-screen">
  <div class="progress-ring">
    <span>75%</span>
  </div>
</body>
</html>
```


**Explanation:**

1. **Tailwind Setup:** The code includes a link to the Tailwind CSS CDN and utilizes basic Tailwind classes for layout (`bg-gray-100`, `flex`, `justify-center`, `items-center`, `h-screen`).

2. **CSS Variables:**  `--progress` is a custom CSS property to control the progress percentage.  This makes it easy to change the progress dynamically.

3. **Pseudo-elements:**  `::before` creates the background circle, and `::after` creates the progress arc. The `clip-path` property creates the semi-circle shape.  The `rotate` transform dynamically adjusts the arc based on the `--progress` value.  The calculation `calc(var(--progress) * 3.6deg)` converts the percentage to degrees (360 degrees in a full circle).

4. **Span for Percentage:**  A `<span>` element is positioned within the circle to display the percentage value.

5. **Responsiveness:** Tailwind's responsive design features can easily be incorporated (e.g., using different sizes for the circle based on screen size using Tailwind's screen size modifiers).


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **CSS Custom Properties (Variables):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
* **CSS Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

