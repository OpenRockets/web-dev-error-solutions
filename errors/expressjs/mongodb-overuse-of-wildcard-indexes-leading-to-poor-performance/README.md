# 🐞 MongoDB: Overuse of Wildcard Indexes Leading to Poor Performance


## Description of the Error

A common performance problem in MongoDB stems from the overuse of wildcard indexes, especially on large collections. Wildcard indexes, using the `$regex` operator in the index definition, can significantly slow down queries, especially when they're not carefully designed.  The issue arises because MongoDB needs to scan a larger portion of the collection to find matching documents, even when only a small subset is actually needed. This becomes exponentially worse with increasing data volume.  Queries intended to use a wildcard index might end up ignoring it in favor of a collection scan, leading to dramatically slower query times.

## Fixing Step-by-Step Code

Let's consider a scenario where we have a collection named `users` with the following structure:

```javascript
{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "city": "New York"
}
```

And we have an incorrectly implemented wildcard index:

```javascript
db.users.createIndex( { "email": 1, "city": "New York" } ) //Incorrect Index
```

This is incorrect because  we are only interested in "New York" and this should be replaced with a compound index. It was implemented in order to search for users in New York and emails with certain patterns like '*.example.com' .


**Step 1: Identify and Remove Inefficient Indexes**

First, we identify and remove the poorly designed wildcard index:

```javascript
db.users.dropIndex({ "email": 1, "city": "New York" })
```

**Step 2: Create an Efficient Compound Index**

Next, we create a compound index that leverages the specificity of our queries. If we frequently query by `email` and `city`, this approach improves performance :

```javascript
db.users.createIndex({ email: 1, city: 1 })
```

This index allows for efficient lookups when both `email` and `city` are specified in a query.

**Step 3 (Optional):  Using Regular Expressions Sparingly (If Absolutely Necessary)**

If wildcard searches are truly necessary, try to be as specific as possible with your regular expressions and create a dedicated index for them. For example:

```javascript
db.users.createIndex({ email: "text" })

// Example query (much faster with the text index)
db.users.find({email: {$regex: /@example\.com$/}})
```


**Step 4: Analyze Query Performance**

Use MongoDB's profiling tools to analyze query performance.  The `db.system.profile` collection (enable profiling first with `db.setProfilingLevel(2)`) records query execution statistics.  Review this data to identify slow queries and optimize accordingly.

## Explanation

The key to avoiding the pitfalls of wildcard indexes is to understand their impact on query performance.  MongoDB's query planner relies on efficient indexing to navigate the collection quickly.  Broad wildcard indexes force a more exhaustive search, significantly slowing down query responses. Compound indexes, which combine multiple fields, are often the better choice when querying based on multiple criteria, because they allow MongoDB to efficiently filter down the data set for a faster query.  Using regular expressions sparingly and focusing on highly specific patterns minimizes their performance impact. Text indexes provide great support when you must work with regular expressions.

## External References

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [MongoDB Performance Tuning](https://www.mongodb.com/docs/manual/administration/performance/)
* [Understanding MongoDB Query Optimization](https://www.mongodb.com/blog/post/query-optimization-in-mongodb)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

