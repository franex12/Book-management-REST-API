# Book Management REST API
A simple RESTful API built with Spring Boot for managing a collection of books. Includes a console-based client application for interacting with the API.
# Technologies Used
-Java 21
-Spring Boot 4.0.3

-Spring Web MVC 
REST API and web server that makes class booksApiService respond to browser requests in the project. runs app on port 8080 and provides MVC that handles HTTP requests and adds jackson that converts Java objects to JSON automatically and back. Also enables @RestController, @GetMappping, @PostMapping annotations.
-Jackson for JSON processing
-Spring Data JPA 
Database (H2) communcation tool(makes @entity,@Id, @GenearateValue work in my Book class)

-H2 Database (in-memory)
creates Database in RAM with (scope runtime) ensuring its only needed when the app runs not when compiling.

-Spring starter validation
for input validation and error checking, it provides validation annotations like @NotNull, @Size, @Email

-Spring boot starter test
testing framework and includes JUnit for writing tests, also provides MockMvc for testing REST APIs without starting server. scope test ensures it only used when running tests, not in production

-Maven for build management

# Prerequisites
Before you begin, ensure you have installed:
Java JDK 17 or 21
Maven 3.6 or later
Git (optional, for cloning)

# Features
Book Model
The Book entity includes the following attributes: id (Long) - Auto-generated primary key, bookTitle (String) - Book title (required), description (String) - Book description (max 500 chars), publishedYear (String) - Year of publication, author (String) - Author name (required), bookCategory (Enum) - Category from predefined list includes(
Math, English, Biography, History, IT, Literature, Physics, Chemistry, Biology)

API Endpoints 
Get All Books
GET /books
Returns a list of all books in the database.
Response is 200 OK with book list or 204 No Content if empty

Get Book by ID
GET /books/id/{id}
Retrieves a specific book by its ID.
Parameters are id (Long) - Book ID
Response is 200 OK with book details or 404 Not Found if book doesn't exist

Get Books by Category
GET /books/category/{category}
Retrieves all books in a specific category (case-insensitive).
Parameters are category (String) - Book category
Response is 200 OK with list of books or 404 Not Found if no books in category or 400 Bad Request if category is invalid

Get Book by Title
GET /books/title/{title}
Searches for a book by title (case-insensitive, partial match).
Parameters are title (String) - Book title to search
Response is 200 OK with book details or 404 Not Found if no matching book

Add New Book
POST /books
Creates a new book entry.

example of a request body:
json
{
    "bookTitle": "Introduction to Java",
    "author": "John Doe",
    "description": "A comprehensive guide to Java programming",
    "publishedYear": "2023",
    "bookCategory": "IT"
}

Validation Rules are Title cannot be empty, Title must be unique, Author cannot be empty, Category must be valid (from predefined list) and description cant exceed 500 characters.
Response is 201 Created with created book, 400 Bad Request for validation errors or 409 Conflict if title already exists.

Delete Book
DELETE /books/{id}
Deletes a book by its ID.
Parameters are id (Long) - Book ID
Response is 200 OK with success message or 404 Not Found if book doesn't exist.

# using Postman (urls)
first start and run BookAssMangApplication,  then navigate to postman
Get: http/localhost/8080/books - fetches all books,
Get: http/localhost/8080/books/id/1 - fetches book with id 1, 
Get: http/localhost/8080/books/category/IT - fetches book/s with category it, 
Get: http/localhost/8080/books/title/Romeo - fetches book with title Romeo.

Post: http/localhost/8080/books - posts a a new book, 
Delete: http/localhost/8080/books/1 - deletes book with id 1.

# run in console
start and run BookAssMangApplication, then run ClientApp and configure the request according to the menu.


