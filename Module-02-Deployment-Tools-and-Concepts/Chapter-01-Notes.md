# 📘 Week 2 – Chapter 1 – Session 1
# Containerization with Podman: From Setup to a Flask Web App Powered by a Local LLM

In this session, I learned the fundamentals of **containerization** using Podman inside WSL.  
I practiced running containers, managing storage and networking, and finally built a **Flask web application** connected to a **local LLM (Ollama)** running inside containers.

---

## 🔹 1. What is Containerization?

Containerization is a method of packaging an application along with:

- Source code  
- Runtime (Python/Node/etc.)  
- Libraries  
- System dependencies  

### Benefits
- Same behavior on every system  
- No dependency conflicts  
- Easy deployment  
- Lightweight compared to virtual machines  

### Basic Terms
- **Image** → Template or blueprint  
- **Container** → Running instance of an image  

---

## 🔹 2. Install Podman in WSL

Update packages:

```bash
sudo apt update
```

Install Podman:

```bash
sudo apt install -y podman
```

(Optional compatibility tool):

```bash
sudo apt install -y qemu-system-x86
```

Check installation:

```bash
podman --version
```

> Note: `podman machine start` may fail in WSL, but containers still run correctly.

---

## 🔹 3. Basic Podman Commands

Test container:

```bash
podman run alpine echo "Podman setup successful"
```

List images:

```bash
podman images
```

List running containers:

```bash
podman ps
```

List all containers:

```bash
podman ps -a
```

---

## 🔹 4. Project 1 – Running Jupyter Lab in a Container

Pull Jupyter image:

```bash
podman pull quay.io/jupyter/base-notebook
```

Run container:

```bash
podman run -d --name jupyter_lab -p 8888:8888 quay.io/jupyter/base-notebook
```

Check logs:

```bash
podman logs jupyter_lab
```

Access in browser:

```
http://localhost:8888
```

---

## 🔹 5. Container Management

Stop container:

```bash
podman stop jupyter_lab
```

Remove container:

```bash
podman rm jupyter_lab
```

Delete image:

```bash
podman rmi quay.io/jupyter/base-notebook
```

---

## 🔹 6. Persistent Storage Using Volumes

Create folder:

```bash
mkdir -p ~/jupyter-data
```

Run with volume:

```bash
podman run -d \
  --name jupyter_lab \
  -p 8888:8888 \
  -v ~/jupyter-data:/home/jovyan/work \
  quay.io/jupyter/base-notebook
```

👉 Files remain saved even if container is deleted.

---

## 🔹 7. Project 2 – Running Ollama for Local LLMs

Pull Ollama image:

```bash
podman pull docker.io/alpine/ollama
```

Run container:

```bash
podman run -d --name ollama -p 11434:11434 docker.io/alpine/ollama
```

Download model:

```bash
podman exec -it ollama ollama pull gemma3:270m
```

Check logs:

```bash
podman logs ollama
```

---

## 🔹 8. Test the LLM API

```bash
curl http://localhost:11434/api/chat -d '{
  "model": "gemma3:270m",
  "messages": [
    {"role": "system", "content": "You are helpful"},
    {"role": "user", "content": "Explain containers simply"}
  ],
  "stream": false
}'
```

---

## 🔹 9. Networking Multiple Containers

Create network:

```bash
podman network create llm-net
```

Run Ollama inside network:

```bash
podman run -d \
  --name ollama \
  --network llm-net \
  -p 11434:11434 \
  docker.io/alpine/ollama
```

Containers communicate using:

```
http://ollama:11434
```

(No need for IP address)

---

## 🔹 10. Project 3 – Flask Web App with LLM Backend

Install requirements:

```bash
pip install flask requests
```

---

## 🔹 11. Flask Application (app.py)

```python
import requests
from flask import Flask, request

app = Flask(__name__)

def ask_llm(prompt, style):
    url = "http://ollama:11434/api/chat"

    payload = {
        "model": "gemma3:270m",
        "messages": [
            {"role": "system", "content": f"You are an assistant. Reply in a {style} style."},
            {"role": "user", "content": prompt}
        ],
        "stream": False
    }

    response = requests.post(url, json=payload)
    return response.json()["message"]["content"]

@app.route("/")
def home():
    return "<form method='POST'><textarea name='prompt'></textarea><input name='style'><button>Submit</button></form>"

@app.route("/", methods=["POST"])
def handle():
    prompt = request.form.get("prompt")
    style = request.form.get("style")
    answer = ask_llm(prompt, style)
    return answer

app.run(host="0.0.0.0", port=5000)
```

---

## 🔹 12. Containerize Flask App

Create Dockerfile:

```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY . .
RUN pip install flask requests
CMD ["python", "app.py"]
```

Build image:

```bash
podman build -t flask-llm-app .
```

Run container:

```bash
podman run -d --name flask-app --network llm-net -p 5000:5000 flask-llm-app
```

---

## 🔹 13. Access Application

Open browser:

```
http://localhost:5000
```

Check containers:

```bash
podman ps
```

Check logs:

```bash
podman logs flask-app
podman logs ollama
```

---

## 🔹 14. Final Takeaways

- Podman runs containers without a daemon  
- Containers isolate dependencies  
- Volumes preserve data  
- Networks allow container communication  
- Local LLMs enable offline AI usage  
- Flask + Ollama demonstrates real AI backend integration  

---

# Session 1 Completed 🎉
