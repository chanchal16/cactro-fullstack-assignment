# 📝 Task Manager API

A simple backend-only RESTful API for managing tasks. This project supports user authentication via JWT and full CRUD operations for tasks. Built using **Node.js**, **Express**, and **MongoDB**.

---

## 📌 Project Overview

This is a secure and minimal Task Manager API that allows users to:

- Register and log in using JWT-based authentication.
- Perform CRUD operations on their personal tasks.
- Only access their own tasks with proper authorization.

---

## 🛠️ Tech Stack

- **Node.js + Express**
- **MongoDB Atlas** (via Mongoose)
- **JWT** for authentication
- **dotenv** for environment variable management

---

## 🚀 Getting Started (Local Setup)

### 🔧 Prerequisites

- Node.js & npm
- MongoDB Atlas account or a local MongoDB instance
- Postman (for testing)

### 📦 Installation

```bash
git clone https://github.com/chanchal16/cactro-fullstack-assignment.git
cd cactro-fullstack-assignment
npm install
```

### ⚙️ Create a .env file
```bash
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```
### ▶️ Run the Server
```bash
npm run dev
```
API will be available at: http://localhost:5000/api

### 🌐 Deployed API
Base URL: https://cactro-fullstack-assignment-307x.onrender.com/api

### 🔐 Authentication
- Register: POST /auth/register
- Login: POST /auth/login
- Returns a JWT token to be used in the Authorization header for protected routes.

Example Authorization Header:
```bash
Authorization: Bearer <your_jwt_token>
```

## 📋 API Endpoints
### 👤 Auth Routes
| Method | Endpoint       | Description         |
|--------|----------------|---------------------|
| POST   | /auth/register | Register a new user |
| POST   | /auth/login    | Login and get a JWT |

### ✅ Task Routes (Protected)
| Method | Endpoint   | Description              |
|--------|------------|--------------------------|
| POST   | /tasks     | Create a new task        |
| GET    | /tasks     | Get all tasks for a user |
| PUT    | /tasks/:id | Update a task            |
| DELETE | /tasks/:id | Delete a task            |

### Task Schema
```bash
{
  "title": "Task title",
  "description": "Optional detailed info",
  "status": "pending | in-progress | completed"
}
```
## 🔁 Sample Request (Postman)
### 📬 Register User
```bash
POST /auth/register
{
  "email": "john@example.com",
  "password": "password123"
}
```
### 🔓 Login
```bash
POST /auth/login
{
  "email": "john@example.com",
  "password": "password123"
}
```
### ➕ Create Task
```bash
POST /tasks
Authorization: Bearer <token>
{
  "title": "Write documentation",
  "description": "Finish the README file",
  "status": "pending"
}
```

### 📬 Postman Collection
🔗 [View Postman Collection](https://tinyurl.com/mr2t4w7p)

This collection includes:
- Auth routes
- Task routes (with token authorization headers)
- Example requests & responses
