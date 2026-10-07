# python-Flask-RestAPI

# 🚀 User Management REST API

A lightweight, fully functional backend service built with **Python**, **Flask-RESTful**, and **SQLAlchemy**. This API handles core CRUD (Create, Read, Update, Delete) data operations for managing user records inside a relational database.

This project showcases a production-ready approach to building decoupled backends, using resource-based routing, strict request validation, and object serialization.

---

## 🛠️ Tech Stack & Architecture

* **Framework:** Flask & Flask-RESTful (Resource-oriented routing)
* **Database / ORM:** SQLite & Flask-SQLAlchemy
* **Data Validation:** `reqparse` (Ensures required fields are validated before hitting the DB)
* **Serialization:** `marshal_with` (Strict data formatting for secure, structured JSON outputs)

---

## 📌 API Endpoints & Documentation

All API requests accept and return JSON payloads. 

| HTTP Method | Endpoint | Description | Status Code |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/users/` | Fetch a list of all registered users | `200 OK` |
| `POST` | `/api/users/` | Create a new user record | `201 Created` |
| `GET` | `/api/users/<id>` | Fetch detailed profile data for a specific user | `200 OK` / `404` |
| `PATCH` | `/api/users/<id>` | Update an existing user's details | `200 OK` / `404` |
| `DELETE` | `/api/users/<id>` | Remove a user permanently from the system | `200 OK` / `404` |

### 📋 Request & Response Schemas

#### 1. Create a New User (`POST /api/users/`)
* **Request Body (`application/json`):**
  ```json
  {
    "name": "Jane Doe",
    "email": "jane@example.com"
  }
  ```
* **Success Response (`201 Created`):**
  Returns the updated list of all users.
  ```json
  [
    {
      "id": 1,
      "name": "Jane Doe",
      "email": "jane@example.com"
    }
  ]
  ```

#### 2. Get Single User Details (`GET /api/users/<id>`)
* **Success Response (`200 OK`):**
  ```json
  {
    "id": 1,
    "name": "Jane Doe",
    "email": "jane@example.com"
  }
  ```
* **Error Response (`404 Not Found`):**
  ```json
  {
    "message": "User not found"
  }
  ```

---

## ⚡ Setup and Installation

Follow these steps to run the Flask development server locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd your-repo-name
   ```

2. **Set up a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install flask flask_sqlalchemy flask_restful
   ```

4. **Initialize database & start the application:**
   *(The app automatically instantiates the `sqlite:///database.db` file upon boot)*
   ```bash
   python app.py
   ```
   The local server will spin up on **`http://127.0.0`**
