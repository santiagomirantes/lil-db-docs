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
## How does lil-db.js organizes data?
Now that you know how to start using lil-db, you need to learn how to work with it. First we are going to see the logic and then, in the next pages of the docs you are going to find how to code it.

Lil-db divides the data into collections. See collections as groups of JS objects that follow a certain structure.

**Example:** if I had an E-Commerce, I would create at least three collections: users, products and carts.

Once you have the collections, you can push objects to them (like if they were arrays), but **be careful** , the objects must follow the specific structure you´ve previously assigned to the collection when it was created.

The collections can also have connections between them, **for example:** in the E-Commerce situation, I could  give each user a cart so they can push products to it. As you can see, this makes the whole database relational.

Now you will learn how to code all these things in the next pages of the docs.

[Move to the next page.](https://www.github.com/santiagomirantes/lil-db-docs/blob/main/Usage/newCollection.md)

[Go back to the usage docs.](https://www.github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)



 
