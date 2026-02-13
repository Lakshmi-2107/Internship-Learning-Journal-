# 🛠️ Hands-On Practice
## Week 2 – Chapter 1 – Session 1
## Containerization with Podman

In this session, I practically worked with Podman inside WSL and learned how to run applications inside containers. I containerized Jupyter Lab, Ollama (LLM), and built a Flask web application that communicates with an AI model running in another container.

---

##  Podman Setup

Updated Ubuntu packages:

```bash
sudo apt update
```

Installed Podman:

```bash
sudo apt install -y podman
```

Verified installation:

```bash
podman --version
```

Tested with sample container:

```bash
podman run alpine echo "Podman setup successful"
```

---

##  Practiced Basic Commands

Listed images:

```bash
podman images
```

Listed running containers:

```bash
podman ps
```

Listed all containers:

```bash
podman ps -a
```

---

##  Project 1 – Jupyter Lab Container

Pulled Jupyter image:

```bash
podman pull quay.io/jupyter/base-notebook
```

Started container:

```bash
podman run -d --name jupyter_lab -p 8888:8888 quay.io/jupyter/base-notebook
```

Checked logs:

```bash
podman logs jupyter_lab
```

Accessed Jupyter using:

```
http://localhost:8888
```

Stopped and removed container:

```bash
podman stop jupyter_lab
podman rm jupyter_lab
```

---

## Practiced Volume Mounting (Persistent Storage)

Created local folder:

```bash
mkdir -p ~/jupyter-data
```

Mounted volume while running container:

```bash
podman run -d \
  --name jupyter_lab \
  -p 8888:8888 \
  -v ~/jupyter-data:/home/jovyan/work \
  quay.io/jupyter/base-notebook
```

Verified that files remained saved after container restart.

---

## Project 2 – Ollama (Local LLM)

Pulled Ollama image:

```bash
podman pull docker.io/alpine/ollama
```

Started container:

```bash
podman run -d --name ollama -p 11434:11434 docker.io/alpine/ollama
```

Downloaded model:

```bash
podman exec -it ollama ollama pull gemma3:270m
```

Checked logs:

```bash
podman logs ollama
```

Tested API using curl.

---

## Networking Containers

Created custom network:

```bash
podman network create llm-net
```

Ran containers inside same network:

```bash
podman run -d --name ollama --network llm-net -p 11434:11434 docker.io/alpine/ollama
```

Confirmed containers could communicate using service names.

---

## Project 3 – Flask + LLM Web App

Installed requirements:

```bash
pip install flask requests
```

Built Flask app that sends user input to LLM and displays response.

Created Docker image:

```bash
podman build -t flask-llm-app .
```

Ran Flask container:

```bash
podman run -d --name flask-app --network llm-net -p 5000:5000 flask-llm-app
```

Accessed app in browser:

```
http://localhost:5000
```

---

##  Outcome

- Successfully installed Podman
- Ran containers smoothly inside WSL
- Used port mapping to access services
- Persisted data using volumes
- Ran local LLM inside container
- Connected multiple containers using network
- Built Flask app integrated with AI backend

---

## Week 2 – Chapter 2 – Session 2
## Podman, GitHub Pages, FastAPI, Vercel & Deployment Tools

In this session, I practically explored modern development and deployment tools. I worked with containers, built APIs using FastAPI, hosted static websites using GitHub Pages, deployed apps using Vercel, exposed local servers using ngrok, and learned how to securely manage API keys.

---

## Podman Practice

Verified Podman installation:

```bash
podman --version
```

Ran a test container:

```bash
podman run alpine echo "Podman working"
```

Listed images:

```bash
podman images
```

Listed running containers:

```bash
podman ps
```

Stopped containers:

```bash
podman stop <container-name>
```

Removed containers:

```bash
podman rm <container-name>
```

---

##  GitHub Pages Practice

- Created a GitHub repository
- Added HTML, CSS files
- Enabled GitHub Pages from repository settings
- Pushed changes to GitHub
- Verified that website automatically deployed
- Accessed live site using GitHub Pages URL

