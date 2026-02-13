# 📘 Chapter 4 – FastAPI Workflow, Testing & Deployment
## Week 2 – Session 4
## Building APIs, Validation, File Uploads, Docker & Deployment

In this session, we learned how to build a complete backend server using FastAPI, handle GET and POST requests, validate data using Pydantic, upload files, automate testing with cURL and scripts, secure applications using environment variables, containerize with Docker, and finally deploy the API online for evaluation.

---

# 🔹 1. Project Workflow Overview

The project follows a clear workflow from development to evaluation.

Flow:

1. Build FastAPI server
2. Deploy server online
3. GitHub Pages hosts frontend/app
4. ITM server sends request to your API
5. Your API responds immediately
6. After 10 minutes → frontend sends evaluation request
7. Server checks and grades automatically

Key points:

- API must respond within time limit
- Response must be valid JSON
- Deployment must be public
- Everything should run automatically

---

# 🔹 2. Understanding FastAPI

FastAPI is a modern Python framework to build APIs quickly.

Features:

- Very fast performance
- Easy syntax
- Automatic validation
- Built-in documentation
- Async support

Install dependencies:

```bash
pip install fastapi uvicorn python-multipart
```

Packages:

- fastapi → API framework
- uvicorn → server runner
- python-multipart → file uploads

---

# 🔹 3. Running the Server

Start the FastAPI app:

```bash
uvicorn main:app --reload
```

Meaning:

- main → file name
- app → FastAPI object
- --reload → auto restart on changes

Server runs at:

```
http://127.0.0.1:8000
```

---

# 🔹 4. Creating Basic GET Requests

GET requests fetch data from the server.

Example:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def home():
    return {"message": "Server running"}
```

Used for:

- checking server health
- retrieving information
- simple responses

---

# 🔹 5. Path Parameters

Path parameters make URLs dynamic.

Example:

```python
@app.get("/items/{item_id}")
def get_item(item_id: int):
    return {"id": item_id}
```

URL:

```
/items/5
```

Use cases:

- fetching specific records
- accessing particular resources

---

# 🔹 6. Query Parameters

Query parameters are optional inputs.

Example:

```python
@app.get("/search")
def search(q: str = ""):
    return {"query": q}
```

URL:

```
/search?q=fastapi
```

Use cases:

- filtering
- searching
- sorting

---

# 🔹 7. Pydantic Data Validation

Pydantic validates request and response data automatically.

Example:

```python
from pydantic import BaseModel

class User(BaseModel):
    name: str
    age: int
```

Benefits:

- type checking
- missing fields → error
- extra fields ignored
- clean structured JSON

---

# 🔹 8. POST Requests

POST requests send data to the server.

Example:

```python
@app.post("/users")
def create_user(user: User):
    return user
```

Used for:

- creating records
- sending forms
- uploading data

---

# 🔹 9. File Uploads

FastAPI supports file uploads using multipart forms.

Single file:

```python
from fastapi import File, UploadFile

@app.post("/upload")
async def upload(file: UploadFile):
    return {"filename": file.filename}
```

Multiple files:

```python
@app.post("/upload-multiple")
async def upload(files: list[UploadFile]):
    return {"count": len(files)}
```

Used for:

- images
- documents
- datasets

---

# 🔹 10. Testing APIs with cURL

Test endpoints quickly from terminal.

GET:

```bash
curl http://127.0.0.1:8000/
```

POST:

```bash
curl -X POST http://127.0.0.1:8000/users \
-H "Content-Type: application/json" \
-d '{"name":"Lakshmi","age":22}'
```

Benefits:

- fast testing
- no browser needed
- easy automation

---

# 🔹 11. Automated Testing with Scripts

Instead of manual testing, use bash scripts.

Example:

```bash
#!/bin/bash

curl http://127.0.0.1:8000/
curl -X POST http://127.0.0.1:8000/users -d '{"name":"Test","age":20}'
```

Run:

```bash
bash test.sh
```

This speeds up development.

---

# 🔹 12. Secret Keys & Environment Variables

Never hardcode API keys.

Install:

```bash
pip install python-dotenv
```

Create `.env`:

```
API_KEY=123456
```

Load in Python:

```python
from dotenv import load_dotenv
import os

load_dotenv()
key = os.getenv("API_KEY")
```

Benefits:

- secure
- hidden credentials
- safe deployment

---

# 🔹 13. Dockerfile Setup

Docker packages your app into a container.

Example Dockerfile:

```dockerfile
FROM python:3.10

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "7860"]
```

Benefits:

- same environment everywhere
- easy deployment
- no dependency issues

---

# 🔹 14. Deploying Online

Deploy API so evaluators can access it.

Steps:

1. Create hosting space
2. Upload files
3. Add Dockerfile
4. Deploy
5. Get public URL

Example:

```
https://yourapp.hf.space
```

Submit this URL for evaluation.

---

# 🔹 Objectives of This Session

- Build FastAPI server
- Create GET and POST endpoints
- Use path and query parameters
- Validate data with Pydantic
- Upload files
- Test using cURL
- Automate tests
- Secure secrets
- Dockerize app
- Deploy online

---

##  Session 4 Completed 🎉
