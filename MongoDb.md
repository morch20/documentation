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
- Equal to `$eq`
    ```mongodb
    db."collection name".find({"rating": {$eq : 10} })
    ```
- Not equal `$ne`
    ```mongodb
    db."collection name".find({"rating": {$ne : 0} })
    ```
- Greater then `$gt`
    ```mongodb
    db."collection name".find({"rating": {$gt : 5} })
    ```
- Greater or Equal then `$gte`
    ```mongodb
    db."collection name".find({"rating": {$gte : 5} })
    ```
- Less then `$lt`
    ```mongodb
    db."collection name".find({"rating": {$lt : 10} })
    ```
- Less then or Equal `$lte`
    ```mongodb
    db."collection name".find({"rating": {$let : 10} })
    ```
- In `$in`
    ```mongodb
    db."collection name".find({ section: { $in : ['Planet', ...] } })
    ```
- Not in `$nin`
    ```mongodb
    db."collection name".find({ section: { $nin : ['Planet',...] } })
    ```
<br>

#### Boolean Operators
- Or `$or`
    ```mongodb
    db."collection name".find({$or: [{price: {$gte:50}}, {amount: 1} ]})
    ```
- And `$and`
    ```mongodb
    db."collection name".find({$and: [{price: 50}, {amount: 10} ]})
    ```
- Not `$not`
    ```mongodb
    db."collection name".find({price: {$not: {$eq:50}} })
    ```

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

#### Delete collection
```mongodb
db."collection name".drop()
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

#### Filter document's index when they are arrays
In the following document genre has an array:  
```json
{
    "author": "Your mom",
    "rating": 10,
    "genre": ["fantasy", "magic"]
}
```
<br>

To find all documents that have the property "fantasy" inside "genre"  
```mongodb
db."collection name".find({"genre": "fantasy"})
```
<br>

To find all documents with **only** the specified property(ies) inside "genre"
```mongodb
db."collection name".find({"genre": ["fantasy", "magic", ...]})
```
<br>

To find all documents that the specified properties are **in** the array even if there are other properties
```mongodb
db."collection name".find({"genre": {$all: ["fantasy", ...]}})
```
<br>

#### Filter documents using nested documents
- For documents nested inside of arrays
    ```json
    {
        "arr": [
            {
                "age": 20,
                "name": "luigi"
            },
            {
                "age": 19,
                "name": "sarah"
            },
            {
                "age": 25,
                "name": "pepe"
            }
        ]
    },
    {...},
    {...}
    ```  
    The document containing "arr" will be returned using:
    ```mongodb
    db."collection name".find({ "arr.age": 20})
    ```
<br>

- Or they can be nested inside other documents
    ```json
    {
        "obj": {
        "person1": {
            "age": 20,
            "name": "luigi"
        },
        "person2": {
            "age": 19,
            "name": "sarah"
        },
        "person3": {
            "age": 25,
            "name": "pepe"
        }
        }
    },
    {...},
    {...}
    ```
    In this case you will have to choose the "person" and see if they have the index/property you are looking for
    ```mongodb
    db."collection name".find({ "obj.person1.age": 20})
    ```  
    <br>

    or use the `$exists` query selector
    ```mongodb
    db."collection name".find({ "obj": {"$exists": { "age": 20}} })
    ```
    In both cases, the document containing "obj" will be returned


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


## Deleting Documents
---

#### Delete one document
```mongodb
db."collection name".deleteOne("property")
```
<br>

#### Delete many documents
```mongodb
db."collection name".deleteMany("property")
```
<br>

#### Delete all documents in collection
```mongodb
db."collection name".deleteMany({})
```
<br>


## Updating Documents
---

#### Update one document
It is better to use the unique id property to find the document
```mongodb
db."collection name".updateOne({"property to find document"}, {$set: {"property(ies) to be updated"}})
```
<br>

#### Update many documents
```mongodb
db."collection name".updateMany({"property to find document"}, {$set: {"property(ies) to be updated"}})
```
<br>


#### Increment a index in a document
```mongodb
db."collection name".updateOne({"property to find document"}, {$inc: {"property(ies) to be updated"}})
```
<br>

#### Delete an array element of an index in a document
```mongodb
db."collection name".updateOne({"property to find document"}, {$pull: {"array name": "element to be deleted"}})
```
<br>

#### Delete multiple array elements of an index in a document
```mongodb
db."collection name".updateOne({"property to find document"}, {$pull: {"array name": {$each: [elements to be deleted]}}})
```
<br>

#### Adding an array element of an index in a document
```mongodb
db."collection name".updateOne({"property to find document"}, {$push: {"array name": "element to be added"}})
```
<br>

#### Adding multiple array elements of an index in a document
```mongodb
db."collection name".updateOne({"property to find document"}, {$push: {"array name": {$each: [elements to be added]}}})
```
<br>

More operators for updating documents
- `$unset`
- `$rename`
- `$mul`
- `$min`
- `$max`
- `$currentDate`



