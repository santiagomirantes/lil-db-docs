# lil-db.delete()
the lil-db.delete() method deletes a specific object from an collection based on it´s id.
## Syntax
```js
lil-db.delete(collection | string, objectID | string)
```

 - collection: the collection´s name
 - objectID: the auto-generated ID of the object that you want to delete
## Usage of the method
```js
const db = require("lil-db")
await db.init("./","your-secret")

const productModel = {
  "name":"string"
  "price":"number"
}

await db.newCollection("products",productModel)

let product1 = {
  "name":"Product test 1",
  "price":6500
}

product1 = await db.insert("products",product1)

await db.delete("products",product1.id)
```
[Go to the previous page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/modify.md)

[Go to the next page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/deleteCollection.md)

[Go back to the usage docs](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)



