# 🐞 Creating a CSS-only Circular Progress Bar


This document details the creation of a circular progress bar using only CSS.  No JavaScript is required. This utilizes CSS gradients, transforms, and animations to achieve the effect.  While this example doesn't use a specific framework like Tailwind, the concepts are easily adaptable.


**Description of the Styling:**

The progress bar is constructed using a `div` element styled as a circle with a background color. A second `div` element, positioned absolutely within the first, represents the progress indicator.  We use a radial gradient to create the circular progress fill, manipulating the `mask` property to control the visible portion of the gradient, thus simulating the progress percentage.  Animations smoothly adjust the `mask-size` to represent the progress.


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
  background-color: #f0f0f0; /* Background color of the ring */
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring::before {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-image: radial-gradient(circle at right, #4CAF50 70%, transparent 70%); /* Green progress fill */
  mask: conic-gradient(transparent 0%, black 0%); /* mask to hide the gradient initially */
  mask-size: 0% 100%; /* initial mask size */
  mask-repeat: no-repeat;
  animation: progress-animation 2s linear forwards; /* animation */
}

@keyframes progress-animation {
  to {
    mask-size: 80% 100%;  /* final mask size, adjust for progress percentage */
  }
}
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

To change the percentage of progress, modify the `mask-size` value in the `@keyframes progress-animation`.  For example, `mask-size: 50% 100%;` would show 50% progress.  You can adjust the colors in the `radial-gradient` to customize the appearance.


**Explanation:**

* **Radial Gradient:** Creates a circular gradient, with the specified color transitioning to transparent.
* **Conic Gradient (used in `mask`):**  A conic gradient is used as a mask. The `transparent` section hides parts of the radial gradient, revealing only the part we want to show as the progress.
* **`mask-size`:** Controls the size of the visible area of the mask, thereby controlling the apparent progress.
* **Animation:**  The `progress-animation` keyframes smoothly changes the `mask-size` over the specified duration, creating the progress animation.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Gradients:** [https://developer.mozilla.org/en-US/docs/Web/CSS/gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)
* **MDN Web Docs on the `mask` property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/mask](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)
* **CSS-Tricks on Animations:** [https://css-tricks.com/snippets/css/keyframe-animation-syntax/](https://css-tricks.com/snippets/css/keyframe-animation-syntax/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

