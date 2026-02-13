# 📚 Learnings
## Week 2 – Chapter 1 – Session 1
## Containerization with Podman

This session helped me understand the concept of containerization and how applications can be packaged and run in isolated environments using Podman. I gained both theoretical knowledge and practical experience by running real-world tools like Jupyter Lab, Ollama (LLM), and a Flask web application inside containers.

---

## Concepts Learned

- What containerization is and why it is important
- Difference between images and containers
- How Podman works as a Docker alternative
- How containers isolate dependencies and environments
- Port mapping to access container services
- Volume mounting for persistent storage
- Networking between multiple containers
- Running local LLMs without cloud services
- Building AI-powered web applications using containers

---

## Technical Knowledge Gained

### Podman
- Pulling images from registries
- Running and stopping containers
- Viewing container logs
- Removing containers and images

### Storage
- Using volumes to save container data
- Preventing data loss after container deletion

### Networking
- Creating custom networks
- Connecting containers using service names
- Enabling inter-container communication

### AI Integration
- Running Ollama locally
- Downloading and testing LLM models
- Sending API requests to LLMs
- Integrating LLM backend with Flask app

---

## Skills Gained

- Installed and configured Podman in WSL
- Managed containers using terminal commands
- Deployed Jupyter Notebook in a container
- Persisted files using volume mounts
- Hosted local AI models inside containers
- Connected multiple containers using networks
- Built and containerized a Flask application
- Debugged container and networking issues

---

## Practical Understanding

Now I understand that:

- Containers are lightweight alternatives to virtual machines
- Applications can run consistently across systems
- Services can be separated into multiple containers (frontend, backend, AI)
- Container networking is useful for real-world microservice architecture
- Podman makes deployment easier and more organized

---

## Outcome

After this session, I am confident in:

- Using Podman commands
- Running applications inside containers
- Managing storage and networking
- Building containerized applications
- Integrating AI models locally
- Creating scalable development setups

This knowledge prepares me for real-world development and deployment workflows used in modern software and AI projects.

---

## Week 2 – Chapter 2 – Session 2
## Deployment & Modern Web Development Tools

This session helped me understand modern tools and workflows used in real-world application deployment and backend development.

---

##  Concepts Learned

- What containers are and how they differ from virtual machines
- How Podman isolates applications efficiently
- Static website hosting using GitHub Pages
- API development using FastAPI
- Deploying apps to cloud using Vercel
- Exposing local servers using ngrok
- Managing secrets with environment variables
- Understanding CORS and cross-origin security

---

##  Technical Knowledge Gained

### Podman
- Running containers
- Managing images
- Isolating environments

### GitHub Pages
- Hosting static sites
- Automatic deployment on push

### FastAPI
- Creating APIs quickly
- Handling HTTP requests
- Running asynchronous servers

### Vercel
- Cloud deployment
- GitHub integration
- Serverless functions

### ngrok
- Creating public tunnels
- Testing local apps externally

### Security
- Protecting API keys
- Using environment variables
- Avoiding hardcoded secrets

---

## Skills Gained

- Used Podman to manage containers
- Hosted websites using GitHub Pages
- Built and tested REST APIs using FastAPI
- Deployed applications to cloud platforms
- Shared local projects publicly using ngrok
- Secured applications with environment variables
- Handled CORS issues

---

##  Practical Understanding

Now I understand that:

- Containers simplify deployment
- Static sites can be hosted easily
- APIs power modern applications
- Cloud platforms automate deployment
- Environment variables improve security
- These tools are widely used in industry

---

##  Outcome

After this session, I am confident in:

- Running applications in containers
- Hosting websites online
- Building backend APIs
- Deploying apps to cloud
- Managing secrets securely
- Debugging deployment issues

This knowledge prepares me for real-world development and production workflows.

---

## Week 2 – Chapter 3 – Session 3
## GitHub Actions, Workflows & Cloud Development Tools

In this session, I learned how modern software projects automate development tasks using GitHub tools and cloud platforms. Instead of doing everything manually, workflows can automatically test, build, deploy, and update projects. This makes development faster, more reliable, and more professional.

---

##  Concepts I Understood

### Automation
- Repetitive tasks can be handled automatically
- Reduces human errors
- Saves time and effort
- Improves productivity

---

### GitHub Actions
- Used to automate tasks inside a repository
- Runs workflows when events occur
- Can test, deploy, or update code automatically
- Works using YAML configuration files

---

### Workflows
- Stored inside `.github/workflows/`
- Define when and how tasks run
- Include triggers, jobs, and steps
- Can run on push, pull request, or schedule

---

### Continuous Integration (CI)
- Runs tests automatically
- Checks code quality
- Detects bugs early
- Keeps project stable

---

### Continuous Deployment (CD)
- Automatically deploys apps after testing
- Reduces manual deployment
- Speeds up release process

---

### Scheduled Jobs
- Run automatically at fixed times
- Useful for daily tasks
- Can fetch data or update files
- Similar to cron jobs

---

### GitHub Codespaces
- Cloud-based development environment
- No local installation needed
- Works in browser
- Same setup for everyone
- Quick and convenient for collaboration

