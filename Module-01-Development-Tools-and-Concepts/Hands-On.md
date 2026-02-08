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


