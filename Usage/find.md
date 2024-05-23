# lil-db.find()
the lil-db.find() method searches through the indexes of an specified collection and returns an array containing the objects that meet the query
## Syntax
```js
lil-db.find(collection | string, index | string, callback | function)
```

 - collection: name of the collection
 - index: name of the property that is going to be matched with the criteria. Must be an index.
 - callback: function that receives each index **in a String format**. If it returns `true`, the object meets the criteria.
 
 ## Usage of the method
```js
const db = require("lil-db")
await db.init()

const usersModel = {
  "name":{
    "type":"string",
    "index":true
  },
  "age":"number"
}

await db.newCollection("users",usersModel)

const user1 = {
  "name":"John Doe",
  "age":18
}

await db.insert("users",user)

await db.find("users","name",name => name === "John Doe")
//this returns an array including the user1 object
await db.find("users","name",name => name !== "John Doe")
//this returns an empty array
await db.find("users","age",age => age === 18)
//this returns an error since age is not an index
```
[Go to the previous page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/insert.md)

[Go to the next page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/modify.md)

[Go back to the usage docs](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)
