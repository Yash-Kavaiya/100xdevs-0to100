# Types of Databases

Notes:- https://daily-code-web.vercel.app/tracks/YOSAherHkqWXhOdlE4yE/

1. **NoSQL Databases:**
   - **Definition:** NoSQL databases, or "Not Only SQL" databases, are a type of database that provides a mechanism for storage and retrieval of data that is modeled in ways other than the traditional relational database management systems (RDBMS).
   - **Examples:**
     - **MongoDB:** A document-oriented database that stores data in flexible, JSON-like documents.
     - **Cassandra:** A distributed NoSQL database designed for handling large amounts of data across multiple commodity servers.
     - **Redis:** An open-source, in-memory data structure store used as a database, cache, and message broker.

2. **Graph Databases:**
   - **Definition:** Graph databases are designed to represent and store data in the form of nodes and relationships, making them highly suitable for data with complex relationships.
   - **Examples:**
     - **Neo4j:** A highly popular graph database that uses a property graph model to represent and store data.
     - **Amazon Neptune:** A fully managed graph database service provided by Amazon Web Services (AWS).
     - **ArangoDB:** A multi-model database that supports graphs alongside documents and key-value pairs.

3. **Vector Databases:**
   - **Definition:** Vector databases are designed to efficiently handle vectorized data, which is common in machine learning and numerical applications.
   - **Examples:**
     - **InfluxDB:** A time-series database that can be used to store and query vector data, especially in the context of monitoring and analytics.
     - **TimescaleDB:** An open-source time-series database built on top of PostgreSQL, designed to handle large volumes of time-stamped data.
     - **FaunaDB:** A multi-model database that supports documents, graphs, and temporal data, making it suitable for various applications including vector data storage.

4. **SQL Databases:**
   - **Definition:** SQL databases, or relational databases, use a structured query language (SQL) for defining and manipulating the data. They organize data into tables with rows and columns.
   - **Examples:**
     - **MySQL:** An open-source relational database management system that is widely used for web applications.
     - **PostgreSQL:** A powerful, open-source object-relational database system known for its extensibility and standards compliance.
     - **Microsoft SQL Server:** A relational database management system developed by Microsoft, commonly used in enterprise environments.

Each type of database has its strengths and weaknesses, and the choice of a database depends on the specific requirements of the application and the nature of the data being stored and processed.

## Why not NoSQL
- It’s schemaless properties make it ideal to for bootstraping a project fast.
- But as your app grows, this property makes it very easy for data to get curropted
- Problems?
  - Can lead to inconsistent database
  - Can cause runtime errors 
  - Is too flexible for an app that needs strictness

- Upsides?
  - Can move very fast
  - Can change schema very easily
 
💡
You might think that mongoose does add strictness to the codebase because we used to define a schema there. 
That strictness is present at the Node.js level, not at the DB level. You can still put in erroneous data in the database that doesn’t follow that schema.

## Why SQL?

- SQL databases have a strict schema. They require you to
  - Define your schema
  - Put in data that follows that schema
  - Update the schema as your app changes and perform migrations
 
- So there are 4 parts when using an SQL database (not connecting it to Node.js, just running it and putting data in it)
  - Running the database.
  - Using a library that let’s you connect and put data in it.
  - Creating a table and defining it’s schema.
  - Run queries on the database to interact with the data (Insert/Update/Delete)


## Creating a database
- Using neondb
- Using docker locally
- Using docker on windows
```
postgresql://username:password@ep-broken-frost-69135494.us-east-2.aws.neon.tech/calm-gobbler-41_db_2253874
```

Using a library that let’s you connect and put data in it.
1. psql
psql is a terminal-based front-end to PostgreSQL. It provides an interactive command-line interface to the PostgreSQL (or TimescaleDB) database. With psql, you can type in queries interactively, issue them to PostgreSQL, and see the query results.
How to connect to your database?
psql Comes bundled with postgresql. You don’t need it for this tutorial. We will directly be communicating with the database from Node.js
psql -h p-broken-frost-69135494.us-east-2.aws.neon.tech -d database1 -U 100xdevs
 
2. pg
pg is a Node.js library that you can use in your backend app to store data in the Postgres DB (similar to mongoose). We will be installing this eventually in our app.

## Creating a table and defining it’s schema.
Tables in SQL
A single database can have multiple tables inside. Think of them as collections in a MongoDB database.

