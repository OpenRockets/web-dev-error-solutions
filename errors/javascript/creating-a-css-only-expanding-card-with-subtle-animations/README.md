# 🐞 Creating a CSS-only Expanding Card with Subtle Animations


This project demonstrates how to create an expanding card effect using only CSS.  No JavaScript is required.  The effect features a subtle animation when the card is hovered over, expanding its content area to reveal more information. This is achieved primarily using CSS transitions and transforms.

**Description of the Styling:**

The card is composed of a container (`div` with class `card`) that holds a header (`div` with class `card-header`) and a content area (`div` with class `card-content`). The primary styling focuses on the `card-content` element.  It initially has a reduced height and `overflow: hidden`, hiding its contents. On hover, the `height` is increased using a CSS transition, revealing the hidden content smoothly.  A subtle transform is also applied to create a slight lift effect.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Expanding Card</title>
<style>
.card {
  background-color: #f2f2f2;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  overflow: hidden; /* Hide content overflow */
  transition: box-shadow 0.3s ease; /* Smooth shadow transition */
  width: 300px;
}

.card:hover {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Enhanced shadow on hover */
}

.card-header {
  background-color: #4CAF50;
  color: white;
  padding: 15px;
  text-align: center;
}

.card-content {
  padding: 15px;
  height: 100px; /* Initially hidden height */
  overflow: hidden; /* Hide initially */
  transition: height 0.3s ease; /* Smooth height transition */
}

.card:hover .card-content {
  height: 200px; /* Expanded height on hover */
  transform: translateY(-5px); /* Slight lift effect */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-header">Expanding Card</div>
  <div class="card-content">
    This is the content of the card.  This text is initially hidden and reveals on hover.  You can add more content here to demonstrate the expanding effect.
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **`transition` property:** This is crucial for the smooth animation. It specifies the properties (`height`, `box-shadow`) that should animate, the duration (`0.3s`), and the easing function (`ease`).
* **`overflow: hidden;`:**  This hides any content that exceeds the specified height of the `.card-content` element, ensuring a clean cut-off before expansion.
* **`transform: translateY(-5px);`:** This subtly lifts the card on hover, adding a small visual cue.
* **`height` manipulation:** The core of the effect is changing the `height` of the `.card-content` on hover, revealing the hidden content.

**Links to Resources to Learn More:**

* **CSS Transitions:** [MDN Web Docs - CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Box Model:** [Understanding the CSS Box Model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

