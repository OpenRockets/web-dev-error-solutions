# 🐞 Overcoming the "Index Scanned" Warning in MongoDB


## Description of the Error

A common problem encountered when working with MongoDB indexes is the appearance of "Index Scanned" warnings in the logs or performance profiling output. This warning, while not always indicative of a critical issue, often signals that a query is not efficiently utilizing an existing index, leading to slower query execution times and potential performance bottlenecks. It suggests that MongoDB is performing a collection scan instead of leveraging an index, which is significantly less efficient for larger datasets.  The warning doesn't specify a precise error code, but rather shows up as a performance metric highlighting a full collection scan instead of using an index.


## Step-by-Step Code Fix

Let's consider a scenario where we have a collection of users with fields like `firstName`, `lastName`, and `age`.  We've created an index on `firstName` but observe the "Index Scanned" warning when querying users by `lastName`.


**Scenario:** We have a collection named `users` with the following documents:

```json
{ "firstName": "John", "lastName": "Doe", "age": 30 }
{ "firstName": "Jane", "lastName": "Smith", "age": 25 }
{ "firstName": "Peter", "lastName": "Jones", "age": 40 }
```

We've created an index on `firstName`:

```javascript
db.users.createIndex( { firstName: 1 } )
```

But the following query, using `lastName`, triggers the "Index Scanned" warning:

```javascript
db.users.find( { lastName: "Smith" } )
```

**The Fix:** To resolve this, we need to create an index on the `lastName` field:

```javascript
db.users.createIndex( { lastName: 1 } )
```

Now, queries filtering by `lastName` will efficiently utilize the index:

```javascript
db.users.find( { lastName: "Smith" } ).explain() // Use explain() to verify index usage
```

The `explain()` method will show that the query now uses the index on `lastName`, avoiding the collection scan and the associated performance penalty.

**Compound Index for Combined Queries:**

If queries frequently filter by both `firstName` and `lastName`, a compound index is beneficial:

```javascript
db.users.createIndex( { firstName: 1, lastName: 1 } )
```

This index will optimize queries involving both fields.  However, order matters – a query matching only `lastName` will still use this index, but a query on `lastName` and `firstName` will only benefit if the order matches the index.


## Explanation

The "Index Scanned" warning implies that MongoDB had to examine every document in the collection to satisfy the query, rather than using an index to quickly locate the matching documents. Indexes are B-tree structures that speed up data retrieval by organizing data based on specific fields.  When a query specifies a field with an appropriate index, MongoDB can efficiently use the index to locate relevant documents without scanning the entire collection.  Failure to create appropriate indexes for frequently used query patterns is the root cause of this problem.


## External References

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [MongoDB Query Optimization](https://www.mongodb.com/docs/manual/tutorial/query-optimization/)
* [MongoDB explain() Method](https://www.mongodb.com/docs/manual/reference/method/cursor.explain/)



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

