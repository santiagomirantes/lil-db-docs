# Getting started with lil-db.js

Once your lil-db.js package is correctly installed, follow the next steps to start using it.

## Asynchronous Environment
All the functions of lil-db are [asynchronous](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function), so we recomend you to enclose your code in async/await functions, just like this:
```js
 async fn() {
    const db = require("lil-db")
    await db.someFunction()
 }
  ```
## The lil-db.init() function
Before calling any lil-db function, you need to execute the .init method.
The syntax is the following:
```js
lil-db.init(path | string, secret | string)
```

 - path : the path to your database folder.
 - secret : a special string that is going to be used to encrypt the passwords
 
 The purpose of the function is to create the folder of the database (if it hasn´t been created) and set up the secret in the memory. If you call any other lil-db method before initializing the db, an exception is going to be thrown.
**Example:**
```js
async fn() {
   const db = require("lil-db")
   await db.init("./","your-secret")
   //other lil-db functions
}
```

[Move to the next page.](https://www.github.com/santiagomirantes/lil-db-docs/blob/main/Usage/newCollection)
[Go back to the usage docs.](https://www.github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)



 
