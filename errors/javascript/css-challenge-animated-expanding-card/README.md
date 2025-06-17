# 🐞 CSS Challenge:  Animated Expanding Card


This challenge focuses on creating an animated expanding card using pure CSS.  The card will subtly expand on hover, providing a visually appealing user interaction. We'll use CSS3 transitions and transforms to achieve this effect.  No JavaScript is required.

**Description of the Styling:**

The card will be a simple rectangle with a background color, some padding, and text content.  The key styling is the application of CSS transitions and transforms to the `transform` property on hover. This will smoothly scale the card up slightly when the mouse hovers over it.  We'll also add a subtle box-shadow to enhance the 3D effect.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out; /* Smooth transition on hover */
}

.card:hover {
  transform: scale(1.05); /* Expand slightly on hover */
  box-shadow: 3px 3px 8px rgba(0, 0, 0, 0.2); /* Stronger shadow on hover */
}

/*Example content styling*/
.card h2{
  margin-top:0;
}
.card p{
  margin-bottom:0;
}
</style>
</head>
<body>

<div class="card">
  <h2>Expanding Card</h2>
  <p>This is an example of an expanding card created using only CSS.  Hover over the card to see the animation.</p>
</div>

</body>
</html>
```

**Explanation:**

* **`transition: transform 0.3s ease-in-out;`**: This line is crucial. It tells the browser to smoothly animate any changes to the `transform` property over 0.3 seconds, using an "ease-in-out" timing function for a natural feel.

* **`transform: scale(1.05);`**: This line, applied on hover, scales the card up by 5% in both dimensions.  You can adjust the `1.05` value to control the expansion amount.

* **`box-shadow`**: The box-shadow property adds a subtle shadow, enhancing the 3D appearance of the card. The shadow's intensity is also increased on hover for a more dramatic effect.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box-shadow:** [MDN Web Docs - CSS box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

