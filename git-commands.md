# 💻 Git & GitHub Complete Command Reference Cheat Sheet
A comprehensive, structured guide to Git version control commands, workflows, branching strategies, stashing, and repository recovery.
---
## ⚙️ 1. Setup & Configuration
Configure Git with your developer identity to ensure commit logs correctly attribute your work.
```bash
# Verify your Git installation and version
git --version
# Configure your global commit username
git config --global user.name "Yogesh Jawlekar"
# Configure your global commit email address
git config --global user.email "yjawlekar@gmail.com"
```
---
## 🔄 2. Basic Workflow
The foundational cycle for tracking project file changes locally.
```bash
# Initialize a local directory as a Git repository (.git)
git init
# Check the status of files (Staged, Unstaged, Untracked)
# - Red indicates unstaged/untracked modifications
# - Green indicates files successfully staged and ready to commit
git status
# Stage a specific file for the next commit
git add <filename>
# Stage all modified and new files in the directory
git add .
# Record staged snapshots into your commit history
git commit -m "feat: commit description message"
# Display the repository commit history logs
git log
# Display commit logs in a concise, single-line format
git log --oneline
```
> [!NOTE]
> **What is Version Control?**
> A Version Control System (VCS) maintains records of changes over time, allowing you to recall specific versions later, compare updates, and collaborate without losing progress.
---
## 🌿 3. Branching & Local Management
Isolate feature implementations, bug fixes, or experimental code from the main codebase.
```bash
# List all local branches (active branch is marked with *)
git branch
# Create a new local branch
git branch <branch-name>
# Switch to an existing branch
git switch <branch-name>
# OR (older syntax):
git checkout <branch-name>
# Create a new branch and switch to it immediately
git checkout -b <branch-name>
# Delete a local branch safely (will warn if commits are unmerged)
git branch -d <branch-name>
# Force-delete a local branch (ignores merge warning checks)
git branch -D <branch-name>
# Rename the local 'master' branch to 'main'
git branch -m master main
```
---
## ☁️ 4. Remote Integration & Collaboration
Connect your local codebase with remote platforms (like GitHub or GitLab) to share, backup, or synchronize code.
```bash
# Connect your local repository to a remote repository URL
git remote add origin <remote-repository-url>
# Check registered remote connection links and paths
git remote -v
# Update remote URL (e.g. swap HTTPS link for an SSH connection)
git remote set-url origin <ssh-repository-url>
# Push local commits to a remote repository
git push origin <branch-name>
# Pull and merge the latest remote commits into your active branch
git pull origin <branch-name>
# Download a copy of an existing remote repository to your local machine
git clone <repository-url>
```
> [!TIP]
> **What are Origin and Upstream?**
> *   `origin` represents your personal remote copy (usually your forked repository).
> *   `upstream` represents the primary source repository (e.g. the team or open-source project). 
> 
> To keep your fork synced with the main project:
> ```bash
> # Add the main repository as upstream
> git remote add upstream https://github.com/microsoft/vscode.git
> 
> # Pull updates directly from the main codebase into your local branch
> git pull upstream main
> ```
---
## 🔀 5. Advanced Merging, Rebasing & Squashing
Integrate histories, clean commit chains, or reconcile branches.
### Merging vs. Rebasing
*   **Git Merge**: Combines histories.
    *   *Fast-Forward Merge*: Simply moves the main branch pointer forward to the new commits if no intervening commits occurred (maintains linear history).
    *   *Commit Merge*: If both branches have progressed independently, Git does a commit merge where we can see visually two separate commit histories of two separate branches joined together.
*   **Git Rebase**: Rewrites history. Re-applies local commits on top of the target branch's latest commit, maintaining a perfectly linear commit line.
```bash
# Merge a feature branch into your active branch
git merge <feature-branch>
# Rebase your active branch onto the target branch
git rebase main
# Squash multiple commits into a single unified commit before merging
git merge main --squash
```
---
## 📦 6. Stashing & Cherry-Picking
Manage temporary progress or pull isolated changes across branches.
```bash
# Save uncommitted changes to a temporary stash stack and clear your workspace
git stash
# Restore and remove the most recently stashed changes
git stash pop
# List all stashed changes currently stored
git stash list
# Apply a specific stash from the list without removing it from stack
git stash apply stash@{0}
# Copy a single commit from another branch into your active branch
git cherry-pick <commit-id>
```
---
## 🚨 7. Undoing Changes: Reset vs. Revert
Safely backtrack or undo mistakes in your repository.
### Git Reset (Locally Undoing Commits)
> [!CAUTION]
> Git Reset rewrites local history. Avoid using reset on branches that have already been pushed to public/shared repositories.
```bash
# Delete the last local commit (HEAD~1) based on three safety levels:
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
```
|
 Reset Level 
|
 Deletes Commit? 
|
 Unstages Files? 
|
 Modifies/Discards File Contents? 
|
|
:---
|
:---:
|
:---:
|
:---
|
|
**
`--soft`
**
|
**
Yes
**
|
 No 
|
 No (Keeps all file changes in staging zone) 
|
|
**
`--mixed`
**
|
**
Yes
**
|
**
Yes
**
|
 No (Keeps all modifications, but unstaged) 
|
|
**
`--hard`
**
|
**
Yes
**
|
**
Yes
**
|
**
Yes (Permanently discards all file modifications)
**
|
### Git Revert (Safely Reversing History)
Revert creates a **new commit** that introduces the exact opposite changes of the target commit, safely reversing the history without erasing old logs. Safe for public branches.
```bash
# Revert a specific commit by creating a new reversing commit
git revert <commit-id>
```
