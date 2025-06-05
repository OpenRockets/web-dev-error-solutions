# 🐞 Next.js API Routes: Handling Large Responses and Avoiding Timeouts


## Description of the Error

A common issue when working with Next.js API routes is exceeding the default request timeout.  This often happens when your API route needs to perform lengthy operations, such as processing large datasets, making multiple external API calls, or generating complex responses.  If the operation takes longer than the server's timeout (typically around 30 seconds), the request will be aborted, resulting in a 504 Gateway Timeout error for the client.

## Problem Scenario:  Processing a Large CSV File

Let's imagine an API route that needs to process a large CSV file (e.g., 100MB+), extract relevant data, and return the processed information as a JSON response.  A naive implementation might lead to timeouts.


## Step-by-Step Code Fix

We'll address this by implementing asynchronous processing and streaming the response to prevent the server from waiting for the entire processing to complete before sending data to the client.

**1. Initial (Problematic) Code:**

```javascript
// pages/api/process-csv.js
import csv from 'csv-parser';
import fs from 'fs';

export default async function handler(req, res) {
  if (req.method === 'GET') {
    const results = [];
    fs.createReadStream('large_file.csv')
      .pipe(csv())
      .on('data', (data) => results.push(data))
      .on('end', () => {
        res.status(200).json(results);
      });
  } else {
    res.status(405).end(); // Method Not Allowed
  }
}
```

This code loads the entire CSV into memory before sending the response, which is highly inefficient and prone to timeouts for large files.

**2.  Improved Code using `ReadableStream`:**

```javascript
// pages/api/process-csv.js
import { pipeline } from 'stream';
import { promisify } from 'util';
import csv from 'csv-parser';
import fs from 'fs';

const pipelineAsync = promisify(pipeline);

export default async function handler(req, res) {
  if (req.method === 'GET') {
    res.setHeader('Content-Type', 'application/json');
    res.writeHead(200, {
      'Content-Type': 'application/json',
      'Transfer-Encoding': 'chunked', // Important for streaming
    });


    try {
      await pipelineAsync(
        fs.createReadStream('large_file.csv'),
        csv(),
        // Convert each CSV row to a JSON string and write to the response
        (data) => res.write(`\n${JSON.stringify(data)}`),
        // Close the response stream after all processing is complete
        () => res.end()
      );
    } catch (err) {
      console.error('Pipeline failed.', err);
      res.status(500).end();
    }
  } else {
    res.status(405).end(); // Method Not Allowed
  }
}

```

This revised code uses Node.js's `pipeline` to stream the CSV data.  Each row is processed and sent to the client immediately as a JSON string without waiting for the entire file to be read. The `Transfer-Encoding: chunked` header is crucial for streaming responses.


## Explanation

The key improvement lies in using `pipeline` and `ReadableStream`. Instead of loading the entire CSV into memory, the data is processed row by row.  Each processed row is immediately sent to the client as a JSON string, preventing memory issues and timeouts. The `Transfer-Encoding: chunked` header tells the client to expect a chunked response, which is essential for streaming.


## External References

* [Node.js `stream` documentation](https://nodejs.org/api/stream.html)
* [Node.js `util.promisify`](https://nodejs.org/api/util.html#utilpromisify)
* [csv-parser npm package](https://www.npmjs.com/package/csv-parser)
* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

