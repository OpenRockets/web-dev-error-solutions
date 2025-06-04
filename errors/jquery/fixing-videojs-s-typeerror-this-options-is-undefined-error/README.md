# 🐞 Fixing VideoJS's "TypeError: this.options is undefined" Error


## Description of the Error

A common error encountered when using Video.js involves a `TypeError: this.options is undefined` message.  This usually occurs during initialization, often stemming from incorrect plugin usage or improper context within the Video.js player setup.  The error points to an attempt to access `this.options` within a plugin or custom function before the Video.js player has fully initialized its options, resulting in `this.options` being undefined.

## Step-by-Step Code Fix

This example focuses on a scenario where a custom plugin attempts to access options before initialization.  Let's assume a plugin meant to add a custom control:


**Problem Code (Incorrect):**

```javascript
// Incorrect plugin code
(function($) {
  $.extend(mejs.MepDefaults, {
    myCustomOption: 'default value'
  });

  mejs.MepFeatures.push("myCustomFeature");

  mejs.players['myCustomFeature'] = function (player, options) {
    console.log(this.options.myCustomOption); // Error occurs here!
    // ...rest of plugin code
  };
})(mejs);
```

**Corrected Code:**

```javascript
// Corrected plugin code
(function($) {
  $.extend(mejs.MepDefaults, {
    myCustomOption: 'default value'
  });

  mejs.MepFeatures.push("myCustomFeature");

  mejs.players['myCustomFeature'] = function (player, options) {
    //Use the 'options' parameter passed to the function
    console.log(options.myCustomOption);  

    //or, access it via the player object after initialization completes:
    player.ready(function(){
      console.log(this.options_.myCustomOption);
    });
    // ...rest of plugin code
  };
})(mejs);

```


**Explanation of the Correction:**

The original code tries to access `this.options` inside the plugin function.  However, `this` doesn't correctly reference the Video.js player object at that point. The correction uses the `options` parameter directly passed to the plugin's initialization function. This parameter already contains the configured options. Alternatively, we can use the `player.ready()` method which ensures the options are available after the player's initialization.  This `player.ready()` is a crucial Video.js method.  Using `this.options_` within the callback ensures we're accessing the player's internal options object.


## External References

* **Video.js Documentation:** [https://videojs.com/](https://videojs.com/) (Check their plugin documentation and API for detailed information about initialization and plugins.)
* **jQuery extend():** [https://api.jquery.com/jquery.extend/](https://api.jquery.com/jquery.extend/) (Understanding how jQuery's `extend` works is vital for proper plugin setup.)

## Explanation

The core issue is a misunderstanding of the execution context within Video.js plugins and the timing of option availability. The `this` keyword might not immediately point to the player object when the plugin is invoked. Always ensure you're accessing options using the correct context, usually the arguments passed to the plugin function or via the `player.ready()` callback.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

