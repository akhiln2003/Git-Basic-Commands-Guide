# Git Basic Commands Guide

This guide provides an overview of the most commonly used Git commands for version control. It's a great reference for beginners and intermediate developers.

## Table of Contents

1. [Setting Up Git](#setting-up-git)
2. [Creating and Cloning Repositories](#creating-and-cloning-repositories)
3. [Committing Changes](#committing-changes)
4. [Working with Branches](#working-with-branches)
5. [Pushing and Pulling Changes](#pushing-and-pulling-changes)
6. [Viewing Changes](#viewing-changes)
7. [Git Remotes](#git-remotes)
8. [Advanced Git Commands](#advanced-git-commands)
9. [Git Best Practices](#git-best-practices)
10. [Troubleshooting](#troubleshooting)

---

## Setting Up Git

Before using Git, configure your username and email:

```bash
# Set your username
git config --global user.name "Your Name"

# Set your email
git config --global user.email "youremail@example.com"

# Check your configuration
git config --list

# Set default branch name
git config --global init.defaultBranch main
```

## Creating and Cloning Repositories

```bash
# Initialize a new repository
git init

# Clone an existing repository
git clone https://github.com/username/repository.git

# Clone a specific branch
git clone -b branch-name https://github.com/username/repository.git

# Clone to a specific directory
git clone https://github.com/username/repository.git directory-name
```

## Committing Changes

```bash
# Check status of working directory
git status

# Add files to staging area
git add filename.txt    # Add specific file
git add .              # Add all files
git add *.js          # Add all JavaScript files

# Commit changes
git commit -m "Your commit message"

# Add and commit in one command
git commit -am "Your commit message"

# Amend last commit
git commit --amend -m "New commit message"
```

## Working with Branches

```bash
# List all branches
git branch            # Local branches
git branch -a         # All branches including remote
git branch -r         # Remote branches only

# Create new branch
git branch branch-name

# Switch to branch
git checkout branch-name
git switch branch-name    # New Git syntax

# Create and switch to new branch
git checkout -b branch-name
git switch -c branch-name # New Git syntax

# Delete branch
git branch -d branch-name  # Safe delete
git branch -D branch-name  # Force delete

# Merge branch
git merge branch-name
```

## Pushing and Pulling Changes

```bash
# Push changes
git push origin branch-name
git push -u origin branch-name  # Set upstream branch

# Pull changes
git pull origin branch-name

# Fetch changes
git fetch origin
git fetch --all

# Update forked repository
git remote add upstream https://github.com/original/repository.git
git fetch upstream
git merge upstream/main
```

## Viewing Changes

```bash
# View commit history
git log
git log --oneline
git log --graph --oneline --decorate

# View changes in working directory
git diff
git diff --staged  # View staged changes

# View specific commit
git show commit-hash

# View file history
git blame filename
```

## Git Remotes

```bash
# List remotes
git remote -v

# Add remote
git remote add origin https://github.com/username/repository.git

# Change remote URL
git remote set-url origin https://github.com/username/new-repository.git

# Remove remote
git remote remove origin
```

## Advanced Git Commands

```bash
# Stash changes
git stash
git stash pop
git stash list
git stash drop

# Reset commits
git reset --soft HEAD~1    # Undo last commit, keep changes
git reset --hard HEAD~1    # Undo last commit, discard changes

# Rebase
git rebase main
git rebase -i HEAD~3      # Interactive rebase

# Cherry-pick
git cherry-pick commit-hash
```

## Git Best Practices

1. **Commit Messages**
   - Use present tense ("Add feature" not "Added feature")
   - Be descriptive but concise
   - Start with a capital letter
   - Keep under 50 characters for the subject line

2. **Branching Strategy**
   ```bash
   main        # Production-ready code
   ├── develop # Development branch
   ├── feature/# Feature branches
   ├── hotfix/ # Urgent fixes
   └── release/# Release preparation
   ```

3. **Regular Updates**
   ```bash
   git fetch origin
   git rebase origin/main
   ```

## Troubleshooting

### Common Issues and Solutions

1. **Merge Conflicts**
   ```bash
   # Abort merge
   git merge --abort

   # Resolve conflicts manually, then
   git add .
   git commit -m "Resolve merge conflicts"
   ```

2. **Wrong Branch**
   ```bash
   # Save changes
   git stash
   
   # Switch branch
   git checkout correct-branch
   
   # Apply changes
   git stash pop
   ```

3. **Undo Last Commit**
   ```bash
   # Keep changes
   git reset --soft HEAD~1
   
   # Discard changes
   git reset --hard HEAD~1
   ```

### Essential .gitignore Contents
```plaintext
# Dependencies
node_modules/
vendor/

# Environment files
.env
.env.local

# Build output
dist/
build/

# IDE files
.vscode/
.idea/

# System files
.DS_Store
Thumbs.db

# Logs
*.log
```

## Additional Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com)
- [Interactive Git Learning](https://learngitbranching.js.org/)
- [Pro Git Book](https://git-scm.com/book/en/v2)

---

*Remember to always verify your current branch and status before making important changes!*