# Employee Management System (EMS)

## Overview

The Employee Management System (EMS) is a web application built using Java Spring Boot. It allows users to perform CRUD (Create, Read, Update, Delete) operations on employee data. This application demonstrates the use of Spring Boot, Spring Data JPA, and RESTful web services.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
- [Usage](#usage)
    - [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Features

- Add a new employee
- Retrieve an employee by ID
- Retrieve all employees
- Update an employee's information
- Delete an employee

## Technologies Used

- Java 11
- Spring Boot 2.5
- Spring Data JPA
- Hibernate
- MySQL
- Lombok
- Maven

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven 3.6 or higher
- MySQL 8.0 or higher

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/ems.git
    cd ems
    ```

2. Create a MySQL database:
    ```sql
    CREATE DATABASE emsSys;
    ```

3. Update the database configuration in `src/main/resources/application.properties`:
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/emsSys
    spring.datasource.username=root
    spring.datasource.password=yourpassword
    spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
    spring.jpa.hibernate.ddl-auto=update
    ```

4. Build the project using Maven:
    ```bash
    mvn clean install
    ```

5. Run the application:
    ```bash
    mvn spring-boot:run
    ```

## Usage

### API Endpoints

- **Create Employee**
    - **URL:** `/api/employees`
    - **Method:** `POST`
    - **Request Body:**
        ```json
        {
          "firstName": "John",
          "lastName": "Doe",
          "email": "john.doe@example.com"
        }
        ```
    - **Response:**
        ```json
        {
          "id": 1,
          "firstName": "John",
          "lastName": "Doe",
          "email": "john.doe@example.com"
        }
        ```

- **Get Employee by ID**
    - **URL:** `/api/employees/{id}`
    - **Method:** `GET`
    - **Response:**
        ```json
        {
          "id": 1,
          "firstName": "John",
          "lastName": "Doe",
          "email": "john.doe@example.com"
        }
        ```

- **Get All Employees**
    - **URL:** `/api/employees`
    - **Method:** `GET`
    - **Response:**
        ```json
        [
          {
            "id": 1,
            "firstName": "John",
            "lastName": "Doe",
            "email": "john.doe@example.com"
          }
        ]
        ```

- **Update Employee**
    - **URL:** `/api/employees/{id}`
    - **Method:** `PUT`
    - **Request Body:**
        ```json
        {
          "firstName": "John",
          "lastName": "Doe",
          "email": "john.doe@newemail.com"
        }
        ```
    - **Response:**
        ```json
        {
          "id": 1,
          "firstName": "John",
          "lastName": "Doe",
          "email": "john.doe@newemail.com"
        }
        ```

- **Delete Employee**
    - **URL:** `/api/employees/{id}`
    - **Method:** `DELETE`
    - **Response:** `204 No Content`

## Project Structure

```plaintext
src/main/java/net/javaguides/ems
├── controller
│   └── EmployeeController.java
├── dto
│   └── EmployeeDto.java
├── entity
│   └── Employee.java
├── exception
│   └── ResourceNotFoundException.java
├── mapper
│   └── EmployeeMapper.java
├── repository
│   └── EmployeeRepository.java
├── service
│   ├── EmployeeService.java
│   └── impl
│       └── EmployeeServiceImpl.java
