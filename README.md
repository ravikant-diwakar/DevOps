# DevOps

<img width="2892" height="7400" alt="DevOps" src="https://github.com/user-attachments/assets/c88eb0db-f41e-40a7-b676-11cccacdd442" />

# Git Commands Cheat Sheet 📚

A comprehensive reference guide for Git version control system commands. Perfect for developers of all levels - from beginners learning the basics to experienced developers looking for quick reference.

## 🚀 Quick Start

This cheat sheet covers all essential Git commands organized by category. Click on any section below to expand and view the commands.

---

## 📋 Table of Contents

- [Setup & Configuration](#setup--configuration)
- [Getting & Creating Projects](#getting--creating-projects)
- [Basic Snapshotting](#basic-snapshotting)
- [Undoing Changes](#undoing-changes)
- [Branching & Merging](#branching--merging)
- [Collaboration](#collaboration)
- [Inspection & Comparison](#inspection--comparison)
- [Stashing & Cleaning](#stashing--cleaning)
- [Tags & Releases](#tags--releases)
- [Advanced Manipulation](#advanced-manipulation)
- [Useful References](#useful-references)

---

## Setup & Configuration

<details>
<summary>Click to expand Setup & Configuration commands</summary>

### Initial Git Configuration
Configure your Git environment with your identity and preferences.

```bash
# Set username globally for commits
git config --global user.name "Your Name"

# Set email globally for commits  
git config --global user.email "your@email.com"

# View current configuration settings
git config --global --list
```

### Additional Configuration Tips
- Use `--global` flag to set configuration for all repositories
- Omit `--global` to set configuration for current repository only
- You can also configure default text editor, merge tools, and other preferences

</details>

---

## Getting & Creating Projects

<details>
<summary>Click to expand Getting & Creating Projects commands</summary>

### Starting with Git
Initialize new repositories or clone existing ones.

```bash
# Initialize a local repository in current directory
git init

# Clone a remote repository to your local machine
git clone <repo_url>

# Add a remote repository (typically named 'origin')
git remote add origin <url>
```

### Common Use Cases
- `git init`: Start version control in an existing project
- `git clone`: Download a project from GitHub, GitLab, etc.
- `git remote add origin`: Connect your local repo to a remote repository

</details>

---

## Basic Snapshotting

<details>
<summary>Click to expand Basic Snapshotting commands</summary>

### Working with Files and Commits
Track changes and create snapshots of your project.

```bash
# Check the status of your working directory
git status

# Stage a specific file for commit
git add <filename>

# Stage all changes in current directory
git add .

# Commit staged changes with a message
git commit -m "Your descriptive commit message"

# Edit the last commit message
git commit --amend
```

### Best Practices
- Always check `git status` before committing
- Write clear, descriptive commit messages
- Commit frequently with logical chunks of changes
- Use `git add .` carefully to avoid staging unwanted files

</details>

---

## Undoing Changes

<details>
<summary>Click to expand Undoing Changes commands</summary>

### Reverting and Resetting
Fix mistakes and undo unwanted changes.

```bash
# Discard changes in a specific file (restore from last commit)
git checkout -- <filename>

# Remove a file from repository and working directory
git rm <filename>

# Reset all changes back to last commit (DANGEROUS!)
git reset --hard HEAD

# Create a new commit that undoes a previous commit
git revert <commit_id>
```

### ⚠️ Important Notes
- `git reset --hard HEAD` will permanently delete all uncommitted changes
- `git revert` is safer than `git reset` for shared repositories
- Always double-check before running destructive commands

</details>

---

## Branching & Merging

<details>
<summary>Click to expand Branching & Merging commands</summary>

### Working with Branches
Create parallel development workflows and merge changes.

```bash
# List all local branches (* indicates current branch)
git branch

# Create a new branch
git branch <branchname>

# Delete a local branch
git branch -d <branchname>

# Create and immediately switch to a new branch
git checkout -b <branchname>

# Switch to an existing branch
git checkout <branchname>

# Merge specified branch into current branch
git merge <branchname>

# Delete a remote branch
git push origin --delete <branchname>
```

### Branch Workflow Tips
- Use descriptive branch names (e.g., `feature/user-authentication`)
- Always test your code before merging
- Consider using pull requests for code review

</details>

---

## Collaboration

<details>
<summary>Click to expand Collaboration commands</summary>

### Sharing Your Work
Synchronize changes with remote repositories and team members.

```bash
# Upload committed changes to remote repository
git push

# Push a specific branch to remote repository
git push origin <branchname>

# Fetch and merge changes from remote repository
git pull

# Pull changes from a specific branch
git pull origin <branchname>

# Download new data from remote without merging
git fetch
```

### Collaboration Best Practices
- Always pull before pushing to avoid conflicts
- Use `git fetch` to see remote changes before merging
- Communicate with your team about branch strategies

</details>

---

## Inspection & Comparison

<details>
<summary>Click to expand Inspection & Comparison commands</summary>

### Viewing History and Changes
Examine your project's evolution and compare different states.

```bash
# Show detailed commit history
git log

# Show brief, one-line commit history
git log --oneline

# Show detailed information about a specific commit
git show <commit_id>

# Show changes that haven't been staged yet
git diff

# Compare changes between two branches
git diff <source_branch> <target_branch>
```

### Useful Log Options
- `git log --graph`: Show branch and merge history visually
- `git log --author="Name"`: Filter commits by author
- `git log -n 10`: Show only the last 10 commits

</details>

---

## Stashing & Cleaning

<details>
<summary>Click to expand Stashing & Cleaning commands</summary>

### Temporary Storage and Cleanup
Save work in progress and clean your working directory.

```bash
# Save current changes and clean working directory
git stash

# List all saved stashes
git stash list

# Apply the most recent stash
git stash pop

# Remove all stashed entries
git stash clear

# Remove untracked files from working directory
git clean -f
```

### When to Use Stashing
- Switching branches with uncommitted changes
- Pulling updates while you have work in progress
- Temporarily setting aside incomplete work

</details>

---

## Tags & Releases

<details>
<summary>Click to expand Tags & Releases commands</summary>

### Marking Important Points
Create tags to mark releases and important milestones.

```bash
# Create a lightweight tag on current commit
git tag <tagname>

# Create an annotated tag with message
git tag -a <tagname> -m "Release version 1.0"

# List all tags
git tag -l

# Push tags to remote repository
git push origin <tagname>

# Push all tags to remote
git push origin --tags
```

### Tagging Best Practices
- Use semantic versioning (e.g., v1.2.3)
- Always use annotated tags for releases
- Include meaningful tag messages

</details>

---

## Advanced Manipulation

<details>
<summary>Click to expand Advanced Manipulation commands</summary>

### Power User Commands
Advanced Git operations for complex scenarios.

```bash
# Apply changes from a specific commit to current branch
git cherry-pick <commit>

# Apply commits from one branch onto another
git rebase <branch>

# Find the commit that introduced a bug using binary search
git bisect start
git bisect bad <commit>
git bisect good <commit>

# Show history of HEAD and branch references
git reflog
```

### ⚠️ Advanced Usage Warning
These commands can rewrite history. Use with caution, especially in shared repositories.

</details>

---

## Useful References

<details>
<summary>Click to expand Additional Resources</summary>

### Documentation and Learning Resources

#### Official Documentation
- [Git Official Documentation](https://git-scm.com/doc) - Comprehensive official guide
- [Pro Git Book](https://git-scm.com/book) - Free online book covering Git in depth

#### Quick References
- [Git Cheat Sheet (PDF)](https://education.github.com/git-cheat-sheet-education.pdf) - GitHub's official cheat sheet
- [Interactive Git Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html) - Visual interactive reference

#### Learning Platforms
- [Learn Git Branching](https://learngitbranching.js.org/) - Interactive Git tutorial
- [GitHub Learning Lab](https://lab.github.com/) - Hands-on Git and GitHub courses
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials) - Comprehensive tutorials with examples

#### Video Resources
- [Git & GitHub Crash Course](https://www.youtube.com/watch?v=SWYqp7iY_Tc) - Traversy Media
- [Git Tutorial for Beginners](https://www.youtube.com/watch?v=8JJ101D3knE) - Programming with Mosh

</details>

---

## 📄 Additional Resources

### PDF Downloads
This repository includes two helpful PDF references:
- **Git-Cheat-Sheet.pdf** - Quick reference for all Git commands
- **GitHub-Git-Cheat-Sheet.pdf** - GitHub-specific workflow guide

*Note: PDF files should be uploaded to your repository for users to download*

---

## 🤝 Contributing

Found an error or want to add a command? Feel free to:
1. Fork this repository
2. Make your improvements
3. Submit a pull request

---

## 📝 License

This cheat sheet is provided under MIT License. Feel free to use, modify, and share!

---

## ⭐ Show Your Support

If this cheat sheet helped you, please consider giving it a star! ⭐

---

*Happy Coding! 🚀*
