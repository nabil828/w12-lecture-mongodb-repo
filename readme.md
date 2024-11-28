# MongoDB & Mongoose tutorial

## I. MongoDB Introduction

MongoDB is a popular NoSQL database that stores data in collections of JSON-like documents. It is known for its flexibility and scalability, making it a popular choice for modern web applications. Mongoose is an Object Data Modeling (ODM) library for MongoDB and Node.js that provides a more structured way to interact with MongoDB.

### A. What is MongoDB?

MongoDB is a NoSQL database that stores data in collections of JSON-like documents. It is known for its flexibility and scalability, making it a popular choice for modern web applications.

## II. Getting started with MongoDB

### A. Installation

To install MongoDB on your system, you can follow the instructions provided on the official MongoDB website. You can download the MongoDB Community Server for free and install it on your system. For example, if you are using Windows, you can find the installation instructions [here](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-windows/). On this page, you can find information on how to download the MongoDB Community Server, install it on your system, and start the MongoDB server.
![alt text](images/image.png).

If you want a playground to test MongoDB queries, you can use https://mongoplayground.net/. It is an online MongoDB shell that allows you to run MongoDB queries and see the results in real-time. You can use it to practice MongoDB queries and learn how to interact with MongoDB.

### B. Starting the MongoDB server

Depending on your operating system, you can start the MongoDB server by running the appropriate command. Check the `Run MongoDB Community Edition` section of the installation instructions for your operating system to find the command you need to run to start the MongoDB server.

### C. Connecting to MongoDB

Once the MongoDB server is running, you can connect to it using the `mongo` shell. Open a new terminal window and run the `mongo` command to start the `mongo` shell. By default, the `mongo` shell will connect to the MongoDB server running on `localhost` on port `27017`. You can also use GUI tools like MongoDB Compass to connect to MongoDB and interact with the data. I prefer to use VSCode with the MongoDB extension to interact with MongoDB. Install the MongoDB extension in VSCode and connect to your MongoDB server to view and interact with the data. Here is a [link](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode) to the MongoDB extension for VSCode.

## MongoDB Basics

![alt text](images/image-2.png)
MongoDB stores data in collections, which are similar to tables in relational databases. Each collection contains a set of documents, which are JSON-like objects that store the data. Each document in a collection can have a different structure, allowing you to store data in a flexible way.
![alt text](images/image-3.png)

## III. CRUD Operations in MongoDB

MongoDB provides a set of CRUD operations to interact with the data stored in the database. These operations include creating, reading, updating, and deleting data.

### A. Inserting Data

To insert a document into a collection, you can use the `insertOne` or `insertMany` methods. The `insertOne` method inserts a single document into the collection, while the `insertMany` method inserts multiple documents into the collection.

```javascript
db.collection.insertOne({ key: value });
```

![alt text](images/image-4.png)

### B. Querying Data

To query data from a collection, you can use the `find` method. The `find` method returns a cursor that you can iterate over to retrieve the documents that match the query criteria.

```javascript
db.collection.find({ key: value });
```

![alt text](images/image-5.png)

### C. Updating Data

To update a document in a collection, you can use the `updateOne` or `updateMany` methods. The `updateOne` method updates a single document that matches the query criteria, while the `updateMany` method updates multiple documents that match the query criteria.

```javascript
db.collection.updateOne({ key: value }, { $set: { key: value } });
```

The `$set` operator is used to set the value of a field in the document.
There are other update operators like `$inc`, `$push`, `$pull`, etc., that you can use to update documents in MongoDB.
HEre is a table summarizing the update operators in MongoDB:
| Operator | Description |
| --- | --- |
| `$set` | Sets the value of a field in the document. |
| `$inc` | Increments the value of a field by a specified amount. |
| `$push` | Adds an element to an array field. |
| `$pull` | Removes an element from an array field. |
| `$addToSet` | Adds an element to an array field if it does not already exist. |
| `$pop` | Removes the first or last element from an array field. |
| `$pullAll` | Removes all matching elements from an array field. |
| `$rename` | Renames a field in the document. |
| `$unset` | Removes a field from the document. |

