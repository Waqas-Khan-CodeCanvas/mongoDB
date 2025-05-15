
# 📘 MongoDB Commands Cheat Sheet

Organized from **Beginner** to **Advanced** level.

---

## 🟢 Beginner MongoDB Commands

### 📁 General Use 
- `show dbs` – Show all databases
- `use <db>` – Switch to/create a database
- `db` – Show current database
- `show collections` – List collections in current DB

### 📂 Database Commands
- `db.createCollection('<name>')` – Create new collection
- `db.getCollectionNames()` – List all collections
- `db.dropDatabase()` – Delete the current database
- `db.<collection>.drop()` – Drop a collection

### 🧾 Insert Documents
- `db.<collection>.insert({})` – Insert one document
- `db.<collection>.insertMany([{},{},...])` – Insert multiple documents
- `db.<collection>.save({})` – Insert or update a document

### 🔍 Basic Queries
- `db.<collection>.find()` – Show all documents
- `db.<collection>.find({<query>})` – Filtered query
- `db.<collection>.findOne({})` – Return a single document

---

## 🟡 Intermediate MongoDB Commands

### 🔄 Update Commands
- `db.<collection>.update({query}, {update}, {options})`
- `db.<collection>.updateOne(...)`
- `db.<collection>.updateMany(...)`
- `db.<collection>.replaceOne(...)`

#### Operators:
- `$set` – Update fields
- `$unset` – Remove a field
- `$inc` – Increment value
- `$rename` – Rename a field
- `$push`, `$pull`, `$addToSet` – Array operations

### ❌ Delete Commands
- `db.<collection>.remove({})`
- `db.<collection>.deleteOne({})`
- `db.<collection>.deleteMany({})`

### 🧮 Query Operators
- `$gt`, `$lt`, `$gte`, `$lte` – Comparisons
- `$ne` – Not equal
- `$in`, `$nin` – Match any/not in array
- `$or`, `$and`, `$not`, `$nor` – Logical operators
- `$exists` – Check field existence
- `$type` – Check data type
- `$regex` – Regular expression matching

### ⌛ Projection
- `{ field: 1, field2: 0 }` – Include/exclude fields in results

### 📑 Cursor Operations
- `.limit(n)` – Limit number of results
- `.sort({field: 1/-1})` – Sort ascending/descending
- `.count()` – Count matching docs
- `.pretty()` – Format output
- `.skip(n)` – Skip n results

---

## 🔴 Advanced MongoDB Commands

### 🧠 Aggregation Framework
- `db.<collection>.aggregate([{...}, {...}])`

#### Common stages:
- `$match` – Filter
- `$group` – Grouping data
- `$project` – Shape the data
- `$sort` – Sort
- `$limit`, `$skip` – Pagination
- `$sum`, `$avg`, `$min`, `$max`, `$push`, `$addToSet` – Accumulators
- `$lookup` – Join with another collection
- `$unwind` – Deconstruct arrays
- `$out` – Output aggregation results to a collection

### 🧱 Indexes
- `db.<collection>.createIndex({ field: 1 })` – Ascending index
- `db.<collection>.createIndex({ field: -1 })` – Descending
- `db.<collection>.dropIndex(...)`
- `db.<collection>.getIndexes()`
- `db.<collection>.ensureIndex({ field: 1 }, { unique: true })`

### 🧮 Text & Geospatial Search
- `db.<collection>.createIndex({ field: "text" })`
- `db.<collection>.find({ $text: { $search: "word" } })`
- `db.<collection>.createIndex({ location: "2dsphere" })`
- `$near`, `$geoWithin`, `$geoIntersects`

### 🛡️ Authentication & Users
- `use admin`
- `db.createUser({ user: "...", pwd: "...", roles: [...] })`
- `db.auth("username", "password")`
- `db.changeUserPassword("username", "newpassword")`

### 🛠️ Backup/Restore (CLI)
- `mongodump --db <db> --out <dir>`
- `mongorestore <dir>`
- `mongoexport --db=<db> --collection=<coll> --out=<file>.json`
- `mongoimport --db=<db> --collection=<coll> --file=<file>.json --jsonArray`

### 🔄 Replication & Sharding
- `rs.initiate()`
- `rs.status()`
- `rs.add("host:port")`
- `sh.enableSharding("dbname")`
- `sh.shardCollection("db.collection", { field: 1 })`

---

📝 *Last Updated: 2025*
