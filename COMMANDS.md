# Exam Command History / Evidence

This folder contains a prepared Git history matching the practical exam workflow.
The actual `git log --graph --all` and branch history are stored in the `.git` directory.

## Stage I — Local repository and GitHub
```bash
git init
git add .
git commit -m "Initial commit: setup project structure"
git branch -M main
git remote add origin <YOUR_GITHUB_REPOSITORY_URL>
git push -u origin main
```

## Stage II — Branch and merge
```bash
git checkout -b feature-header
git add index.html
git commit -m "Add header component to index.html"
git push -u origin feature-header
git checkout main
git merge feature-header
git push origin main
```

## Stage III — Conflict creation and resolution
```bash
git checkout -b nav-feature
git commit -am "Add primary navigation menu"
git checkout main
git checkout -b nav-alt
git commit -am "Add alternative navigation menu"
git checkout main
git merge nav-feature
git merge nav-alt
# CONFLICT (content): Merge conflict in index.html
# Markers: <<<<<<< HEAD, =======, >>>>>>> nav-alt
git add index.html
git commit -m "Resolve merge conflict between nav-feature and nav-alt"
git push origin main
```

## Before GitHub upload
Create a **Public** GitHub repository named `examproject` without README, .gitignore, or license, then run:
```bash
git remote add origin <YOUR_GITHUB_REPOSITORY_URL>
git push -u origin main
git push -u origin feature-header
git push -u origin nav-feature
git push -u origin nav-alt
```
