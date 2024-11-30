 # MongoDB-Basics
 MongoDB Basic Course - 1 
 1. MongoDB Database Methods
 2. MongoDB Collection Methods
 3. CRUD Operation
 4. Different data types
 5. Cursor Object

## Commands

>  ### MongoDB Database Methods

##### 1. Create Database
 Switches to the specified database, creating it if it doesn't exist

```bash
use <databaseName>   
```

###### 2. Read Database
 Displays the current database
 Lists all databases
```bash
show dbs                            
```

###### 3. Delete Database
Deletes the current database
```bash
db.dropDatabase()   
```

>  ### MongoDB Collection Methods



###### 1. List Collections

```bash
show collections
```


###### 2. Drop a Collection
```bash
db.<collectionName>.drop()
```
Drops (deletes) the specified collection from the database.
Example: db.students.drop()

###### 3. Count Documents in a Collection
```bash
db.<collectionName>.countDocuments({<filter>})
```
Counts the number of documents matching the filter in the collection.
Example: db.students.countDocuments({age: 27})   Counts documents where age is 27

###### 4. Distinct Values in a Collection
```bash
db.<collectionName>.distinct(<field>, {<filter>})

```
  Returns an array of distinct values for a given field.
Example: db.students.distinct("district")   Returns all distinct values for the "district" field



>  ### CRUD Operation 

### 1. Create

- insertOne(data, options)
- insertMany([data1, data2, ...], options)

#### 2. Read
- find(query, projection)
- findOne(query, projection)

#### 3. Update
- updateOne(filter, update, options)
- updateMany(filter, update, options)

#### 4. Delete

- deleteOne(filter, options)
- deleteMany(filter, options)

#### 5. Replace

- replaceOne(filter, replacement, options)



>  ###  CRUD Operation Commands


### 1. Insert Operations

 #### Insert a Single Document

```bash
db.student.insertOne({name: 'tamil', age: 27})
```

#### Insert One Document with Embedded Data

```bash
db.student.insertOne({
  name: 'Harish',
  age: 22,
  address: {
    street: 'nerhu nager',
    district: 'Chennai',
    pincode: 600001
  }
})

```

#### Insert Multiple Documents

```bash
db.student.insertMany([
  {
    name: 'Harish',
    age: 22,
    address: {
      street: 'nerhu nager',
      district: 'chennai',
      pincode: 600001
    }
  },
  {
    name: 'Dhanush',
    age: 20,
    address: {
      street: 'subash nager',
      district: 'cuddalore',
      pincode: 607302
    }
  }
])

```
> #### Insert with Different Data Types

```bash
db.student.insertOne({
  name: 'Raja',
  age: 25,
  height: 5.5,
  isActive: true,
  address: {
    street: 'nerhu nager',
    district: 'covai',
    pincode: 600002
  },
  mobileNumbers: ['9012345611', '9078906712'],
  joined: new Date(),
  createdAt: new Timestamp()
})

```


### 2. Read Operations

#### Retrieve all documents
```bash
db.student.find()
```

#### Retrieve data with a filter
```bash
db.student.find({district: 'Chennai'})
```

#### Retrieve a single document

```bash
db.student.findOne({name: 'Harish'})
```

### 3. Update Operations

#### Update a single document
```bash
db.student.updateOne({name: 'Harish'}, {$set: {age: 23}})
```

#### Update multiple documents
```bash
db.student.updateMany({district: 'Chennai'}, {$set: {district: 'Madras'}})
```

### 4. Delete Operations

#### Delete a single document
```bash
db.student.deleteOne({name: 'Harish'})
```

#### Delete multiple documents
```bash
db.student.deleteMany({district: 'Cuddalore'})
```

### 5. Replace Operations

#### Replace a single document
```bash
db.student.replaceOne(
  {name: 'Harish'},
  {name: 'Harish Kumar', age: 24, district: 'Bangalore'}
)
```

### Cursor Object

1. toArray()  ```bash  db.students.find().toArray() ```

2. forEach() , db.students.find().forEach((student) => printjson(student))

3. limit() , db.students.find().limit(3)

4. skip() , db.students.find().skip(2)

5. sort() ,
   db.students.find().sort({ name: 1 })
   db.students.find().count()


7. count() db.students.find({ grade: "A" }).count()












