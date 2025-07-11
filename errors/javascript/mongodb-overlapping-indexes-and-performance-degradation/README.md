# 🐞 MongoDB: Overlapping Indexes and Performance Degradation


## Description of the Error

A common performance problem in MongoDB stems from creating overlapping indexes.  Overlapping indexes, where one index is a subset of another, lead to increased write times and unnecessary disk space consumption.  While MongoDB will choose the most appropriate index for a query, having redundant indexes can significantly slow down write operations as the database must update multiple indexes for every document insertion or modification. This can especially impact applications with high write loads, leading to noticeable performance degradation and potentially impacting application responsiveness.


## Step-by-Step Code Fix

Let's imagine we have a collection called `products` with the following schema:

```json
{
  "category": "Electronics",
  "subcategory": "Laptop",
  "brand": "Dell",
  "price": 1200
}
```

We've mistakenly created two indexes:

```javascript
// First index: category, subcategory
db.products.createIndex( { category: 1, subcategory: 1 } )

// Second index: category, subcategory, brand (overlapping!)
db.products.createIndex( { category: 1, subcategory: 1, brand: 1 } )
```

The second index overlaps with the first; it includes all the fields of the first and adds the `brand` field.  This is redundant. To fix this, we need to drop the less efficient index (the more comprehensive one in this case)


```javascript
// Drop the overlapping index
db.products.dropIndex( { category: 1, subcategory: 1, brand: 1 } )

//Verify remaining indexes
db.products.getIndexes()
```

This will leave only the `category` and `subcategory` index, which is sufficient for many queries involving these two fields. If queries requiring `brand` are frequent, we can create a compound index including brand:


```javascript
//if brand queries are frequent create a new efficient index
db.products.createIndex( { category: 1, brand:1 } )

//verify indexes again.
db.products.getIndexes()
```


## Explanation

Overlapping indexes create redundancy. MongoDB needs to update both indexes on every write, which consumes extra time and resources. Choosing the right indexes requires careful consideration of query patterns.  Generally, you want compound indexes that cover the fields used in the `$query` part of your find operations.  Avoid creating indexes on frequently updated fields unless absolutely necessary for query performance as these updates add overhead.


## External References

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [Understanding Index Selection in MongoDB](https://www.mongodb.com/blog/post/understanding-index-selection-in-mongodb)
* [MongoDB Performance Tuning](https://www.mongodb.com/docs/manual/tutorial/optimize-for-performance/)


## Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

