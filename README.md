# Registry Service

The **Registry Service** acts as the **Service Discovery** server for the Vendo platform.

It is built on top of **Spring Cloud Netflix Eureka Server** and allows all other microservices in the system to register themselves and discover one another dynamically, eliminating the need for hardcoded IP addresses or ports.

---

# Tech Stack

* Java 17
* Spring Boot
* Lombok
* Maven
* Netflix Eureka Server
---

# Architecture

Unlike domain-centric microservices, the Registry Service is a pure **Infrastructure Component**. It does not contain business logic, Hexagonal Architecture, or CQRS.

---

# Project Structure

```
src
 └── main
     └── java
         └── com.vendo.api_gateway
             └── config
```

---

# Prerequisites

Before running this service, you need to start the centralized configuration server, as the Registry Service fetches its settings from it.

## Dependencies

This service depends on:

- **Config Server** – provides externalized configuration

---

## 1. Clone and run Config Server

```
git clone https://github.com/vendo-marketplace/config-server
cd config-server
mvn spring-boot:run
```

---

# Running the Service

---

## 3. Run application

Or build and run:

```
mvn clean package
java -jar target/registry-service.jar
```

---

# Environment Variables

| Variable          | Description       | Default   |
|-------------------|-------------------|-----------|
| CONFIG_SERVER_URL | Config server url | 8010      |

---

# Code Style

The project follows standard **Java code conventions**.

Key principles:

* Clean Architecture
* SOLID principles
* Immutable DTOs
* Constructor injection
* Clear separation between layers

---

# Contributing

1. Create feature branch
2. Write tests
3. Ensure tests pass
4. Create pull request