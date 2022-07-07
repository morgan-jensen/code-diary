MERN Stack HotSheet

# What you need
1. Install [Node](https://nodejs.org/en/)
2. A text editor

# Setup
## Create a React App 

Create an app starter
```
npx create-react-app <name> 
```

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
npm install mongodb express cors dotenv
```
- `mongodb`: MongoDB database driver that allows Node.js applications to connect to the database and work with data.
- `express`: Web framework for Node.js 
- `cors`: Node.js package that will allow cross-origin resource sharing
- `dotenv`: Loads environment variables from a .env file into process.env. This seperates configuration files from the code.

Create server.js file with:
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

