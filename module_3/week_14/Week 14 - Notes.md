# Relational Databases and SQL

![Database Components](https://teachcomputerscience.com/wp-content/uploads/2016/12/dbase_components.png)

## Defining Relational Databases
A relational database is a type of database that stores and provides access to data points that are related to one another. Its key features include:

- **Structured Schema**: Data is organized into tables (think of them like spreadsheets), each with a defined structure or 'schema'.
- **Table-Based Organization**: Each table consists of rows and columns. Rows (or records) are individual entries, and columns (or fields) are the specific data points, like 'name', 'email', etc.

## Understanding SQL
SQL, or Structured Query Language, is the standard language for relational database management. It's used for:

- **Data Manipulation**: Adding, updating, or deleting records.
- **Data Querying**: Fetching specific data by querying the database.

SQL is essential because it provides a uniform way to interact with various relational databases, whether you're using MySQL, SQLite, or PostgreSQL.

## Core SQL Queries
The backbone of SQL lies in its queries. Here are some examples:

1. **SELECT** - Used to fetch data from a database.
   ```sql
   -- Selects all columns from the 'users' table
   SELECT * FROM users;
   
   -- Selects only the 'name' and 'email' columns from the 'users' table
   SELECT name, email FROM users;
   ```

2. **INSERT** - Adds new rows (records) to a table.
   ```sql
   -- Inserts a new record into the 'users' table
   INSERT INTO users (name, email) VALUES ('John Doe', 'john@example.com');
   ```

3. **UPDATE** - Modifies existing data.
   ```sql
   -- Updates the 'email' of the user with id 1
   UPDATE users SET email = 'newemail@example.com' WHERE id = 1;
   ```

4. **DELETE** - Removes records from a table.
   ```sql
   -- Deletes the user with id 1
   DELETE FROM users WHERE id = 1;
   ```

## Database Structures: Tables, Rows, Columns, PK, and FK
Understanding the structure of a relational database is crucial:

- **Tables**: Collections of related data, like a list of users or a catalog of products.
- **Rows/Records**: Individual entries in a table. Each row in a 'users' table represents a different user.
- **Columns/Fields**: Attributes of the data. In a 'users' table, columns might include 'id', 'name', 'email', etc.
- **Primary Keys (PK)**: Unique identifiers for each row. For example, a user ID that uniquely identifies a user in the 'users' table.
- **Foreign Keys (FK)**: Columns that reference the primary key in another table, creating a link between them. For instance, an 'order' table may have a 'user_id' foreign key linking it to the 'users' table.

These components work together to create an organized and efficient way to store, retrieve, and manage data in a relational database environment. Understanding them is fundamental for anyone diving into the world of database management.

![Database Structure](https://miro.medium.com/v2/resize:fit:1200/1*wr_PNTP9fQHxXeMydaSfnQ.jpeg)

# Introduction to NoSQL Databases

## Overview of NoSQL Databases

Imagine NoSQL databases as a more free-form filing system, unlike the structured, table-based SQL approach. They come in various types, each suited to different data storage and retrieval needs:
 
- **Document**: Stores data in JSON-like documents (e.g., MongoDB). Ideal for storing data with varied structures.
- **Key-Value**: Simplest form, storing data as a collection of key-value pairs (e.g., Redis). Great for quick lookups by key.
- **Wide-Column**: Stores data in tables, rows, and dynamic columns (e.g., Cassandra). Efficient for querying large datasets.
- **Graph**: Designed for data whose relations are best represented as a graph (e.g., Neo4j). Perfect for complex hierarchies and networks.

## When to Use NoSQL Over SQL

- **Scalability**: NoSQL databases often provide better horizontal scalability, making them a good choice for applications that anticipate large-scale growth.
- **Flexibility**: NoSQL allows for a more flexible data model, which can evolve with your application's needs.
- **Speed**: Some NoSQL types (like key-value stores) offer faster data retrieval by simplifying the data model and optimizing for specific operations.

# Mongoose and MongoDB

1. Setting Up MongoDB Atlas

MongoDB Atlas is a cloud-based database service that offers high availability, global scalability, and robust security features.

Steps:
1. Create an Account and Cluster – Sign up on MongoDB Atlas and create a new cluster.
2.	Configure Security – Set up IP whitelisting and create a database user.
3.	Obtain Connection String – Retrieve the MongoDB connection string to use in the application.

2. Installing Dependencies and Setting Up Environment Variables

Before integrating MongoDB with our Node.js application, we need to install the required dependencies and configure environment variables.

Install Required Packages:
```
npm install express mongoose dotenv bcryptjs
```
- express: Framework for handling server routes.
- mongoose: ODM (Object-Document Mapper) for MongoDB.
- dotenv: Loads environment variables from a .env file.
- bcryptjs: Used for hashing passwords.

Creating the .env File:
1.	Create a .env file at the root of the project.
2.	Add the database connection string:
```
MONGO_URI=your_mongodb_connection_string_here
PORT=3000
```

3.	Load .env in server.js:
```
require('dotenv').config();
```


3. Understanding Mongoose Schemas and Models

Mongoose provides a structured way to interact with MongoDB through schemas and models.
- Schema: Defines the structure, field types, default values, and validations.
- Model: A model wraps around a schema to allow CRUD operations.

User Model Example (user.model.js):
```javascript
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  username: {
    type: String,
    required: true,
    unique: true,
  },
  password: {
    type: String,
    required: true,
  },
});

const User = mongoose.model('User', userSchema);
module.exports = User;
```
4. Setting Up the Server and Connecting to MongoDB Atlas

server.js
```javascript
require('dotenv').config();
const express = require('express');
const mongoose = require('mongoose');

const app = express();
const PORT = process.env.PORT || 3000;

// Connect to MongoDB Atlas
mongoose.connect(process.env.MONGO_URI, { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => {
    console.log('MongoDB connected');
    app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
  })
  .catch((err) => console.error('MongoDB connection error:', err));
```
Key Points:
- dotenv is required at the beginning to load environment variables.
- The MONGO_URI is pulled from .env instead of being hardcoded.
- The server only starts after a successful database connection.

5. Integrating Models with Express Routes

Now, we integrate the User model with Express routes.

Creating a User (routes/userRoutes.js)
```javascript
const express = require('express');
const bcrypt = require('bcryptjs');
const User = require('../models/user.model');

const router = express.Router();

router.post("/register", async (req, res) => {
  try {
    const { username, password } = req.body;
    const existingUser = await User.findOne({ username });
    if (existingUser) {
      return res.status(400).json({ message: "Username already exists" });
    }

    const hashedPassword = await bcrypt.hash(password, 10);
    const newUser = new User({ username, password: hashedPassword });

    await newUser.save();
    res.status(201).json({ message: "User registered successfully" });
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
});

module.exports = router;
```
Explanation:
	•	Checks if the username already exists.
	•	Hashes the password before saving it.
	•	Stores the user in the database.

Fetching All Users
```javascript
router.get("/users", async (req, res) => {
  try {
    const users = await User.find();
    res.status(200).json(users);
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
});
```
Updating a User
```javascript
router.put("/users/:id", async (req, res) => {
  try {
    const { username, password } = req.body;
    const hashedPassword = await bcrypt.hash(password, 10);
    
    const updatedUser = await User.findByIdAndUpdate(
      req.params.id,
      { username, password: hashedPassword },
      { new: true }
    );

    res.status(200).json(updatedUser);
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
});
```
Deleting a User
```javascript
router.delete("/users/:id", async (req, res) => {
  try {
    await User.findByIdAndDelete(req.params.id);
    res.status(200).json({ message: "User deleted successfully" });
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
});
```
6. Bringing It All Together

Final server.js (Including Routes)
```javascript
require('dotenv').config();
const express = require('express');
const mongoose = require('mongoose');

const userRoutes = require('./routes/userRoutes');

const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json()); // Middleware to parse JSON
app.use('/api', userRoutes); // Register user routes

mongoose.connect(process.env.MONGO_URI, { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => {
    console.log('MongoDB connected');
    app.listen(PORT, () => console.log(`Server running on port ${PORT}`));
  })
  .catch((err) => console.error('MongoDB connection error:', err));
```


# Common HTTP Status Codes for CRUD Operations

### Create

- **Success: 201 Created**
  - Indicates that the request has been fulfilled and has resulted in one or more new resources being created.
  - Example:
    ```json
    {
      "status": 201,
      "message": "Resource created successfully."
    }
    ```

- **Failure: 400 Bad Request**
  - Indicates that the server cannot process the request due to a client error (e.g., validation error, malformed syntax).
  - Example:
    ```json
    {
      "status": 400,
      "message": "Invalid input. Resource not created."
    }
    ```

### Read

- **Success: 200 OK**
  - Indicates that the request has succeeded and the requested resource is sent in the response body.
  - Example:
    ```json
    {
      "status": 200,
      "data": {
        "id": 1,
        "name": "John Doe",
        "email": "john@example.com"
      }
    }
    ```

- **Failure: 404 Not Found**
  - Indicates that the requested resource could not be found on the server.
  - Example:
    ```json
    {
      "status": 404,
      "message": "Resource not found."
    }
    ```

### Update

- **Success: 200 OK**
  - Indicates that the request has succeeded and the resource has been updated.
  - Example:
    ```json
    {
      "status": 200,
      "message": "Resource updated successfully."
    }
    ```

- **Failure: 400 Bad Request**
  - Indicates that the server cannot process the request due to a client error (e.g., validation error, malformed syntax).
  - Example:
    ```json
    {
      "status": 400,
      "message": "Invalid input. Resource not updated."
    }
    ```

- **Failure: 404 Not Found**
  - Indicates that the resource to be updated could not be found.
  - Example:
    ```json
    {
      "status": 404,
      "message": "Resource not found."
    }
    ```

### Delete

- **Success: 200 OK**
  - Indicates that the request has succeeded and the resource has been deleted.
  - Example:
    ```json
    {
      "status": 200,
      "message": "Resource deleted successfully."
    }
    ```

- **Failure: 404 Not Found**
  - Indicates that the resource to be deleted could not be found.
  - Example:
    ```json
    {
      "status": 404,
      "message": "Resource not found."
    }
    ```

- **Failure: 409 Conflict**
  - Indicates that the request could not be completed due to a conflict with the current state of the target resource (e.g., trying to delete a resource that is referenced elsewhere).
  - Example:
    ```json
    {
      "status": 409,
      "message": "Conflict. Resource could not be deleted."
    }
    ```

By using appropriate HTTP status codes for CRUD operations, you can provide clear and meaningful responses to clients, helping them understand the result of their requests and take appropriate actions.