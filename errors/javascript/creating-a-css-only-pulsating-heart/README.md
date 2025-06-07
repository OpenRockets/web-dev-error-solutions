# 🐞 Creating a CSS-Only Pulsating Heart


This challenge involves creating a pulsating heart animation using only CSS.  No JavaScript is needed.  We'll achieve this effect using CSS animations and transforms.  The heart itself will be created using a combination of pseudo-elements and borders.


**Description of the Styling:**

The styling consists of creating a heart shape using a cleverly positioned border on a pseudo-element (`:before`).  A second pseudo-element (`:after`) adds a subtle inner glow.  The `@keyframes` animation then smoothly scales the heart to create the pulsating effect.  We will use pure CSS for this effect, demonstrating the power and flexibility of CSS alone.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Pulsating Heart</title>
<style>
.heart {
  width: 100px;
  height: 100px;
  position: relative;
  margin: 50px auto;
}

.heart:before,
.heart:after {
  position: absolute;
  content: "";
  background-color: #e74c3c; /* Or your preferred color */
  border-radius: 50%;
}

.heart:before {
  left: 50%;
  top: 0;
  width: 50px;
  height: 50px;
  transform: translateX(-50%);
  transform-origin: 50% 100%;
  border-radius: 50% 50% 0 0;
}

.heart:after {
  left: 25%;
  top: 50%;
  width: 50px;
  height: 50px;
  transform: translateX(-50%) translateY(-50%);
  border-radius: 0 0 50% 50%;
  filter: blur(2px); /* For the inner glow effect */
  opacity: 0.5; /* Adjust opacity for glow intensity */
}


.heart {
  animation: pulse 1s infinite ease-in-out;
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
</style>
</head>
<body>

<div class="heart"></div>

</body>
</html>
```

**Explanation:**

* **`width` and `height`:** Set the overall size of the heart.
* **`position: relative`:**  Allows us to absolutely position the pseudo-elements.
* **`:before` and `:after`:** Create the two semi-circular parts of the heart.
* **`transform: translateX(-50%)`:** Centers the pseudo-elements horizontally.
* **`transform-origin`:**  Sets the point around which the scaling happens for the pulsating effect.
* **`border-radius`:** Creates the rounded shapes.
* **`filter: blur(2px)` and `opacity: 0.5`:** Creates a subtle inner glow on the :after element.
* **`@keyframes pulse`:** Defines the animation, scaling the heart up and down repeatedly.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **MDN Web Docs on Pseudo-elements:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS-Tricks (General CSS Resources):** [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

