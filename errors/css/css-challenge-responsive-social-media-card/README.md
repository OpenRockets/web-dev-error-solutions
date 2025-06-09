# 🐞 CSS Challenge:  Responsive Social Media Card


This challenge involves creating a responsive social media card using CSS. The card should adapt its layout seamlessly to different screen sizes, maintaining a clean and visually appealing design.  We'll be using pure CSS (no CSS frameworks like Tailwind for this example, to focus on fundamental CSS concepts).


**Description of the Styling:**

The social media card will feature:

* A main image at the top, taking up the full width.
* A content section below the image with:
    * A title (h2)
    * A short description (p)
    * Buttons for "Share" and "Learn More" (using `<button>` elements).
* Responsive design: The layout should adjust gracefully to different screen sizes (desktop, tablet, mobile).
* Modern and clean aesthetics.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Responsive Social Media Card</title>
<style>
body {
  font-family: sans-serif;
  margin: 20px;
}

.card {
  max-width: 600px;
  margin: 0 auto;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  border-radius: 5px;
  overflow: hidden;
}

.card-image {
  width: 100%;
}

.card-image img {
  width: 100%;
  height: auto;
  display: block; /* Prevents extra space below the image */
}

.card-content {
  padding: 20px;
}

.card-title {
  margin-bottom: 10px;
}

.card-buttons {
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
}

.card-button {
  padding: 8px 15px;
  background-color: #4CAF50;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
  text-decoration: none;
}

/* Media Query for smaller screens (e.g., mobile) */
@media (max-width: 500px) {
  .card {
    max-width: 95%; /* Adjusts the card width for smaller screens */
  }

  .card-buttons {
    flex-direction: column; /* Stacks buttons vertically on smaller screens */
    align-items: center;
  }

  .card-button {
    margin-bottom: 10px; /* Adds space between vertically stacked buttons */
  }
}

</style>
</head>
<body>

<div class="card">
  <div class="card-image">
    <img src="https://via.placeholder.com/600x300" alt="Social Media Card Image">
  </div>
  <div class="card-content">
    <h2 class="card-title">My Awesome Project</h2>
    <p>This is a short description of my amazing project.  It's really cool and you should check it out!</p>
    <div class="card-buttons">
      <button class="card-button">Share</button>
      <button class="card-button">Learn More</button>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

The CSS code utilizes selectors to style different parts of the card.  The `@media` query ensures responsiveness by adjusting the layout based on screen width.  The `flexbox` model is used for easy button arrangement, and it's adapted for smaller screens using `flex-direction: column;`.  The placeholder image URL can be replaced with your own image.


**Links to Resources to Learn More:**

* **CSS Fundamentals:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
* **Flexbox Layout:** [CSS-Tricks Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **Responsive Web Design:** [Responsive Web Design Basics](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design/Responsive_design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