SQL stands for Structured query language. It is a language in which you can describe what/how you want to put data in the database.
To create a table, the command to run is - 
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
);
There are a few parts of this SQL statement, let’s decode them one by one
1. CREATE TABLE users
CREATE TABLE users: This command initiates the creation of a new table in the database named users.
2. id SERIAL PRIMARY KEY
id: The name of the first column in the users table, typically used as a unique identifier for each row (user). Similar to _id in mongodb
SERIAL: A PostgreSQL-specific data type for creating an auto-incrementing integer. Every time a new row is inserted, this value automatically increments, ensuring each user has a unique id.
PRIMARY KEY: This constraint specifies that the id column is the primary key for the table, meaning it uniquely identifies each row. Values in this column must be unique and not null.
3.  email VARCHAR(255) UNIQUE NOT NULL,
email: The name of the second column, intended to store the user's username.
VARCHAR(50): A variable character string data type that can store up to 50 characters. It's used here to limit the length of the username.
UNIQUE: This constraint ensures that all values in the username column are unique across the table. No two users can have the same username.
NOT NULL: This constraint prevents null values from being inserted into the username column. Every row must have a username value.
4. password VARCHAR(255) NOT NUL
Same as above, can be non uniqye
5. created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
created_at: The name of the fifth column, intended to store the timestamp when the user was created.
TIMESTAMP WITH TIME ZONE: This data type stores both a timestamp and a time zone, allowing for the precise tracking of when an event occurred, regardless of the user's or server's time zone.
DEFAULT CURRENT_TIMESTAMP: This default value automatically sets the created_at column to the date and time at which the row is inserted into the table, using the current timestamp of the database server.
 
💡
If you have access to a database right now, try running this command to create a simple table in there
```
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
);
```

Interacting with the database

There are 4 things you’d like to do with a database 
 
1. INSERT
INSERT INTO users (username, email, password) VALUES ('username_here', 'user@example.com', 'user_password');
💡
Notice how you didn’t have to specify the id  because it auto increments
2. UPDATE
UPDATE users
SET password = 'new_password' WHERE email = 'user@example.com';
3. DELETE
DELETE FROM users WHERE id = 1;
4. Select
SELECT * FROM users WHERE id = 1;
 
💡
Try running all 4 of these in your terminal if you have psql  installed locally.
If not, that’s fine we’ll eventually be doing these through the pg  library

## How to do queries from a Node.js app?
In the end, postgres exposes a protocol that someone needs to talk to be able to send these commands (update, delete) to the database.
psql  is one such library that takes commands from your terminal and sends it over to the database.
To do the same in a Node.js , you can use one of many Postgres clients 
pg library
https://www.npmjs.com/package/pg
Non-blocking PostgreSQL client for Node.js. 
Documentation - https://node-postgres.com/

import { Client } from 'pg'
 
const client = new Client({
  host: 'my.database-server.com',
  port: 5334,
  database: 'database-name',
  user: 'database-user',
  password: 'secretpassword!!',
})

client.connect()


const result = await client.query('SELECT * FROM USERS;')
console.log(result)

// write a function to create a users table in your database.
import { Client } from 'pg'
 
const client = new Client({
  connectionString: "postgresql://postgres:mysecretpassword@localhost/postgres"
})

async function createUsersTable() {
    await client.connect()
    const result = await client.query(`
        CREATE TABLE users (
            id SERIAL PRIMARY KEY,
            username VARCHAR(50) UNIQUE NOT NULL,
            email VARCHAR(255) UNIQUE NOT NULL,
            password VARCHAR(255) NOT NULL,
            created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
        );
    `)
    console.log(result)
}

createUsersTable();

### Creating a simple Node.js app

Initialise an empty typescript project
npm init -y
npx tsc --init
Change the rootDir and outDir in tsconfig.json
"rootDir": "./src",
"outDir": "./dist",
Install the pg library and it’s types (because we’re using TS)
npm install pg
npm install @types/pg
Create a simple Node.js app that lets you put data
Create a function that let’s you insert data into a table. Make it async, make sure client.connect resolves before u do the insert
Answer
💡
This is an insecure way to store data in your tables. 
When you expose this functionality eventually via HTTP, someone can do an SQL INJECTION to get access to your data/delete your data.
More secure way to store data.
Update the code so you don’t put user provided fields in the SQL string
What are user provided strings?
In your final app, this insert statement will be done when a user signs up on your app. 
Email, username, password are all user provided strings
What is the SQL string ?
const insertQuery = "INSERT INTO users (username, email, password) VALUES ('username2', 'user3@example.com', 'user_password');";
Hint
const insertQuery = 'INSERT INTO example_table(column1, column2) VALUES($1, $2)';
const res = await client.query(insertQuery, [column1Value, column2Value]);
 
Solution
import { Client } from 'pg';

