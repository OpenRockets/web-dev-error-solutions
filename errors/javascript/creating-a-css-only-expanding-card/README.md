# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. We'll achieve this using CSS transitions and the `max-height` property.  No JavaScript is required.


**Description of the Styling:**

The card uses a simple layout with a header and a content section. The content section initially has a `max-height` of zero, making it hidden. On hover, the `max-height` is changed to allow the content to expand to its natural height.  Smooth transitions are added using the `transition` property to create a visually appealing animation.  We'll also style the card for basic aesthetics.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content that overflows */
  transition: box-shadow 0.3s ease-in-out; /* Add transition for box-shadow */
}

.card:hover {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Enhance shadow on hover */
}

.card-header {
  background-color: #333;
  color: white;
  padding: 15px;
  text-align: center;
}

.card-content {
  max-height: 0; /* Initially hidden */
  overflow: hidden; /* Hide overflowing content */
  transition: max-height 0.5s ease-in-out; /* Smooth transition */
}

.card:hover .card-content {
  max-height: 500px; /* Allow content to expand */
}

.card-text {
  padding: 15px;
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">
    <h3>Expanding Card</h3>
  </div>
  <div class="card-content">
    <p class="card-text">This is some example text inside the expanding card.  You can add as much content as you like here.  The card will smoothly expand to accommodate it. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam id molestie diam. Sed at quam sed dui ultricies ultrices.</p>
    <p class="card-text">More example text to demonstrate the expansion.</p>
  </div>
</div>

</body>
</html>
```


**Explanation:**

* **`max-height: 0;`:** This initially hides the card content.
* **`overflow: hidden;`:** This prevents content from overflowing the card before expansion.
* **`transition: max-height 0.5s ease-in-out;`:** This creates a smooth transition effect for the `max-height` property, making the expansion animation fluid.
* **`:hover .card-content { max-height: 500px; }`:**  On hover, the `max-height` is set to `500px`, allowing the content to expand.  You can adjust this value to control the maximum height.  Removing it would allow the content to expand to its natural height.


**Links to Resources to Learn More:**

* **MDN Web Docs on CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **Understanding CSS `max-height`:** [Search for "CSS max-height" on your favorite search engine]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

