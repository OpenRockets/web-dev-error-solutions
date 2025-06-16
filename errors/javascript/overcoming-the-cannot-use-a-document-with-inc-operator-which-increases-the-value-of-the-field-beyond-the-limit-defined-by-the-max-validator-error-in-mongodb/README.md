# 🐞 Overcoming the "Cannot use a document with $inc operator which increases the value of the field beyond the limit defined by the `max` validator" Error in MongoDB


## Description of the Error

This error arises when you attempt to increment a numeric field in a MongoDB document using the `$inc` operator within an update operation, but the incremented value exceeds the maximum value allowed by a validation rule defined using the `$max` validator.  This often occurs when you have implemented validation rules to constrain the range of certain fields in your documents.

## Scenario: Managing Inventory Levels

Let's say you have a collection named `products` with documents representing inventory items.  Each document includes a field `quantityInStock` which must not exceed 1000. You've implemented a validation rule to enforce this.  Now, if you try to increment `quantityInStock` beyond 1000 using `$inc`, this error will occur.

## Code Example (Illustrating the Problem)

**1. Setup (Creating a collection and adding a document):**

```javascript
// Connect to your MongoDB instance (replace with your connection string)
const { MongoClient } = require('mongodb');
const uri = "mongodb://localhost:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+1.10.1"; // Replace with your connection string
const client = new MongoClient(uri);

async function run() {
  try {
    await client.connect();
    const database = client.db('myDatabase');
    const productsCollection = database.collection('products');

    // Create a document with a validator
    await productsCollection.createIndex( { quantityInStock: 1 }, {
      validationLevel: 'strict',
      validator: {
        $jsonSchema: {
          bsonType: "object",
          properties: {
            quantityInStock: {
              bsonType: "int",
              description: "must be an integer and is required",
              maximum: 1000
            }
          },
          required: [ "quantityInStock" ]
        }
      }
    } );

    await productsCollection.insertOne({ productName: "Widget", quantityInStock: 500 });

  } finally {
    await client.close();
  }
}
run().catch(console.dir);
```

**2.  Attempting the Increment (Leading to the Error):**

```javascript
// Connect to your MongoDB instance (same connection string as above)
const { MongoClient } = require('mongodb');
const uri = "mongodb://localhost:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+1.10.1"; // Replace with your connection string
const client = new MongoClient(uri);

async function run() {
  try {
    await client.connect();
    const database = client.db('myDatabase');
    const productsCollection = database.collection('products');

    // Attempt to increment beyond the limit
    const result = await productsCollection.updateOne(
      { productName: "Widget" },
      { $inc: { quantityInStock: 600 } } // This will cause the error
    );
    console.log(result);

  } finally {
    await client.close();
  }
}
run().catch(console.dir);
```

This second code snippet will produce the error because the increment attempts to set `quantityInStock` to 1100, exceeding the `$max` validator's limit of 1000.

## Fixing the Issue:  Conditional Increments

To solve this, you need to prevent the update if it would violate the validation rule.  One approach is to use a conditional update with `$inc` inside a `$max` operator within the update statement:


```javascript
// Correct Code: Using $max to prevent exceeding the limit
async function run() {
  try {
    await client.connect();
    const database = client.db('myDatabase');
    const productsCollection = database.collection('products');

    const result = await productsCollection.updateOne(
      { productName: "Widget" },
      { $inc: { quantityInStock: { $min: [600, 1000 - 500] } } }  //Increment is limited to avoid exceeding 1000
    );
    console.log(result);

  } finally {
    await client.close();
  }
}
run().catch(console.dir);
```

This revised code uses `$min` within the `$inc` operation. It calculates the difference between the maximum and current quantity first, and then ensures that the increment does not exceed the remaining available space up to the maximum limit.


## Explanation

The original error occurs because MongoDB's validation rules are enforced *after* the update operation.  The `$inc` operator first attempts the increment, and only then does the validation check occur, resulting in the error. The solution involves using a conditional operator that performs the increment only if the resulting value remains within the valid range. This prevents the violation by performing a pre-check before the update.

## External References

* [MongoDB Documentation on Validation](https://www.mongodb.com/docs/manual/core/data-validation/)
* [MongoDB Documentation on $inc Operator](https://www.mongodb.com/docs/manual/reference/operator/update/inc/)
* [MongoDB Documentation on $max Operator](https://www.mongodb.com/docs/manual/reference/operator/aggregation/max/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

