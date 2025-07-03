# Journal App

A simple **End-to-End Encrypted (E2EE) Journal App** built with Spring Boot. This application provides a RESTful API for managing journal entries.

## Features

- Create, retrieve, update, and delete journal entries (CRUD)
- Simple in-memory storage (using a `HashMap`)
- Health check endpoint
- Clean, minimal REST API

## Requirements

- Java 17+
- Maven 3.6+
- Spring Boot (3.3.13)

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/garvsharmxa/Journal_SpringBoot.git
cd journalApp
```

### 2. Build the project

```bash
mvn clean install
```

### 3. Run the application

```bash
mvn spring-boot:run
```

The app will start on [http://localhost:8080](http://localhost:8080).

---

## REST API Endpoints

### Health Check

- **GET** `/health-check`  
  Returns `"OK"` if the app is running.

### Journal Entry Endpoints

| Method | Endpoint                  | Description                     |
|--------|--------------------------|---------------------------------|
| GET    | `/journal/`              | Get all journal entries         |
| POST   | `/journal/`              | Create a new journal entry      |
| GET    | `/journal/id/{id}`       | Get entry by ID                 |
| PUT    | `/journal/id/{id}`       | Update entry by ID              |
| DELETE | `/journal/id/{id}`       | Delete entry by ID              |

#### Example: Create a Journal Entry

```bash
curl -X POST http://localhost:8080/journal/ \
-H 'Content-Type: application/json' \
-d '{"id": 1, "title": "My First Entry", "content": "Hello Journal!"}'
```

#### Example: Get All Entries

```bash
curl http://localhost:8080/journal/
```

---

## Project Structure

```
src/
 └── main/
      └── java/
          └── com.xgrave.journalApp/
               ├── Controller/
               │     ├── JournalEntryController.java
               │     └── HealthCheck.java
               └── entity/
                     └── JournalEntry.java
 └── resources/
      └── application.properties
pom.xml
```

---

## Notes

- **Data is in-memory only:** All journal entries will be lost when the application stops.
- **No authentication or security:** This is a demo/starter project for learning Spring Boot REST APIs.

---

## License

This project is licensed under the MIT License.

---

## Contributing

Pull requests and stars are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## Author

- [Garv Sharma](https://github.com/garvsharmxa)
