# Microservices with Spring Boot & Spring Cloud

## 📌 Project Overview

This project is a complete **distributed microservices system** built using **Spring Boot** and **Spring Cloud**. It manages employee, department, and organization data across multiple independent services that communicate with each other seamlessly.

The project demonstrates real-world microservices patterns including **service discovery**, **API routing**, **centralized configuration**, and **declarative HTTP communication**.

---

## 🧠 Architecture Overview

The system follows a **Service-Oriented Architecture (SOA)** with six independent modules:

| Service | Port | Responsibility |
|---------|------|----------------|
| **Discovery Service (Eureka)** | 8761 | All services register here. Acts as a phonebook for services to find each other. |
| **Config Service** | 8888 | Centralized server that provides dynamic configuration to all other services. |
| **Gateway Service** | 8080 | Single entry point for all external clients. Routes requests to the correct internal service. |
| **Employee Service** | Dynamic | Manages employee data (Add, Update, Delete, Search). |
| **Department Service** | Dynamic | Manages department data. Communicates with Employee Service to fetch employees. |
| **Organization Service** | Dynamic | Manages organization data. Communicates with Department Service. |

---

## 🔄 Communication Flow

1. **Client Request** → Gateway Service (Port 8080).
2. **Gateway** checks with **Discovery Service (Eureka)** to find the location of the required service.
3. **Gateway forwards** the request to the specific microservice.
4. If a service needs data from another service, it uses **OpenFeign** to call that service via Eureka.
5. **Config Service** provides environment-specific settings to all services at startup.

---

## ⚙️ Key Features & Implementation

| Feature | Implementation |
| :--- | :--- |
| **Service Registration** | Every microservice registers with Eureka on startup. |
| **Load Balancing** | Gateway automatically balances requests using Spring Cloud LoadBalancer. |
| **Centralized Config** | Config Server serves `.yml` files from a git repository (or local). |
| **Inter-service Communication** | Using OpenFeign - Services call each other like local methods. |
| **Resilience** | Built-in retry and fallback mechanisms (Spring Retry). |
| **API Documentation** | Springdoc/OpenAPI generates interactive Swagger UI. |
| **Containerization** | Dockerfiles allow building images for containerized deployment. |

---

## 💻 Technology Stack

- **Language:** Java 17
- **Frameworks:** Spring Boot 3, Spring Cloud
- **Service Discovery:** Eureka (Netflix)
- **API Gateway:** Spring Cloud Gateway
- **Config Management:** Spring Cloud Config Server
- **HTTP Client:** OpenFeign
- **Build Tool:** Maven
- **Container:** Docker

---

## 🚀 How It Works (Internal Logic)

1. **Config First:** When a service starts, it first contacts the Config Server to fetch its specific configuration.
2. **Register with Eureka:** After getting config, the service registers itself with the Discovery Service.
3. **Routing via Gateway:** The Gateway service queries Eureka to map URLs to the actual service instances.
4. **Data Fetching:** If Department Service needs employee data, it uses OpenFeign to call employee-service via Eureka.

---

## 📚 Core Learnings from This Project

Building this project gave me hands-on experience with:

- **Microservices Patterns:** How to break a monolithic app into independent services.
- **Service Discovery:** How services find each other without hardcoding IP addresses.
- **API Gateway:** Handling cross-cutting concerns like logging, security, and routing at a single point.
- **Fault Tolerance:** Understanding how services can fail without taking down the entire system.
- **Centralized Configuration:** Managing environment-specific settings from one place.
- **Containerization:** Packaging Java applications into Docker images.

---

## 🌟 Why This Project Stands Out

- **Complete Architecture:** It is not a CRUD app. It is a system of microservices.
- **Industry Standards:** Implements patterns used in companies like Uber, Amazon, and Netflix.
- **Scalable Design:** New services can be added without modifying existing ones.
