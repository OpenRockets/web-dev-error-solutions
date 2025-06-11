# 🐞 Overcoming the "Index Not Used" Error in MongoDB


This document addresses a common problem developers encounter when working with MongoDB indexes: queries that fail to utilize the created index, leading to performance degradation.  This frequently happens when the query structure doesn't perfectly match the index's structure.


## Description of the Error

The "Index Not Used" error isn't a specific MongoDB error message but rather a performance issue observed when a query runs significantly slower than expected, even after an index seemingly relevant to the query has been created. This is often indicated by examining the MongoDB profiler or by noticing slow query times in your application's logs.  The problem stems from the query optimizer failing to choose the optimal execution plan due to subtle mismatches between the query and the index.


## Scenario:  Inefficient Query on a `users` Collection

Let's say we have a `users` collection with documents structured like this:

```json
{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "age": 30,
  "city": "New York"
}
```

We create an index on `firstName` and `lastName`:

```javascript
db.users.createIndex( { firstName: 1, lastName: 1 } )
```

Now, we execute this query:

```javascript
db.users.find( { lastName: "Doe", firstName: "John" } )
```

You *expect* the index to be used. However, if the query is still slow, the index might not be used due to field order mismatch within the query.



## Fixing the Issue Step-by-Step

**Step 1: Verify Index Existence and Structure**

First, confirm the index exists and its structure using:

```javascript
db.users.getIndexes()
```

This will list all indexes on the `users` collection. Check if your expected index is present and has the correct fields and order.


**Step 2:  Correct Query Field Order**

The key to resolving this is ensuring the query's field order precisely matches the index's field order.  MongoDB's query optimizer is highly sensitive to field order when choosing an index.  Change the query to:


```javascript
db.users.find( { firstName: "John", lastName: "Doe" } )
```


**Step 3: Analyze the Query Plan (Optional but Recommended)**

Use `explain()` to analyze the query's execution plan and verify index usage:


```javascript
db.users.find( { firstName: "John", lastName: "Doe" } ).explain()
```

Look for the "winningPlan" section. If the index is used, it should show the index key and the number of documents examined.  If not, it will likely show a "COLLSCAN" (collection scan), indicating a full table scan and thus no index usage.


**Step 4: Consider Compound Index Selectivity**

If you're querying on multiple fields, the selectivity of each field in the compound index matters.  Fields with higher cardinality (more unique values) should come earlier in the index. A highly selective field early in the index will greatly enhance performance.


**Step 5: Check for Data Type Mismatches**

Ensure your query values match the data types in your index.  For example, if your `age` field is an integer, don't compare it to a string.


## Explanation

The MongoDB query optimizer analyzes queries and chooses the most efficient execution plan based on available indexes. When the query structure doesn't exactly match an existing index (especially concerning field order in compound indexes), the optimizer may choose a less efficient plan, resulting in a full collection scan instead of using the index.


## External References

* **MongoDB Documentation on Indexes:** [https://www.mongodb.com/docs/manual/indexes/](https://www.mongodb.com/docs/manual/indexes/)
* **MongoDB Documentation on Query Optimization:** [https://www.mongodb.com/docs/manual/reference/method/db.collection.explain/](https://www.mongodb.com/docs/manual/reference/method/db.collection.explain/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

