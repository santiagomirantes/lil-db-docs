# lil-db.deleteCollection()
The lil-db.deleteCollection() method deletes a specific collection and all of its objects.
## Syntax
```js
lil-db.deleteCollection(collection | string, mode | string)
```

 - collection: the collection´s name
 - mode: if it´s `"cascade"`, all collections referencing or beign referenced by the collection (with `id()` and `idsArray()` datatypes) will be deleted too.
Otherwise, it will delete only the specified collection and will throw an error if there are any references.

## Usage of the method
```js
const db = require("lil-db-js")
await db.init("./","your-secret")

const productsModel = {
    "name":"string",
    "price":"number"
}

const cartsModel = {
     "products":"id(products)"
}

await db.newCollection("products",productsModel)

await db.newCollection("carts",cartsModel)

await db.deleteCollection("carts","cascade")
//this deletes both the carts and the products collections since there is a reference between them (the "products" property). 
//If the mode wouldn´t have been set as "cascade" an error would have been thrown.
```
[Go to the previous page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/delete.md)

[Go to the next page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/backup.md)

[Go back to the usage docs](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)

