# Smart Clinic Management System

A full-stack hospital management capstone application built with Java and Spring Boot. The system supports role-based workflows for administrators, doctors, and patients, including appointment booking and prescription management.

## Features

- **Admin:** Log in, manage doctor profiles, and view appointment usage statistics.
- **Doctor:** Manage appointments, availability, profiles, and patient details.
- **Patient:** Browse doctors, register, log in, book appointments, and view upcoming bookings.
- **Prescriptions:** Store and manage prescription records.
- **Dashboards:** Thymeleaf-based Admin and Doctor dashboards with REST-backed modules.

## Tech Stack

- Java 17
- Spring Boot 3.4.4
- Spring MVC and REST controllers
- Spring Data JPA
- Spring Data MongoDB
- Thymeleaf
- MySQL
- MongoDB
- Maven
- HTML, CSS, and JavaScript
- JSON Web Tokens (JWT)

## Project Structure

```text
app/
├── pom.xml
├── mvnw
└── src/
    ├── main/
    │   ├── java/com/project/back_end/
    │   │   ├── controllers/
    │   │   ├── models/
    │   │   ├── repo/
    │   │   ├── services/
    │   │   ├── mvc/
    │   │   └── config/
    │   └── resources/
    │       ├── application.properties
    │       ├── static/
    │       └── templates/
    └── test/
```

Additional planning documents:

- [`schema-architecture.md`](schema-architecture.md)
- [`user_stories.md`](user_stories.md)

## Prerequisites

- JDK 17 or later
- Maven (or use the included Maven wrapper)
- MySQL
- MongoDB

## Configuration

Before running the application, update `app/src/main/resources/application.properties`.

Configure MySQL:

```properties
spring.datasource.url=jdbc:mysql://<mysql_host>/cms?usessl=false
spring.datasource.username=<mysql_username>
spring.datasource.password=<mysql_password>
```

Configure MongoDB:

```properties
spring.data.mongodb.uri=mongodb://<mongodb_username>:<mongodb_password>@<mongodb_host>:27017/prescriptions?authSource=admin
```

For local development, a typical MySQL URL is:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/cms?useSSL=false&allowPublicKeyRetrieval=true
```

Create the `cms` MySQL database if it does not already exist:

```sql
CREATE DATABASE cms;
```

## Run the Application

Linux or macOS:

```bash
cd app
./mvnw spring-boot:run
```

Windows:

```bat
cd app
mvnw.cmd spring-boot:run
```

Once started, open:

```text
http://localhost:8080
```

## Run Tests

Linux or macOS:

```bash
cd app
./mvnw test
```

Windows:

```bat
cd app
mvnw.cmd test
```

## Architecture

The application follows a layered architecture:

1. MVC or REST controllers receive requests.
2. Controllers delegate work to the service layer.
3. Services enforce application business logic.
4. Repositories interact with MySQL and MongoDB.
5. Thymeleaf renders the Admin and Doctor dashboards.
6. Static HTML and JavaScript provide the patient-facing interface and API interactions.

## License

This project is licensed under the Apache License 2.0. See [`LICENSE`](LICENSE) for details.
