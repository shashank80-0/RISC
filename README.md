
> POST /api/v1/authenticate_user
- **Request Data Type** - Object
- **Request Data Example** - {"username" : *your username*, "password" : *yourpassword*}
- **Response Data Example** - *Unique Authentication Key* 

#### All Endpoints require Authentication

header = {"Authorization" : Bearer ***your authentication key***}

> GET /api/v1/get_all_products

Get the details of all the products in the database.

- **URL:** `/api/v1/get_all_products`
- **Method:** GET
- **Auth Required:** YES

#### Success Response
- **Code:** 200
- **Response Data Example:**
```json
[
    {
        "product_id": 2, 
        "product_name": "Notebook", 
        "brand_id": 3, 
        "category_id": 3, 
        "price": 40000.0, 
        "discount": 300.0,
        "quantity": 5, 
        "created_at": "2020-10-02 15:01:28", 
        "updated_at": "2020-10-02 21:58:45"
    }, 
    {
        "product_id": 3,
        "product_name": "Logitech",
        "brand_id": 3,
        "category_id": 3,
        "price": 45000.0,
        "discount": 400.0,
        "quantity": 9,
        "created_at": "2020-10-02 15:42:58",
        "updated_at": "2020-10-02 21:58:45"
        }
]
```

> POST /api/v1/get_all_products

Add new product(s)

