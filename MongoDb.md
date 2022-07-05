#### Official MongoDB Cheat Sheet

[Click here for website](https://www.mongodb.com/developer/products/mongodb/cheat-sheet/)
<br>

#### Official MongoDB Documentation
[Click here for website](https://www.mongodb.com/docs/)

---

First you need to **connect to the sever** before doing anything else
<br>

Connect on MongoDB Compass

- On MongoDB Compass > new collection > connect to local host
<br>

Connect on using mongosh

- Connect to default port 27017
    ```mongodb
    mongo
    ```
<br>

This is going to create 3 new databases by default named: **admin**, **config**, and **local**.
<br>


# Basics
---


#### Show all databases
```mongodb
show dbs
```
<br>

#### Show current database
```mongodb
db
```
<br>

#### Switch database
This will access to the database named even if it doesn't exist
```mongodb
use "name"
```
<br>

#### Make a variable
```mongodb
var "variable name" = "value"
```
<br>

#### Get variable
```mongodb
"variable name"
```
<br>

#### Arithmetic Operators
- Greater then `$gt`
- Greater or Equal then `$gte`
- Less then `$lt`
- Less then or Equal `$lte`

```mongodb
db."collection name".find({"rating": })
```
<br>

#### Boolean Operators
- Or `$or`


<br>
#### Make new database/collection/document
In order to make a database you need to make a collection first, and in order to make a collection you need to make a document first or use the `createCollection()` method.  

Switch to the database name you want to create

```mongodb
use "database name"
```  
<br>

Then, make the document using desired collection name  
```mongodb
db."collection name".insertOne("document")
```
<br>


# Collections
---

#### Create collection
```mongodb
db.createCollection("name")
```
or
```mongodb
db.createCollection("name", "jsonschema")
```
<br>

#### Show collections
```mongodb
show collections
```
<br>

#### Switch collection
```mongodb
db."collection name"
```
<br>


# CRUD Operations
---
<br>

## Creating documents
---

#### Insert one document to collection
```mongodb
db."collection name".insertOne()
```
<br>

#### Insert many documents to collection
```mongodb
db."collection name".insertMany(["document 1",...])
```
<br>


## Reading documents
---

#### Find one document
This will return the first occurrence if more document have the same index

```mongodb
db."collection name".findOne("property to be search for. Ex: id")
```
<br>

#### Find document
This method will find the first 20 documents
```mongodb
db."collection name".find()
``` 

To iterate through next 20 type
```mongodb
it
```
<br>


#### Filter documents
```mongodb
db."collection name".find("filter property(ies)")
```
<br>

#### Get specific properties from document
The index(es) have to be set to 1 to be returned
Ex: `{"title": 1}`
```mongodb
db."collection name".find({}, "index(es) to be returned")
```
<br>

#### Filter and get specific properties
```mongodb
db."collection name".find("filter index(es)", "index(es) to be returned")
```
<br>


#### Get specific amount of elements
```mongodb
db."collection name".find("filter index(es)").limit("amount")
```
<br>

#### Count documents
Returns all documents
```mongodb
db."collection name".countDocuments()
```

or
```mongodb
db."collection name".find().count()
```
<br>

#### Count filtered documents
```mongodb
db."collection name".find("filter index(es)").count()
```
<br>


#### Sort
Specify the index to be sort by and order
- Ex: `{"title": 1}` sort by title in ascending order
- Ex: `{"title": -1}` sort by title in descending order

```mongodb
db."collection name".find().sort()
```
<br>





