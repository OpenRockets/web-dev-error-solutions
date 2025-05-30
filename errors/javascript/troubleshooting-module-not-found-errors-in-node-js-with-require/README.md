# 🐞 Troubleshooting "Module Not Found" Errors in Node.js with `require()`


This document addresses a common problem encountered in Node.js projects, particularly when using `require()` to import modules: the "Module not found" error.  This error occurs when Node.js cannot locate the module you're trying to import.

**Description of the Error:**

The error message typically looks something like this:

```
Error: Cannot find module 'module-name'
    at Function.Module._resolveFilename (node:internal/modules/cjs/loader:933:15)
    at Function.Module._load (node:internal/modules/cjs/loader:778:27)
    // ... more stack trace ...
```

Replace `module-name` with the actual name of the module you're trying to import. This error signifies that Node.js can't find the specified module in its search path.

**Code & Step-by-Step Fix:**

Let's assume you have a file `my-module.js` containing:

```javascript
// my-module.js
module.exports = {
  hello: () => console.log('Hello from my module!')
};
```

And you're trying to use it in `main.js`:

```javascript
// main.js
const myModule = require('./my-module.js');
myModule.hello();
```

If you run `node main.js` and get the "Module not found" error, here's how to troubleshoot:

**Step 1: Verify File Path and Name**

Double-check the path `'./my-module.js'` in `main.js`.  Make absolutely sure the filename and path are correct, including case sensitivity (important on Linux/macOS).  Incorrect casing or a typo is a frequent cause.

**Step 2:  Check File Existence**

Ensure `my-module.js` actually exists in the same directory as `main.js`.  If it's in a different directory, adjust the path accordingly (e.g., `require('../path/to/my-module.js')`).

**Step 3:  `node_modules` and `npm install` (for external modules)**

If `my-module.js` is an external module you installed via npm, make sure you've run `npm install` (or `yarn install`) in your project's root directory.  The module should be installed in the `node_modules` directory.  Then, you would use the module name directly (without the path):

```javascript
// For example, using Lodash:
const _ = require('lodash');
console.log(_.capitalize('hello'));
```

**Step 4:  Check `package.json` (for external modules)**

If you are still getting the error for an external module, ensure it is listed as a dependency in your `package.json` file under `dependencies` or `devDependencies`.

**Step 5:  Relative vs. Absolute Paths**

Consider using absolute paths for clarity, especially in larger projects.  This avoids ambiguity about the module's location:

```javascript
const path = require('path');
const myModule = require(path.join(__dirname, 'my-module.js'));
```

`__dirname` gives you the absolute path of the current directory.


**Explanation:**

Node.js uses a module resolution algorithm to find required modules.  It starts by looking in the current directory, then checks the `node_modules` folder, and finally follows any parent directories until it finds the module or gives up.  The error occurs when the module is not found along this search path.

**External References:**

* [Node.js Documentation on Modules](https://nodejs.org/api/modules.html)
* [npm Documentation](https://docs.npmjs.com/)


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

