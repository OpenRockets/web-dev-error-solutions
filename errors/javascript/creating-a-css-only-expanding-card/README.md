# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This example utilizes only CSS3 properties, making it lightweight and efficient. No JavaScript is required.

**Description of the Styling:**

The styling utilizes a combination of CSS transitions, transforms, and pseudo-elements to achieve the expansion effect. The card is initially set to a smaller height. On hover, the `height` property is animated using a transition, and the `transform` property subtly shifts the card upwards to create a more visually appealing expansion.  A pseudo-element (`::before`) is used to create a subtle overlay effect during expansion.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  width: 200px;
  background-color: #f0f0f0;
  border-radius: 5px;
  overflow: hidden; /* Hide content outside the card */
  transition: height 0.3s ease-in-out, transform 0.3s ease-in-out; /* Smooth transition */
  transform: translateY(0); /* Initial position */
}

.card:hover {
  height: 300px; /* Expanded height */
  transform: translateY(-5px); /* Subtle lift on hover */
  box-shadow: 0 5px 10px rgba(0,0,0,0.2);
}

.card-content {
  padding: 15px;
  height: 150px; /* Initial content height */
  overflow: hidden; /* Hide overflow during transition */
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255,255,255,0.8); /* Overlay on hover */
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
}

.card:hover::before {
  opacity: 1;
}

.card h2 {
  margin-top: 0;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>This is some sample text that will be revealed when the card is hovered over.  You can add more content here.</p>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This smoothly animates changes to the `height` and `transform` properties over 0.3 seconds.
* **`transform: translateY(-5px)`:**  This creates the subtle lift effect on hover.
* **`overflow: hidden`:**  This prevents content from overflowing the card during the transition.
* **Pseudo-element (`::before`):**  This creates the overlay effect, enhancing the visual appeal.

**Links to Resources to Learn More:**

* [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [CSS-Tricks](https://css-tricks.com/) (General CSS resource)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

