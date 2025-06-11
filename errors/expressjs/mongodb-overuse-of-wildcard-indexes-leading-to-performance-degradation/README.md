# 🐞 MongoDB: Overuse of Wildcard Indexes Leading to Performance Degradation


## Description of the Error

A common performance issue in MongoDB stems from the overuse or misuse of wildcard indexes, specifically `$regex` indexes with excessive wildcard characters at the beginning of the search pattern.  While wildcard indexes can be useful for flexible querying, improperly designed ones can severely impact query performance, leading to slow response times and high server load.  This happens because MongoDB can't utilize such indexes effectively; it often has to perform a collection scan instead of using the index for optimization.  The more wildcard characters at the beginning, the less selective the index becomes, making the problem worse.

## Scenario: Inefficient Search with Wildcard Index

Let's imagine a collection named `products` with a field `productName` (string type).  We have an index on `productName`:

```javascript
db.products.createIndex( { productName: 1 } )
```

Now, we want to search for products whose names start with "Laptop":

```javascript
db.products.find({ productName: /^Laptop/ })
```

This query uses the index efficiently.  However, if we frequently perform searches like this:

```javascript
db.products.find({ productName: /.*Laptop/ }) // Inefficient wildcard at the beginning
```

The index becomes almost useless because `.*` at the beginning matches *any* character sequence before "Laptop". MongoDB has to essentially scan the entire collection to find matches, negating the benefits of the index.


## Fixing Step-by-Step

Instead of using a wildcard index with leading wildcards, we should optimize our indexing and query strategies.

**Step 1: Analyze Queries**

Identify the most frequent and performance-critical queries on your `productName` field.   If many queries start with specific prefixes (e.g., "Laptop", "Tablet", "Smartphone"), create separate indexes for those prefixes:

```javascript
db.products.createIndex( { productName: 1 } ) //Keeps this general index.
db.products.createIndex( { productName: "Laptop" } )
db.products.createIndex( { productName: "Tablet" } )
db.products.createIndex( { productName: "Smartphone" } )
```

**Step 2: Refine Queries**

Modify your queries to leverage the specific indexes created in Step 1:

```javascript
// Instead of:
db.products.find({ productName: /.*Laptop/ })

// Use:
db.products.find({ productName: /^Laptop/ })  // This uses the index efficiently.
db.products.find({ productName: { $regex: "^Laptop" } }) //Equivalent and more explicit
```
OR, if you only need the prefix match:

```javascript
db.products.find({ productName: { $regex: "^Laptop", $options: "i" } }) //Case insensitive match
```

**Step 3:  Consider Text Indexes (For broader wildcard searches)**

For more complex wildcard searches where you truly need the flexibility, consider using a text index:


```javascript
db.products.createIndex( { productName: "text" } )

db.products.find( { $text: { $search: "Laptop" } } )
```

Text indexes are optimized for full-text searches, handling multiple words and partial matches more efficiently than regular expression indexes with excessive wildcards.  But be aware that Text indexes also have their own performance trade-offs, especially on very large collections.


## Explanation

Leading wildcards in `$regex` significantly reduce the selectivity of an index.  MongoDB can't efficiently use such an index because it needs to examine a substantial portion of the collection to find matches, leading to a collection scan. Creating more specific indexes tailored to frequently used query patterns ensures that MongoDB can utilize the indexes for optimized query performance. Text indexes provide a better approach for general full-text searches involving wildcards where specific prefixes are not known in advance.


## External References

* [MongoDB Indexing Documentation](https://www.mongodb.com/docs/manual/indexes/)
* [MongoDB Regex Indexes](https://www.mongodb.com/docs/manual/reference/operator/query/regex/)
* [MongoDB Text Indexes](https://www.mongodb.com/docs/manual/core/index-text/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

