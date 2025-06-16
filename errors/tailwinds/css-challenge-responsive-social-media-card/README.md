# 🐞 CSS Challenge:  Responsive Social Media Card


This challenge involves creating a responsive social media card using CSS. The card should adapt its layout seamlessly to different screen sizes, maintaining a clean and visually appealing design. We'll use plain CSS (no CSS frameworks like Tailwind here for demonstration purposes, although you could easily adapt this to use Tailwind).

**Description of the Styling:**

The card will feature:

* A header with a profile image and username.
* A main content area displaying a short message.
* A footer with buttons for liking and sharing.
* Responsive design adapting to various screen sizes (mobile, tablet, desktop).
* Clean and modern aesthetics.

**Full Code:**

```css
/* Styles for the Social Media Card */
.social-card {
  background-color: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  width: 300px; /* Default width, will be responsive */
  margin: 20px auto; /* Center the card */
}

.social-card img {
  width: 100%;
  height: auto;
  display: block; /* Prevents extra space below image */
}

.header {
  padding: 15px;
  display: flex;
  align-items: center;
}

.profile-image {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-right: 10px;
}

.username {
  font-weight: bold;
  font-size: 16px;
}

.content {
  padding: 15px;
  font-size: 14px;
  line-height: 1.6;
}

.footer {
  padding: 15px;
  display: flex;
  justify-content: space-around; /* Distribute buttons evenly */
}

.footer button {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
}


/* Media Queries for Responsiveness */
@media (max-width: 400px) {
  .social-card {
    width: 90%; /* Make card take up most of screen width on smaller screens */
  }
}
```

**HTML (required to use the CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Social Media Card</title>
<link rel="stylesheet" href="styles.css"> </head>
<body>
  <div class="social-card">
    <div class="header">
      <img src="profile.jpg" alt="Profile Picture" class="profile-image">
      <div class="username">John Doe</div>
    </div>
    <div class="content">
      This is a sample social media post.  It could be about anything!
    </div>
    <div class="footer">
      <button>Like</button>
      <button>Share</button>
    </div>
  </div>
</body>
</html>
```

Remember to replace `"profile.jpg"` with the actual path to your profile image.


**Explanation:**

The CSS uses selectors to target specific elements within the HTML structure.  The `@media` query allows the card to adapt its width based on the screen size.  The flexbox layout is used for easy alignment and distribution of elements within the header and footer.  Padding and margins provide spacing.


**Resources to Learn More:**

* **CSS Tutorial:** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - A comprehensive resource for learning CSS.
* **Flexbox Tutorial:** [CSS-Tricks Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) -  A great guide to understanding and using flexbox.
* **Responsive Design:** [Google Web Fundamentals Responsive Design](https://developers.google.com/web/fundamentals/design-and-ux/responsive/) -  Learn about creating responsive websites.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

