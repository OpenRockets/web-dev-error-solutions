# 🐞 Fixing VideoJS Player Controls Disappearing on Mobile


## Description of the Error

A common issue encountered when using Video.js on mobile devices is the disappearance of the player controls after a short period of inactivity.  This can severely impact user experience, as users may struggle to resume playback or adjust settings. The controls seem to auto-hide and never reappear. This problem isn't directly related to a specific error message but manifests as a missing UI element.


## Fixing Steps (Code Example)

This issue often stems from conflicts between Video.js's default behavior and mobile browser's touch interactions.  The solution usually involves explicitly disabling or configuring the autohide feature.  Below are steps to fix this:


**Step 1: Include the necessary CSS (if not already included):**

```html
<link href="https://cdn.jsdelivr.net/npm/video.js@7/dist/video-js.css" rel="stylesheet">
```

**Step 2: Initialize the Video.js player with options to disable or control autohide:**

```html
<video id="my-video" class="video-js vjs-big-play-centered" controls preload="auto" width="640" height="360" poster="my-poster.jpg" data-setup="{}">
  <source src="my-video.mp4" type="video/mp4">
  <p class="vjs-no-js">
    To view this video please enable JavaScript, and consider upgrading to a
    web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
  </p>
</video>

<script src="https://cdn.jsdelivr.net/npm/video.js@7/dist/video.js"></script>
<script>
  var player = videojs('my-video');

  // Option 1: Completely disable autohide (Not recommended for best UX)
  // player.on('ready', function() {
  //   this.controlBar.removeChild(this.controlBar.children[0]); //remove the autohide element
  // });

  // Option 2:  Configure autohide using the `userActivity` plugin (Recommended)
  player.ready(function() {
    this.on('useractive', function() {
      //console.log('user was active');
      this.controls(true);
    });
    this.on('userinactive', function(){
      //console.log('user was inactive');
      setTimeout( () => {
          this.controls(false);
      }, 2000); //hide controls after 2 seconds of inactivity
    });
  });
</script>
```

**Explanation:**

* **Option 1 (Not Recommended):** Completely removing autohide functionality might result in permanently visible controls, cluttering the screen on smaller devices.

* **Option 2 (Recommended):** This utilizes the `userActivity` plugin (implicitly included in recent Video.js versions). The `useractive` and `userinactive` events are triggered based on user interaction. This allows for a better balance between keeping the controls accessible and preventing them from constantly obstructing the video. The timeout ensures that the controls are hidden after a certain period of inactivity, optimizing the viewing experience.  Remember to adjust the 2000 (2 seconds) timeout value according to your preferences.


## External References

* **Video.js Documentation:** [https://docs.videojs.com/](https://docs.videojs.com/)  (Check for the latest version's documentation as it can change)
* **Video.js GitHub Repository:** [https://github.com/videojs/video.js](https://github.com/videojs/video.js) (For issues, community support, and potential fixes)


## Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

