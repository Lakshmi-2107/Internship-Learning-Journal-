# 🛠️ Hands-On Practice
## Chapter 1 – Week 1 – Session 1
## WSL & Ubuntu Setup

In this session, I practically installed WSL, configured Ubuntu, and verified that the Linux environment works correctly inside Windows.

---

##  Checked WSL availability

```powershell
wsl --version
```

Initially, the command was not recognized.

---

##  Installed WSL manually using MSI

```powershell
msiexec /package wsl.2.6.3.0.x64.msi
```

This installed the WSL engine successfully.

---

##  Verified WSL installation

```powershell
wsl --version
```

WSL version details were displayed.

---

##  Set default version to WSL 2

```powershell
wsl --set-default-version 2
```

---

##  Listed available distributions

```powershell
wsl --list --online
```

Viewed all supported Linux distributions.

---

##  Installed Ubuntu

```powershell
wsl --install ubuntu-24.04
```

Ubuntu downloaded and installed successfully.

---

##  Started Ubuntu

```powershell
wsl
```

Ubuntu terminal opened and asked to create username and password.

---

##  Updated Ubuntu packages

```bash
sudo apt update
sudo apt upgrade -y
```

System packages updated successfully.

---

##  Result

- WSL installed successfully
- Ubuntu installed and configured
- Linux terminal running inside Windows
- Ready to use for development



## Chapter 2 – Development Environment Setup

In this session, I practically worked with WSL, Ubuntu, and Git commands to get comfortable using the Linux environment and version control.

---

##  Updated WSL

```powershell
wsl --update
wsl --version
```

WSL was updated successfully and the latest version was verified.

---

##  Started Ubuntu

```powershell
wsl
```

Ubuntu terminal opened correctly.

---

##  Practiced Linux Navigation Commands

```bash
pwd
ls
mkdir demo
cd demo
```

Created and navigated into folders.

---

##  Created and Managed Files

```bash
touch test.txt
cp test.txt copy.txt
mv copy.txt new.txt
rm new.txt
```

Tested file creation, copy, move, and delete operations.

---

##  Updated Ubuntu Packages

```bash
sudo apt update
sudo apt upgrade -y
```

System packages were updated successfully.

---

##  Installed Git

```bash
sudo apt install git
git --version
```

Git installed and verified.

---

##  Practiced Git Workflow

```bash
git init
git add .
git commit -m "first commit"
git remote add origin <repo-url>
git push -u origin main
```

Initialized repository and pushed code to GitHub.

---

## Result

- WSL updated successfully  
- Ubuntu running properly  
- Linux commands executed  
- Git installed and configured  
- Project uploaded to GitHub  

---

## Chapter 3 – Week 1 – Session 3
## WSL Internals, Linux File System & UV/LLM Tools

In this session, I practically explored the Linux environment inside WSL, navigated the file system, accessed Windows files, integrated VS Code, and installed UV and LLM tools to interact with AI models from the terminal.

---

##  Opened Ubuntu using WSL

```powershell
wsl
```

Ubuntu terminal launched successfully.

---

##  Checked current directory

```bash
pwd
```

Verified the current working location.

---

##  Listed files and folders

```bash
ls
```

Viewed directory contents.

---

##  Navigated directories

```bash
cd ~
cd ..
cd /mnt/c
```

- Accessed home folder  
- Moved to parent directory  
- Opened Windows C drive  

---

##  Explored Linux file structure

```bash
cd /
ls
```

Observed directories like `/home`, `/mnt`, `/bin`, `/etc`.

---

##  Cleared terminal

```bash
clear
```

---

##  Opened project in VS Code

```bash
code .
```

VS Code opened with WSL terminal integration.

---

##  Installed UV tool

```bash
pip install uv
uv --version
```

Verified installation.

---

##  Installed LLM tool

```bash
uv tool install llm
```

Successfully installed CLI tool.

---

##  Configured API keys

```bash
llm key set gemini
llm key set openai
```

Added API keys for model access.

---

##  Tested LLM commands

```bash
llm "Hello"
llm -m gemini-2.5 "Explain WSL"
llm -m gpt-4 "What is Linux?"
```

Received responses from AI models.

---

##  Result

- Navigated Linux directories confidently
- Accessed Windows files through `/mnt`
- Used VS Code with WSL
- Installed UV and LLM tools
- Connected Gemini and GPT models
- Ran AI commands directly from terminal



## Chapter 4 – Week 1 – Session 4

In this session, I set up my complete development environment on Windows using WSL (Ubuntu). I installed the required tools and configured Python, Git, UV, and LLM CLI for project development and automation.

---

## Tasks Performed

- Opened Ubuntu using WSL
- Installed VS Code on Windows
- Connected VS Code with WSL terminal
- Installed Python and pip inside Ubuntu
- Installed pyenv for Python version management
- Installed UV for project management
- Initialized a new project using uv init
- Added and removed Python packages
- Installed GitHub CLI
- Created repository from terminal
- Installed LLM CLI tool
- Configured API keys
- Tested AI prompts from terminal

---

## Commands Practiced

Started WSL:
wsl

Initialize project:
uv init

Add package:
uv add flask

Remove package:
uv remove flask

Git workflow:
git add .
git commit -m "first commit"
gh repo create

Run LLM:
llm "Hello"

---

## Result

- Development environment ready inside WSL
- Python versions managed properly
- Dependencies handled using UV
- GitHub repositories managed from terminal
- AI tools working from command line

