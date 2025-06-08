# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS. No JavaScript is required.  This utilizes CSS gradients and the `conic-gradient()` function (CSS3) for a smooth and visually appealing effect.

**Description of the Styling:**

The circular progress bar is achieved using a combination of a circle created with `border-radius: 50%`, a background color, and a `conic-gradient()` for the progress fill. The `conic-gradient()` function allows us to create a gradient that fills a circular area based on the angle specified. We manipulate this angle to represent the percentage of progress.  We also use a pseudo-element (`::before`) to create the visual progress indicator within the circle.

**Full Code:**

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
  background-color: #f0f0f0; /* Light gray background */
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: conic-gradient(#4CAF50 75%, #f0f0f0 75%); /* Green fill, 75% progress */
  mask: radial-gradient(farthest-side, #fff 80%, transparent 80%);
}

.progress-ring .percentage {
  position: absolute;
  font-size: 1.2em;
  font-weight: bold;
  color: #333; /* Dark text color */
}
</style>
</head>
<body>

<div class="progress-ring">
  <div class="percentage">75%</div>
</div>

</body>
</html>
```

To change the percentage, simply modify the first value in the `conic-gradient()` function. For example, `conic-gradient(#4CAF50 50%, #f0f0f0 50%)` would create a half-filled circle.  You can also easily adjust colors.

**Explanation:**

1. **Base Circle:** The `.progress-ring` class creates the base circle using `border-radius: 50%`.
2. **Pseudo-element:** The `::before` pseudo-element creates the progress fill.
3. **`conic-gradient()`:** This function creates the circular gradient. The first color (`#4CAF50` - a green color in this case) represents the filled portion, and the second color (`#f0f0f0`) represents the unfilled portion. The percentage value (e.g., `75%`) determines the proportion of the circle filled with the first color.
4. **`mask`:** The `mask` property is used to create a sharp edge for the progress indicator and prevent the slight blurring that can occur at the edges of the conic gradient.
5. **Percentage Text:** The `.percentage` class displays the progress percentage in the center of the circle.


**Links to Resources to Learn More:**

* **MDN Web Docs - `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **MDN Web Docs - CSS Gradients:** [https://developer.mozilla.org/en-US/docs/Web/CSS/gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/gradients)
* **CSS-Tricks (various gradient tutorials):** [https://css-tricks.com/](https://css-tricks.com/) (search for "CSS gradients")


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

