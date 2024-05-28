# lil-db.backup()
The lil-db.backup() method makes a whole copy of your database in a single human-friendly JSON file.
## Syntax
```js
lil-db.backup()
```
## Reasons to do a backup

 - Data safety: while making queries to our database we can mess everything up, is better to be safe.
 - Migrations: since lil-db is not intended for big proyects, if your app grows you will need to migrate to paid database services (like Mongo or AWS). The backups of lil-db are human-friendly so you can easily loop through each collection and replicate them in those services.
 - Updates: if you want to install a new version of lil-db, the best you can do is make a preventive copy of your entire database and then load it into the newly installed version. This will prevent your data from corrupting in eventual changes of files and folders organization.
## Where are the backups stored?
All backups are stored inside the folder where your database is located, in a subfolder named "backups". The filenames of the backups are timestamps that will tell you how recently they were created.
## Usage of the method
```js
const db = require("lil-db-js")
await db.init("./","your-secret")

await db.backup()
```

[Go to the previous page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/deleteCollection.md)

[Go to the next page](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/load.md)

[Go back to the  usage docs](https://github.com/santiagomirantes/lil-db-docs/blob/main/Usage/USAGE_DOCS.md)


