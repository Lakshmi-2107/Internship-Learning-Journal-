# 📚 Learnings

## Chapter 1 – WSL & Ubuntu
## Learnings

From this session, I learned how to set up and use Linux inside Windows using Windows Subsystem for Linux (WSL).

---

##  What I Learned

- What WSL is and why it is used
- How Linux runs inside Windows without a virtual machine
- Difference between WSL and Virtual Machine
- How to install Ubuntu on WSL
- How to work in the Linux terminal
- How to troubleshoot WSL installation issues

---

##  New Commands Learned

```powershell
wsl --version
wsl --list --online
wsl --set-default-version 2
wsl
```

```bash
sudo apt update
sudo apt upgrade -y
```

---

##  Practical Understanding

- Enabled Windows features required for WSL
- Installed WSL manually using MSI installer
- Verified WSL installation
- Installed Ubuntu distribution
- Created Linux username and password
- Opened Ubuntu using terminal
- Updated Linux packages

---

##  Skills Gained

- Installed and configured WSL successfully
- Used Ubuntu inside Windows
- Navigated Linux terminal
- Managed packages using apt
- Set up a basic Linux development environment

---

##  Conclusion

Now I can comfortably use Ubuntu inside Windows for development and practice Linux commands without using a virtual machine or dual boot setup.



## Chapter 2 – Development Environment Setup

In this session, I learned how to work inside the Ubuntu environment installed using WSL and how to manage projects using Git and GitHub.

---

##  Concepts Learned

- What WSL update is and why it is important
- How Ubuntu runs inside Windows
- Difference between Linux terminal and Windows command prompt
- Importance of version control using Git

---

##  Linux Skills Learned

- Navigating directories using cd, ls, pwd
- Creating folders and files
- Copying, moving, and deleting files
- Updating packages using apt

---

##  Git Skills Learned

- Initializing a repository using git init
- Adding files using git add
- Saving changes using git commit
- Connecting local repo to GitHub
- Uploading code using git push

---

##  Practical Understanding

- How to open Ubuntu using WSL
- How to maintain and update the system
- How Git tracks project changes
- How GitHub stores projects online

---

##  Outcome

Now I am comfortable:
- Working in the Linux terminal
- Managing files using commands
- Using Git for version control
- Pushing projects to GitHub

This setup will help me in future development and internship tasks.

---

## Chapter 3 – Week 1 – Session 3
## WSL Internals, Linux File System & UV/LLM Tools

In this session, I gained a deeper understanding of how Linux works inside Windows using WSL and learned how to use terminal-based tools for development and AI interaction.

---

## 🔹 Concepts Learned

- How the computer boot process works (BIOS/UEFI → OS loading)
- What a hypervisor is and how it manages hardware resources
- How WSL runs Linux inside Windows without a virtual machine
- Difference between WSL and traditional virtual machines
- Basic structure of the Linux file system

---

## 🔹 Linux Knowledge Gained

- Root directory structure (/)
- Important folders like /home, /mnt, /bin, /etc
- Difference between absolute and relative paths
- Difference between Linux (/) and Windows (\) paths
- How Windows drives are mounted inside WSL

---

## 🔹 Terminal Skills Learned

- Navigating folders using commands
- Managing files and directories
- Clearing terminal
- Working fully from command line

---

## 🔹 Development Skills Learned

- Using VS Code with WSL
- Opening projects directly from terminal
- Installing Python-based tools
- Managing packages using UV
- Using command-line automation tools

---

## 🔹 AI Tool Knowledge

- Installing LLM CLI tool
- Setting API keys securely
- Connecting to Gemini and GPT models
- Running AI queries directly from terminal
- Understanding practical use of AI in development workflow

---

## 🔹 Outcome

Now I am comfortable:
- Working inside Ubuntu (WSL)
- Navigating Linux file systems
- Integrating VS Code with Linux
- Installing and managing tools from terminal
- Using AI models from command line for productivity

This session improved my confidence in Linux usage and automation-based development.

---

## Chapter 4 – Week 1 – Session 4

