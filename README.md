"# Category-Product-Management


Category & Product Management API Documentation
Base URL
All endpoints are prefixed with /api.

http://localhost:8080/api
1. Category CRUD Operations
1.1. Get All Categories
Retrieve a paginated list of all categories.

URL: /categories

Method: GET

Query Parameters:

page (optional): The page number (default is 0).
size (optional): The number of items per page (default is 10).
Example Request:

GET http://localhost:8080/api/categories?page=1&size=5
Response:

json

{
    "content": [
        {
            "id": 1,
            "name": "Electronics"
        },
        {
            "id": 2,
            "name": "Books"
        }
    ],
    "pageable": {
        "pageNumber": 1,
        "pageSize": 5
    },
    "totalElements": 10,
    "totalPages": 2
}
1.2. Create a New Category
Create a new category.

URL: /categories

Method: POST

Request Body:

json

{
    "name": "New Category"
}
Example Request:

POST http://localhost:8080/api/categories
Response:

json

{
    "id": 3,
    "name": "New Category"
}
1.3. Get Category by ID
Retrieve details of a specific category by its ID.

URL: /categories/{id}

Method: GET

Path Variable:

id: The ID of the category.
Example Request:

GET http://localhost:8080/api/categories/1
Response:

json
Copy code
{
    "id": 1,
    "name": "Electronics"
}
1.4. Update Category by ID
Update an existing category by its ID.

URL: /categories/{id}

Method: PUT

Path Variable:

id: The ID of the category.
Request Body:

json

{
    "name": "Updated Category"
}
Example Request:

PUT http://localhost:8080/api/categories/1
Response:

json

{
    "id": 1,
    "name": "Updated Category"
}
1.5. Delete Category by ID
Delete a specific category by its ID.

URL: /categories/{id}

Method: DELETE

Path Variable:

id: The ID of the category.
Example Request:


DELETE http://localhost:8080/api/categories/1
Response:

json

{
    "message": "Category with ID 1 was deleted successfully."
}
