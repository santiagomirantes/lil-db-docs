# lil-db.newCollection()
The lil-db.newCollection() method creates a collection of objects based on a given structure.

Each object inserted has an auto-generated id.
## Syntax
```js
 lil-db.newCollection(collection-name | string, model | object)
 ```
 

 - collection-name : an unique identifier of your collection.
 - model : an object that defines the structure of the collection.

## How to create a collection´s model
Collections´ models define the structure of the objects that are going to be pushed to those collections. To create a collection´s model, you need to create an object with the following structure:

```js
const collectionModel = {
   "key":{
      "type":String,
      "index":Boolean,
      "unique":Boolean,
    }
}
```

 - key : name of the field (e.g. username, email, age, etc.).
 - type : data that goes in that field (see list below).
 - index : defines if you are going to search objects based on that field of the collection. Passwords, objects and arrays can´t be indexes. 
Default is  ``true`` for ids and ``false`` for every other type.
 - unique : it can only be ``true`` if `index` is also ``true``. It restricts two or more objects from having identical values in that field. Default is ``false``.

If you want ``index`` and ``unique`` properties set to `false`, you can just give a string as a value representing the type. **Example:**
```js
const collectionModel = {
   "key":"type"
}
```
## List of types for models

 - any
 - string
 - number
 - boolean
 - email
 - id(collection_name)
 - idsArray(collection_name)
 - password
 - object
 - array
 

## Ids connections between collections
 
 The ``id(collection_name)``and the `idsArray(collection_name)` data types allow a collection to refer to other collections based on the ids of their objects. If  the collection that is beign referenced doesn´t exist, an error will be thrown.

This data type must be an ``index``.
## Usage example of the method
```js
const db = require("lil-db-js")
await db.init("./","your-secret")

const userModel = {
   "username":{
     "type":"string",
     "index":true,
     "unique":true
    },
    "email":{
      "type":"email",
      "index":true,
      "unique":true
     },
     "password":"password",
     "age":"number"
}
const productsModel = {
   "name":{
      "type":"string",
      "index":true
    },
    "price":"number"
}
const cartModel = {
   "user":"id(users)",
   "products":"idsArray(products)"
}

await db.newCollection("users",userModel)
await db.newCollection("products",productsModel)
await
db.newCollection("carts", cartModel)
```
[Go to the next page.](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/insert.md)

[Go to the previous page.](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/GETTING_STARTED.md)

[Go back to the usage docs.](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)
