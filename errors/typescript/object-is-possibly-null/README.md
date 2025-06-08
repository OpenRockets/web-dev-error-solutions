🐞 Error: Object is possibly 'null'
This is one of the most common TypeScript errors when dealing with DOM elements or values that might not be present.

📝 Description of the Error:

TypeScript checks for null and undefined if strictNullChecks is enabled. If a variable could be null, you must handle it.

💥 Problem Code:

document.addEventListener("DOMContentLoaded", () => {
  const heading = document.getElementById("main-heading");

  heading.innerHTML = "Welcome!"; // ❌ Object is possibly 'null'
});

✅ Solution:

document.addEventListener("DOMContentLoaded", () => {
  const heading = document.getElementById("main-heading");

  if (heading) {
    heading.innerHTML = "Welcome!";
  }
});

OR using optional chaining:


document.addEventListener("DOMContentLoaded", () => {
  const heading = document.getElementById("main-heading");
  heading?.classList.add("visible");
});


🔍 Explanation:

getElementById might return null if the element isn’t found. TypeScript forces you to check for that possibility.

📚 External References: https://www.typescriptlang.org/docs/handbook/2/narrowing.html