# 🐞 Creating a Pure CSS Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required! This technique leverages CSS's `conic-gradient` function and some clever calculations to create a dynamic and visually appealing progress indicator.


## Description of the Styling

This progress bar is a circle divided into two sections: a filled section representing the progress and an unfilled section. The filled section uses a `conic-gradient` to create a circular arc of a specified color. The size and color of the progress bar are easily customizable through CSS variables.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
:root {
  --progress-bar-size: 100px;
  --progress-bar-color: #007bff;
  --progress-bar-background: #f0f0f0;
  --progress: 75; /* Percentage of progress (0-100) */
}

.progress-ring {
  width: var(--progress-bar-size);
  height: var(--progress-bar-size);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.progress-ring::before {
  content: '';
  position: absolute;
  width: var(--progress-bar-size);
  height: var(--progress-bar-size);
  background: conic-gradient(
    var(--progress-bar-color) calc(var(--progress) * 1%),
    var(--progress-bar-background) calc(var(--progress) * 1%)
  );
  border-radius: 50%;
  z-index: 1;
}

.progress-ring::after {
  content: attr(data-progress) '%';
  position: absolute;
  z-index: 2;
  font-size: 14px;
  color: #333;
}
</style>
</head>
<body>

<div class="progress-ring" data-progress="75"></div>

</body>
</html>
```


## Explanation

* **CSS Variables:**  The `:root` element defines custom CSS variables for easy customization of the progress bar's size, colors, and progress percentage.
* **`conic-gradient`:** This function is crucial.  It creates a circular gradient.  `calc(var(--progress) * 1%)` dynamically calculates the angle of the filled arc based on the `--progress` variable.
* **Pseudo-elements `::before` and `::after`:** `::before` creates the circular progress ring itself using the `conic-gradient`.  `::after` overlays the percentage value on top.
* **Data Attribute:** The percentage is set using the `data-progress` attribute on the `.progress-ring` element, making it easy to update dynamically if needed (though this example is static).


## Links to Resources to Learn More

* **MDN Web Docs - `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks - Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/) (A broader overview of CSS gradients, including conic gradients)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

