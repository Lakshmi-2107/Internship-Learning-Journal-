# 📘 Chapter 1 – Foundation
## Week 1 – Session 1
## Installing WSL with Ubuntu on Windows

In this session, we set up a Linux environment on Windows using Windows Subsystem for Linux (WSL) and installed the Ubuntu distribution.

---

## 🔹 Step 1: Turn on Required Windows Features

Open:

Programs → Turn Windows features on or off

Enable:

- Virtual Machine Platform
- Windows Hypervisor Platform
- Windows Subsystem for Linux

Apply changes and restart the system.

---

## 🔹 Step 2: Install WSL (Automatic Method – Recommended)

Open PowerShell as Administrator and run:

```powershell
wsl --install
```

This command:
- Enables required components
- Installs WSL kernel
- Downloads Ubuntu automatically
- Sets default version to WSL 2

Restart if prompted.

---

## 🔹 Step 3: Confirm WSL Installation

```powershell
wsl --version
```

If version details appear, WSL is installed successfully.

---

## 🔹 Step 4: Check Available Linux Distributions

```powershell
wsl --list --online
```

This shows all Linux distributions supported by WSL.

---

## 🔹 Step 5: Install Ubuntu (LTS Release)

```powershell
wsl --install ubuntu-24.04
```

Wait for the installation to complete.

---

## 🔹 Step 6: Manual Installation (Alternative – Used in My System)

If `wsl --install` does not work, install WSL manually:

Download the WSL installer for x64 systems and run:

```powershell
msiexec /package wsl.2.6.3.0.x64.msi
```

After installation, verify:

```powershell
wsl --version
```

---

## 🔹 Step 7: Set Default WSL Version

```powershell
wsl --set-default-version 2
```

---

## 🔹 Step 8: Set Up User Account

When Ubuntu launches for the first time:

- Enter username
- Set password
- Confirm password

These credentials will be used for future sessions.

---

## 🔹 Step 9: Launch Ubuntu

Start Ubuntu using:

```powershell
wsl
```

or

Start Menu → Ubuntu

---

##  Session 1 Completed 🎉
