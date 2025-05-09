# 🇵🇰 Hello Pakistan - FastAPI Project

Welcome to **Hello Pakistan**, a FastAPI-based project to kickstart your Python web development journey with blazing-fast APIs! 🚀

---

## 📁 Step 1: Create Project Directory and Switch to It
```bash

uv init hello-pakistan
cd hello-pakistan
```
## 🐍 Step 2: Create and Activate the Virtual Environment
## On macOS/Linux:

uv venv

```source .venv/bin/activate```

## On Windows:`
uv venv
.venv\Scripts\activate

```✅ Note: If you're using Python 3.11+, manual activation might not be necessary thanks to PEP 582.```

## 📦 Step 3: Install Dependencies
```Install FastAPI and Uvicorn:```
```uv add "fastapi[standard]"```

Add development dependencies like pytest:
```uv add --dev pytest pytest-asyncio```
📝 This updates your pyproject.toml with all required packages.

## 🧑‍💻 Step 4: Create Your First API Route

Create a file named main.py and add the following code:

## CODE: 
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"Hello": "Pakistan"}

@app.get("/items/{item_id}")
def read_item(item_id: int, q: str | None = None):
    return {"item_id": item_id, "q": q}


## 🚀 Step 5: Run the Server
## Development Mode:
fastapi dev main.py

## Or using Uvicorn:
uv run uvicorn main:app --host 0.0.0.0 --port 8000 --reload

🔄 --reload enables automatic server reload on code changes.



## 🧪 Step 6: Test Your APIs
Once the server is running, open your browser:

🌐 Root endpoint: http://localhost:8000

Returns:
{"Hello": "Pakistan"}

🌐 Items endpoint: http://localhost:8000/items/5?q=somequery

Returns:
{"item_id": 5, "q": "somequery"}

## 📚 Step 7: Interactive API Docs
FastAPI auto-generates interactive documentation:

📄 Swagger UI: http://localhost:8000/docs

📘 ReDoc: http://localhost:8000/redoc








