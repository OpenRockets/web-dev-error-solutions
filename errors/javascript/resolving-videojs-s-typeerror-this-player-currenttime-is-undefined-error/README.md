# 🐞 Resolving VideoJS's "TypeError: this.player_.currentTime is undefined" Error


## Description of the Error

The "TypeError: this.player_.currentTime is undefined" error in Video.js typically occurs when you attempt to access the `currentTime` property of the Video.js player before the player has fully initialized.  This is common when trying to manipulate the video's playback time within an event handler (like `ready`) that fires *before* the player's internal components are ready.  Essentially, you're trying to access a property that doesn't exist yet.

## Code: Step-by-Step Fix

This example demonstrates the problem and provides a solution using the `player.readyState` property to ensure the player is fully initialized before accessing `currentTime`.

**Problem Code:**

```javascript
var player = videojs('my-video');

player.on('ready', function() {
  console.log("Player Ready", this.player_.currentTime); //Error occurs here!
  this.currentTime(10); // Attempting to set currentTime before player is ready
});
```

**Corrected Code:**


```javascript
var player = videojs('my-video');

player.on('ready', function() {
  // Check if the player is ready before accessing currentTime
  if (this.readyState() >= 2) { //Check for `HAVE_CURRENT_DATA` or higher readyState
    console.log("Player Ready, currentTime:", this.currentTime());
    this.currentTime(10); // Now this will work correctly
  } else {
    console.warn("Player not yet ready, delaying currentTime setting.");
  }
});
```

**Explanation of the fix:**

* **`this.readyState()`:** Video.js provides a `readyState` property that indicates the player's loading state.  The values are integers representing different stages of loading.  We use `readyState >= 2` to check if the player has at least `HAVE_CURRENT_DATA`, indicating that the current playback time is available. You can find the complete list of states in the Video.js documentation (linked below).  Using this condition prevents attempts to access `currentTime` before it is defined.

* **Error Handling:** The `else` block provides basic error handling by logging a warning message.  In a more robust application, you might implement a retry mechanism or a more sophisticated way to handle the delay.


## External References

* **Video.js Documentation:** [https://docs.videojs.com/](https://docs.videojs.com/)  (Look for sections on events and the `readyState` property)
* **Video.js API Reference:** [https://videojs.com/api/](https://videojs.com/api/) (For detailed information about methods and properties)


## Explanation

The core issue revolves around asynchronous operations. The `ready` event fires when the player *begins* loading, not when it's fully initialized and ready for interaction.  The `readyState` check ensures that we wait for a sufficient level of player readiness before attempting to access or modify its properties.  This prevents the `undefined` error and ensures smoother, more reliable video playback control.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

