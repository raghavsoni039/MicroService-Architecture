# 🚀 DevOps Microservices Architecture

## 📌 Overview

This project demonstrates a simple **microservices-based architecture** using Flask, PostgreSQL, Redis, and Docker Compose. It is designed to showcase service separation, inter-service communication, caching, and containerized deployment.

---

## 🏗️ Architecture

The system consists of the following services:

### 1. User Service

* Handles user registration
* Stores user data in PostgreSQL
* Runs on port **5000**

### 2. Data Service

* Fetches user information
* Uses Redis for caching to improve performance
* Runs on port **5001**

### 3. PostgreSQL

* Primary database for storing user data
* Initialized using `init.sql`

### 4. Redis

* In-memory cache for fast data retrieval

---

## 🔄 Workflow

1. User registers via User Service
2. Data is stored in PostgreSQL
3. Data Service fetches user info:

   * Checks Redis cache first
   * If not found, fetches from DB
   * Stores result in Redis

---

## 📂 Project Structure

```
.
├── user-service/
├── data-service/
├── docker-compose.yml
├── init.sql
└── README.md
```

---

## ⚙️ Technologies Used

* Python (Flask)
* PostgreSQL
* Redis
* Docker
* Docker Compose

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/raghavsoni039/DevOps-Project-2-MicroService-Architecture.git
cd DevOps-Project-2-MicroService-Architecture
```

### 2. Start services

```bash
docker-compose up --build
```

---

## 🌐 API Endpoints

### User Service

#### Register User

```http
POST /register
```

**Body:**

```json
{
  "name": "john",
  "info": "John is a developer"
}
```

---

### Data Service

#### Get User Info

```http
GET /user/<name>
```

**Example:**

```bash
curl http://localhost:5001/user/alice
```

---

## 🧪 Example Output

```json
{
  "name": "alice",
  "cached": false,
  "info": "Alice is a data scientist."
}
```

---

## 📦 Features

* Microservices architecture
* Redis caching
* PostgreSQL integration
* Dockerized environment
* Automatic DB initialization
* Retry mechanism for DB connection

---

## 🧠 Learning Outcomes

* Understanding microservices design
* Container orchestration using Docker Compose
* Service-to-service communication
* Implementing caching strategies
* Managing environment configurations

---

## 📌 Future Improvements

* Add API Gateway
* Implement authentication (JWT)
* Add logging & monitoring (Prometheus, Grafana)
* Scale services using Kubernetes

---

## 👨‍💻 Author

Raghav Soni

---
