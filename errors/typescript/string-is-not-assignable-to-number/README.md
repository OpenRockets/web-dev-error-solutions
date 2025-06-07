Dealing with this error occurs when you're assigning a value of one type (e.g. string) to a variable declared as another type (e.g. number).

📝 Description of the Error:

TypeScript is a statically typed language, meaning every variable must adhere to its declared type. If you try to assign a string to a variable typed as a number, TypeScript will throw this error.

Problem Code-: 

```function calculateTotal(price: number, quantity: number) {
  return price * quantity;
}

let price: number = "100";  // ❌ Type 'string' is not assignable to type 'number'
let quantity: number = 2;

console.log(calculateTotal(price, quantity));```


Solution-: 

```function calculateTotal(price: number, quantity: number) {
  return price * quantity;
}

let price: number = 100;  // ✅ Correct type
let quantity: number = 2;

console.log(calculateTotal(price, quantity));
```

🔍 Explanation:

You declared price as a number but assigned a string. TypeScript prevents this to avoid potential runtime bugs.

📚 External References: https://www.typescriptlang.org/docs/handbook/type-compatibility.html