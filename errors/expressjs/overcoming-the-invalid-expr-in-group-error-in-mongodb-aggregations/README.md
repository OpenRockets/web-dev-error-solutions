# 🐞 Overcoming the "Invalid $expr in $group" Error in MongoDB Aggregations


## Description of the Error

The "invalid $expr in $group" error in MongoDB arises when you use the `$expr` operator within a `$group` stage of an aggregation pipeline, but the expression within `$expr` is not compatible with the `$group` operation's requirement for grouping keys to be atomic.  This typically happens when your `$expr` uses operators that return non-atomic results (like arrays or documents) as grouping keys. MongoDB needs a single, simple value to group documents efficiently.

## Scenario: Grouping by a Calculated Field with a Conditional

Let's say we have a collection named `products` with the following structure:

```json
{
  "category": "Electronics",
  "price": 100,
  "discount": 10
},
{
  "category": "Clothing",
  "price": 50,
  "discount": 5
},
{
  "category": "Electronics",
  "price": 200,
  "discount": 0
}
```

We want to group products by their discounted price and calculate the total discounted price for each group. A naive attempt might look like this:

```javascript
db.products.aggregate([
  {
    $group: {
      _id: { $expr: { $cond: { if: { $gt: ["$discount", 0] }, then: { $subtract: ["$price", "$discount"] }, else: "$price" } } },
      totalDiscountedPrice: { $sum: { $cond: { if: { $gt: ["$discount", 0] }, then: { $subtract: ["$price", "$discount"] }, else: "$price" } } }
    }
  }
]);
```

This will throw the "invalid $expr in $group" error because the `$cond` operator (conditional expression) returns different data types depending on the condition, making the `_id` (grouping key) non-atomic.

## Step-by-Step Fix

**1. Create a calculated field using `$addFields`:**

We'll first create a new field containing the discounted price using the `$addFields` stage. This ensures a consistent data type for our grouping key.

```javascript
db.products.aggregate([
  {
    $addFields: {
      discountedPrice: { $cond: { if: { $gt: ["$discount", 0] }, then: { $subtract: ["$price", "$discount"] }, else: "$price" } }
    }
  },
  // ...rest of the pipeline
]);
```


**2. Group by the new calculated field:**

Now, we can group by the newly created `discountedPrice` field, which is consistently a number.

```javascript
db.products.aggregate([
  {
    $addFields: {
      discountedPrice: { $cond: { if: { $gt: ["$discount", 0] }, then: { $subtract: ["$price", "$discount"] }, else: "$price" } }
    }
  },
  {
    $group: {
      _id: "$discountedPrice",
      totalDiscountedPrice: { $sum: "$discountedPrice" }
    }
  }
]);
```

This corrected aggregation will produce the desired result without the error.

## Explanation

The key to solving the "invalid $expr in $group" error is to ensure that the grouping key (`_id`) is always a simple, atomic value (like a number, string, or boolean).  By pre-calculating the discounted price in a separate stage (`$addFields`), we avoid the inconsistent data type issue caused by the conditional operator within `$expr`.  Using `$addFields` ensures that the grouping key is consistent and atomic across all documents, satisfying MongoDB's requirements for the `$group` operation.

## External References

* [MongoDB Aggregation Framework Documentation](https://www.mongodb.com/docs/manual/aggregation/)
* [MongoDB $expr Operator Documentation](https://www.mongodb.com/docs/manual/reference/operator/aggregation/expr/)
* [MongoDB $group Operator Documentation](https://www.mongodb.com/docs/manual/reference/operator/aggregation/group/)
* [MongoDB $addFields Operator Documentation](https://www.mongodb.com/docs/manual/reference/operator/aggregation/addFields/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

