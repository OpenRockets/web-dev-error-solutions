# 🐞 Overcoming the "Cannot Use $lookup with Array of Objects" Error in MongoDB Aggregation


## Description of the Error

A common challenge in MongoDB aggregation pipelines involves using the `$lookup` operator with an array of embedded documents.  The standard `$lookup` expects a field containing a single value to match on, but when dealing with an array of objects within a document, the direct use of `$lookup` results in an error. This error typically manifests as: "The $lookup stage is only supported for fields that contain an atomic value. The field 'arrayField' contains an array."

## Fixing the Problem Step-by-Step

Let's assume we have two collections: `users` and `orders`. The `users` collection contains an array of `orders` within each user document:


**users collection:**

```json
[
  {
    "_id": 1,
    "name": "Alice",
    "orders": [
      { "orderId": 101, "amount": 100 },
      { "orderId": 102, "amount": 200 }
    ]
  },
  {
    "_id": 2,
    "name": "Bob",
    "orders": [
      { "orderId": 103, "amount": 300 }
    ]
  }
]
```

**orders collection:**

```json
[
  { "_id": 101, "totalAmount": 110 },
  { "_id": 102, "totalAmount": 220 },
  { "_id": 103, "totalAmount": 330 }
]
```

Our goal is to join the `users` and `orders` collections to get the `totalAmount` for each order within the user's order array.  Direct `$lookup` won't work because `orders` is an array.

Here's the step-by-step solution using `$unwind`, `$lookup`, and `$group`:

**Step 1: Unwind the `orders` array**

This step transforms the array of orders into individual documents, allowing `$lookup` to work on each individual order.

```javascript
db.users.aggregate([
  {
    $unwind: "$orders"
  }
])
```

**Step 2: Perform the `$lookup`**

Now we can use `$lookup` to join with the `orders` collection based on the `orderId`.

```javascript
db.users.aggregate([
  {
    $unwind: "$orders"
  },
  {
    $lookup: {
      from: "orders",
      localField: "orders.orderId",
      foreignField: "_id",
      as: "orderDetails"
    }
  }
])
```

**Step 3:  Process the results and restructure**

The result of Step 2 will have an array `orderDetails` even if there is only one matching document. We can use `$replaceRoot` and `$arrayElemAt` to simplify:

```javascript
db.users.aggregate([
  {
    $unwind: "$orders"
  },
  {
    $lookup: {
      from: "orders",
      localField: "orders.orderId",
      foreignField: "_id",
      as: "orderDetails"
    }
  },
  {
    $replaceRoot: { newRoot: { $mergeObjects: [ { $arrayElemAt: [ "$orderDetails", 0 ] }, { "_id": "$_id", "name": "$name", "orderDetails": "$orderDetails" }] } }
  },
  {
    $project: {
      _id: 1,
      name: 1,
      orderId: "$orders.orderId",
      amount: "$orders.amount",
      totalAmount: "$totalAmount"
    }
  }
])
```

**Step 4 (Optional): Group back to original structure**

If you need to reconstruct the original document structure with the `totalAmount` embedded within the `orders` array, you'll need a final `$group` stage. This will be more complex and depends on your exact desired output.



## Explanation

The key to solving this problem is understanding that `$lookup` expects atomic values for the join fields.  By using `$unwind`, we deconstruct the array, allowing each order to be individually joined.  After the join, we use `$replaceRoot` and `$arrayElemAt` to make the data easier to handle. The final `$project` stage cleans up the output to only include necessary fields.  The optional `$group` stage allows for reconstruction if the original structure is required.


## External References

* **MongoDB Aggregation Framework Documentation:** [https://www.mongodb.com/docs/manual/aggregation/](https://www.mongodb.com/docs/manual/aggregation/)
* **MongoDB $lookup Operator:** [https://www.mongodb.com/docs/manual/reference/operator/aggregation/lookup/](https://www.mongodb.com/docs/manual/reference/operator/aggregation/lookup/)
* **MongoDB $unwind Operator:** [https://www.mongodb.com/docs/manual/reference/operator/aggregation/unwind/](https://www.mongodb.com/docs/manual/reference/operator/aggregation/unwind/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