Outcome:
Static site successfully hosted online.

---

##  FastAPI Practice

Installed FastAPI:

```bash
pip install fastapi uvicorn
```

Created simple API server.

Started server:

```bash
uvicorn app:app --reload
```

Tested API:
- GET requests
- POST requests
- Checked auto-generated docs

Accessed:
```
http://localhost:8000
```

---

##  Vercel Deployment Practice

Installed Vercel CLI:

```bash
npm install -g vercel
```

Logged in and deployed project:

```bash
vercel
```

Connected GitHub repository to Vercel for automatic deployment.

Verified:
- App deployed successfully
- Changes auto-updated on push

---

##  ngrok Practice

Started local Flask/FastAPI server.

Exposed server:

```bash
ngrok http 5000
```

Received public URL.

Shared link and accessed app from browser.

---

##  Environment Variables Practice

Set API key:

```bash
export OPENAI_API_KEY=your_key_here
```

Accessed inside Python using `os.getenv()`.

Verified that secrets were not stored in code.

---

##  CORS Testing

- Connected frontend to backend
- Faced cross-origin issue
- Enabled CORS
- Confirmed requests worked properly

---

##  Outcome

- Containers ran successfully
- Static site hosted online
- API server created and tested
- App deployed on Vercel
- Local server exposed with ngrok
- Secrets stored securely
- Understood frontend-backend communication

---

## Week 2 – Chapter 3 – Session 3
## GitHub Actions, Codespaces & Cloud Automation

In this session, I practically worked with GitHub automation tools and cloud-based development platforms. I created workflows, tested automated jobs, used Codespaces for development, and explored deployment using online hosting services.

---

##  GitHub Actions Setup

Created workflow folder:

```
.github/workflows/
```

Added workflow file:

```
automation.yml
```

---

##  Created First Workflow

Basic workflow to run on every push.

```yaml
name: Test Workflow

on:
  push:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: echo "Workflow executed successfully"
```

### Result
- Workflow triggered automatically after push
- Checked execution logs in GitHub Actions tab
- Verified job completed successfully

---

##  Practiced Scheduled Workflow

Created a scheduled job using cron timing.

```yaml
on:
  schedule:
    - cron: "0 0 * * *"
```

### Activity performed
- Simulated daily execution
- Ran Python script automatically
- Generated JSON output file
- Observed automatic commit

### Learning
Understood how GitHub can run tasks without manual execution.

---

##  Automatic Commit Practice

Added steps to save changes automatically.

```bash
git config --global user.name "github-actions"
git config --global user.email "actions@github.com"
git add .
git commit -m "Auto update"
git push
```

### Result
- File updated automatically
- Changes pushed to repository without manual action

---

##  Used GitHub Codespaces

Steps performed:
- Opened repository in Codespaces
- Developed directly in browser
- Edited files
- Installed dependencies
- Ran scripts

### Observations
- No local setup required
- Faster startup
- Same environment every time

---

##  Practiced GitHub Pages

Steps:
- Created static HTML page
- Pushed to repository
- Enabled GitHub Pages in settings
- Verified live site

### Result
Website hosted successfully using GitHub link.

---

## Explored Hugging Face Spaces

Steps:
- Created new Space
- Connected GitHub repo
- Pushed app files
- Deployed automatically

### Result
App went live without manual server setup.

---

##  Tested Workflow Logs

Checked:
- job status
- execution time
- errors
- success messages

Learned how to debug workflows using logs.

---

##  Commands Practiced

Inline commands used during session:

`git add .`  
`git commit -m "message"`  
`git push`  

---

## Outcome

By the end of the session, I was able to:

- create GitHub workflows
- automate tasks on push
- schedule jobs using cron
- commit files automatically
- develop using Codespaces
- host static sites using GitHub Pages
- deploy apps using Spaces
- monitor workflow logs

This hands-on practice helped me understand real-world CI/CD automation.

--
  
## Chapter 4  – Session 4
## FastAPI Workflow, Testing & Deployment Lab

