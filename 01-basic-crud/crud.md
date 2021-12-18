# Basic Operations (CRUD)

- Create a database:

```js
use hospital
```

- To delete a database:

```js
use hospital

db.dropDatabase()
```

- To delete a collection:

```js
db.patients.drop()
```

- Insert a new single record:

```js
db.patients.insertOne(
  {
    "firstName": "John",
    "lastName": "Doe",
    "age": 25,
    "history": [
      { "disease": "cold", "treatment": "any treatment" },
      { "disease": "insomnia", "treatment": "any treatment" }
    ]
  }
)
```

- Insert many records:

```js
db.patients.insertMany([
  {
    "firstName": "Michael",
    "lastName": "Scott",
    "age": 45,
    "history": [
      { "disease": "cold", "treatment": "any treatment" },
      { "disease": "pneumonia", "treatment": "any treatment" },
    ]
  },
  {
    "firstName": "Jim",
    "lastName": "Halpert",
    "age": 33,
    "history": [
      { "disease": "pneumonia", "treatment": "any treatment" },
      { "disease": "insomnia", "treatment": "any treatment" }
    ]
  },
])
```

- Update a single record:

```js
db.patients.updateOne(
  { "firstName": "John" },
  {
    $set: { "age": 30, "history": [{ "disease": "pneumonia", "treatment": "any treatment" }] }
  }
)
```

- Find many records:

```js
db.patients.find(
  { "age": { $gt: 30 } }
)
```

- Delete many records:

```js
db.patients.deleteMany(
  { "history.disease": "cold" }
)
```
