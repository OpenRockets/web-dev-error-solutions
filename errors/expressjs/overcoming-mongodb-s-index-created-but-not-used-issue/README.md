# 🐞 Overcoming MongoDB's "Index Created but Not Used" Issue


This document addresses a common problem encountered when working with MongoDB indexes: the index is successfully created, yet the query still performs poorly because MongoDB doesn't utilize it. This often stems from subtle discrepancies between the query and the index definition.


**Description of the Error:**

The MongoDB profiler or `explain()` method reveals that a query is performing a `COLLSCAN` (collection scan) instead of using an available index. This indicates that the index, although present, is not being leveraged for optimization, leading to slow query performance, especially with large datasets.  The error itself isn't a specific error message but rather a performance bottleneck identifiable through query analysis.


**Scenario:** Let's assume we have a collection named `products` with documents containing fields like `category`, `name`, and `price`. We create an index on `category` and `price` but a query targeting `category` and `name` still results in a `COLLSCAN`.


**Fixing the Problem Step-by-Step:**

**1. Verify Index Existence and Definition:**

First, ensure the index exists and matches your expectations. Use the following command:

```bash
db.products.getIndexes()
```

This will list all indexes on the `products` collection.  Look for an index that includes the fields used in your query.  Example showing a compound index on `category` and `price`:

```json
[
  {
    "v" : 2,
    "key" : {
      "category" : 1,
      "price" : 1
    },
    "name" : "category_1_price_1",
    "ns" : "mydatabase.products"
  }
]
```


**2. Analyze Slow Query:**

Use the `explain()` method to understand why your query isn't using the index.

```javascript
db.products.find({ category: "Electronics", name: "Laptop" }).explain()
```

Look for the "executionStats" section in the output.  A `COLLSCAN` in "executionStages" indicates index ineffectiveness.


**3. Correcting the Query or Index:**

If the `explain()` output reveals that the query structure doesn't align with the index, you might need to modify either the query or the index.

* **Problem: Query doesn't match index fields:**  In our example, the index was created on `category` and `price`, but the query uses `category` and `name`.

* **Solution 1: Modify the query:** If possible, restructure the query to include `price`:

```javascript
db.products.find({ category: "Electronics", price: { $gt: 1000 } }).explain()
```

* **Solution 2: Create a new index:** Create a compound index that covers both `category` and `name`:

```javascript
db.products.createIndex( { category: 1, name: 1 } )
```

* **Solution 3 (Partial Index):** If the specific value range for `category` is known, use a partial index. For instance, only index documents with "Electronics" category. This improves indexing efficiency for the given category.

```javascript
db.products.createIndex( { category: 1, name: 1 }, { partialFilterExpression: { category: "Electronics" } } )
```

**4. Verify Index Usage After Correction:**

After adjusting the query or creating a new index, run the `explain()` command again to confirm that the index is now being used. You should see an "executionStats" section with an execution stage other than `COLLSCAN`, such as `IXSCAN` (index scan).


**Explanation:**

MongoDB uses indexes to speed up data retrieval. An index is a data structure that stores a sorted subset of the fields from a collection, allowing MongoDB to quickly find specific documents without needing to scan the entire collection. However, if the query doesn't precisely match the index structure (fields, order, and operators), MongoDB might not use it.  A `COLLSCAN` indicates that MongoDB is performing a full collection scan, negating the efficiency benefits of the index.


**External References:**

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [MongoDB Query Optimization](https://www.mongodb.com/docs/manual/tutorial/query-optimization/)
* [MongoDB explain() Method](https://www.mongodb.com/docs/manual/reference/method/db.collection.explain/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

