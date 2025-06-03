# 🐞 Fixing VideoJS's "TypeError: Cannot read properties of undefined (reading 'play')" Error


## Description of the Error

The "TypeError: Cannot read properties of undefined (reading 'play')" error in Video.js frequently arises when you attempt to call the `.play()` method on a Video.js player instance before the player has fully initialized and its internal components are ready. This typically happens when you try to initiate playback too early in your JavaScript code, often before the `<video>` element itself has been loaded or parsed by the browser.

## Fixing the Error Step-by-Step

This solution focuses on ensuring the `play()` method is called only after the player is ready.  We'll utilize Video.js's built-in `ready` event.


**Step 1: Include Video.js**

First, ensure you've correctly included the Video.js library in your HTML file. You can download it from the official website or use a CDN:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Video.js Playback</title>
  <link href="https://vjs.zencdn.net/7.20.3/video-js.css" rel="stylesheet">
  <script src="https://vjs.zencdn.net/7.20.3/video.min.js"></script>
</head>
<body>

  <video id="my-video" class="video-js" controls preload="auto" width="640" height="360" data-setup="{}">
    <source src="your-video.mp4" type="video/mp4">
    <p class="vjs-no-js">To view this video please enable JavaScript, and consider upgrading to a web browser that supports HTML5 video</p>
  </video>

  <script>
    // JavaScript code will go here
  </script>

</body>
</html>
```
Remember to replace `"your-video.mp4"` with the actual path to your video file.

**Step 2:  Use the `ready` event**


Instead of calling `.play()` directly after player initialization, we'll use the `ready` event:

```javascript
var player = videojs('my-video');

player.ready(function() {
  // This function is called when the player is ready
  this.play();
});
```

This code snippet waits until the Video.js player is fully initialized before attempting to start playback.  The `this` keyword inside the `ready` callback refers to the player instance.

**Step 3: Handling Potential Errors (Optional)**

While the `ready` event significantly reduces the risk of this error, you can add error handling for robustness:

```javascript
var player = videojs('my-video');

player.ready(function() {
  try {
    this.play();
  } catch (error) {
    console.error("Error playing video:", error);
    // Add more sophisticated error handling here, like displaying an error message to the user.
  }
});
```


## Explanation

The core issue is a race condition. Your code tries to interact with the Video.js player before it's internally prepared. The `ready` event acts as a synchronization mechanism, guaranteeing that the player's internal structures (like the `play` method) are properly defined and accessible before your code executes the `play()` function.  The `try...catch` block adds an extra layer of protection, preventing the entire script from crashing if playback still fails for some other reason.


## External References

* **Video.js Documentation:** [https://docs.videojs.com/](https://docs.videojs.com/)  (Check their API documentation for details on events and methods)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

