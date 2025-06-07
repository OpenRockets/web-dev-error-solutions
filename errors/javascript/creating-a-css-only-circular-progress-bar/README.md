# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  We'll leverage CSS3's `conic-gradient` function for a clean and efficient solution.  No JavaScript required!

**Description of the Styling:**

This progress bar uses a combination of a circle created with the `border-radius` property and a `conic-gradient` to represent the progress.  The `conic-gradient` allows us to easily create a pie-chart-like effect, where the filled portion represents the progress percentage. We'll also add some styling for visual appeal.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Circular Progress Bar</title>
<style>
.progress-ring {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: conic-gradient(
    #e74c3c 70%,
    #f1f2f6 0
  );
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
  background: #fff;
  z-index: 1;
}
.progress-ring::after {
    content: "70%";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 2;
    font-size: 1.2em;
    font-weight: bold;
}

</style>
</head>
<body>

<div class="progress-ring"></div>


</body>
</html>
```

**Explanation:**

* **`.progress-ring`**: This class styles the main circular element.  `border-radius: 50%;` creates the circle. The `conic-gradient` function defines the progress.  The first color (`#e74c3c`) is the filled portion, and the percentage (70%) determines how much of the circle is filled. The second color (`#f1f2f6`) is the background.

* **`.progress-ring::before`**: This pseudo-element creates a white circle on top to create the visual effect of a progress ring.  `z-index: 1` ensures it's layered correctly.

* **`.progress-ring::after`**: This pseudo-element adds the percentage text in the center.  `z-index: 2` places it on top of other elements.  You can easily adjust the percentage value in the content to update the progress.


**To change the percentage:**  Modify the first value in `conic-gradient` (currently 70%) to adjust the filled portion of the circle.  Also, update the text content of `.progress-ring::after` to reflect the new percentage.


**Links to Resources to Learn More:**

* **CSS Gradients:** [MDN Web Docs on Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient)
* **CSS Pseudo-elements:** [MDN Web Docs on Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS `conic-gradient`:** [CSS-Tricks article on conic-gradient](https://css-tricks.com/conic-gradient-for-circular-progress-bars/) (Search for relevant articles; conic-gradient documentation is scattered across various sites)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

