# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required! This utilizes CSS gradients and the `conic-gradient` function for a clean and efficient solution.  This example will demonstrate a simple 75% progress bar, but the percentage can easily be adjusted.

**Description of the Styling:**

The styling relies on a single `<div>` element.  We use a combination of `border-radius`, `box-sizing`, and `conic-gradient` to create the circular shape and the progress indicator.  The `conic-gradient` function allows us to define a gradient that sweeps around a circle, creating the progress bar effect.  The percentage is controlled by adjusting the angle of the gradient.


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
  box-sizing: border-box;
  border: 10px solid #f0f0f0; /* Light gray border */
  background-color: transparent; /* Needed for conic-gradient to work properly */
  position: relative; /* For positioning the percentage text */
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 5px;
  left: 5px;
  width: calc(100% - 10px);
  height: calc(100% - 10px);
  border-radius: 50%;
  background-image: conic-gradient(
    #4CAF50 75%, /* Green color for progress, adjust percentage here */
    #f0f0f0 75%  /* Light gray color for remaining progress */
  );
}

.progress-ring::after{
  content: "75%"; /* Percentage Display, adjust as needed*/
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 1.2em;
}
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

1. **`progress-ring` class:** This sets the basic dimensions, shape (circle using `border-radius: 50%`), and border of the progress bar.  `box-sizing: border-box` ensures that the border is included within the specified width and height.

2. **`::before` pseudo-element:** This creates the colored segment of the progress bar.  `conic-gradient` is the key here.  The first color (`#4CAF50` - a green color in this example) is the progress color, and its angle determines the progress percentage (75% in this case). The second color is the background color of the remaining section.

3. **`::after` pseudo-element:** This adds the percentage text to the center of the progress bar. `transform: translate(-50%, -50%)` centers the text.

**To adjust the percentage:**

Simply change the first percentage value in the `conic-gradient` function (e.g., `#4CAF50 90%` for 90% progress). Also, remember to change the percentage displayed in the `::after` pseudo-element content.  You can also change the colors used for a different visual effect.


**Links to Resources to Learn More:**

* **MDN Web Docs - `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS-Tricks - Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

