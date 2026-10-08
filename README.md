# MongoDB Student Database Project

A simple MongoDB Student Database Project demonstrating CRUD operations and query operations using MongoDB Shell (`mongosh`).

## Project Overview

This project uses:

- **Database:** `studentProjectDB`
- **Collection:** `studentRecords`
- **Initial Records:** 51
- **Final Records:** 44
- **Technology:** MongoDB / NoSQL

## Operations Covered

- Create / Select Database
- Insert One
- Insert Many
- Update One
- Update Many
- Delete One
- Delete Many
- Query Operations
- Document Counting
- Student Search
- Database Verification

## Database Setup

```javascript
use studentProjectDB
```

Check the current database:

```javascript
db
```

Show collections:

```javascript
show collections
```

## Insert Operations

### Insert One

```javascript
db.studentRecords.insertOne({
  rollNo: 201,
  name: "Ananya",
  age: 19,
  department: "CSE",
  marks: 91
});
```

### Insert Many

```javascript
db.studentRecords.insertMany([
  { rollNo: 202, name: "Raghav", age: 20, department: "IT", marks: 76 },
  { rollNo: 203, name: "Meera", age: 18, department: "ECE", marks: 84 }
]);
```

## Update Operations

### Update One

```javascript
db.studentRecords.updateOne(
  { rollNo: 201 },
  { $set: { marks: 95 } }
);
```

### Update Many

```javascript
db.studentRecords.updateMany(
  { department: "CSE" },
  { $set: { status: "Active" } }
);
```

## Delete Operations

### Delete One

```javascript
db.studentRecords.deleteOne({
  rollNo: 251
});
```

### Delete Many

```javascript
db.studentRecords.deleteMany({
  marks: { $lt: 40 }
});
```

## Query Operations

### Marks Greater Than 80

```javascript
db.studentRecords.find({
  marks: { $gt: 80 }
});
```

### Marks Less Than 80

```javascript
db.studentRecords.find({
  marks: { $lt: 80 }
});
```

### Marks Equal to 85

```javascript
db.studentRecords.find({
  marks: { $eq: 85 }
});
```

### Marks Greater Than or Equal to 80

```javascript
db.studentRecords.find({
  marks: { $gte: 80 }
});
```

### Marks Not Equal to 85

```javascript
db.studentRecords.find({
  marks: { $ne: 85 }
});
```

### AND Operation

```javascript
db.studentRecords.find({
  $and: [
    { marks: { $gt: 70 } },
    { age: { $lt: 23 } }
  ]
});
```

### OR Operation

```javascript
db.studentRecords.find({
  $or: [
    { department: "CSE" },
    { department: "ECE" }
  ]
});
```

### NOT Operation

```javascript
db.studentRecords.find({
  marks: { $not: { $gt: 80 } }
});
```

## Verification Commands

Show all records:

```javascript
db.studentRecords.find();
```

Show records in readable format:

```javascript
db.studentRecords.find().pretty();
```

Count total documents:

```javascript
db.studentRecords.countDocuments();
```

Find student by Roll No.:

```javascript
db.studentRecords.findOne({
  rollNo: 201
});
```

Find all CSE students:

```javascript
db.studentRecords.find({
  department: "CSE"
});
```

## Final Dataset

After the delete operations, the final dataset contains **44 documents**.

| Department | Students |
|---|---:|
| CSE | 11 |
| ECE | 11 |
| IT | 11 |
| ME | 11 |
| **Total** | **44** |

## Learning Outcomes

This project demonstrates practical knowledge of:

- MongoDB databases and collections
- CRUD operations
- MongoDB query operators
- Filtering and searching documents
- Updating single and multiple documents
- Deleting documents
- Counting and verifying records

## Student Information

**Name:** Vikas Sharma  
**Program:** BCA DS & AI  
**University:** Babu Banarasi Das University, Lucknow  
**Session:** 2026–2027  
**Roll No.:** 1250258503  
**Course:** NoSQL and DBaaS 101

---

**Made by Vikas Sharma | BCA DS & AI | 2026–2027**
