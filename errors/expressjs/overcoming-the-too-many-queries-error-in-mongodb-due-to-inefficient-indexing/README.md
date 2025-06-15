# 🐞 Overcoming the "Too Many Queries" Error in MongoDB Due to Inefficient Indexing


## Description of the Error

A common performance bottleneck in MongoDB stems from issuing too many queries, often indicated by slow response times and high server load. This isn't inherently an error message but rather a symptom pointing towards inefficient database design and a lack of optimized indexing.  When queries don't utilize appropriate indexes, MongoDB performs collection scans, examining every document to find matches. This becomes exponentially slower as the collection grows.

## Scenario: Slow User Search in an E-commerce Application

Imagine an e-commerce application where users can search for products based on name and category. Without proper indexing, a query like this:

```javascript
db.products.find({ name: /.*widget.*/i, category: "electronics" })
```

will result in a full collection scan if no indexes exist on `name` or `category`.  With a large product catalog, this leads to significantly slow search times.


## Step-by-Step Fix: Creating Compound Indexes

To address this, we need to create a compound index encompassing both `name` and `category`. This allows MongoDB to efficiently locate documents matching both criteria simultaneously.

**Step 1: Identify the Query Pattern**

Determine the common query patterns used to retrieve data. In this case, it's finding products based on `name` (with partial matches) and `category`.

**Step 2: Create the Compound Index**

The following command creates a compound index on `name` (text index for partial match support) and `category`:

```javascript
db.products.createIndex( { name: "text", category: 1 } )
```

* `name: "text"` creates a text index on the `name` field, enabling efficient text searches including partial matches (using regular expressions or $text operator).
* `category: 1` creates an ascending index on the `category` field.  The order matters for compound indexes; adjust to descending (`-1`) if needed.

**Step 3: Verify Index Creation**

Confirm the index was created successfully:

```javascript
db.products.getIndexes()
```

This will list all indexes on the `products` collection.  You should see the newly added compound index.

**Step 4: Re-run the Query**

Execute the search query again:

```javascript
db.products.find({ name: /.*widget.*/i, category: "electronics" })
```

This time, MongoDB should leverage the newly created index, resulting in significantly faster query execution.  You can monitor query execution time using the `explain()` method:

```javascript
db.products.find({ name: /.*widget.*/i, category: "electronics" }).explain()
```

Look for the "executionStats" section within the output.  A "winningPlan" using the index instead of a collection scan is the desired outcome.


## Explanation

By creating a compound index on `name` and `category`, we enable MongoDB to directly access relevant documents without scanning the entire collection.  The text index on `name` supports efficient partial string matching, while the ascending index on `category` further refines the search.  Choosing the right index type is crucial for optimal performance, based on the data type and query patterns.



## External References

* **MongoDB Documentation on Indexing:** [https://www.mongodb.com/docs/manual/indexes/](https://www.mongodb.com/docs/manual/indexes/)
* **MongoDB Documentation on Text Indexes:** [https://www.mongodb.com/docs/manual/core/index-text/](https://www.mongodb.com/docs/manual/core/index-text/)
* **MongoDB Query Optimization Guide:** [https://www.mongodb.com/docs/manual/tutorial/query-optimization/](https://www.mongodb.com/docs/manual/tutorial/query-optimization/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