- **URL:** `/api/v1/add_product`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of objects 
- **Request Data Example:**
```json
[
    {
        "product_name": "Headphones", 
        "brand_name": "Sony", 
        "category_name": "Speakers", 
        "price": 40000.0, 
        "discount": 300.0,
        "quantity": 5
    }, 
    {
        "product_name": "Pen Drive",
        "brand_name": "Kingston",
        "category_name": "Accessory",
        "price": 45000.0,
        "discount": 400.0,
        "quantity": 9
    }
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```
Product(s) Added
```

> PATCH /api/v1/update_product_by_id

Update product(s) by *product_id* (INTEGER)

- **URL:** `/api/v1/update_product_by_id`
- **Method:** PATCH
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of objects 
- **Request Data Example:**
```json
[
    {   
        "product_id": 2, 
        "category_name": "Speakers", 
        "price": 20000.0, 
    }, 
    {   
        "product_id":6,
        "brand_name": "Kingston",
        "price": 45000.0,
        "discount": 400.0,
        "quantity": 9
    }
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```
Product(s) Updated
```

> PATCH /api/v1/update_product_by_name

Update product(s) by *product_id* (STRING)

- **URL:** `/api/v1/update_product_by_id`
- **Method:** PATCH
- **Auth Required:** YES
- **Request Data Example:**
```json
[
    {   
        "product_name":"Bean Bag", 
        "quantity":2, 
        "price": 20000.0, 
    }, 
    {   
        "product_name": "Macbook",
        "brand_name":"Apple",
        "discount": 400.0,
        "quantity": 9
    }
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```
Product(s) Updated
```

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

> POST /api/v1/get_product_by_id

Filter product(s) by *product_id* (INTEGER)

- **URL:** `/api/v1/get_product_by_id`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of integers
- **Request Data Example:**
```json
[
    2,
    5
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```json
[
    {
        "product_id": 2,
        "product_name": "Notebook",
        "brand_id": 3, 
        "category_id": 3, 
        "price": 40000.0, 
        "discount": 300.0,
        "quantity": 5, 
        "created_at": "2020-10-02 15:01:28", 
        "updated_at": "2020-10-02 21:58:45"
    }, 
    {
        "product_id": 5,
        "product_name": "Legion Y540", 
        "brand_id": 2, 
        "category_id": 2, 
        "price": 80000.0, 
        "discount": 1000.0, 
        "quantity": 10,
        "created_at": "2020-10-02 20:24:43", 
        "updated_at": "2020-10-02 20:24:43"
    }
]
```

### Error Respone
- **Code:** 204
- **Response Data Example:**
```
No Records
```
- **Note:** POST received empty list

> POST /api/v1/get_product_by_name

Filter product(s) by *product_name* (STRING)

- **URL:** `/api/v1/get_product_by_name`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of strings
- **Request Data Example:**
```json
[
    "Legion Y540",
    "Notebook"
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```json
[
    {
        "product_id": 5, 
        "product_name": "Legion Y540", 
        "brand_id": 2, 
        "category_id": 2, 
        "price": 80000.0, 
        "discount": 1000.0,
        "quantity": 10, 
        "created_at": "2020-10-02 20:24:43", 
        "updated_at": "2020-10-02 20:24:43"
    }, 
    {
        "product_id": 2,
        "product_name": "Notebook", 
        "brand_id": 3, 
        "category_id": 3, 
        "price": 40000.0, 
        "discount": 300.0, 
        "quantity": 5,
        "created_at": "2020-10-02 15:01:28", 
        "updated_at": "2020-10-02 21:58:45"
    }
]
```

### Error Respone
- **Code:** 204
- **Response Data Example:**
```
No Records
```
- **Note:** POST received empty list


> POST /api/v1/get_product_by_brand

Filter product(s) by *brand_name* (STRING)

- **URL:** `/api/v1/get_product_by_brand`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of strings
- **Request Data Example:**
```json
[
    "Kingston",
    "Lenovo"
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```json
{
    "Apple": [
        {
            "product_id": 8, 
            "product_name": "iPhone", 
            "brand_id": 5, 
            "category_id": 4, 
            "price": 266666.0, 
            "discount":10.0, 
            "quantity": 5, 
            "created_at": "2020-10-03 14:26:38", 
            "updated_at": "2020-10-03 14:26:38"
        }, 
        {
            "product_id": 9,
            "product_name": "Printer", 
            "brand_id": 5, 
            "category_id": 4, 
            "price": 111212.0, 
            "discount": 10.0, 
            "quantity": 5,
            "created_at": "2020-10-03 14:26:38", 
            "updated_at": "2020-10-03 14:26:38"
        }
    ], 
    "Kingston": [], 
    "Lenovo": [
        {
            "product_id": 5,
            "product_name": "Legion Y540", 
            "brand_id": 2, 
            "category_id": 2, 
            "price": 80000.0, 
            "discount": 1000.0, 
            "quantity": 10,
            "created_at": "2020-10-02 20:24:43", 
            "updated_at": "2020-10-02 20:24:43"
        }
    ]
}
```

### Error Respone
- **Code:** 204
- **Response Data Example:**
```
No Records
```
- **Note:** POST received empty list

> POST /api/v1/get_product_by_category

Filter product(s) by *category_name* (STRING)

- **URL:** `/api/v1/get_product_by_category`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of strings
- **Request Data Example:**
```json
[   
    "Speaker",
    "Accessories",
    "Laptop"
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```json
{
    "Speaker": [], 
    "Accessories": [
        {
            "product_id": 10, 
            "product_name": "Headphones", 
            "brand_id": 6, 
            "category_id": 5,
            "price": 2000.0, 
            "discount": 0.0, 
            "quantity": 20, 
            "created_at": "2020-10-03 15:56:17", 
            "updated_at": "2020-10-03 15:56:17"
        }
    ], 
    "Laptop": [
        {
            "product_id": 5, 
            "product_name": "Legion Y540", 
            "brand_id": 2, 
            "category_id": 2, 
            "price":80000.0, 
            "discount": 1000.0, 
            "quantity": 10, 
            "created_at": "2020-10-02 20:24:43", 
            "updated_at": "2020-10-02 20:24:43"
        }
    ]
}
```

### Error Respone
- **Code:** 204
- **Response Data Example:**
```
No Records
```
- **Note:** POST received empty list


> POST /api/v1/get_product_by_price_range

Filter product(s) by *price* (INTEGER/FLOAT) range (price_1,price_2)

- **URL:** `/api/v1/get_product_by_price_range`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of exact two integers/float (min_price and max_price (*any order*))
- **Request Data Example:**
```json
[   
    65000,
    20000
]
```

#### Success Response
- **Code:** 200
- **Response Data Example:** 
```json
[
    {
        "product_id": 2, 
        "product_name": "Notebook", 
        "brand_id": 3, 
        "category_id": 3, 
        "price": 40000.0, 
        "discount": 300.0,
        "quantity": 5, 
        "created_at": "2020-10-02 15:01:28", 
        "updated_at": "2020-10-02 21:58:45"
    }, 
    {
        "product_id": 3,
        "product_name": "Logitech", 
        "brand_id": 3, 
        "category_id": 3, 
        "price": 45000.0, 
        "discount": 400.0, 
        "quantity": 9,
        "created_at": "2020-10-02 15:42:58", 
        "updated_at": "2020-10-02 21:58:45"
    }
]
```

### Error Respone
- **Code:** 400
- **Response Data Example:**
```
Mismatch datatype
```
- **Note:** POST received non-integers value

- **Code:** 422
- **Response Data Example:**
```
Invalid Request
```
- **Note:** POST does not received array(or list) of length 2 


> POST /api/v1/get_product_by_minimum_discount

Filter product(s) by minimum *discount* (INTEGER/FLOAT) percentage

- **URL:** `/api/v1/get_product_by_minimum_discount`
- **Method:** POST
- **Auth Required:** YES
- **Request Data Type:** Array (or List) of integers
- **Request Data Example:**
```json
{
    "0.9": [
        {
            "product_id": 5, 
            "product_name": "Legion Y540", 
            "brand_id": 2, 
            "category_id": 2, 
            "price": 80000.0, 
            "discount": 1000.0, 
            "quantity": 10, 
            "created_at": "2020-10-02 20:24:43", 
            "updated_at": "2020-10-02 20:24:43"
        }
    ], 
    "3.0": [], 
    "1.0":[
        {
            "product_id": 5, 
            "product_name": "Legion Y540", 
            "brand_id": 2, 
            "category_id": 2, 
            "price": 80000.0, 
            "discount": 1000.0,
            "quantity": 10, 
            "created_at": "2020-10-02 20:24:43", 
            "updated_at": "2020-10-02 20:24:43"
        }
    ]
}
```

### Error Respone
- **Code:** 400
- **Response Data Example:**
```
Mismatch datatype
```
- **Note:** POST received non-integers value