This hands-on guide helps you practically implement everything learned in this session.

By the end, you will:

✅ Build a FastAPI server  
✅ Create GET & POST endpoints  
✅ Validate data using Pydantic  
✅ Upload files  
✅ Test using curl  
✅ Use environment variables  
✅ Dockerize the app  
✅ Deploy online  

---

# 🔹 Step 1 – Create Project Folder

```bash
mkdir fastapi-project
cd fastapi-project
```

---

# 🔹 Step 2 – Install Dependencies

```bash
pip install fastapi uvicorn python-multipart python-dotenv
```

---

# 🔹 Step 3 – Create main.py

Create file:

```bash
touch main.py
```

Paste:

```python
from fastapi import FastAPI, UploadFile, File
from pydantic import BaseModel
from dotenv import load_dotenv
import os

load_dotenv()

app = FastAPI()

class User(BaseModel):
    name: str
    age: int

@app.get("/")
def home():
    return {"message": "Server running"}

@app.get("/items/{item_id}")
def get_item(item_id: int):
    return {"id": item_id}

@app.get("/search")
def search(q: str = ""):
    return {"query": q}

@app.post("/users")
def create_user(user: User):
    return user

@app.post("/upload")
async def upload_file(file: UploadFile = File(...)):
    return {"filename": file.filename}
```

---

# 🔹 Step 4 – Run Server

```bash
uvicorn main:app --reload
```

Open browser:

```
http://127.0.0.1:8000
```

Docs:

```
http://127.0.0.1:8000/docs
```

Test APIs directly from Swagger UI.

---

# 🔹 Step 5 – Test Using curl

## GET

```bash
curl http://127.0.0.1:8000/
```

## Path parameter

```bash
curl http://127.0.0.1:8000/items/10
```

## Query parameter

```bash
curl "http://127.0.0.1:8000/search?q=fastapi"
```

## POST request

```bash
curl -X POST http://127.0.0.1:8000/users \
-H "Content-Type: application/json" \
-d '{"name":"Lakshmi","age":22}'
```

---

# 🔹 Step 6 – File Upload Test

```bash
curl -X POST http://127.0.0.1:8000/upload \
-F "file=@sample.txt"
```

---

# 🔹 Step 7 – Automate Testing Script

Create:

```bash
touch test.sh
```

Paste:

```bash
curl http://127.0.0.1:8000/
curl http://127.0.0.1:8000/items/5
curl -X POST http://127.0.0.1:8000/users -H "Content-Type: application/json" -d '{"name":"Test","age":20}'
```

Run:

```bash
bash test.sh
```

---

# 🔹 Step 8 – Add Environment Variables

Create:

```bash
touch .env
```

Add:

```
API_KEY=123456
```

Update main.py:

```python
key = os.getenv("API_KEY")
```

Never hardcode secrets.

---

# 🔹 Step 9 – Create requirements.txt

```bash
pip freeze > requirements.txt
```

---

# 🔹 Step 10 – Create Dockerfile

```bash
touch Dockerfile
```

Paste:

```dockerfile
FROM python:3.10

WORKDIR /app

COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "7860"]
```

---

# 🔹 Step 11 – Build Docker Image

```bash
docker build -t fastapi-app .
```

Run container:

```bash
docker run -p 7860:7860 fastapi-app
```

Open:

```
http://localhost:7860
```

---

# 🔹 Step 12 – Deploy Online

Deploy to any platform:

Options:

- Hugging Face Spaces
- Render
- Railway
- Docker server

Upload:

- main.py
- requirements.txt
- Dockerfile

After deployment, you get:

```
https://yourapp-url
```

Test:

```bash
curl https://yourapp-url
```

---


# 🔹 Final Checklist

Before submission:

✅ Server runs  
✅ All endpoints work  
✅ curl tests pass  
✅ requirements.txt created  
✅ Dockerfile works  
✅ App deployed  
✅ Public URL accessible  

---

##  Hands-On Practice Completed 🎉
