# 🐞 Fixing VideoJS Player Controls Disappearing on Mobile


## Description of the Error

A common issue in VideoJS, especially on mobile devices, is the disappearance of the player controls after a short period of inactivity.  The controls simply vanish, leaving the user unable to pause, adjust volume, or interact with the video. This frustrating experience significantly impacts user engagement and satisfaction.  The problem often stems from a conflict between VideoJS's default behavior and mobile browser optimizations designed to save battery power and screen space.


## Step-by-Step Code Fix

This solution focuses on modifying the `userActivity` property within VideoJS's options to prevent the automatic hiding of controls.

**Before:**

Let's assume your basic VideoJS initialization looks something like this:

```javascript
videojs('my-video', {
  sources: [{
    src: 'myvideo.mp4',
    type: 'video/mp4'
  }],
  poster: 'myposter.jpg'
});
```

**After:**

We will add the `userActivity` option to explicitly control the behavior of the controls. The `userActivity` option takes a boolean value. Setting it to `true` disables the automatic hiding.

```javascript
videojs('my-video', {
  sources: [{
    src: 'myvideo.mp4',
    type: 'video/mp4'
  }],
  poster: 'myposter.jpg',
  userActivity: true // <-- This line fixes the issue
});
```

This simple addition tells VideoJS to keep the controls visible at all times, regardless of user inactivity.


## Explanation

The `userActivity` option in VideoJS manages the automatic hiding and showing of player controls based on user interaction. By default, VideoJS utilizes this feature to optimize the user experience, especially on mobile where battery life is a major concern.  However, this automatic hiding can be problematic, leading to the issue described above. Setting `userActivity` to `true` disables this automatic behavior, guaranteeing that the controls remain permanently visible on screen.


## External References

* **Video.js Documentation:** [https://docs.videojs.com/](https://docs.videojs.com/)  (While the exact documentation for `userActivity` might require searching within the site,  the official documentation is your best source for the most up-to-date information about VideoJS options and functionality.)
* **Stack Overflow (search for "VideoJS controls disappearing mobile"):**  Searching relevant keywords on Stack Overflow can often provide alternative solutions or workarounds for this common problem.


## Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

