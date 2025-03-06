# Git for DevOps

## Introduction
Git is an essential tool for DevOps engineers. It helps in version control, collaboration, and automation of CI/CD pipelines. This README covers the basics of Git, including branches, branch creation, switching, merging, configurations, and ignoring files.

---

## Git Basics
### 1. Installing Git
Make sure Git is installed on your system:
```sh
git --version
```
If not installed, follow the instructions at: [Git Downloads](https://git-scm.com/downloads)

### 2. Configuring Git
Set up your username and email:
```sh
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
Check your configurations:
```sh
git config --list
```

---

## Git Branching
### 1. Creating a Branch
```sh
git branch feature-branch
```
Or create and switch to a new branch:
```sh
git checkout -b feature-branch
```

### 2. Switching Between Branches
```sh
git checkout main
```
Or use the newer command:
```sh
git switch main
```

### 3. Listing Branches
```sh
git branch
```

---

## Merging Branches
### 1. Merge a Branch into Main
```sh
git checkout main
git merge feature-branch
```
Or using `switch`:
```sh
git switch main
git merge feature-branch
```
If there are conflicts, resolve them and then:
```sh
git add .
git commit -m "Resolved merge conflicts"
```

---

## Ignoring Files
### 1. Creating a `.gitignore` File
Add unnecessary files or folders inside `.gitignore`:
```
node_modules/
.env
.DS_Store
*.log
```
Then commit the `.gitignore` file:
```sh
git add .gitignore
git commit -m "Added gitignore"
```

---

## Staging and Committing Changes
### 1. Adding Files to Staging
```sh
git add filename
```
Or add all files:
```sh
git add .
```

### 2. Committing Changes
```sh
git commit -m "Your commit message"
```

---

## Pushing to Remote Repository
### 1. Adding a Remote Repository
```sh
git remote add origin https://github.com/yourusername/repository.git
```

### 2. Pushing Changes
```sh
git push -u origin main
```

---

## Pulling Changes
### 1. Fetch and Merge Latest Changes
```sh
git pull origin main
```

---

