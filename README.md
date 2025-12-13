---

# **My Ride Share Backend**

A robust and scalable backend service for a ride-sharing application, built using **Spring Boot** and **MongoDB**. The project includes secure authentication, real-time ride management, and role-based access control tailored for passengers and drivers.

---

## 🚀 **Key Features**

* **Secure Authentication**

  * JWT-based stateless authentication
  * BCrypt password hashing

* **Role-Based Access Control**

  * Separate permissions for **Passengers (ROLE_USER)** and **Drivers (ROLE_DRIVER)**

* **Ride Management**

  * Full lifecycle: **Request → Accept → Complete**
  * Real-time status with proper validation

* **Data Validation**

  * Strong input validation for stable and error-free operation

* **Scalable Architecture**

  * Clean, service-oriented design following Spring Boot best practices

---

## 🛠 **Tech Stack**

| Category   | Technology           |
| ---------- | -------------------- |
| Framework  | Spring Boot 3+       |
| Language   | Java 17+             |
| Database   | MongoDB              |
| Security   | Spring Security, JWT |
| Build Tool | Maven                |

---

## 📦 **Setup & Installation**

### **Prerequisites**

Ensure you have:

* Java **JDK 17+**
* MongoDB running locally (default port **27017**)
* Maven (optional, Maven wrapper included)

### **1. Clone the Repository**

```bash
git clone https://github.com/yourusername/rideshare_backend.git
cd rideshare_backend
```

### **2. Configuration**

The server runs on **port 8081** by default.
Modify this file if needed:

```
src/main/resources/application.properties
```

### **3. Build & Run**

```bash
./mvnw spring-boot:run
```

---

## 📘 **API Documentation**

### 🔐 **Authentication**

| Method | Endpoint             | Description                               |
| ------ | -------------------- | ----------------------------------------- |
| POST   | `/api/auth/register` | Register a new user (Passenger or Driver) |
| POST   | `/api/auth/login`    | Login and receive JWT token               |

---

### 🚖 **Trip Management — Passenger**

| Method | Endpoint             | Description            |
| ------ | -------------------- | ---------------------- |
| POST   | `/api/v1/rides`      | Request a new trip     |
| GET    | `/api/v1/user/rides` | View your trip history |

---

### 🚗 **Trip Management — Driver**

| Method | Endpoint                           | Description                |
| ------ | ---------------------------------- | -------------------------- |
| GET    | `/api/v1/driver/rides/requests`    | View pending trip requests |
| POST   | `/api/v1/driver/rides/{id}/accept` | Accept a trip request      |

---

### 🔄 **General**

| Method | Endpoint                      | Description              |
| ------ | ----------------------------- | ------------------------ |
| POST   | `/api/v1/rides/{id}/complete` | Mark a trip as completed |

---

## 🧪 **Testing**

You can test APIs using **Postman** or **cURL**.

### ▶️ **Register User**

```bash
curl -X POST http://localhost:8081/api/auth/register \
-H "Content-Type: application/json" \
-d '{"username":"john_doe","password":"password123","role":"ROLE_USER"}'
```

### ▶️ **Login**

```bash
curl -X POST http://localhost:8081/api/auth/login \
-H "Content-Type: application/json" \
-d '{"username":"john_doe","password":"password123"}'
```

---

## 📂 **Project Structure**

```
com.ridehub.backend
├── config       # Security and App Configuration
├── controller   # REST API Controllers
├── dto          # Data Transfer Objects
├── exception    # Global Exception Handling
├── model        # MongoDB Entities (Account, TripRequest)
├── repository   # Data Access Layer
├── service      # Business Logic
└── util         # Utilities (JWT, etc.)
```




