# 🐞 Resolving CanvasJS Chart Rendering Issues in IE11


## Description of the Error

A common problem encountered when using CanvasJS charts in Internet Explorer 11 (IE11) is the failure of the chart to render correctly, often resulting in a blank space where the chart should appear or displaying only a partially rendered chart. This is primarily due to IE11's limited support for modern JavaScript features and its older rendering engine compared to other modern browsers.  The error messages might not be very explicit, often manifesting as a blank space or an incomplete chart, with no obvious console errors.


## Step-by-Step Code Fix

This example focuses on ensuring compatibility with IE11 by incorporating polyfills for missing features.  We'll assume you are already including the CanvasJS library correctly.

**Step 1: Include necessary polyfills.**

IE11 lacks support for some `Array` methods and other features used by CanvasJS.  We'll use a polyfill library like `core-js`. You can install it using a package manager like npm:

```bash
npm install core-js
```

Then, include it in your HTML file:

```html
<script src="node_modules/core-js/client/shim.min.js"></script>
```

**Step 2:  Include CanvasJS Library**

Ensure you have included the CanvasJS library correctly.  Replace `"path/to/canvasjs.min.js"` with the actual path to your CanvasJS library file.

```html
<script src="path/to/canvasjs.min.js"></script>
```

**Step 3:  Create and Render your Chart (Example)**

This example creates a simple chart. Adapt it to your specific data and chart type.

```html
<!DOCTYPE HTML>
<HTML>
<HEAD>
<title>CanvasJS IE11 Fix</title>
<script src="node_modules/core-js/client/shim.min.js"></script>
<script src="path/to/canvasjs.min.js"></script>
</HEAD>
<BODY>
<div id="chartContainer" style="height: 300px; width: 100%;"></div>
<script>
window.onload = function () {

var chart = new CanvasJS.Chart("chartContainer", {
	animationEnabled: true,
	title:{
		text: "IE11 Compatible Chart"
	},
	data: [{
		type: "column",
		dataPoints: [
			{ label: "Apple",  y: 10  },
			{ label: "Orange", y: 15  },
			{ label: "Banana", y: 25  }
		]
	}]
});
chart.render();

}
</script>
</BODY>
</HTML>

```

## Explanation

The core issue is that IE11 lacks support for certain ES6+ features and modern JavaScript functionalities that CanvasJS relies upon. The `core-js` library provides polyfills, which are essentially code snippets that simulate the missing functionality, making it appear as though IE11 supports those features.  By including `core-js`, we bridge the compatibility gap between CanvasJS's expectations and IE11's capabilities.  Without this, CanvasJS might fail to initialize or render properly.


## External References

* **CanvasJS Documentation:** [https://canvasjs.com/](https://canvasjs.com/)  (Check their documentation for specific browser compatibility notes)
* **core-js Documentation:** [https://github.com/zloirock/core-js](https://github.com/zloirock/core-js)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

