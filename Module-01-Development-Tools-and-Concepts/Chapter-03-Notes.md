# 📘 Chapter 3 – System Fundamentals & AI Tools
## Week 1 – Session 3
## Boot Process, WSL Internals, Linux File System & UV/LLM Setup

In this session, we studied how operating systems boot, how WSL works internally using hypervisors, how to navigate the Linux file system, and how to install automation tools like UV and LLM to interact with AI models such as Gemini and GPT from the terminal.

---

# 🔹 1. Boot Process Overview

When a computer starts:

1. BIOS/UEFI performs hardware checks
2. Looks for bootable drives (HDD/SSD)
3. Finds EFI partition
4. Loads operating system
5. Windows/Linux starts

Key points:
- Each OS has its own bootloader
- Multiple OS → dual boot possible
- WSL runs Linux inside Windows without dual boot

---

# 🔹 2. Understanding Hypervisors

A hypervisor is software that manages hardware resources for virtual systems.

Functions:
- Allocates CPU
- Allocates memory
- Allocates storage
- Runs multiple OS environments

Used in:
- WSL (Hyper-V)
- Cloud platforms (AWS, Azure)

Benefits:
- Near-native performance
- Faster than VirtualBox
- Efficient resource sharing

---

# 🔹 3. Windows Subsystem for Linux (WSL)

WSL allows running Linux inside Windows.

Advantages:
- No dual boot required
- Lightweight
- Faster startup
- Direct hardware access
- Easy Windows ↔ Linux integration

Start WSL:

```powershell
wsl
```

---

# 🔹 4. Linux File System Structure

Linux starts at root directory:

```
/
```

Common directories:

- /home → user folders
- /mnt → mounted drives
- /bin → system binaries
- /etc → configurations
- /var → logs

Home directory:

```
/home/username
```

Shortcut:

```
~
```

---

# 🔹 5. Access Windows Files in WSL

Windows drives are mounted inside:

```
/mnt/c
/mnt/d
```

Example:

```bash
cd /mnt/c/Users
```

So:

```
C:\Users
```

becomes:

```
/mnt/c/Users
```

---

# 🔹 6. Basic Linux Commands

Navigation:

```bash
pwd
ls
cd
clear
```

Special symbols:

```
.   → current directory
..  → parent directory
```

Paths:
- Absolute → start with /
- Relative → start from current folder

Linux uses:
```
/
```

Windows uses:
```
\
```

---

# 🔹 7. VS Code with WSL

Open project directly:

```bash
code .
```

Benefits:
- Linux terminal inside VS Code
- Easy development
- Integrated workflow

---

# 🔹 8. Installing UV Tool

UV is a Python automation and package management tool.

Install:

```bash
pip install uv
```

Check:

```bash
uv --version
```

---

# 🔹 9. Installing LLM Tool

LLM CLI allows interacting with AI models from terminal.

Install:

```bash
uv tool install llm
```

Uninstall:

```bash
uv tool uninstall llm
```

---

# 🔹 10. Setting API Keys

Gemini (Google AI Studio):

```bash
llm key set gemini
```

OpenAI / GPT:

```bash
llm key set openai
```

Keys stored in:

```
~/.bashrc or ~/.zshrc
```

---

# 🔹 11. Running AI Models from Terminal

Examples:

```bash
llm "Explain Linux commands"
llm -m gemini-2.5 "Who are you?"
llm -m gpt-4 "Summarize this text"
```

Use cases:
- Ask questions
- Generate code
- Automate tasks
- Summarize text

---

# 🔹 Objectives of this Session

- Understand boot process
- Learn hypervisors
- Navigate Linux file system
- Use WSL effectively
- Integrate VS Code
- Install UV and LLM tools
- Use AI models from terminal

---

##  Session 3 Completed 🎉
