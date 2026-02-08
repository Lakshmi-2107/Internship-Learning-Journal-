# 🛠️ Hands-On Practice

## Chapter 1 – WSL & Ubuntu Setup

In this session, I practically installed and tested WSL and Ubuntu.

---

## Commands Executed

Checked WSL version:

```powershell
wsl --version
```

Installed WSL:

```powershell
wsl --install
```

Listed distributions:

```powershell
wsl --list --online
```

Installed Ubuntu:

```powershell
wsl --install ubuntu-24.04
```

Started Ubuntu:

```powershell
wsl
```

Updated packages inside Ubuntu:

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Result

- WSL installed successfully
- Ubuntu launched correctly
- Linux terminal working inside Windows


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


