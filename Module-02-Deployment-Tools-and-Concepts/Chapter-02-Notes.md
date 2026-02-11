#  Week 2 – Chapter 2 – Session 2
# Modern Deployment Tools: Podman, GitHub Pages, FastAPI, Vercel & ngrok

In this session, we explored modern tools and concepts used for application deployment and web development. The focus was on containers using Podman, hosting static sites with GitHub Pages, building APIs using FastAPI, deploying applications with Vercel, exposing local servers using ngrok, and securing applications with environment variables and CORS.

---

##  1. Podman and Containers

Podman is a container engine used to run applications inside containers.

### What are Containers?

Containers package:
- Application code
- Dependencies
- Runtime
- Libraries

They run in isolated environments.

### Containers vs Virtual Machines

| Feature | Container | Virtual Machine |
|---------|-----------|----------------|
| Kernel | Shared with host | Separate kernel |
| Size | Lightweight | Heavy |
| Speed | Fast startup | Slow startup |
| Resource usage | Low | High |

### Benefits
- Lightweight
- Faster deployment
- Better resource usage
- Easy to manage multiple services

Example use:
- Database container
- Backend container
- Frontend container

---

##  2. GitHub Pages

GitHub Pages is used to host static websites directly from a GitHub repository.

### Supports:
- HTML
- CSS
- JavaScript

### Does NOT directly support:
- Markdown (needs tools like Jekyll/Quarto to convert)

### Features:
- Free hosting
- Auto deployment on push
- Easy setup
- Perfect for portfolios and documentation

### Workflow:
1. Push files to GitHub
2. GitHub automatically builds site
3. Site becomes live

---

##  3. FastAPI

`FastAPI` is a modern Python web framework for building APIs.

### Key Features
- High performance
- Asynchronous support
- Easy syntax
- Automatic API docs
- Built-in validation

### Why FastAPI?
- Handles many requests at once
- Faster than traditional frameworks
- Ideal for backend services

### Common HTTP Methods
- GET → fetch data
- POST → send data
- PUT → update
- DELETE → remove

### Example install
```bash
pip install fastapi uvicorn
```

Run server:
```bash
uvicorn app:app --reload
```

---

##  4. Vercel Deployment

Vercel is a cloud platform for hosting:
- Static websites
- APIs
- Serverless apps

### Deployment Methods

### Method 1 – GitHub Integration
- Connect GitHub repo
- Auto deploy on every push
- Easy continuous deployment

### Method 2 – Vercel CLI
Install:
```bash
npm install -g vercel
```

Deploy:
```bash
vercel
```

### Free Plan Limitations
- 300 second execution limit
- No long-running processes
- Limited file system access
- Serverless only

---

## 5. ngrok (Expose Local Server)

`ngrok` creates a public URL for a local server.

### Purpose
- Test webhooks
- Share local app
- Demo projects
- External API testing

Example:
```bash
ngrok http 5000
```

This creates:
```
https://random-url.ngrok.io
```

Now your local app is accessible globally.

---

##  6. Environment Variables (Secrets Management)

Environment variables store sensitive information safely.

### Examples
- API keys
- Tokens
- Database passwords

### Why use them?
- Avoid hardcoding secrets
- Secure applications
- Safe for GitHub

Example:
```bash
export OPENAI_API_KEY=your_key_here
```

Access in Python:
```python
import os
key = os.getenv("OPENAI_API_KEY")
```

---

##  7. CORS (Cross-Origin Resource Sharing)

CORS is a browser security feature.

### Purpose
Controls which domains can access your API.

### Problem
Frontend → calls backend from different domain → blocked

### Solution
Enable CORS in backend.

### Why important?
- Prevents unauthorized access
- Improves security
- Required for frontend-backend communication

---

##  Key Takeaways

- Containers are lightweight alternatives to virtual machines
- Podman manages isolated environments efficiently
- GitHub Pages hosts static websites easily
- FastAPI builds high-performance APIs
- Vercel simplifies cloud deployment
- ngrok exposes local servers for testing
- Environment variables protect secrets
- CORS controls cross-domain access

---

#  Session 2 Completed 🎉
