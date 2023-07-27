# Blog API 
Welcome to the BlogApp REST API! This API provides a simple blogging platform with a set of endpoints for managing posts, users, and categories. The API uses JSON Web Tokens (JWT) for authentication and supports basic CRUD operations.

# Authentication Endpoints:

### Sign Up

* Method: POST /auth/signup
* Request Body: {
"username": "string",
"email": "string",
"password": "string"
}
* Response: {
"token": "string"
}

The sign up endpoint allows users to create an account with their username, email, and password. The response includes a JWT token that can be used for authentication.

### Login

* Method: POST /auth/login
* Request Body: {
"username": "string",
"password": "string"
}
* Response: {
"token": "string"
}

The login endpoint authenticates a user with their username and password. The response includes a JWT token that can be used for authentication.

### Logout

* Method: POST /auth/logout
* Request Body: {
"token": "string"
}
* Response: {
"message": "Logged out successfully"
}

The logout endpoint invalidates the JWT token and logs the user out of their account.

### Stateful Jwt Authentication

* Method: GET /auth/me
* Request Header: Authorization: Bearer {token}
* Response: {
"user": {
"id": "integer",
"username": "string",
"email": "string"
},
"token": "string"
}

The stateful JWT authentication endpoint returns the user's details and a new JWT token upon successful authentication. The token can be used for subsequent requests.

Basic CRUD Endpoints:

### Create Posts

* Method: POST /posts
* Request Body: {
"title": "string",
"content": "string",
"user_id": "integer"
}
* Response: {
"id": "integer",
"title": "string",
"content": "string",
"user_id": "integer",
"created_at": "string"
}

The create posts endpoint allows users to create a new post with a title, content, and user ID. The response includes the newly created post's details.

### Get All Posts

* Method: GET /posts
* Response: [
{
"id": "integer",
"title": "string",
"content": "string",
"user_id": "integer",
"created_at": "string"
},
{
"id": "integer",
"title": "string",
"content": "string",
"user_id": "integer",
"created_at": "string"
},
...
]

The get all posts endpoint returns a list of all posts.

### Get Post

* Method: GET /posts/{id}
* Response: {
"id": "integer",
"title": "string",
"content": "string",
"user_id": "integer",
"created_at": "string"
}

The get post endpoint returns a single post by its ID.

### Update Posts

* Method: PUT /posts/{id}
* Request Body: {
"title": "string",
"content": "string",
"user_id": "integer"
}
* Response: {
"id": "integer",
"title": "string",
"content": "string",
"user_id": "integer",
"created_at": "string"
}

The update posts endpoint allows users to update a post's title, content, and user ID. The response includes the updated post's details.

### Delete Posts

* Method: DELETE /posts/{id}
* Response: {
"message": "Post deleted successfully"
}

The delete posts endpoint allows users to delete a post by its ID.

### Create Users

* Method: POST /users
* Request Body: {
"username": "string",
"email": "string",
"password": "string"
}
* Response: {
"id": "integer",
"username": "string",
"email": "string",
"created_at": "string"
}

The create users endpoint allows users to create a new user with a username
