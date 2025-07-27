
# Fitguy: Fitness Run Tracker

`fitguy` is a web application built with Java and Spring Boot 3 for tracking fitness runs. This project serves as a practical application of the concepts learned in the "Building web applications in Java with Spring Boot 3" course. It features a complete REST API for Create, Read, Update, and Delete (CRUD) operations, connects to a database for persistence, and is backed by a thorough test suite.

## Project Overview

This application allows users to manage their running activities through a RESTful API. The primary goal is to demonstrate the fundamentals of building robust, enterprise-grade web applications using the Spring ecosystem.

### Core Features
*   **REST API:** A complete set of endpoints to manage run data.
*   **Data Persistence:** Support for both in-memory (H2) and relational (PostgreSQL) databases.
*   **Data Validation:** Ensures the integrity of the data submitted to the API.
*   **Configuration Management:** Externalized configuration for different environments.
*   **Comprehensive Testing:** Includes unit, integration, and slice tests to ensure application reliability.

## Technologies Used

*   **Framework:** Spring Boot 3.5.4
*   **Language:** Java 21
*   **Build Tool:** Apache Maven
*   **Core Dependencies:**
    *   Spring Web: For building RESTful web applications.
    *   Spring Data: To simplify database access.
    *   Spring Boot DevTools: For rapid application development.
    *   Spring Boot Starter Test: For writing unit and integration tests with JUnit 5.
*   **Database:**
    *   H2 (for development & testing)
    *   PostgreSQL (with Docker Compose for production-like environments)

## Prerequisites

Before you begin, ensure you have the following installed on your system:

*   **JDK 17+:** Java Development Kit (the project is configured for Java 21). You can check your version with `java --version`.
*   **Apache Maven:** For dependency management and building the project.
*   **IDE / Text Editor:** A suitable editor like IntelliJ IDEA, Visual Studio Code, or Eclipse.
*   **API Testing Tool:** A tool to interact with the REST API, such as Postman, IntelliJ HTTP Client, or cURL.
*   **Docker Desktop:** Required for running a PostgreSQL database instance.

## Getting Started

Follow these instructions to get the project up and running on your local machine.

**1. Clone the repository:**
```sh
git clone <your-repository-url>
cd fitguy
```

**2. Build the project:**
This command will compile the code and download all the necessary dependencies defined in `pom.xml`.
```sh
mvn clean install
```

**3. Run the application:**
You can run the application using the Spring Boot Maven plugin.
```sh
mvn spring-boot:run
```The application will start on the default port `8080`. You can access it at `http://localhost:8080`.

## Project Structure

The project follows a standard Maven layout and is organized into modules based on functionality:

*   **`src/main/java/dev/famguy/fitguy`**: Contains the main application source code.
    *   **`FitguyApplication.java`**: The main entry point for the Spring Boot application.
    *   **`model`**: Contains the data models (e.g., `Run`, `Location`).
    *   **`controller`**: Handles incoming HTTP requests (REST API endpoints).
    *   **`repository`**: Manages data persistence and access.
    *   **`service`**: Contains the business logic.
*   **`src/test/java/dev/famguy/fitguy`**: Contains all the tests for the application.
*   **`pom.xml`**: Defines all project dependencies and build configurations.

## API Endpoints

Once the application is running, you can interact with the following REST API endpoints for managing runs.

| Method | Endpoint          | Description                |
| :----- | :---------------- | :------------------------- |
| `GET`    | `/api/runs`       | Get a list of all runs.    |
| `GET`    | `/api/runs/{id}`  | Get a single run by its ID.|
| `POST`   | `/api/runs`       | Create a new run.          |
| `PUT`    | `/api/runs/{id}`  | Update an existing run.    |
| `DELETE` | `/api/runs/{id}`  | Delete a run by its ID.    |

## Running Tests

To run the complete suite of tests for the application, use the following Maven command:
```sh
mvn test
```
This will execute all tests, including unit tests, slice tests, and integration tests, such as the `FitguyApplicationTests.java` context loader test.

## Reference Documentation

For further reference, please consider the following official documentation:

*   [Official Apache Maven documentation](https://maven.apache.org/guides/index.html)
*   [Spring Boot Maven Plugin Reference Guide](https://docs.spring.io/spring-boot/3.5.4/maven-plugin)
*   [Spring Web](https://docs.spring.io/spring-boot/3.5.4/reference/web/servlet.html)
*   [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)