// Async function to insert data into a table
async function insertData(username: string, email: string, password: string) {
  const client = new Client({
    host: 'localhost',
    port: 5432,
    database: 'postgres',
    user: 'postgres',
    password: 'mysecretpassword',
  });

  try {
    await client.connect(); // Ensure client connection is established
    // Use parameterized query to prevent SQL injection
    const insertQuery = "INSERT INTO users (username, email, password) VALUES ($1, $2, $3)";
    const values = [username, email, password];
    const res = await client.query(insertQuery, values);
    console.log('Insertion success:', res); // Output insertion result
  } catch (err) {
    console.error('Error during the insertion:', err);
  } finally {
    await client.end(); // Close the client connection
  }
}

// Example usage
insertData('username5', 'user5@example.com', 'user_password').catch(console.error);
Query data
Write a function getUser that lets you fetch data from the database given a email as input.
import { Client } from 'pg';

// Async function to fetch user data from the database given an email
async function getUser(email: string) {
    const client = new Client({
        host: 'localhost',
        port: 5432,
        database: 'postgres',
        user: 'postgres',
        password: 'mysecretpassword',
    });
    

  try {
    await client.connect(); // Ensure client connection is established
    const query = 'SELECT * FROM users WHERE email = $1';
    const values = [email];
    const result = await client.query(query, values);
    
    if (result.rows.length > 0) {
      console.log('User found:', result.rows[0]); // Output user data
      return result.rows[0]; // Return the user data
    } else {
      console.log('No user found with the given email.');
      return null; // Return null if no user was found
    }
  } catch (err) {
    console.error('Error during fetching user:', err);
    throw err; // Rethrow or handle error appropriately
  } finally {
    await client.end(); // Close the client connection
  }
}

// Example usage
getUser('user5@example.com').catch(console.error);

##  Relationships and Transactions
Relationships let you store data in different tables and relate it with each other.
Relationships in Mongodb
Since mongodb is a NoSQL database, you can store any shape of data in it. 
If I ask you to store a users details along with their address, you can store it in an object that has the address details.

Relationships in SQL
Since SQL can not store objects as such, we need to define two different tables to store this data in.

This is called a relationship , which means that the Address table is related to the Users table.
When defining the table, you need to define the relationship 
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE addresses (
    id SERIAL PRIMARY KEY,
    user_id INTEGER NOT NULL,
    city VARCHAR(100) NOT NULL,
    country VARCHAR(100) NOT NULL,
    street VARCHAR(255) NOT NULL,
    pincode VARCHAR(20),
    created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
 
SQL query
To insert the address of a user - 
INSERT INTO addresses (user_id, city, country, street, pincode)
VALUES (1, 'New York', 'USA', '123 Broadway St', '10001');
 
Now if you want to get the address of a user given an id , you can run the following query - 
SELECT city, country, street, pincode
FROM addresses
WHERE user_id = 1;
Extra - Transactions in SQL
💡
Good question to have at this point is what queries are run when the user signs up and sends both their information and their address in a single request.
Do we send two SQL queries into the database? What if one of the queries (address query for example) fails? 
This would require transactions  in SQL to ensure either both the user information and address goes in, or neither does
SQL Query
BEGIN; -- Start transaction

INSERT INTO users (username, email, password)
VALUES ('john_doe', 'john_doe1@example.com', 'securepassword123');

INSERT INTO addresses (user_id, city, country, street, pincode)
VALUES (currval('users_id_seq'), 'New York', 'USA', '123 Broadway St', '10001');

Node.js Code
import { Client } from 'pg';

async function insertUserAndAddress(
    username: string, 
    email: string, 
    password: string, 
    city: string, 
    country: string, 
    street: string, 
    pincode: string
) {
    const client = new Client({
        host: 'localhost',
        port: 5432,
        database: 'postgres',
        user: 'postgres',
        password: 'mysecretpassword',
    });

    try {
        await client.connect();

        // Start transaction
        await client.query('BEGIN');

        // Insert user
        const insertUserText = `
            INSERT INTO users (username, email, password)
            VALUES ($1, $2, $3)
            RETURNING id;
        `;
        const userRes = await client.query(insertUserText, [username, email, password]);
        const userId = userRes.rows[0].id;

        // Insert address using the returned user ID
        const insertAddressText = `
            INSERT INTO addresses (user_id, city, country, street, pincode)
            VALUES ($1, $2, $3, $4, $5);
        `;
        await client.query(insertAddressText, [userId, city, country, street, pincode]);

        // Commit transaction
        await client.query('COMMIT');

        console.log('User and address inserted successfully');
    } catch (err) {
        await client.query('ROLLBACK'); // Roll back the transaction on error
        console.error('Error during transaction, rolled back.', err);
        throw err;
    } finally {
        await client.end(); // Close the client connection
    }
}

// Example usage
insertUserAndAddress(
    'johndoe', 
    'john.doe@example.com', 
    'securepassword123', 
    'New York', 
    'USA', 
    '123 Broadway St', 
    '10001'
);

