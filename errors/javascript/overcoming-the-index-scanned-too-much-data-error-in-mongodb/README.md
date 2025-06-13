# 🐞 Overcoming the "Index Scanned Too Much Data" Error in MongoDB


This document addresses a common performance issue in MongoDB: the "index scanned too much data" warning or error. This often arises when queries don't effectively utilize indexes, leading to slow query execution.  We'll focus on a scenario involving inefficient querying of a collection of product documents.


**Description of the Error:**

When MongoDB's query planner selects an index but still needs to scan a significant portion of the collection to satisfy the query, it logs a warning or might even throw an error indicating that the index "scanned too much data."  This implies that the index, while used, isn't sufficiently selective, forcing the database to examine more documents than ideal, resulting in performance degradation. The error message might vary slightly depending on the MongoDB version and logging level, but generally hints at inefficient index usage despite the presence of an index.


**Scenario:**  We have a `products` collection with documents containing fields like `productName`, `category`, `price`, and `inventory`.  We have an index on `category` but frequently execute queries that involve filtering by `category` and `price`.

**Inefficient Query (leading to the error):**

```javascript
db.products.find( { category: "Electronics", price: { $gt: 100 } } )
```

**Fixing the Problem Step-by-Step:**

1. **Analyze the Query:** The query above utilizes the index on `category` to quickly locate documents in the "Electronics" category. However, it then needs to further filter these documents based on `price`,  resulting in the "index scanned too much data" issue because the index on `category` alone is not sufficient to narrow down the results effectively.

2. **Create a Compound Index:**  The solution is to create a compound index that includes both `category` and `price`.  This compound index will allow the query planner to use the index for both filtering conditions, significantly improving performance.

```javascript
db.products.createIndex( { category: 1, price: 1 } )
```

3. **Verify the Index:** Check that the index has been created successfully.

```javascript
db.products.getIndexes()
```

4. **Re-run the Query:** After creating the compound index, re-run the original query.  You should observe a significant performance improvement with fewer documents scanned and a faster query execution time.

```javascript
db.products.find( { category: "Electronics", price: { $gt: 100 } } )
```

5. **Monitor Performance:** Use the `explain()` method to analyze the query execution plan and verify that the compound index is being used effectively.

```javascript
db.products.find( { category: "Electronics", price: { $gt: 100 } } ).explain()
```


**Explanation:**

The original query only benefited from the single-field index on `category`. This index sped up the process of finding documents belonging to the "Electronics" category. However, subsequent filtering by `price` required scanning a significant subset of the documents found using the initial index, leading to the "index scanned too much data" problem.

Creating a compound index on `category` and `price` allows MongoDB to efficiently filter by both fields simultaneously, using the index to narrow down the search space significantly. The order of fields in the compound index matters; in this example, `category` is the leading field because we expect the `category` filter to be more selective than the `price` filter.  If you frequently use queries filtering by `price` first, you might consider creating a separate index like `{price:1, category:1}`.


**External References:**

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [MongoDB Query Optimization](https://www.mongodb.com/docs/manual/core/query-optimization/)
* [Understanding MongoDB Explain Output](https://www.mongodb.com/docs/manual/reference/method/db.collection.explain/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

