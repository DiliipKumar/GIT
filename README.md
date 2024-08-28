
---

# **Git Workflow Guide**

## **Table of Contents**
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [Cloning the Repository](#cloning-the-repository)
  - [Navigating to the Project Directory](#navigating-to-the-project-directory)
  - [Initializing a New Git Repository](#initializing-a-new-git-repository)
  - [Adding and Committing Changes](#adding-and-committing-changes)
  - [Setting Up the Remote Repository](#setting-up-the-remote-repository)
  - [Generating a Personal Access Token (PAT)](#generating-a-personal-access-token-pat)
  - [Configuring Git to Use the PAT](#configuring-git-to-use-the-pat)
- [Usage](#usage)
  - [Pushing to a Remote Repository](#pushing-to-a-remote-repository)
  - [Pulling Latest Changes](#pulling-latest-changes)
  - [Creating a New Branch](#creating-a-new-branch)
  - [Merging a Branch](#merging-a-branch)
- [Common Git Commands](#common-git-commands)
  - [Checking the Current Status](#checking-the-current-status)
  - [Viewing Remote Repositories](#viewing-remote-repositories)
  - [Removing a Remote Repository](#removing-a-remote-repository)
  - [Adding a Remote Repository](#adding-a-remote-repository)
  - [Renaming the Default Branch to Main](#renaming-the-default-branch-to-main)
  - [Resetting Changes](#resetting-changes)

---

## **Prerequisites**
Before you begin, make sure you have:
- **Git** installed on your machine.
- A **GitHub account**.
- **Access permissions** to the repository.

## **Installation**

### **1. Cloning the Repository**
To clone a repository, use:
```bash
git clone https://github.com/username/repository.git
```

### **2. Navigating to the Project Directory**
Move into your project directory:
```bash
cd repository
```

### **3. Initializing a New Git Repository**
For a new repository, run:
```bash
git init
```

### **4. Adding and Committing Changes**
Add and commit your changes with:
```bash
git add .
git commit -m "Initial commit"
```

### **5. Setting Up the Remote Repository**
Link your local repository to a remote repository:
```bash
git remote add origin https://github.com/username/repository.git
```

### **6. Generating a Personal Access Token (PAT)**
🔐 **Create a PAT on GitHub:**
1. **Log in** to GitHub and go to **Settings**.
2. Navigate to **Developer settings**.
3. Click **Personal access tokens**, then **Tokens (classic)**.
4. Click **Generate new token**.
5. Provide a **descriptive name**, set an **expiration date**, and select the **required scopes**.
6. Click **Generate token** and **copy** your token immediately.

💡 **Tip:** Keep your PAT secure; it's used as a password for Git operations.

### **7. Configuring Git to Use the PAT**
🛠 **Set Up Your Git Configuration:**

**a. Update Remote URL with PAT:**
For existing repositories, update the remote URL:
```bash
git remote set-url origin https://<username>:<PAT>@github.com/username/repository.git
```

**b. Enable Credential Caching:**
To avoid re-entering your PAT frequently:
```bash
git config --global credential.helper cache
# This caches your credentials temporarily (e.g., 15 minutes).
```
Or store your credentials permanently:
```bash
git config --global credential.helper store
```

---

## **Usage**

### **1. Pushing to a Remote Repository**
Push changes to the `main` branch:
```bash
git push -u origin main
```

### **2. Pulling Latest Changes**
Retrieve the latest updates from the remote repository:
```bash
git pull origin main
```

### **3. Creating a New Branch**
Create and switch to a new branch:
```bash
git checkout -b feature-branch-name
```

### **4. Merging a Branch**
Merge a branch into `main`:
```bash
git checkout main
git merge feature-branch-name
```

---

## **Common Git Commands**

### **1. Checking the Current Status**
```bash
git status
```

### **2. Viewing Remote Repositories**
```bash
git remote -v
```

### **3. Removing a Remote Repository**
```bash
git remote remove origin
```

### **4. Adding a Remote Repository**
```bash
git remote add origin https://github.com/username/repository.git
```

### **5. Renaming the Default Branch to Main**
```bash
git branch -M main
```

### **6. Resetting Changes**
To discard changes in a file before committing:
```bash
git checkout -- filename
```

---

This structured layout makes it easier to navigate through the sections and find the information you need.
