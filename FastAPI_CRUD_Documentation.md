
# 🚀 FastAPI CRUD API – With Swagger UI & Requests

This project demonstrates a simple FastAPI application with basic CRUD operations (Create, Read, Update, Delete) using JSON requests via Pydantic models.

---

## 🌐 How to Run the API

Start the server using:

```bash
uvicorn main:app --reload
```

Then open your browser and go to:

```
http://localhost:8000/docs
```

This will open the **Swagger UI**, where you can test all endpoints (GET, POST, PUT, DELETE) interactively.

---

## 📘 Endpoints Overview

### 🔹 `GET /`

**Purpose**: Get the list of all names.

- **URL**: `http://localhost:8000/`
- **Response**: JSON list of names

✅ Example Output:
```json
["Ali", "Ahmed", "Sara", "Tariq", "Aisha"]
```

---

### 🔹 `POST /create`

**Purpose**: Add a new name to the list.

- **URL**: `http://localhost:8000/create`
- **Request Body**:
```json
{
  "name": "Zain",
  "age": 25
}
```

- **Response**: Updated list of names.

---

### 🔹 `PUT /update/{item_id}`

**Purpose**: Update the name at a specific index.

- **URL**: `http://localhost:8000/update/index-number`
- **Request Body**:
```json
{
  "name": "Updated Name",
  "age": 30
}
```

- **Response**: List with updated name.

---

### 🔹 `DELETE /{item_id}`

**Purpose**: Delete a name at a specific index.

- **URL**: `http://localhost:8000/index-number`

- **Response**: List after deletion.

---

## 🧪 Testing in Swagger UI

1. Go to `http://localhost:8000/docs`
2. You'll see all available functions.
3. Click any function → Click `Try it out` → Fill data → Click `Execute`.
4. You'll get response status (e.g., `200 OK`) and output.

---

## 📁 Example Code

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

names = ["Ali", "Ahmed", "Sara", "Tariq", "Aisha"]

@app.get("/")
def get_function():
    return names

class Data(BaseModel):
    name: str
    age: int

@app.post("/create")
def create_function(data: Data):
    names.append(data.name)
    return names

@app.put("/update/{item_id}")
def update_function(json_data: Data, item_id: int):
    for i, name in enumerate(names):
        if item_id == i:
            names[i] = json_data.name
            break
    return names

@app.delete("/{item_id}")
def delete_function(item_id: int):
    names.pop(item_id)
    return names
```

---

## ✅ Summary

| Method | Endpoint           | Description          |
|--------|--------------------|----------------------|
| GET    | `/`                | Get list of names    |
| POST   | `/create`          | Add a new name       |
| PUT    | `/update/{id}`     | Update existing name |
| DELETE | `/{id}`            | Delete name by index |

---

> 🧠 This API is fully interactive and testable using Swagger UI. Ideal for learning and demonstrating basic RESTful concepts with FastAPI!
