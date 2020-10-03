> DELETE /api/v1/update_product_by_id

Delete product(s) by *product_id* (INTEGER)

- **URL:** `/api/v1/delete_product_by_id`
- **Method:** DELETE
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of integers
- **Request Data Example:**
```json
[
    3,
    5,
    6
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```
Product(s) Deleted
```

> DELETE /api/v1/delete_product_by_name

DELETE product(s) by *product_name* (STRING)

- **URL:** `/api/v1/update_product_by_id`
- **Method:** PATCH
- **Auth Required:** YES
- **Request Data Example:**
```json
[
    "Macbook",
    "Bean Bag",
    "Headphone"
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```
Product(s) Deleted
```