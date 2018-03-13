## MongoDB CheatSheet
###### (TODO: Impliment in React + Mongo)

### Document
---
Analogous to item. A single entry in a `collection`. A JSON object.

* cannot start with a dollar sign > $ (as this specifies a field path or an operator)
* cannot contain a dot > .
* cannot have _null_
* maximum size: 16mb

##### Field
A name-value pair in a document. (Analogous to key-value).


### Collection
---
A _collection_ of `documents`. In my head this is what I think of as a `database`.

### Database
---
Basically a _collection_ (container) of `collections`. Every `database` has its own file set.

### Indexes
---
Data structures that store small parts of the collection's data that you set so that Mongo can search without scanning every single document in that collection.

``` js
// $lt is the query criteria
// users is the collection
db.users.find( { score: { "$lt": 30 } } ).sort( { score: -1 } );
```
```
                                       Here
                                        V
+---------------+----------------+---------------+---------------+----------------+
| {             | {              | {             | {             | {              |
|     score: 1  |     score: 15  |     score: 30 |     score: 35 |     score: 100 |
| }             | }              | }             | }             | }              |
+---------------+----------------+---------------+---------------+----------------+
```
### ObjectId
---
12-byte id generated automatically that displays in hexadecimal.

### Shard(ing)
---
Distributing a mongo server, to individual _shards_
