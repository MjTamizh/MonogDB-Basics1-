# MongoDB-Basics
MongoDB Basic Course - 1

## Commands
### To Create a Database
```bash
use school
```

# CRUD Operation 

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



# CRUD Operation Commands


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
#### Insert with Different Data Types

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









