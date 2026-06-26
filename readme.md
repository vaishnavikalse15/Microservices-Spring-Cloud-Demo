# Microservices with Spring Cloud

## 📌 Project Overview

This project demonstrates a complete **microservices-based architecture** built using **Spring Boot** and **Spring Cloud**. It showcases how to build a distributed system with service discovery, API gateway, centralized configuration, and inter-service communication.

The system consists of **six core microservices** that work together to manage employee, department, and organization data in a scalable, cloud-ready architecture.

---

## 🚀 Key Features

- **Service Discovery** – Automatic service registration and discovery using **Eureka**
- **API Gateway** – Single entry point for all client requests using **Spring Cloud Gateway**
- **Distributed Configuration** – Centralized configuration management with **Spring Cloud Config Server**
- **Inter-Service Communication** – REST communication between services using **OpenFeign**
- **API Documentation** – Auto-generated Swagger/OpenAPI documentation
- **Log Correlation** – Distributed tracing and log correlation
- **Containerization** – Docker support for containerized deployment

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| **Java 17** | Programming language |
| **Spring Boot 3** | Application framework |
| **Spring Cloud** | Microservices framework |
| **Eureka** | Service discovery & registration |
| **Spring Cloud Gateway** | API gateway / routing |
| **Spring Cloud Config** | Centralized configuration |
| **OpenFeign** | Declarative REST client |
| **Springdoc / OpenAPI** | API documentation (Swagger UI) |
| **Docker** | Containerization |
| **Maven** | Build automation |

---

## 🏗️ Architecture

Our microservices-based system consists of the following modules:

| Service | Description |
|---------|-------------|
| **config-service** | Centralized configuration server using Spring Cloud Config |
| **discovery-service** | Eureka server for service registration and discovery |
| **gateway-service** | API gateway that routes requests to appropriate microservices |
| **employee-service** | Manages employee data with CRUD operations (in-memory repository) |
| **department-service** | Manages department data and communicates with employee-service |
| **organization-service** | Manages organization data and communicates with other services |
