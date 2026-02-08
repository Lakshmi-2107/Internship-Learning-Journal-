# 📘 Session 2 – Week 1
## Linux Usage, WSL Update & Git Workflow

In this session, the goal is to start using the Ubuntu environment installed through WSL, update the system, and learn Git and GitHub workflow for version control.

---

## 🔹 Step 1: Update WSL

```powershell
wsl --update
wsl --version
```

---

## 🔹 Step 2: Start Ubuntu

```powershell
wsl
```

---

## 🔹 Step 3: Practice Basic Linux Commands

Navigation:

```bash
pwd
ls
cd foldername
cd ..
```

File handling:

```bash
mkdir test
touch file.txt
rm file.txt
mv file1 file2
cp file1 file2
```

---

## 🔹 Step 4: Update Ubuntu Packages

```bash
sudo apt update
sudo apt upgrade -y
```

---

## 🔹 Step 5: Install Git

```bash
sudo apt install git
```

Check version:

```bash
git --version
```

---

## 🔹 Step 6: Git Workflow

Initialize repository:

```bash
git init
```

Add files:

```bash
git add .
```

Commit:

```bash
git commit -m "message"
```

Connect remote:

```bash
git remote add origin <repo-url>
```

Push:

```bash
git push -u origin main
```

---

## 🔹 Step 7: Use GitHub

- Create repository
- Push local code
- Backup projects online
- Track changes

---

## ✅ Session 2 Completed 🎉
