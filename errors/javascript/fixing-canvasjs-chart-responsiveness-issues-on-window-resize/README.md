# 🐞 Fixing CanvasJS Chart Responsiveness Issues on Window Resize


## Description of the Error

A common problem encountered when using CanvasJS charts is maintaining their responsiveness when the browser window is resized.  Charts often fail to automatically adjust their size and layout, leading to distorted visuals, overlapping elements, or content being cut off. This usually manifests as a chart that remains fixed at its initial size, regardless of the browser window dimensions.

## Step-by-Step Code Fix

This example assumes you're using a basic CanvasJS column chart. The key is to use the `window.addEventListener` method to detect resize events and then redraw the chart with the updated dimensions.

**Original (Non-Responsive) Code:**

```javascript
window.onload = function () {
  var chart = new CanvasJS.Chart("chartContainer", {
    title: {
      text: "Sales by Year"
    },
    data: [
      {
        type: "column",
        dataPoints: [
          { label: "2021", y: 150 },
          { label: "2022", y: 200 },
          { label: "2023", y: 250 }
        ]
      }
    ]
  });
  chart.render();
};
```

**Fixed (Responsive) Code:**

```javascript
window.onload = function () {
  var chart = new CanvasJS.Chart("chartContainer", {
    title: {
      text: "Sales by Year"
    },
    data: [
      {
        type: "column",
        dataPoints: [
          { label: "2021", y: 150 },
          { label: "2022", y: 200 },
          { label: "2023", y: 250 }
        ]
      }
    ]
  });
  chart.render();

  // Add event listener for window resize
  window.addEventListener('resize', function() {
    //  This is crucial; it clears the existing chart before redrawing.  Otherwise you'll have multiple charts overlapping!
    chart.destroy();
    chart = new CanvasJS.Chart("chartContainer", { // Recreate the chart
      title: {
        text: "Sales by Year"
      },
      data: [
        {
          type: "column",
          dataPoints: [
            { label: "2021", y: 150 },
            { label: "2022", y: 200 },
            { label: "2023", y: 250 }
          ]
        }
      ]
    });
    chart.render();
  });
};
```

Remember to include the CanvasJS library in your HTML file:

```html
<script src="https://canvasjs.com/assets/script/canvasjs.min.js"></script>
```


## Explanation

The solution involves adding an event listener that triggers a redraw of the CanvasJS chart whenever the browser window is resized.  The crucial part is using `chart.destroy()` before recreating the chart.  Without this step, you'll repeatedly render the chart on top of itself, creating a messy and unresponsive display.  The code recreates the chart instance within the resize event handler to ensure the chart adapts to the new dimensions of its container.


## External References

* **CanvasJS Documentation:** [https://canvasjs.com/docs/](https://canvasjs.com/docs/)  (Look for sections on chart rendering and responsiveness)

## Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

