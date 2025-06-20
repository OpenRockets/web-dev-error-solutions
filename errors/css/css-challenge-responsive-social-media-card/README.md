# 🐞 CSS Challenge:  Responsive Social Media Card


This challenge involves creating a responsive social media card using CSS.  The card will feature an image, title, description, and social media icons.  We'll utilize a simple, clean design suitable for various social media platforms.  This example uses CSS Grid for layout, but could be adapted to other layout methods like Flexbox.


**Description of the Styling:**

The card will be rectangular with rounded corners. The image will occupy the top portion, followed by the title, description, and social media icons arranged horizontally at the bottom.  The design prioritizes responsiveness, adapting gracefully to different screen sizes.  We'll aim for a modern, clean aesthetic.


**Full Code (CSS only):**

```css
.social-card {
  width: 300px;
  border-radius: 8px;
  overflow: hidden; /* Prevents image overflow */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  display: grid;
  grid-template-rows: auto 1fr auto; /* Image, content, icons */
  grid-gap: 10px;
}

.social-card img {
  width: 100%;
  height: auto;
  object-fit: cover; /* Maintain aspect ratio */
}

.social-card .content {
  padding: 15px;
}

.social-card h3 {
  margin-top: 0;
  font-size: 1.2em;
}

.social-card p {
  font-size: 0.9em;
  line-height: 1.5;
  margin-bottom: 10px;
}

.social-card .icons {
  display: flex;
  justify-content: space-around;
  padding: 10px;
}

.social-card .icons a {
  display: inline-block;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: #f0f0f0;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
  color: #333;
}


/* Responsive Adjustments */
@media (max-width: 350px) {
  .social-card {
    width: 90vw; /* Adjust width for smaller screens */
  }
}
```

**HTML (example - to be paired with the CSS above):**

```html
<div class="social-card">
  <img src="your-image.jpg" alt="Social Media Card Image">
  <div class="content">
    <h3>Awesome Title</h3>
    <p>This is a short description of the content of this social media card.</p>
  </div>
  <div class="icons">
    <a href="#"><i class="fab fa-facebook"></i></a>
    <a href="#"><i class="fab fa-twitter"></i></a>
    <a href="#"><i class="fab fa-instagram"></i></a>
  </div>
</div>
```

Remember to replace `"your-image.jpg"` with the actual path to your image and include Font Awesome (or similar icon library) for the social media icons.


**Explanation:**

The CSS uses `grid-template-rows` to divide the card into three sections: image, content, and icons.  `grid-gap` adds spacing.  Media queries handle responsiveness. The HTML provides a basic structure, easily customizable with different content.


**Links to Resources to Learn More:**

* **CSS Grid Layout:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)
* **CSS Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* **Responsive Web Design:** [https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

