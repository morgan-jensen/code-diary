# Getting Started with the MERN Stack
(Info pulled from [mongodb.com](https://www.mongodb.com/languages/mern-stack-tutorial))

## Prerequisites
1. Install [Node](https://nodejs.org/en/)
2. A text editor

## Setup
### Create a React App 

Create an app starter
```
npx create-react-app <name> 
```

### Create the Back-End
Create a folder for the back end.
```
mkdir server
```

Jump to the server folder and create the server.  
Then initialize `package.json` using `npm init`.
```
cd server
npm init -y 
```

Install dependencies.
```
npm install express cors dotenv
```
- `express`: Web framework for Node.js 
- `cors`: Node.js package that will allow cross-origin resource sharing
- `dotenv`: Loads environment variables from a .env file into process.env. This seperates configuration files from the code.


Which database solution?
```
npm install mongodb 
```
or 
```
npm install mysql
```

- `mongodb`: MongoDB database driver that allows Node.js applications to connect to the database and work with data.
- `mysql`: MySQL database driver that allows Node.js applications to connect to the database and work with data.

_MySQL vs MongoDB_
While MongoDB is the traditional __M__ in __MERN__, MySQL is another option.

When to use MySQL vs MongoDB:<br>
__MongoDB__:<br>
MongoDB is a NoSQL solution, meaning it is non-relational. It is more flexible than a SQL 
database, because the data doesn't have to conform to rows and columns. For more info,
check out the MongoDB [documentation](https://www.mongodb.com/docs/). 

__MySQL__:<br>
MySQL is a SQL-based solution. Being a SQL-based solution means that it conforms to a 
standard table format of rows, columns and tables. It is less flexible than a NoSQL 
solution like MongoDB, but will enforce more rigidity in your data. You can find
their documentation [here](https://www.mysql.com/doc/).

Which one you should use is dependent on what you want to do.

Create server.js file with ->

For a MongoDB back-end:
```
const express = require("express");
const app = express();
const cors = require("cors");
require("dotenv").config({ path: "./config.env" });
const port = process.env.PORT || 5000;

app.use(cors());
app.use(express.json());
app.use(require("./routes/record"));

// get driver connection
const dbo = require("./db/conn");

app.listen(port, () => {
    // perform a database connection when server starts
    dbo.connectToServer(function (err) {
        if (err) console.error(err);
    });
    console.log(`Server is running on port: ${port}`);
});
```

For a MySQL back-end, include:
```
var mysql = require('mysql')

var con = mysql.createConnection({
    host: "localhost",
    user: "yourusername",
    password: "yourpassword"
});

con.connect(function(err) {
    if (err) throw err;
    console.log("console.log("Connected!");
});
```

### Starting the Server
How to start the server:
```
cd <name>   // same name declared when app created
npm start
```
Other Options:
* `npm start`: Starts the development server
* `npm run build`: Bundles the app into static files for production
* `npm test`: Starts the test runner

