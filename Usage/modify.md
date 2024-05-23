# lil-db.modify()
The lil-db.modify() method deletes an object based on it´s id and creates a new object in it´s replacement with the same id.
## Syntax
```js
lil-db.modify(collection | string, objectID | string, callback | function)
```

 - collection: the name of the collection where the object belongs to.
 - objectID: the unique identifier of the object that is meant to be modified.
 - callback: a function that receives the current object with the given id and returns a new object. The returned object must be based on the collection´s model.
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

let user1 = {
  "name":"John Doe",
  "age":18
}

user1 = await db.insert("users",user)

await db.modify("users",user1.id,prev => {
   prev.age = 19
   return prev
})
//Now John Doe is 19 years old
```

[Go to the previous page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/find.md)

[Go to the next page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/delete.md)

[Go back to the usage docs](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)