This session helped me understand how to set up a professional development environment on Windows using WSL and command-line tools.

---

## Concepts Learned

- Importance of Linux environment for development
- Using WSL to run Ubuntu inside Windows
- Role of package managers (apt, winget)
- Python version management using pyenv
- Dependency management using UV
- Git workflow and repository management
- Using AI tools directly from terminal

---

## Skills Gained

- Installed and configured VS Code with WSL
- Managed Python versions using pyenv
- Created isolated Python projects using UV
- Installed and removed packages easily
- Used GitHub CLI to create and manage repositories
- Set environment variables for API keys
- Ran AI models using LLM CLI
- Performed most tasks using terminal instead of GUI

---

## Outcome

Now I can:

- Work comfortably inside Ubuntu (WSL)
- Manage Python projects efficiently
- Use Git and GitHub from terminal
- Install tools using command line
- Use AI models for development tasks
- Build and manage projects in a professional workflow

This setup improves productivity and prepares me for real-world development work.

---


## Chapter 5 – Week 1 – Session 5

This session helped me understand Git and GitHub practically and how version control is used in real projects.

---

## Concepts Learned

- What version control is
- Difference between Git and GitHub
- Local vs remote repositories
- SSH authentication
- Cloning repositories
- Git commit workflow
- Common Git errors and fixes
- Importance of Linux/WSL for development
- Role of GitHub Copilot

---

## Skills Gained

- Installed Git successfully
- Generated and configured SSH keys
- Connected local machine to GitHub securely
- Cloned repositories
- Added, committed, and pushed changes
- Managed projects using Git commands
- Troubleshot permission errors
- Used Copilot for faster coding

---

## Outcome

Now I can:

- Use Git confidently
- Manage repositories from terminal
- Push and pull code from GitHub
- Collaborate with others
- Track project history
- Maintain clean version control workflow

This session improved my development workflow and prepared me for real-world collaboration.

---


## Chapter 4  – Session 4
## FastAPI Workflow, Testing & Deployment Reflections

This session focused on understanding how to design, build, test, secure, and deploy a complete backend API using FastAPI.  
Instead of only learning theory, we practiced building a real server and preparing it for production deployment.

---

# 🔹 Core Concepts Learned

## ✅ FastAPI Basics

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

## ✅ GET Requests

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

## ✅ Path Parameters

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

## ✅ Query Parameters

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

## ✅ Pydantic Validation

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

## ✅ POST Requests

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

## ✅ File Uploads

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

## ✅ API Testing with curl

curl helps test APIs from terminal.

Learned:
- testing GET and POST quickly
- no browser required
- useful for automation
- faster debugging

Now I can test endpoints without UI.

---

## ✅ Automated Testing Scripts

Instead of manual testing:

- created bash scripts
- automated repeated tests
- saved time

This improves:
- productivity
- reliability
- faster development

---

## ✅ Environment Variables & Secrets

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

## ✅ Docker Basics

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

## ✅ Deployment Concepts

Learned:
- hosting API online
- making public URLs
- preparing project for evaluation
- submitting deployed links

Understood:
Local → Docker → Cloud → Public API

This is real-world backend workflow.

---

# 🔹 Skills Gained

After this session, I can:

✅ Build a FastAPI server  
✅ Create GET/POST endpoints  
✅ Use path & query parameters  
✅ Validate data using Pydantic  
✅ Upload files  
✅ Test APIs using curl  
✅ Automate testing  
✅ Use environment variables  
✅ Dockerize application  
✅ Deploy backend online  

---

# 🔹 Challenges Faced

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

# 🔹 Real-World Importance

These skills are used in:

- backend development
- web applications
- microservices
- AI/ML APIs
- cloud deployment
- DevOps workflows

FastAPI + Docker is widely used in startups and production systems.

---

# 🔹 Personal Takeaway

This session helped me move from:

❌ only writing Python scripts  
to  
✅ building real deployable backend services  

Now I understand how an API goes from:
code → server → testing → container → cloud → public

This is a complete development lifecycle.

---

## Learnings Completed 🎉





