### Resources
- [Mongoose Overview](https://youtu.be/DZBGEVgL2eE?si=USRz8BQT-8cN4xiK)
- [MongoDB and Mongoose](https://www.youtube.com/watch?v=bALyYC10ABw)
- [SQL](https://www.youtube.com/watch?v=p3qvj9hO_Bo)

### Topics
- Fundamentals of Relational (SQL) Databases and SQL
- Introduction to NoSQL Databases and Their Types
- Detailed Understanding of MongoDB and Mongoose
- Integrating Mongoose Models with Express in Node.js

### Learning Goals
By the end of this week, students should be able to:
- [ ] Understand the structure and purpose of relational databases and effectively use SQL for database management.
- [ ] Grasp the concepts and applications of different types of NoSQL databases.
- [ ] Set up and configure MongoDB Atlas for cloud-based database management.
- [ ] Create and manage data schemas and models using Mongoose in a Node.js environment.
- [ ] Implement and integrate Mongoose models with Express routes for CRUD operations.

### Homework Assignment for Week 14: Integrating Database with Express Server

#### Objective
Update your Week 13 Express server to integrate a database at each route. This will involve modifying your existing CRUD routes to interact with a database instead of local storage or simple data structures.

#### Step-by-Step Guide

1. **Review and Plan**: 
   - Plan how to adapt your Week 13 API to use a database for data storage and retrieval.

2. **Database Integration**:
   - Choose a database system (e.g., MongoDB, SQLite, MySQL). If you're using MongoDB, you can integrate with Mongoose for easier data handling.
   - Install necessary packages for database integration (`npm install mongoose` for MongoDB).

3. **Modifying CRUD Routes**:
   - Update your existing CRUD (`GET`, `POST`, `PUT`, `DELETE`) routes to interact with the database.
   - Replace local storage operations with database queries.
   - Ensure each route performs the appropriate database operation: retrieving data, adding new records, updating existing records, and deleting records.

4. **Implementing Models**:
   - If using MongoDB with Mongoose, define models that correspond to your data structure.
   - Ensure your route handlers use these models for database interactions.

#### Deliverables
Submit the following:
- Your updated project folder containing the server file (`app.js` or `server.js`) and any other relevant files (e.g., model definitions, updated package.json).
- A revised document detailing your API's theme, updated CRUD operations structure, database schema and models, and the implementation of database interactions, error handling, and validation.

### Glossary of Key Terms
- **Relational Database**: A database structured to recognize relations among stored items of information.
- **SQL (Structured Query Language)**: A standardized programming language used for managing relational databases and performing various operations on the data in them.
- **NoSQL Database**: A diverse class of database management systems that differ from the traditional table-based SQL databases.
- **MongoDB**: A popular NoSQL database known for its flexibility and scalability, storing data in JSON-like documents.
- **Mongoose**: An Object Data Modeling (ODM) library for MongoDB and Node.js, providing a schema-based solution to model application data.
- **Schema**: In MongoDB, a schema defines the structure of the document, including the field types and validation.
- **Model**: In Mongoose, a model acts as a wrapper on the schema, providing an interface to interact with the database.
- **Express.js**: A web application framework for Node.js, designed for building web applications and APIs.
- **CRUD Operations**: Stands for Create, Read, Update, and Delete, representing the basic operations performed on database data.
- **Primary Key (PK)**: A unique identifier for each record in a relational database table.
- **Foreign Key (FK)**: A field in a relational database table that provides a link between data in two tables.