---

### GitHub Pages
- Hosts static websites
- Easy to deploy HTML/CSS/JS projects
- Updates automatically when code is pushed
- Good for portfolios and documentation

---

### Hugging Face Spaces
- Quick hosting for AI/ML applications
- Git-based deployment
- No server management
- Useful for demos and experiments

---

##  Skills I Gained

After this session, I can:

- create workflow YAML files
- automate tasks on every push
- schedule jobs using cron
- monitor workflow logs
- debug failed jobs
- develop using Codespaces
- host static sites on GitHub Pages
- deploy apps easily using Spaces
- understand CI/CD pipeline

---

##  Practical Understanding

Now I clearly understand that:

- automation reduces manual work
- workflows make projects more efficient
- CI/CD is important in real-world development
- cloud tools simplify deployment
- modern teams rely heavily on these tools

These skills are useful for internships, team projects, and production environments.

---

##  Final Outcome

This session improved my confidence in:

- project automation
- deployment practices
- cloud-based development
- professional workflows

I can now build, test, and deploy applications more efficiently using modern tools.

---
## Chapter 4  – Session 4
## FastAPI Workflow, Testing & Deployment Reflections

This session focused on understanding how to design, build, test, secure, and deploy a complete backend API using FastAPI.  
Instead of only learning theory, we practiced building a real server and preparing it for production deployment.

---

# 🔹 Core Concepts Learned

##  FastAPI Basics

- FastAPI is a modern Python framework to build APIs
- Very fast and lightweight
- Easy syntax compared to Flask/Django
- Automatic API documentation at `/docs`
- Supports async programming

I learned how to:
- create a FastAPI app
- define routes
- return JSON responses
- run server using uvicorn

---

##  GET Requests

Used to fetch data from the server.

Learned:
- basic endpoints
- returning JSON
- checking server health

Example use:
- home page
- fetching items
- retrieving information

---

##  Path Parameters

Path parameters make URLs dynamic.

Example:
```
/items/10
```

Learned:
- how to pass values inside URL
- how FastAPI automatically converts types
- useful for fetching specific records

---

##  Query Parameters

Query parameters allow optional inputs.

Example:
```
/search?q=python
```

Learned:
- filtering data
- searching records
- optional arguments

Difference:
- Path → required
- Query → optional

---

##  Pydantic Validation

Pydantic handles request validation automatically.

Learned:
- defining models using BaseModel
- type checking
- automatic errors for wrong input
- cleaner backend logic

Benefits:
- safer APIs
- fewer bugs
- consistent data format

---

##  POST Requests

Used to send data to the server.

Learned:
- how to accept JSON body
- creating new records
- sending structured data
- backend validation using models

Use cases:
- signup forms
- submitting data
- uploads

---

##  File Uploads

Learned how to upload:

- single files
- multiple files

Using:
- UploadFile
- multipart forms

Use cases:
- images
- documents
- datasets

This is important for real-world apps.

---

##  API Testing with curl

curl helps test APIs from terminal.

Learned:
- testing GET and POST quickly
- no browser required
- useful for automation
- faster debugging

Now I can test endpoints without UI.

---

##  Automated Testing Scripts

Instead of manual testing:

- created bash scripts
- automated repeated tests
- saved time

This improves:
- productivity
- reliability
- faster development

---

##  Environment Variables & Secrets

Learned not to hardcode keys.

Used:
- .env file
- python-dotenv

Benefits:
- secure
- hidden credentials
- safer deployment

Important for:
- API keys
- tokens
- passwords

---

##  Docker Basics

Docker packages the app into a container.

Learned:
- writing Dockerfile
- installing dependencies
- running uvicorn inside container
- building images
- running containers

Benefits:
- works same everywhere
- no dependency issues
- easy deployment

Very useful for production systems.

---

##  Deployment Concepts

Learned:
- hosting API online
- making public URLs
- preparing project for evaluation
- submitting deployed links

Understood:
Local → Docker → Cloud → Public API

This is real-world backend workflow.

---

#  Skills Gained

After this session, I can:

-Build a FastAPI server  
-Create GET/POST endpoints  
 -Use path & query parameters  
 -Validate data using Pydantic  
 -Upload files  
 -Test APIs using curl  
 -Automate testing  
 -Use environment variables  
 -Dockerize application  
 -Deploy backend online  

---

#  Challenges Faced

- Understanding request vs response flow
- Debugging POST JSON format
- File upload syntax
- Writing Dockerfile correctly
- Deployment errors initially

Solved by:
- testing step-by-step
- using curl
- checking logs

---

#  Real-World Importance

These skills are used in:

- backend development
- web applications
- microservices
- AI/ML APIs
- cloud deployment
- DevOps workflows

FastAPI + Docker is widely used in startups and production systems.

---

#  Personal Takeaway

This session helped me move from:

❌ only writing Python scripts  
to  
✅ building real deployable backend services  

Now I understand how an API goes from:
code → server → testing → container → cloud → public

This is a complete development lifecycle.

---

## Learnings Completed 🎉
