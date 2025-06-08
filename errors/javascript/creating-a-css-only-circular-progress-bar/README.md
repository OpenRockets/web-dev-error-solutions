# 🐞 Creating a CSS-Only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS. No JavaScript is required.  We'll leverage CSS's `conic-gradient` function for a clean and efficient solution. This example uses plain CSS; adapting it to Tailwind CSS is straightforward (explained in the code section).

**Description of the Styling:**

The progress bar is created using a single `<div>` element.  The visual effect is achieved using a combination of `border-radius`, `conic-gradient`, and `transform` properties. The `conic-gradient` creates the circular gradient, representing the progress. The percentage of the circle filled is dynamically controlled by rotating the gradient using `transform: rotate()`.

**Full Code (Plain CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: conic-gradient(
    #f0f0f0 0%,
    #f0f0f0 calc(100% - var(--progress)),
    #4CAF50 calc(100% - var(--progress)),
    #4CAF50 100%
  );
}
</style>
</head>
<body>

<div class="progress-ring" style="--progress: 75%;"></div>

</body>
</html>
```

**Full Code (with Tailwind CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar with Tailwind</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<style>
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: conic-gradient(
    gray-300 0%,
    gray-300 calc(100% - var(--progress)),
    green-500 calc(100% - var(--progress)),
    green-500 100%
  );
}
</style>
</head>
<body>

<div class="progress-ring w-32 h-32 rounded-full" style="--progress: 75%;"></div>

</body>
</html>

```

**Explanation:**

* **`width` and `height`:**  Sets the size of the progress ring.
* **`border-radius: 50%;`:** Creates a perfect circle.
* **`conic-gradient()`:** This is the key. It creates a circular gradient.  The parameters define the colors and their positions.  `calc(100% - var(--progress))` dynamically calculates the end point of the lighter color based on the `--progress` custom property.
* **`--progress` Custom Property:** This CSS variable allows us to easily change the progress percentage by adjusting its value (e.g., `style="--progress: 50%;"` for 50% progress).  This makes it very easy to dynamically update the progress from JavaScript if needed (although not required for this example).
* **Tailwind Integration:** The Tailwind CSS version uses Tailwind's utility classes (`w-32`, `h-32`, `rounded-full`) instead of inline styles for width, height, and border-radius.  The colors are also replaced with Tailwind color names.


**Links to Resources to Learn More:**

* **MDN Web Docs on `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks (general CSS learning):** [https://css-tricks.com/](https://css-tricks.com/)
* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

