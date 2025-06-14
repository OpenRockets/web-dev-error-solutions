# 🐞 MongoDB: Overuse of Wildcard Indexes Leading to Inefficient Queries


## Description of the Error

A common mistake in MongoDB is the overuse of wildcard indexes, especially those starting with `$**`.  While seemingly convenient for flexible querying, these indexes can significantly degrade query performance.  They create large indexes that don't efficiently target specific queries, often resulting in collection scans instead of index lookups.  This is particularly detrimental with large datasets. The query planner might choose the wildcard index even when a more specific index would be far more efficient.


## Fixing Step-by-Step (Code Example)

Let's assume we have a collection called `products` with documents like this:

```json
{
  "category": "electronics",
  "subcategory": "laptops",
  "name": "Awesome Laptop",
  "price": 1200
}
```

**Problem:** We have a wildcard index on `category` and `subcategory`, leading to poor performance when querying for specific `category` and `subcategory` combinations:

```javascript
db.products.createIndex( { "category": 1, "subcategory": "laptops" } ) //Inefficient index if you only care about laptop.
db.products.createIndex( { "category": "electronics", "subcategory":1 } ) //Inefficient index if you only care about electronics.
db.products.createIndex( { "category": 1, "subcategory":1 } ) //Better, but a bit general.
db.products.createIndex( { "category.$**": 1 } ) //Wildcard index - inefficient!
```

This wildcard index will be very large and likely not used efficiently by the query planner.

**Solution:** Replace the wildcard index with specific compound indexes that cater to common query patterns. For example:


```javascript
// Drop the inefficient wildcard index.
db.products.dropIndex( { "category.$**": 1 } )

// Create specific compound indexes for frequent queries
db.products.createIndex( { "category": 1, "subcategory": 1 } ) // Index for queries filtering by category and subcategory
db.products.createIndex( { "category": 1, "price": -1 } ) // Index for queries filtering by category and sorting by price (descending)

//Example query
db.products.find({ category: "electronics", subcategory: "laptops" }) //will use the compound index

// Another query, this time using the second index efficiently
db.products.find({ category: "electronics" }).sort({ price: -1 })
```

By creating multiple, specific compound indexes,  the query planner can select the most efficient index for each query, leading to drastically improved performance.


## Explanation

Wildcard indexes (`$**`) are powerful but come at a cost. They can significantly increase index size and lead to slower query performance.  The query planner might struggle to find a suitable index even when there is a perfectly fitting index that is not a wildcard index.

Creating specific indexes targeted at your most frequent query patterns is crucial for optimal performance.  Analyze your application's query patterns and create compound indexes that cover those patterns.  Use the `explain()` method on your queries to understand how MongoDB is utilizing indexes.


## External References

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [MongoDB Query Optimization](https://www.mongodb.com/docs/manual/reference/method/db.collection.explain/)
* [Understanding MongoDB Indexes](https://blog.mongodb.com/post/understanding-mongodb-indexes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

