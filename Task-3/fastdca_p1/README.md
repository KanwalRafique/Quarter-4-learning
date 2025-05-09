# 🤖 FastDCA Pydantic Demo 🚀

Welcome to the **FastDCA Chatbot API**, a demonstration of how to use **Pydantic** with **FastAPI** for agentic workflows in DACA (Distributed Agentic Cloud Ascent) systems.

---

## 📌 What is Pydantic?

**Pydantic** is a powerful Python library for data validation and settings management using type hints. It plays a key role in FastAPI by:
- ✅ Validating data using type hints
- 🔄 Automatically converting data types
- 🚫 Raising detailed validation errors
- 📦 Supporting nested models
- 📤 Serializing models for API responses
- 🧠 Allowing custom validators

---

## 🧪 Getting Started

### 🔧 Setup Instructions

```bash
uv init fastdca_p1
cd fastdca_p1
uv venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
uv add "fastapi[standard]"
```

### 🧵 Examples
### 1️⃣ Basic Pydantic Model: pydantic_example_1.py
```
from pydantic import BaseModel, ValidationError

class User(BaseModel):
    id: int
    name: str
    email: str
    age: int | None = None
```
✅ Handles valid data and ❌ raises error on invalid input.

### 2️⃣ Nested Models: pydantic_example_2.py

```
class Address(BaseModel):
    street: str
    city: str
    zip_code: str

class UserWithAddress(BaseModel):
    ...
    addresses: list[Address]
```
✔️ Great for modeling real-world data!


### 3️⃣ Custom Validators: pydantic_example_3.py
@validator("name")
def name_must_be_at_least_two_chars(cls, v):
    ...
🛡️ Ensures name length and other custom rules.


### 🧠 Why Pydantic for DACA?
✅ Data Integrity

📊 Complex Workflows

🔁 Serialization

🛠️ Error Handling

### 💬 Chatbot API: main.py
This is a sample chatbot API using FastAPI and Pydantic models:
```
@app.post("/chat/", response_model=Response)
async def chat(message: Message):
    ...
```
🔁 Request Structure
```
{
  "user_id": "123",
  "text": "Hello!",
  "metadata": {
    "timestamp": "...",
    "session_id": "..."
  },
  "tags": ["greeting"]
}
```
✅ Response Structure
```
{
  "user_id": "123",
  "reply": "Hello, 123! You said: 'Hello!'. How can I assist you today?",
  "metadata": {
    "timestamp": "...",
    "session_id": "..."
  }
}
```
### ▶️ Run the App

fastapi dev main.py
Then visit: http://localhost:8000/docs for interactive Swagger UI 🧪

![Screenshot 2025-05-09 212557](https://github.com/user-attachments/assets/a032dbce-7024-4d27-8121-88eb8dea1d66)














