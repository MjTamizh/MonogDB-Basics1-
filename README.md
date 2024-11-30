# MongoDB-Basics1
MongoDB Basic Course - 1

## Commands

### To Create a Database

use school

Create a Collection

 ### Insert a Single Document

db.student.insertOne({name: 'tamil', age: 27})

### Retrieve All Data from a Collection

db.student.find()


### Insert Operations

db.student.insertOne({name: 'tamil', age: 27, district: 'cuddalore'})


### Insert One Document with Embedded Data

db.student.insertOne({
  name: 'Harish',
  age: 22,
  address: {
    street: 'nerhu nager',
    district: 'Chennai',
    pincode: 600001
  }
})

### Insert Multiple Documents

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

### Insert with Different Data Types


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


> CRUD Operation commands
1. create



# CRUD Operation Commands

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





