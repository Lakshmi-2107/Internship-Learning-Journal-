📘 Chapter 1 – Foundation
🖥️ Week 1 – Session 1: WSL (Ubuntu) Installation Guide

This session covers installing Windows Subsystem for Linux (WSL) and setting up Ubuntu 24.04 LTS on Windows.

✅ Method 1 — Automatic Installation (Recommended & Easiest)
Step 1 — Open PowerShell as Administrator

Press:
```
Win + X → Windows Terminal (Admin)
``
Step 2 — Run WSL Install Command
```
wsl --install
```

This command automatically:

Enables required Windows features

Installs WSL

Installs Ubuntu

Sets WSL 2 as default

Step 3 — Restart PC

After installation, restart your system.

Step 4 — Create Linux User

When Ubuntu opens:
```
Enter new UNIX username: Lakshmi
Enter password:
Confirm password:
```
Step 5 — Verify Installation

Run:
```
wsl --version
```
Step 6 — Start Ubuntu

You can launch Ubuntu using:
```
Start Menu → Ubuntu
```
OR
```
wsl
```

🎉 Setup Complete!

✅ Method 2 — Manual Installation (Alternate Way)

Use this method if automatic installation fails.

Step 1 — Enable Windows Features

Open:
```
Control Panel → Programs → Turn Windows features on or off
```

Enable:

✔ Virtual Machine Platform

✔ Windows Hypervisor Platform

✔ Windows Subsystem for Linux

Click OK and restart PC.

Step 2 — Install WSL

Open PowerShell (Admin):
```
wsl --set-default-version 2
```
Step 3 — Check Available Distributions
```
wsl --list --online
```
Step 4 — Install Ubuntu 24.04 (LTS)
```
wsl --install ubuntu-24.04
```

Step 5 — Verify
```
wsl --version
```
🔧 Useful Commands
List installed distributions
```
wsl -l -v
```

Start Ubuntu
```
wsl
```
Shutdown WSL
```
wsl --shutdown
```

Update Ubuntu packages
```
sudo apt update && sudo apt upgrade
```


✅ Session 1 Completed 🎉