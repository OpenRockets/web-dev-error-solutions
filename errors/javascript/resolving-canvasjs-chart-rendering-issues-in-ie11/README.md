# 🐞 Resolving CanvasJS Chart Rendering Issues in IE11


This document addresses a common problem encountered when using CanvasJS charts within Internet Explorer 11 (IE11):  charts failing to render correctly or appearing blank.  This is often due to IE11's limitations with certain Canvas features or compatibility issues with older versions of CanvasJS.

**Description of the Error:**

In IE11, a CanvasJS chart might display as a blank space, a broken image, or render incorrectly with missing elements. The browser's developer console may or may not reveal specific error messages, but the core problem lies in the browser's limited support for the rendering techniques employed by CanvasJS.

**Fixing Steps (Code):**

The most effective solution involves using a polyfill to bridge the compatibility gap between CanvasJS and IE11.  We'll use the `excanvas` library.

**Step 1: Include the excanvas library:**

First, download the `excanvas.js` file (available through various sources; see external references). Then, include it in your HTML file *before* including the CanvasJS script.


```html
<!DOCTYPE HTML>
<html>
<head>
<title>CanvasJS IE11 Fix</title>
<script src="excanvas.js"></script> <script src="https://canvasjs.com/assets/script/canvasjs.min.js"></script> </head>
<body>
<div id="chartContainer" style="height: 300px; width: 100%;"></div>
<script>
//Your chart code will go here (see step 2)
</script>
</body>
</html>
```

**Step 2:  Your CanvasJS chart code:**

This remains unchanged, assuming you've already written your CanvasJS chart setup. Here's an example:


```javascript
window.onload = function () {
    var chart = new CanvasJS.Chart("chartContainer", {
        title: {
            text: "IE11 Compatible Chart"
        },
        data: [{
            type: "column",
            dataPoints: [
                { label: "Apple", y: 10 },
                { label: "Orange", y: 15 },
                { label: "Banana", y: 25 }
            ]
        }]
    });
    chart.render();
}
```

**Explanation:**

`excanvas.js` provides a compatibility layer for older browsers lacking full canvas support.  By including it before the CanvasJS script, you essentially give CanvasJS an environment where it can successfully render the chart, even in IE11.  This polyfill emulates the Canvas API in IE11, allowing CanvasJS to function as intended.

**External References:**

* **CanvasJS Documentation:** [https://canvasjs.com/](https://canvasjs.com/)  (Check for specific IE11 compatibility notes.)
* **excanvas (search for it):**  You'll find various sources for `excanvas.js` through a web search. Be cautious to download it from a reputable source.  Note that excanvas is outdated and might not be actively maintained, hence the importance of finding a trusted source.  Consider alternative approaches like upgrading to a modern browser if possible.

**Important Note:** While `excanvas` provides a solution, upgrading to a modern browser (or using conditional rendering to bypass IE11 entirely) is strongly recommended for long-term maintainability and security.  IE11 is no longer supported by Microsoft.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

