Basic CRUD API with Golang

This is a basic CRUD (Create, Read, Update, Delete) API implemented using Golang. The API provides endpoints to create, read, update, and delete data from a database.
Technologies Used

    Golang
    Gorilla Mux - A powerful HTTP router and URL matcher for building Go web servers
    MySQL - A popular relational database management system

Installation and Setup

    Clone the repository:

sh
git clone https://github.com/username/repo.git

    Install the required dependencies:

sh
go get -u github.com/gorilla/mux
go get -u github.com/go-sql-driver/mysql

    Set up the MySQL database. Create a new database and table using the following SQL commands:

sql
CREATE DATABASE dbname;

USE dbname;

CREATE TABLE IF NOT EXISTS users (
    id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(30) NOT NULL,
    email VARCHAR(50) NOT NULL,
    password VARCHAR(255) NOT NULL
);

    Configure the database connection in config.go:

go
const (
    host     = "localhost"
    port     = "3306"
    user     = "yourusername"
    password = "yourpassword"
    dbname   = "dbname"
)

    Run the API:

sh
go run main.go

Usage

The API provides the following endpoints:

    GET /users - Get all users
    GET /users/{id} - Get a specific user
    POST /users - Create a new user
    PUT /users/{id} - Update a specific user
    DELETE /users/{id} - Delete a specific user

The request and response bodies for each endpoint are as follows:
GET /users

No request body is required.

Response body:

json
[
    {
        "id": 1,
        "name": "John Doe",
        "email": "johndoe@example.com",
        "password": "password123"
    },
    {
        "id": 2,
        "name": "Jane Doe",
        "email": "janedoe@example.com",
        "password": "password456"
    }
]

GET /users/{id}

No request body is required.

Response body:

json
{
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123"
}

POST /users

Request body:

json
{
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123"
}

Response body:

json
{
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123"
}

PUT /users/{id}

Request body:

json
{
    "name": "John Doe Jr.",
    "email": "johnjr@example.com",
    "password": "newpassword"
}

Response body:

json
{
    "id": 1,
    "name": "John Doe Jr.",
    "email": "johnjr@example.com",
    "password": "newpassword"
}

DELETE /users/{id}

No request body is required.

Response body:

json
{
    "message": "User deleted successfully"
}

License

This project is licensed under the MIT License - see the [LICENSE](
