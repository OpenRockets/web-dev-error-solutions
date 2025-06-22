# 🐞 CSS Challenge:  Centered, Responsive Image Card


This challenge involves creating a responsive image card that is centered on the page, regardless of screen size.  The card will contain an image, a title, and a short description.  We'll use CSS3 for styling.

**Description of the Styling:**

The card will have a consistent border-radius, padding, and a subtle shadow.  The image will be responsive, scaling down gracefully to fit within the card without distortion.  The title will be prominently displayed above the image, and the description will appear below. The entire card will be horizontally centered, and its width will adjust responsively.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Centered Image Card</title>
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
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
  max-width: 400px; /* Adjust as needed */
  width: 90%; /* Maintain responsiveness */
}

.card img {
  max-width: 100%;
  height: auto;
  display: block; /* Prevents extra space below image */
  margin: 0 auto 10px auto; /* Center the image */
  border-radius: 5px;
}

.card h2 {
  margin-bottom: 10px;
}

.card p {
  line-height: 1.6;
}
</style>
</head>
<body>

<div class="card">
  <h2>Beautiful Sunset</h2>
  <img src="https://via.placeholder.com/350x200" alt="Sunset Image">
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.  Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
</div>

</body>
</html>
```

**Explanation:**

* **`body` styles:** Uses flexbox for easy centering of the card.  `min-height: 100vh;` ensures the content fills the viewport.
* **`.card` styles:** Sets the background color, border radius, box shadow, padding, and text alignment. `max-width` and `width` ensure responsiveness.
* **`.card img` styles:** Makes the image responsive and centers it within the card. `display: block;` is crucial for preventing extra space below the image.
* **`.card h2` and `.card p` styles:** Add some basic styling for the title and description.


**Resources to Learn More:**

* **CSS Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **CSS Box Model:** [https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing](https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing)
* **Responsive Images:** [https://developer.mozilla.org/en-US/docs/Web/Responsive_Images](https://developer.mozilla.org/en-US/docs/Web/Responsive_Images)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

