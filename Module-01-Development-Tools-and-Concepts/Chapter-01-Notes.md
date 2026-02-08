# 📘 Chapter 1 – Foundation  
## Week 1 – Session 1  
## Installing WSL with Ubuntu on Windows

In this session, we set up a Linux environment on Windows using Windows Subsystem for Linux (WSL) and install the Ubuntu distribution.

---

## Step 1: Turn on Required Windows Features

Open the Control Panel and navigate to:

```text
Programs → Turn Windows features on or off
```

From the list, enable:

- Virtual Machine Platform  
- Windows Hypervisor Platform  
- Windows Subsystem for Linux  

Apply the changes and restart your system.

---

## Step 2: Install WSL

After the system reboots, open PowerShell with administrator privileges and execute:

```powershell
wsl --install
```

This command downloads and configures WSL automatically.

---

## Step 3: Confirm WSL Installation

To make sure WSL is installed correctly, run:

```powershell
wsl --version
```

If the version details are displayed, the installation was successful.

---

## Step 4: Check Available Linux Distributions

To view the list of Linux distributions that can be installed:

```powershell
wsl --list --online
```

---

## Step 5: Install Ubuntu (LTS Release)

Install the latest Ubuntu LTS version using:

```powershell
wsl --install ubuntu-24.04
```

Wait until the download and setup process completes.

---

## Step 6: Set Up User Account

When Ubuntu launches for the first time, create your login credentials:

- Enter a username  
- Set a password  
- Confirm the password  

These credentials will be used for future Linux sessions.

---

## Step 7: Launch Ubuntu

Ubuntu can now be accessed anytime using:

```powershell
wsl
```

or by opening:

```text
Start Menu → Ubuntu
```

---

## ✅ Session 1 Completed
