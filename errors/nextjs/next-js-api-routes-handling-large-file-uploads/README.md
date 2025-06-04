# 🐞 Next.js API Routes: Handling Large File Uploads


## Description of the Error

A common issue when working with API routes in Next.js is handling large file uploads.  The default request body size limit imposed by Node.js and potentially your hosting provider might be too small for larger files, leading to errors like "Request entity too large" or similar.  This results in the upload failing, leaving the user with an unsatisfactory experience.


## Step-by-Step Code Fix

This solution involves increasing the body size limit for your API route. We'll use the `busboy` library for parsing multipart/form-data (the standard format for file uploads).

**1. Install `busboy`:**

```bash
npm install busboy
```

**2. Modify your API Route:**

```javascript
// pages/api/upload.js
import Busboy from 'busboy';

export const config = {
  api: {
    bodyParser: false, // Important: Disable Next.js's built-in body parser
  },
};

export default async function handler(req, res) {
  if (req.method === 'POST') {
    const busboy = new Busboy({ headers: req.headers });
    let file;

    busboy.on('file', (fieldname, stream, filename, encoding, mimetype) => {
      const filePath = `/tmp/${filename}`; // Choose a suitable temporary file path.  Adjust for your server environment.
      const fstream = require('fs').createWriteStream(filePath);
      stream.pipe(fstream);
      fstream.on('finish', () => {
        file = { path: filePath, filename, mimetype };
      });
    });

    busboy.on('field', (fieldname, val) => {
      console.log(`${fieldname}: ${val}`); // Handle other form fields if needed
    });

    busboy.on('finish', () => {
      if (file) {
        // Process the uploaded file. For example, save it to a database or cloud storage.
        console.log('File uploaded:', file);
        //Remember to remove the temporary file after processing
        require('fs').unlinkSync(file.path);
          res.status(200).json({ message: 'File uploaded successfully', filename: file.filename });
      } else {
        res.status(400).json({ error: 'No file uploaded' });
      }
    });

    req.pipe(busboy);
  } else {
    res.status(405).end(); // Method Not Allowed
  }
}
```

**3.  (Optional but recommended) Add error handling:**


```javascript
// ... (previous code) ...

busboy.on('error', (err) => {
  console.error('Busboy error:', err);
  res.status(500).json({ error: 'Error uploading file' });
});

fstream.on('error', (err) => {
  console.error('File stream error:', err);
  res.status(500).json({ error: 'Error writing file' });
  //Clean up the partially written file if necessary
  require('fs').unlinkSync(filePath);
});

// ... (rest of the code) ...
```


## Explanation

* **`config.api.bodyParser: false`:** This is crucial.  It disables Next.js's default body parser, preventing it from hitting the size limit before `busboy` can handle the request.
* **`Busboy`:** This library efficiently parses multipart/form-data, allowing us to handle large files without memory issues.
* **`req.pipe(busboy)`:** This pipes the incoming request stream to the `busboy` instance for processing.
* **Error Handling:** The added `error` event listeners for `busboy` and `fstream` provide robust error handling, crucial for production environments.  It also includes a cleanup step to remove a potentially partially-written file on error.
* **Temporary File:** The code saves the uploaded file to a temporary location (`/tmp/`). **You should adapt this path to your server's environment and consider using a more robust temporary file solution in production.**  Additionally, remember to remove the temporary file after processing to avoid disk space issues.  This example uses `fs.unlinkSync`.  For more sophisticated handling in a production environment, consider asynchronous removal or a more robust temporary file system.



## External References

* [Busboy Documentation](https://github.com/mscdex/busboy)
* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)
* [Node.js File System](https://nodejs.org/api/fs.html)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

