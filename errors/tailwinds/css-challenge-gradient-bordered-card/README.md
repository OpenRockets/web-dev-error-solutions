# 🐞 CSS Challenge:  Gradient-bordered Card


This challenge focuses on creating a visually appealing card with a gradient border using CSS.  We'll achieve this using only CSS, specifically leveraging CSS3 gradients. No external libraries or frameworks like Tailwind CSS will be used to keep the focus on core CSS concepts.

**Description of the Styling:**

The goal is to build a card with rounded corners and a vibrant gradient border.  The card's content will be simple – a title and some placeholder text. The gradient border will be distinct and eye-catching, showcasing the power of CSS gradients.  We'll aim for a modern and clean aesthetic.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Gradient Border Card</title>
<style>
body {
  font-family: sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f0f0f0;
}

.card {
  background-color: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  position: relative; /* Needed for the pseudo-element */
  width: 300px;
}

.card::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  border-radius: inherit; /* Inherit border-radius from the card */
  z-index: -1; /* Place it behind the card content */
  background-image: linear-gradient(to right, #FF7F50, #FFD700, #00FF00); /* Adjust gradient colors as desired */
  margin: -5px; /* Adjust margin to control border thickness */
  padding: 5px;
}

.card h2 {
  margin-top: 0;
}

.card p {
  line-height: 1.6;
}
</style>
</head>
<body>
  <div class="card">
    <h2>Gradient Card</h2>
    <p>This is a simple card with a gradient border created using only CSS.  It demonstrates the use of the `::before` pseudo-element and linear-gradients to achieve this effect.</p>
  </div>
</body>
</html>
```


**Explanation:**

* **HTML Structure:** A simple `div` with class `card` holds the content.
* **CSS Styling:**
    * `body`: Basic styling for the page background and centering the card.
    * `.card`: Styles the card background, padding, rounded corners, and shadow.
    * `.card::before`: This is a crucial part.  It's a pseudo-element that creates an overlay behind the card.  We use `background-image` to apply the linear gradient. `z-index: -1` ensures it sits behind the card content. The `margin` and `padding` properties control the thickness and offset of the gradient border.
    * `margin:-5px` creates a 5px border. Adjust to change the width.
    * `padding:5px` helps to position the gradient correctly within the margin and to avoid a potential double-border effect.


**Links to Resources to Learn More:**

* **CSS Gradients:** [MDN Web Docs - CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Using_CSS_gradients)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **Box Model:** [MDN Web Docs - Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

