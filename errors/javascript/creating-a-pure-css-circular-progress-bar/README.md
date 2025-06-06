# 🐞 Creating a Pure CSS Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required! This utilizes CSS3's `clip-path` and `transform` properties to achieve the effect.  This example will create a progress bar that is 75% complete.  You can easily adjust this value.

**Description of the Styling:**

The progress bar consists of two concentric circles. The outer circle acts as the background, while the inner circle represents the progress.  We use `clip-path` to create a circular segment that represents the filled portion of the progress bar. The `transform: rotate()` property is used to dynamically rotate this segment based on the percentage of progress.

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
  position: relative;
}

.progress-ring .progress-ring-background {
  width: 100%;
  height: 100%;
  border: 5px solid #ddd; /* Background circle */
  border-radius: 50%;
  position: absolute;
}

.progress-ring .progress-ring-progress {
  width: 100%;
  height: 100%;
  border: 5px solid #4CAF50; /* Progress circle */
  border-radius: 50%;
  position: absolute;
  clip-path: polygon(50% 50%, 75% 0%, 100% 50%, 75% 100%, 50% 100%, 25% 100%, 0 50%, 25% 0%); /* Adjust percentage as needed*/
  transform: rotate(270deg); /* 75% progress = 75% * 360deg = 270deg */
  transform-origin: 50% 50%;
}

</style>
</head>
<body>

<h1>CSS Circular Progress Bar</h1>

<div class="progress-ring">
  <div class="progress-ring-background"></div>
  <div class="progress-ring-progress"></div>
</div>

</body>
</html>
```

**Explanation:**

* **`progress-ring`:** This class sets the size and shape of the overall progress bar.
* **`progress-ring-background`:** This creates the outer circle, providing context for the progress.
* **`progress-ring-progress`:** This is the crucial part.
    * `clip-path`: This creates the circular segment. The polygon coordinates define the shape.  Adjusting the `75%` values will alter the progress.
    * `transform: rotate()`: This rotates the segment, creating the progress effect.  The calculation (`75% * 360deg`) determines the rotation angle based on the percentage.
    * `transform-origin`:  This sets the center point of rotation.

To change the percentage, modify the `clip-path` polygon points and the `rotate()` value accordingly. For example, for 50% progress:

* `clip-path: polygon(50% 50%, 50% 0%, 100% 50%, 50% 100%, 50% 100%, 50% 100%, 0 50%, 50% 0%);`
* `transform: rotate(180deg);`

**Resources to Learn More:**

* [MDN Web Docs - clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* [MDN Web Docs - transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [CSS Tricks](https://css-tricks.com/)  (General resource for CSS techniques)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

