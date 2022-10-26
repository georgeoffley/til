# Basic CLI Migrations Setup

---
## Docs and Source
[Docs](https://sequelize.org/docs/v6/other-topics/migrations/)

---
## Explanation and Notes

Sequelize's CLI helps you setup a production ready setup for data on your projects. The big draw for me is having a generated state of the database within your project. It also generates all the files you need. Basic setup looks like the below.

1. Install Sequelize using the command `npm install --save-dev sequelize-cli`
2. Then you can run `npx sequelize-cli init` which setups your starting files. I like creating a new directory for data stuff. Usually name it something like `seqeulize` or `data`.
3. Setup the `config/config.json` file with the needed database information.
4. Run the `npx sequelize-cli model:generate` command to have the CLI tool create the model. This is a sample of the command and below is the example from the docs of a User model file.
```bash
npx sequelize-cli model:generate --name User --attributes firstName:string,lastName:string,email:string
```
5. Once the model is made you can run the `npx sequelize-cli db:migrate` command which takes your models and creates migration files which show the generated SQL. This will sync up with the database and create the needed tables.

```ad-warning
title: Please Note

This method generates Javascript files and not TypeScript files for some reason. And this can cause issues with TypeScript projects. This will not work for TypeScript projects and will require manually writting your models, config files, and api logic.
```

---
## Code Example

```JavaScript
const { Sequelize, DataTypes } = require('sequelize');  
const sequelize = new Sequelize('sqlite::memory:');  
  
const User = sequelize.define('User', {  
// Model attributes are defined here  
firstName: {  
type: DataTypes.STRING,  
allowNull: false  
},  
lastName: {  
type: DataTypes.STRING  
// allowNull defaults to true  
}  
}, {  
// Other model options go here  
});
```


#Sequelize
#TypeScript 
#JavaScript 