# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript required! This uses techniques that leverage the `clip-path` property and CSS variables for easy customization.

**Description of the Styling:**

This progress bar utilizes a circle created with the `border-radius` property.  A pseudo-element (`::before`) is then used to create the progress indicator.  The `clip-path` property, along with the `rotate` transform, dynamically cuts the circle to represent the percentage complete. CSS variables are used to make customizing the size, colors, and progress percentage incredibly easy.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
  .progress-ring {
    --size: 100px; /* Customize the size */
    --progress: 75%; /* Customize the progress percentage (0-100) */
    --primary-color: #007bff; /* Customize primary color */
    --secondary-color: #e9ecef; /* Customize secondary color */

    width: var(--size);
    height: var(--size);
    border-radius: 50%;
    background-color: var(--secondary-color);
    position: relative;
  }

  .progress-ring::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: var(--size);
    height: var(--size);
    border-radius: 50%;
    background-color: var(--primary-color);
    clip-path: polygon(
      50% 50%,
      50% 0,
      calc(50% + var(--size) / 2 * cos(calc(var(--progress) * 3.1415926 / 50))) calc(50% - var(--size) / 2 * sin(calc(var(--progress) * 3.1415926 / 50))),
      calc(50% + var(--size) / 2 * cos(calc(var(--progress) * 3.1415926 / 50))) calc(50% + var(--size) / 2 * sin(calc(var(--progress) * 3.1415926 / 50)))
    );
    transform: rotate(calc(var(--progress) * 3.6deg)); /* Rotates the progress bar */

  }
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

* **CSS Variables:**  The use of `--size`, `--progress`, `--primary-color`, and `--secondary-color` allows for easy customization without modifying the core CSS.
* **`clip-path`:** This property is key. It creates the "cut" effect, revealing only the portion of the circle representing the progress. The complex polygon calculation determines the shape of the visible section.
* **`rotate` Transform:** This rotates the clipped section to create the circular progress effect.  It's crucial for creating a visually appealing progress bar.
* **Pseudo-element (`::before`):**  This avoids the need for extra HTML elements, keeping the code clean and efficient.


**Links to Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Tricks on advanced techniques:** [https://css-tricks.com/](https://css-tricks.com/) (Search for articles on `clip-path` and CSS animations)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