You can find the complete list of update operators in the MongoDB documentation [here](https://docs.mongodb.com/manual/reference/operator/update/).

### D. Deleting Data

To delete a document from a collection, you can use the `deleteOne` or `deleteMany` methods. The `deleteOne` method deletes a single document that matches the query criteria, while the `deleteMany` method deletes multiple documents that match the query criteria.

```javascript
db.collection.deleteOne({ key: value });
```

![alt text](images/image-6.png)

### Miscellaneous MongoDB Commands

Here are some other useful MongoDB commands that you can use to interact with the database:

- `show dbs`: Lists all the databases on the MongoDB server.
- `use database`: Switches to the specified database.
- `show collections`: Lists all the collections in the current database.
- `db.collection.drop()`: Drops the specified collection.
- `db.dropDatabase()`: Drops the current database.

### Unicorns Queries

Let us MongoDB to answer the following questions:

```
Q1. Find the male unicorns weigh more than 700 pounds
Q2. Find the unicorns that have no vampire field
Q3. Find the unicorns that like apples or carrots
Q4. Find the female unicorns that either love apples or weigh less than 500 pounds
Q5. Decrease unicorn Pilot’s number of vampires by 2
Q6. Add “sugar” to the list of food unicorn Aurora loves to eat
Q7. Give all of the unicorns vaccine (set vaccinated to be true)
Q8. Sort the unicorns based on weights decreasingly
Q9. Sort the unicorns based on the names increasingly, then the number of vampires decreasingly
Q10. Get the second and third heaviest unicorns
Q11. Count the number of unicorns who have more than 50 vampires
Q12. Find the average weight of unicorns that love apples
```

You can find the JSON data for the unicorns collection in the [little mongodb book](https://github.com/karlseguin/the-little-mongodb-book/blob/master/en/mongodb.markdown).

You may test your attempts in:

- [MongoDB Shell](https://docs.mongodb.com/manual/mongo/)
- [MongoDB Compass](https://www.mongodb.com/products/compass)
- [VSCode with MongoDB extension](https://marketplace.visualstudio.com/items?itemName=mongodb.mongodb-vscode)
- [MongoDB Playground](https://mongoplayground.net/)

I will choose the MongoDB extension in VSCode to answer the questions. Just make sure you install the MongoDB extension in VSCode and connect to your MongoDB server to view and interact with the data.

After opening new VSCode window, click on the MongoDB icon on the left sidebar, then click on the `Connect to MongoDB` button to connect to your MongoDB server. You can then view the databases, collections, and documents in your MongoDB server.
![alt text](images/image-7.png)

If you see the green leaf icon, it means you are connected to the MongoDB server.
![alt text](images/image-8.png)

You will have some databases in your MongoDB server. Expand any database and Right Click on the collection you want to work with and select `View Documents` to see the collections in the database.

To insert the unicorns into a new collection, create a new playground file and insert the unicorns data into a new collection. Here is the code to insert the unicorns data into a new collection:

```javascript
use("w12db");
db.unicorns.insert({
  name: "Horny",
  dob: new Date(1992, 2, 13, 7, 47),
  loves: ["carrot", "papaya"],
  weight: 600,
  gender: "m",
  vampires: 63,
});
db.unicorns.insert({
  name: "Aurora",
  dob: new Date(1991, 0, 24, 13, 0),
  loves: ["carrot", "grape"],
  weight: 450,
  gender: "f",
  vampires: 43,
});
db.unicorns.insert({
  name: "Unicrom",
  dob: new Date(1973, 1, 9, 22, 10),
  loves: ["energon", "redbull"],
  weight: 984,
  gender: "m",
  vampires: 182,
});
db.unicorns.insert({
  name: "Roooooodles",
  dob: new Date(1979, 7, 18, 18, 44),
  loves: ["apple"],
  weight: 575,
  gender: "m",
  vampires: 99,
});
db.unicorns.insert({
  name: "Solnara",
  dob: new Date(1985, 6, 4, 2, 1),
  loves: ["apple", "carrot", "chocolate"],
  weight: 550,
  gender: "f",
  vampires: 80,
});
db.unicorns.insert({
  name: "Ayna",
  dob: new Date(1998, 2, 7, 8, 30),
  loves: ["strawberry", "lemon"],
  weight: 733,
  gender: "f",
  vampires: 40,
});
db.unicorns.insert({
  name: "Kenny",
  dob: new Date(1997, 6, 1, 10, 42),
  loves: ["grape", "lemon"],
  weight: 690,
  gender: "m",
  vampires: 39,
});
db.unicorns.insert({
  name: "Raleigh",
  dob: new Date(2005, 4, 3, 0, 57),
  loves: ["apple", "sugar"],
  weight: 421,
  gender: "m",
  vampires: 2,
});
db.unicorns.insert({
  name: "Leia",
  dob: new Date(2001, 9, 8, 14, 53),
  loves: ["apple", "watermelon"],
  weight: 601,
  gender: "f",
  vampires: 33,
});
db.unicorns.insert({
  name: "Pilot",
  dob: new Date(1997, 2, 1, 5, 3),
  loves: ["apple", "watermelon"],
  weight: 650,
  gender: "m",
  vampires: 54,
});
db.unicorns.insert({
  name: "Nimue",
  dob: new Date(1999, 11, 20, 16, 15),
  loves: ["grape", "carrot"],
  weight: 540,
  gender: "f",
});
db.unicorns.insert({
  name: "Dunx",
  dob: new Date(1976, 6, 18, 18, 18),
  loves: ["grape", "watermelon"],
  weight: 704,
  gender: "m",
  vampires: 165,
});
```

Notice that this is not JS code, but MongoDB shell code. You can run this code in the MongoDB shell to insert the unicorns data into a new collection. The VSCode just provides a nice interface to interact with MongoDB.

To Run the code in VSCode, click on the `Run` button on the top right corner of the editor.
![alt text](images/image-9.png)

Oh, I forgot to mention that you need to create a new database called `w12db` before inserting the unicorns data. That is why I used the `use('w12db')` command to switch to the `w12db` database before inserting the unicorns data.

Phew! Now that we have the unicorns data in a new collection, we can start answering the questions.

**Q1. Find the male unicorns weigh more than 700 pounds**
In a new playground file, write the following

```javascript
db.unicorns.find({ gender: "m", weight: { $gt: 700 } });
```

The `find` method takes two arguments: the query criteria and the projection. The query criteria is an object that specifies the conditions that the documents must meet to be included in the result set. Both arguments are objects, and the query criteria object can contain multiple key-value pairs to specify the conditions that the documents must meet.

the `$gt` operator is used to find documents where the value of the field is greater than the specified value.

Here is a table summary of the comparison operators in MongoDB:
| Operator | Description |
| --- | --- |
| `$eq` | Matches values that are equal to a specified value. |
| `$gt` | Matches values that are greater than a specified value. |
| `$gte` | Matches values that are greater than or equal to a specified value. |
| `$lt` | Matches values that are less than a specified value. |
| `$lte` | Matches values that are less than or equal to a specified value. |
| `$ne` | Matches values that are not equal to a specified value. |
| `$in` | Matches any of the values specified in an array. |
| `$nin` | Matches none of the values specified in an array. |

You can find the complete list of comparison operators in the MongoDB documentation [here](https://docs.mongodb.com/manual/reference/operator/query-comparison/).

You should get `x` unicorns for this query.

**Q2. Find the unicorns that have no vampire field**
In a new playground file, write the following

```javascript
db.unicorns.find({ vampires: { $exists: false } });
```

The `$exists` operator is used to find documents where the field exists or does not exist in the document.

You should get unicorns for this query.

**Q3. Find the unicorns that like apples or carrots**
In a new playground file, write the following

```javascript
db.unicorns.find({ loves: { $in: ["apple", "carrot"] } });
```

The `$in` operator is used to find documents where the value of the field matches any of the values specified in an array. The `$in` operator always takes an array of values to match against.

<details>
<summary>
Matching all values in an array
</summary>
If you want match all values in the array, you can use the `$all` operator instead where the order of the values in the array matters. If the order does not matter, you can use the `$elemMatch` operator. Check the MongoDB documentation for more information on these operators.
</details>

Alternatively, you can use the `$or` operator to achieve the same result:

```javascript
db.unicorns.find({ $or: [{ loves: "apple" }, { loves: "carrot" }] });
```

The `$or` operator is used to find documents where at least one of the conditions specified in an array is met. Notice that the `$or` operator takes an array of conditions, and each condition is an object that specifies the conditions that the documents must meet.

You should get `x` unicorns for this query.

**Q4. Find the female unicorns that either love apples or weigh less than 500 pounds**
In a new playground file, write the following

```javascript
db.unicorns.find({
  gender: "f",
  $or: [{ loves: "apple" }, { weight: { $lt: 500 } }],
});
```

This query should return `x` unicorns.

**Q5. Decrease unicorn Pilot’s number of vampires by 2**
In a new playground file, write the following

```javascript
db.unicorns.updateOne({ name: "Pilot" }, { $inc: { vampires: -2 } });
```

The `$inc` operator is used to increment or decrement the value of a field in the document. You can specify a positive value to increment the field or a negative value to decrement the field.

To verify the update, you can run the following query:

```javascript
db.unicorns.find({ name: "Pilot" });
```

**Q6. Add “sugar” to the list of food unicorn Aurora loves to eat**

In a new playground file, write the following

```javascript
db.unicorns.updateOne({ name: "Aurora" }, { $push: { loves: "sugar" } });
```

The `$push` operator is used to add an element to an array field in the document.

**Q7. Give all of the unicorns vaccine (set vaccinated to be true)**
In a new playground file, write the following

```javascript
db.unicorns.updateMany({}, { $set: { vaccinated: true } });
```

The `$set` operator is used to set the value of a field in the document.

**Q8. Sort the unicorns based on weights decreasingly**
In a new playground file, write the following

```javascript
db.unicorns.find().sort({ weight: -1 });
```

The `sort` method is used to sort the documents in the result set based on the specified field. The sort method takes an object that specifies the field to sort on and the sort order. The sort order can be either `1` for ascending order or `-1` for descending order.

**Q9. Sort the unicorns based on the names increasingly, then the number of vampires decreasingly**
In a new playground file, write the following

```javascript
db.unicorns.find().sort({ name: 1, vampires: -1 });
```

**Q10. Get the second and third heaviest unicorns**
In a new playground file, write the following

```javascript
db.unicorns.find().sort({ weight: -1 }).skip(1).limit(2);
```

The `skip` method is used to skip a specified number of documents in the result set. The `limit` method is used to limit the number of documents returned in the result set.

**Q11. Count the number of unicorns who have more than 50 vampires**
In a new playground file, write the following

```javascript
db.unicorns.count({ vampires: { $gt: 50 } });
```

The `count` method is used to count the number of documents that match the query criteria.

This query should return `x` unicorns.

**Q12. Find the average weight of unicorns that love apples**
In a new playground file, write the following

```javascript
db.unicorns.aggregate([
  { $match: { loves: "apple" } },
  { $group: { _id: null, avgWeight: { $avg: "$weight" } } },
]);
```

To calculate the average weight of unicorns that love apples, you can use the `aggregate` method with the `$match` and `$group` stages. The `$match` stage is used to filter the documents that match the query criteria, and the `$group` stage is used to group the documents and calculate the average weight.

Beside the `$avg` operator, there are other aggregation operators like `$sum`, `$min`, `$max`, `$first`, `$last`, etc., that you can use to perform aggregation operations in MongoDB.

Phew! That was a lot of queries. Try to write the queries on your own to practice and understand how MongoDB queries work.

## I. Introduction to Mongoose

### A. What is Mongoose?

Mongoose is an Object Data Modeling (ODM) library for MongoDB and Node.js that provides a more structured way to interact with MongoDB. It provides a schema-based solution to model the application data and define the data structure in a more consistent and predictable way.

### B. Advantages of using Mongoose

Mongoose provides several advantages when working with MongoDB:

- Schema-based modeling: Mongoose allows you to define a schema for your data, which provides a more structured way to interact with MongoDB.
- Data validation: Mongoose provides built-in data validation features to ensure that the data stored in MongoDB meets the specified requirements.

and many more...

### C. How Mongoose works with MongoDB

## II. Getting Started with Mongoose

### A. Installation

To install Mongoose in your Node.js project, you can use npm or yarn to install the mongoose package. You can run the following command to install Mongoose in your project:

```bash
npm install mongoose
```

### B. Connecting to MongoDB

To connect to MongoDB using Mongoose, you need to create a connection to the MongoDB server. You can use the `mongoose.connect` method to connect to the MongoDB server. Here is an example of how to connect to MongoDB using Mongoose:

```javascript
const mongoose = require("mongoose");

main().catch((err) => console.log(err));

async function main() {
  await mongoose.connect("mongodb://127.0.0.1:27017/test");

  // use `await mongoose.connect('mongodb://user:password@127.0.0.1:27017/test');` if your database has auth enabled
}
```

### C. Defining a Mongoose schema

To define a Mongoose schema, you can use the `mongoose.Schema` class to create a new schema object. The schema object allows you to define the structure of the data that will be stored in MongoDB. Here is an example of how to define a Mongoose schema:

```javascript
const kittySchema = new mongoose.Schema({
  name: String,
});
```

In this example, we define a Mongoose schema for a `kittens` with a `name` field of type `String`.

### D. Creating a Mongoose model

To create a Mongoose model, you can use the `mongoose.model` method to create a new model based on the schema you defined. The model provides an interface to interact with the data stored in MongoDB. Here is an example of how to create a Mongoose model:

```javascript
const Kitten = mongoose.model("kittens", kittySchema);
```

In this example, we create a Mongoose model for the `kittens` collection based on the `kittySchema` schema.

## III. CRUD Operations with Mongoose

### A. Reading documents

Let us prepare an Express.JS application to interact with MongoDB using Mongoose.

create `server.js` file and add the following code:

```javascript
const express = require("express");
const mongoose = require("mongoose");

const app = express();
const port = 3000;

main().catch((err) => console.log(err));

async function main() {
  await mongoose.connect("mongodb://127.0.0.1:27017/w12db");

  const unicornSchema = new mongoose.Schema({
    name: String,
  });

  const unicornModel = mongoose.model("unicorns", unicornSchema);

  app.get("/", (req, res) => {
    res.send("Hello World!");
  });

  app.listen(port, () => {
    console.log(`Server is running on http://localhost:${port}`);
  });

  app.get("/unicorns", async (req, res) => {
    const result = await unicornModel.find({});
    console.log(result);
    res.json(result);
  });
}
```

install the `express` package by running the following command:

```bash
npm install express
```

Also, install `mongoose` by running the following command:

```bash
npm install mongoose
```

Run the server by running the following command:

```bash
node server.js
```

Now let us query the MongoDB database using Mongoose.

```js
app.get("/unicorns", async (req, res) => {
  const result = await unicornModel.find({});
  console.log(result);
  res.json(result);
});
```

The `find` method is used to query the MongoDB database and retrieve all the documents in the `unicorns` collection. The `find` method returns a promise that resolves to an array of documents that match the query criteria. We always use the model to interact with the database and execute the CRUD operations.

### B. Creating a new document

To create a new document in the `unicorns` collection, you can use the `create` method on the model. Here is an example of how to create a new document in the `unicorns` collection:

```javascript
app.use(express.json());
app.post("/unicorns", async (req, res) => {
  console.log(req.body);
  try {
    const result = await unicornModel.insertMany([
      { name: req.body.name, weight: Number(req.body.weight) },
    ]);
    console.log(result);
  } catch (err) {
    console.log(err);
  }
  res.send("Unicorn added");
});
```

The `insertMany` method is used to insert multiple documents into the collection. The `insertMany` method takes an array of documents to insert into the collection.

Notice the usage of `express.json()` middleware to parse the request body as JSON. This middleware is used to parse the request body and make it available in `req.body`.

Also, notice the usage of `Number` function to convert the weight to a number before inserting it into the database.

One last thing, do you remember that `.catch()` to handle errors? You can instead use `try-catch` block to handle errors. This is a better way to handle errors in asynchronous code.

Did I say one last thing? I lied. Make sure you modify the schema to include the `weight` field.

```javascript
const unicornSchema = new mongoose.Schema({
  name: String,
  weight: Number,
});
```

![alt text](images/image-10.png)

![alt text](images/image-11.png)

### C. Updating documents

To update a document in the `unicorns` collection, you can use the `updateOne` or `updateMany` methods on the model. Here is an example of how to update a document in the `unicorns` collection:

```javascript
app.patch("/unicorns/:name", async (req, res) => {
  try {
    const result = await unicornModel.updateOne(
      { name: req.params.name },
      {
        $set: { name: req.body.name, weight: Number(req.body.weight) },
      }
    );
    console.log(result);
  } catch (err) {
    console.log(err);
  }
  res.send("Unicorn updated");
});
```

HTTP PATCH usually used to update a resource partially. On the other hand, HTTP PUT is used to update a resource entirely. In this case, we are using HTTP PATCH to update the unicorn's name and weight. If you want to replace the entire document, you can use HTTP PUT and mongoose's `replaceOne` method.

HEre is a table summarizing HTTP methods and their mongoose methods:

| HTTP Method | Mongoose Method | Description                                                 |
| ----------- | --------------- | ----------------------------------------------------------- |
| GET         | find            | Retrieves documents that match the query criteria.          |
| POST        | create          | Creates a new document in the collection.                   |
| PATCH       | updateOne       | Updates a single document that matches the query criteria.  |
| DELETE      | deleteOne       | Deletes a single document that matches the query criteria.  |
| PUT         | replaceOne      | Replaces a single document that matches the query criteria. |

### D. Deleting documents

To delete a document in the `unicorns` collection, you can use the `deleteOne` or `deleteMany` methods on the model. Here is an example of how to delete a document in the `unicorns` collection:

```javascript
app.delete("/unicorns/:name", async (req, res) => {
  try {
    const result = await unicornModel.deleteOne({ name: req.params.name });
    console.log(result);
  } catch (err) {
    console.log(err);
  }
  res.send("Unicorn deleted");
});
```

If you think of it, we have just build a simple _Unicorns_ RESTful API. Clients can interact with the API to create, read, update, and delete unicorns in the database.

HEre is a table a summary of the RESTful API endpoints we have partially built:

And here is a table of the RESTful API endpoints we have implemented:
| Method | Endpoint | Description |
| --- | --- | --- |
| GET | /unicorns | Returns all unicorns. |
| POST | /unicorns | Adds a new unicorn. |
| DELETE | /unicorns/:name | Deletes a unicorn by name. |
| PATCH | /unicorns/:name | Updates a unicorn by name. It should only update the fields that are passed in the request body. |
| PUT | /unicorns/:name | Replaces a unicorn by name. It should replace the entire document with the new document passed in the request body. |
| GET | /unicorns/:name | Returns a unicorn by name. |
| GET | /unicorns/search?name=... | Returns a unicorn by name. |

As a challenge try to complete the API by implementing the remaining endpoints. We will practice this in the next week's labs.
