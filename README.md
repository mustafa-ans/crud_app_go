# Basic CRUD API with Golang

This is a basic CRUD (Create, Read, Update, Delete) API implemented using Golang. The API provides endpoints to create, read, update, and delete data from a database.
Technologies Used

    Golang
    Gorilla Mux - A powerful HTTP router and URL matcher for building Go web servers

#### Installation and Setup

    Clone the repository:

`git clone https://github.com/username/repo.git`

### Install the required dependencies:

`go get -u github.com/gorilla/mux`


## Run the API:

`go run main.go`


## Usage

The API provides the following endpoints:

    GET /users - Get all users
    GET /users/{id} - Get a specific user
    POST /users - Create a new user
    PUT /users/{id} - Update a specific user
    DELETE /users/{id} - Delete a specific user


### The request and response bodies for each endpoint are as follows:
GET /users

No request body is required.

Response body:

json
`[
    {
        "id": "1",
        "isbn": "45321",
        "title": "The Prestige",
        "director": {
            "Firstname": "Christropher",
            "Lastname": "Nolan"
        }
    },
    {
        "id": "2",
        "isbn": "87628",
        "title": "Slumdog millionair",
        "director": {
            "Firstname": "Danny",
            "Lastname": "Boyle"
        }
    }
]`

GET /users/1

No request body is required.

Response body:

json
`{
        "id": "1",
        "isbn": "45321",
        "title": "The Prestige",
        "director": {
            "Firstname": "Christropher",
            "Lastname": "Nolan"
        }
}`

POST /users

Request body:

json
`{
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123"
}`

Response body:

json
`{
    "id": 1,
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123"
}`

PUT /users/{id}

Request body:

json
`{
    "name": "John Doe Jr.",
    "email": "johnjr@example.com",
    "password": "newpassword"
}`

Response body:

json
`{
    "id": 1,
    "name": "John Doe Jr.",
    "email": "johnjr@example.com",
    "password": "newpassword"
}`

DELETE /users/{id}

No request body is required.

Response body:

It will return all the remaining objects except the one that was deleted

### License

This project is licensed under the MIT License 
