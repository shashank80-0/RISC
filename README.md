
> POST /api/v1/authenticate_user
- Request Data Type - Object
- Request Data - {"username" : *your username*, "password" : *yourpassword*}
- Response Data - Unique Authentication Key 

#### All Endpoints require Authentication

header = {"Authorization" : Bearer *your authentication key*}

> GET /api/v1/get_all_products

Get the details of all the products in the database.

- **URL**: /api/v1/get_all_products
- **Method**: GET
- **Auth Required**: YES

#### Success Response
- **Code**: 200
- **Content examples**
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






