# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required! This utilizes CSS gradients and transformations to achieve a visually appealing and performant progress indicator.  We'll be focusing on a solution using pure CSS rather than a framework like Tailwind, to demonstrate the underlying concepts.


**Description of the Styling:**

This circular progress bar consists of two concentric circles. The outer circle acts as the track, while the inner circle represents the progress. We use a `radial-gradient` to create a semi-circular fill for the progress indicator, rotating it to simulate progress. The percentage of progress is controlled by a single CSS custom property (variable).


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
  background: conic-gradient(
    #ddd 0%,
    #ddd 70%,
    transparent 70%,
    transparent 100%
  ); /*Outer track*/
  position: relative;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: conic-gradient(
    #4CAF50 0%,
    #4CAF50 calc(var(--progress, 0) * 3.6deg),
    transparent calc(var(--progress, 0) * 3.6deg),
    transparent 100%
  );
}

/* Example Usage with 75% progress */
.progress-ring-example {
  --progress: 0.75;
}
</style>
</head>
<body>

<h1>CSS Circular Progress Bar</h1>

<div class="progress-ring progress-ring-example"></div>

<div class="progress-ring" style="--progress: 0.3;"></div>
<div class="progress-ring" style="--progress: 0.9;"></div>

</body>
</html>
```


**Explanation:**

* **`conic-gradient`:** This is the key to creating the circular progress. It creates a gradient that radiates from the center. We use `transparent` sections to control the visible portion of the progress.
* **`calc(var(--progress, 0) * 3.6deg)`:** This dynamically calculates the angle of the progress based on the `--progress` custom property (a value between 0 and 1 representing the percentage).  360 degrees / 100% = 3.6 degrees per percentage point.
* **`::before` pseudo-element:** This is used to create the inner circle representing the progress.
* **Custom Property `--progress`:** This allows easy modification of the progress level by simply changing its value.

**Resources to Learn More:**

* **MDN Web Docs on `conic-gradient`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks on Gradients:** [https://css-tricks.com/css-gradients/](https://css-tricks.com/css-gradients/)
* **Understanding CSS Variables (Custom Properties):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

