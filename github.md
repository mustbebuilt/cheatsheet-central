# Git & GitHub Cheat Sheet — VS Code

A quick reference for the most common Git commands when using **Visual Studio Code**.

## 1. Check Git is installed

```bash
git --version
```

## 2. Set your Git identity

Set these once on your computer:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Check your settings:

```bash
git config --global --list
```

---

## 3. Create or open a Git repository

### Create a new repository

In the VS Code terminal:

```bash
git init
```

### Clone an existing GitHub repository

```bash
git clone https://github.com/username/repository.git
```

Then open the folder in VS Code.

---

## 4. Check what has changed

```bash
git status
```

Shows modified, new and deleted files.

---

## 5. Add files to the staging area

### Add one file

```bash
git add filename
```

### Add all changes

```bash
git add .
```

---

## 6. Commit your changes

```bash
git commit -m "Describe what you changed"
```

Example:

```bash
git commit -m "Add student registration form"
```

---

## 7. Send changes to GitHub

```bash
git push
```

For the first push of a new branch:

```bash
git push -u origin main
```

---

## 8. Get changes from GitHub

```bash
git pull
```

Usually use this **before starting work** if other people may have changed the repository.

---

## 9. See your commit history

```bash
git log
```

Shorter version:

```bash
git log --oneline
```

---

## 10. Work with branches

### See branches

```bash
git branch
```

### Create a branch

```bash
git branch feature-name
```

### Switch to a branch

```bash
git switch feature-name
```

### Create and switch in one command

```bash
git switch -c feature-name
```

### Push a new branch to GitHub

```bash
git push -u origin feature-name
```

### Switch back to main

```bash
git switch main
```

---

## 11. Connect a local repository to GitHub

Check existing remote:

```bash
git remote -v
```

Add a GitHub repository:

```bash
git remote add origin https://github.com/username/repository.git
```

---

## 12. The everyday workflow

For most VS Code projects, the basic cycle is:

```text
EDIT FILES
    ↓
git status
    ↓
git add .
    ↓
git commit -m "Describe changes"
    ↓
git push
```

If working with others:

```text
git pull
    ↓
EDIT FILES
    ↓
git add .
    ↓
git commit -m "Describe changes"
    ↓
git push
```

---

## 13. Useful VS Code tip

You **don't have to type all of these commands**.

VS Code's **Source Control** panel provides buttons for:

- View changes
- Stage files
- Commit
- Push
- Pull
- Create/switch branches

However, understanding the commands is useful because the VS Code interface is essentially providing a graphical front end to Git.

### ⭐ The five commands to remember

```bash
git status
git add .
git commit -m "message"
git pull
git push
```

**Think:**
**Check → Add → Commit → Pull/Push**
