# Book Management REST API
A simple RESTful API built with Spring Boot for managing a collection of books. Includes a console-based client application for interacting with the API.

**Table of Contents**
Features
Technologies Used
Prerequisites
Project Structure
Installation & Setup
Running the Application
API Endpoints
Testing the API
Using the Console Client
H2 Database Console
Troubleshooting

# Features
Complete CRUD Operations for books
Search functionality by title and category
In-memory H2 database for easy testing
Validation for required fields like category, author, title and data constraints
Console-based client for API interaction
RESTful endpoints following best practices

# Technologies Used
-Java 17
-Spring Boot 3.1.5

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
Git (optional, for cloning
# Create the project

