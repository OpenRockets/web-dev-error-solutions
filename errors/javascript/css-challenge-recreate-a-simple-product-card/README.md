# 🐞 CSS Challenge: Recreate a Simple Product Card


This challenge involves creating a visually appealing product card using CSS.  We'll focus on a clean, modern design utilizing only CSS (no JavaScript or image assets). This example uses plain CSS, but you could easily adapt it to use a framework like Tailwind CSS.

**Description of the Styling:**

The product card will feature:

* A rectangular container with rounded corners.
* An image at the top.
* A title below the image.
* A short description beneath the title.
* A "View Details" button.


**Full Code (Plain CSS):**

```css
.product-card {
  width: 300px;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  background-color: #fff;
}

.product-image {
  width: 100%;
  height: 200px;
  object-fit: cover; /* Maintain aspect ratio while covering container */
}

.product-info {
  padding: 15px;
}

.product-title {
  font-size: 1.2rem;
  font-weight: bold;
  margin-bottom: 5px;
}

.product-description {
  font-size: 0.9rem;
  color: #555;
  margin-bottom: 10px;
}

.product-button {
  background-color: #007bff; /* Blue button */
  color: white;
  padding: 10px 15px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  text-decoration:none;
  display: inline-block;
}

.product-button:hover{
  background-color: #0069d9;
}
```

**HTML Structure (required to use the CSS):**

```html
<div class="product-card">
  <img src="product-image.jpg" alt="Product Image" class="product-image">
  <div class="product-info">
    <h2 class="product-title">Product Name</h2>
    <p class="product-description">Short description of the product.</p>
    <a href="#" class="product-button">View Details</a>
  </div>
</div>
```

Remember to replace `"product-image.jpg"` with the actual path to your product image.

**Explanation:**

The CSS uses common selectors and properties to style the different elements of the product card.  `box-shadow` adds a subtle shadow for depth, `border-radius` creates rounded corners, and `object-fit: cover` ensures the image fills its container while maintaining aspect ratio.  The button styling includes hover effects for better user interaction.

**Resources to Learn More:**

* **CSS Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - A comprehensive resource for learning CSS.
* **CSS Tricks:** [CSS-Tricks](https://css-tricks.com/) -  A blog and resource site with articles and tutorials on CSS.
* **FreeCodeCamp:** [FreeCodeCamp's Responsive Web Design Certification](https://www.freecodecamp.org/learn/responsive-web-design/) -  A great place to learn web development including CSS.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

