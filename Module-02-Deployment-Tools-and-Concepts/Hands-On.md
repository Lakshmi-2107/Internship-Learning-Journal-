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
