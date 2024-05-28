# lil-db.findIds()
The lil-db.findIds() method searches through the indexes of an specified collection and returns an array containing the ids of the objects that meet the query.
## Syntax
```js
lil-db.findIds(collection | string, index | string, callback | (string || function))
```

 - collection: name of the collection
 - index: name of the property that is going to be matched with the criteria. Must be an index.
 - callback:  If it´s a string, it finds all objects whose  properties equal the string.
 If it's a function, it receives each index **in a String format**. If it returns `true`, the object meets the criteria.
 Executing `lil-db.findIds()` with a string as the callback is much faster than with a function since it doesn´t run through all the indexes folder.
 
 ## Usage of the method
```js
const db = require("lil-db-js")
await db.init("./","your-secret")

const usersModel = {
  "name":{
    "type":"string",
    "index":true
  },
  "age":{
    "type":"number",
    "index":true
  },
  "role":"string"
}

await db.newCollection("users",usersModel)

const user1 = {
  "name":"John Doe",
  "age": 18,
  "role":"user"
}
const user2 = {
   "name":"Jane Doe",
   "age":16,
   "role":"user"
}

await db.insert("users",user1)
await db.insert("users",user2)

await db.findIds("users","name","John Doe")
//this returns an array including the user1 id
await db.findIds("users","age", age => age > 15)
//this returns an array including the user1 and user2 ids
await db.findIds("users","name","Santiago Mirantes")
//this returns an empty array
await db.findIds("users","role","user")
//this returns an error since role is not an index
```
[Go to the previous page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/find.md)

[Go to the next page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/modify.md)

[Go back to the usage docs](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)
