# 🐞 Creating a CSS-only Circular Progress Bar


This document shows how to create a circular progress bar using only CSS. No JavaScript needed! We'll use CSS gradients, masks, and animations to get this working. The technique is pretty neat and works with any framework or vanilla CSS.

**Description of the Styling:**

We'll use a simple div styled as a circle for the background. Then we'll use the `::before` pseudo-element to create the progress fill. The trick is using a radial gradient combined with a CSS mask to control how much of the progress shows. The mask property lets us hide and reveal parts of the gradient, and we animate the mask-size to create the progress effect.

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

**Explanation:**

* **`.progress-ring`**: This creates our circular container. The `border-radius: 50%` makes it a perfect circle, and we use flexbox to center any content inside.
* **`::before` pseudo-element**: This is where the magic happens! We create the progress fill using this pseudo-element so we don't need extra HTML.
* **Radial gradient**: Creates a circular color effect. The `circle at right` positions the gradient, and `70%` controls where the color stops.
* **CSS mask with conic gradient**: This is the clever part. The conic gradient mask hides portions of our radial gradient. By animating `mask-size`, we reveal more or less of the progress.
* **Animation**: Simple keyframe animation that grows the `mask-size` from 0% to 80%, creating the progress effect.

Want different progress? Just change the final `mask-size` value. For 50% progress, use `mask-size: 50% 100%`. You can also swap out the `#4CAF50` color for whatever you like.


**Resources to Learn More:**

* **MDN Web Docs on CSS Gradients:** [https://developer.mozilla.org/en-US/docs/Web/CSS/gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient)  Great reference for all gradient types.
* **MDN Web Docs on the mask property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/mask](https://developer.mozilla.org/en-US/docs/Web/CSS/mask)  The mask property documentation - this technique relies heavily on it.
* **CSS-Tricks on Animations:** [https://css-tricks.com/snippets/css/keyframe-animation-syntax/](https://css-tricks.com/snippets/css/keyframe-animation-syntax/)  Solid guide to CSS animations if you want to customize the timing.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.