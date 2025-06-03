# 🐞 Fixing VideoJS Player Controls Disappearing on Mobile


## Description of the Error

A common issue encountered when using Video.js on mobile devices is the disappearance of the player controls after a short period of inactivity.  This frustrating user experience stems from the default behavior of many mobile browsers to hide UI elements to conserve screen real estate and improve battery life. While this is a desirable feature for general UI, it's problematic for video players where controls are essential for user interaction.  The controls might vanish completely, leaving users unable to pause, seek, or adjust the volume.

## Step-by-Step Code Fix

This solution focuses on preventing the automatic hiding of the Video.js controls on mobile devices. We'll achieve this by manipulating Video.js's options and potentially adding some CSS to ensure consistent visibility.


**1.  Include necessary CSS (optional but recommended):**

This CSS prevents the browser's default touch-based control hiding behavior. Add this to your `<style>` tag or a separate CSS file linked to your HTML.

```css
/* Prevent default mobile behavior of hiding controls */
video::-webkit-media-controls-panel {
    display: none !important;
}
video::-webkit-media-controls-overlay-play-button {
    display: none !important;
}
video::-webkit-media-controls-start-playback-button {
    display: none !important;
}
video::-webkit-media-controls {
    display: none !important;
}
```


**2. Initialize Video.js with the `userActions` option:**

This is the core of the solution. By setting `userActions` to `false` within the Video.js player options, we disable the automatic control hiding behavior provided by Video.js itself.

```javascript
// Assuming you've already included Video.js in your project

const player = videojs('my-video', {
  userActions: false, //Disable auto-hiding of controls
  // ... other Video.js options ...
});


// Example with a simple video tag and basic VideoJS initiation
<video id="my-video" class="video-js vjs-big-play-centered" controls preload="auto" width="640" height="360" poster="my-poster.jpg"
    data-setup='{ "sources": [{"src": "my-video.mp4", "type": "video/mp4"}] }'>
</video>
<script>
  videojs('my-video');
</script>

```

**3. (Optional)  Enhancements for a better user experience:**

While disabling automatic hiding solves the primary issue, you might want to add custom controls to maintain a consistent design.  Video.js allows for considerable customization. Consult their documentation for advanced control options.


## Explanation

The solution works by overriding the default behaviors of both the browser and Video.js. The CSS prevents the browser from hiding controls altogether, while the `userActions: false` option in the Video.js player initialization prevents Video.js's own mechanism for automatically hiding the controls. Combining these two approaches ensures that the controls are always visible on mobile.

## External References

* **Video.js Documentation:** [https://videojs.com/](https://videojs.com/)  (Check the documentation for the latest version and advanced customization options)
* **CSS Specificity:** [Understanding CSS Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) (Helpful if you encounter issues with CSS overriding).


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

