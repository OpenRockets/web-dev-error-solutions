🐞 Error: Property 'age' does not exist on type '{ name: string }'
This happens when you try to access an object property that hasn’t been defined in its type.

📝 Description of the Error:

If you don’t explicitly define a property, TypeScript won’t allow access to it even if you think it should be there.

💥 Problem Code:

const user = {
  name: "Aryan"
};

function printUserInfo(u: { name: string }) {
  console.log(`Name: ${u.name}`);
  console.log(`Age: ${u.age}`); // ❌ Property 'age' does not exist
}

printUserInfo(user);

✅ Solution:

const user = {
  name: "Aryan",
  age: 21
};

function printUserInfo(u: { name: string; age: number }) {
  console.log(`Name: ${u.name}`);
  console.log(`Age: ${u.age}`);
}

printUserInfo(user);

🔍 Explanation:

The function was only typed to accept name, not age. You must include all expected properties in the parameter type.

📚 External References:

Interfaces – (https://www.typescriptlang.org/docs/handbook/interfaces.html)

