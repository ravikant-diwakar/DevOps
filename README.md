# DevOps

<img width="2892" height="7400" alt="DevOps" src="https://github.com/user-attachments/assets/c88eb0db-f41e-40a7-b676-11cccacdd442" />


Here’s a well-structured `README.md` content for your Git cheat sheet, designed for a GitHub repository. It uses collapsible sections (`<details>`) so that clicking on "Git Commands Cheatsheet" expands the full content. Also includes placeholders for your PDF links at the bottom.

---

````markdown
# Git Commands Cheatsheet

This cheat sheet provides a quick reference to commonly used Git commands for setup, collaboration, version control, and more.

<details>
<summary><strong>Click to Expand Git Command Cheatsheet 📘</strong></summary>

---

## 🛠️ Setup & Configuration

```bash
git config --global user.name "Your Name"          # Set username globally for commits
git config --global user.email "your@email.com"    # Set email globally for commits
git config --global --list                         # View current config
````

---

## 📦 Getting & Creating Projects

```bash
git init                             # Initialize a local repository
git clone <repo_url>                # Clone a remote repository
git remote add origin <url>         # Add a remote (GitHub, etc.)
```

---

## 📝 Basic Snapshotting

```bash
git status                          # List files to be committed
git add <filename>                  # Stage a file for commit
git add .                           # Stage all files
git commit -m "Your message"        # Commit staged changes
git commit --amend                  # Edit last commit message
```

---

## ↩️ Undoing Changes

```bash
git checkout -- <filename>          # Discard changes in a file
git rm <filename>                   # Remove file from repo
git reset --hard HEAD               # Reset all changes back to last commit
git revert <commit_id>              # Make a new commit that undoes a previous one
```

---

## 🌿 Branching & Merging

```bash
git branch                          # List all branches
git branch <branchname>             # Create a new branch
git branch -d <branchname>          # Delete a branch
git checkout -b <branchname>        # Create and switch to a new branch
git checkout <branchname>           # Switch branches
git merge <branchname>              # Merge branch into current branch
git push origin --delete <branchname> # Delete a remote branch
```

---

## 🤝 Collaboration

```bash
git push                            # Upload changes to remote repo
git push origin <branchname>        # Push a branch to remote
git pull                            # Fetch and merge changes from remote repo
git pull origin <branchname>        # Pull branch changes from remote
git fetch                           # Download new data from remote but don’t merge
```

---

## 🔍 Inspection & Comparison

```bash
git log                             # Show commit history
git log --oneline                   # Brief log format
git show <commit_id>                # Show what changed in a commit
git diff                            # Show changes not yet staged
git diff <source_branch> <target_branch> # Show changes between branches
```

---

## 🧳 Stashing & Cleaning

```bash
git stash                           # Save dirty work and clean working directory
git stash list                      # List all stashes
git stash clear                     # Remove all stashed entries
git clean -f                        # Remove untracked files from working directory
```

---

## 🏷️ Tags & Releases

```bash
git tag <tagname>                   # Tag specific commits for release
git tag -a <tagname> -m "message"   # Create annotated tag
```

---

## 🧠 Advanced Manipulation

```bash
git cherry-pick <commit>            # Apply changes from a specific commit
git rebase <branch>                 # Apply commits from one branch onto another
git bisect                          # Find commit that introduced a bug (binary search)
git reflog                          # Show the history of HEAD and branch references
```

---

</details>

---

## 📚 Useful References

* [Git Official Documentation](https://git-scm.com/doc)
* [Pro Git Book (Free)](https://git-scm.com/book/en/v2)
* 📄 [Download Git Cheat Sheet PDF 1](./pdf1.pdf)
* 📄 [Download Git Cheat Sheet PDF 2](./pdf2.pdf)

---

> ✅ Tip: You can always run `git help <command>` for in-terminal documentation.

```

---

### 🔧 What You Need to Do

1. **Place your two PDF files** in the root or a `/pdf` folder of your repository.
2. **Rename them accordingly**, e.g., `pdf1.pdf`, `pdf2.pdf`, or give them meaningful names like `git_cheatsheet_basic.pdf`.
3. **Update the download links** if your PDFs are stored elsewhere.

Would you like this in a downloadable `.md` file or copy it to a GitHub repo directly?
```

