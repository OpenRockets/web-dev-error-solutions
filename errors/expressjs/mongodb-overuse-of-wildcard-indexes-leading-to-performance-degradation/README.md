# 🐞 MongoDB: Overuse of Wildcard Indexes Leading to Performance Degradation


## Description of the Error

A common performance bottleneck in MongoDB stems from the overuse of wildcard indexes, particularly with leading wildcards.  While wildcard indexes can seem convenient for flexible querying, they can severely impact performance due to their inability to leverage efficient index lookups.  MongoDB needs to perform a collection scan to find the relevant documents when you use a leading wildcard index because the index can't be used efficiently to pinpoint documents that match the query efficiently.  This leads to slow query times, especially with large datasets.

## Scenario:  Inefficient Search using Leading Wildcard

Let's say we have a collection called `products` with documents like this:

```json
{ "category": "electronics", "name": "Laptop XYZ" }
{ "category": "clothing", "name": "T-Shirt ABC" }
{ "category": "electronics", "name": "Phone 123" }
```

And we want to find all products where the `name` field *starts* with "Laptop".  A developer might create a wildcard index like this (incorrect approach):

```javascript
db.products.createIndex( { name: { $regex: "Laptop.*" } } )
```

This index uses a leading wildcard (`Laptop.*`).  Queries that match this index perfectly will still be slow because of the nature of the regular expressions within MongoDB.   If you try to search for "Laptop" with this leading wildcard index, MongoDB will perform a collection scan rather than utilizing the index.


## Fixing Step-by-Step

1. **Identify Inefficient Indexes:** Use the `db.products.getIndexes()` command to list all indexes on the `products` collection. Look for indexes with leading wildcards in the `name` field or similar fields where performance is degrading.

2. **Drop the Inefficient Index:** Drop the wildcard index that's causing problems:

```javascript
db.products.dropIndex( { name: { $regex: "Laptop.*" } } )
```

3. **Create a More Efficient Index:** Create a precise index that supports the common query patterns. In this case, because we want to query based on exact beginning text for the name, we should use a regular index.

```javascript
db.products.createIndex( { name: 1 } )
```

Alternatively, if you need to handle partial matches (but not starting with), you might consider text indexing, which is well suited for these types of partial searches.


```javascript
db.products.createIndex( { name: "text" } )
```

After creating this index, use the `$text` operator for queries:

```javascript
db.products.find({$text: {$search: "Laptop"}})
```


4. **Optimize Queries:**  Even with the correct index, poorly structured queries can hinder performance.  Avoid using `$regex` unless strictly necessary and prefer precise matching where feasible.

5. **Monitor Performance:** After implementing these changes, monitor the query performance using the `db.currentOp()` command or MongoDB profiling tools to ensure the improvements have taken effect.



## Explanation

Leading wildcard indexes are generally inefficient because MongoDB cannot directly use them for efficient lookups. They necessitate a full collection scan, negating the benefit of indexing.  A properly constructed index, tailored to common query patterns, leverages B-tree structures for fast lookups.  Therefore, creating specific indexes for fields with frequent queries and using the `$text` operator for text search queries significantly improves database performance.

## External References

* **MongoDB Documentation on Indexes:** [https://www.mongodb.com/docs/manual/indexes/](https://www.mongodb.com/docs/manual/indexes/)
* **MongoDB Documentation on Text Search:** [https://www.mongodb.com/docs/manual/core/text-search/](https://www.mongodb.com/docs/manual/core/text-search/)
* **MongoDB Performance Tuning Best Practices:** [https://www.mongodb.com/blog/post/performance-tuning-best-practices-for-mongodb](https://www.mongodb.com/blog/post/performance-tuning-best-practices-for-mongodb) (search for relevant sections regarding indexing)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

