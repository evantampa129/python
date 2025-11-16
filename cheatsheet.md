// ...existing code...
# Git & GitHub Cheat Sheet — Ready to copy/paste with brief descriptions

Commands are shown on one line for easy copy/paste. A one-line description follows each command.

## Setup
```sh
git config --global user.name "Your Name"
```
Set your Git username (used in commits).

```sh
git config --global user.email "you@example.com"
```
Set your Git email (used in commits).

```sh
git config --list
```
Show current Git configuration.

## Helpful aliases
```sh
git config --global alias.co checkout
```
Create a short alias "git co" for "git checkout".

```sh
git config --global alias.br branch
```
Create "git br" alias for "git branch".

```sh
git config --global alias.st status
```
Create "git st" alias for "git status".

```sh
git config --global alias.lg "log --oneline --graph --decorate --all"
```
Create "git lg" to view a compact commit graph.

## Repo lifecycle
```sh
git init
```
Initialize a new local Git repository.

```sh
git clone <repo-url>
```
Copy a remote repository to your machine.

```sh
git remote add origin <repo-url>
```
Add a remote named "origin" pointing to a URL.

```sh
git push -u origin main
```
Push local branch "main" and set upstream to origin/main.

## Staging & commits
```sh
git status
```
Show current working tree status and staged changes.

```sh
git add <file>
```
Stage a specific file for the next commit.

```sh
git add .
```
Stage all changed files in the working directory.

```sh
git add -p
```
Interactively choose hunks to stage.

```sh
git commit -m "Short message"
```
Create a commit with a concise message.

```sh
git commit --amend --no-edit
```
Amend the last commit without changing its message.

## Branching & merging
```sh
git branch
```
List local branches.

```sh
git checkout -b feature/name
```
Create and switch to a new branch.

```sh
git checkout main
```
Switch to the main branch.

```sh
git merge feature/name
```
Merge changes from the feature branch into the current branch.

```sh
git branch -d feature/name
```
Delete a local branch that has been merged.

## Syncing with remote
```sh
git fetch
```
Download objects and refs from the remote without merging.

```sh
git pull
```
Fetch and merge remote changes into the current branch.

```sh
git pull --rebase
```
Fetch and rebase local commits on top of remote changes (keeps linear history).

```sh
git push origin feature/name
```
Push a local branch to the remote repository.

```sh
git push -u origin main
```
Push main and set it to track origin/main (first-time push).

## Undo & recovery
```sh
git restore --staged <file>
```
Unstage a file (move from index back to working tree).

```sh
git restore <file>
```
Discard local changes to a file (restore from HEAD).

```sh
git reset --soft HEAD~1
```
Undo last commit but keep changes staged.

```sh
git revert <commit-hash>
```
Create a new commit that undoes the specified commit (safe for public history).

## Stash
```sh
git stash
```
Save uncommitted changes to a stack and clean the working directory.

```sh
git stash list
```
Show saved stashes.

```sh
git stash pop
```
Apply the most recent stash and remove it from the stash list.

## Viewing history
```sh
git log --oneline
```
Compact list of commits (one line per commit).

```sh
git log --oneline --graph --decorate --all
```
Visualize commit history with a graph and refs.

## Tags & releases
```sh
git tag -a v1.0 -m "Release v1.0"
```
Create an annotated tag for a release.

```sh
git push origin --tags
```
Push tags to the remote repository.

## GitHub workflow (basic)
```sh
git checkout -b feature/x
```
Create branch for a new feature or fix.

```sh
git add .
```
Stage changes before committing.

```sh
git commit -m "Describe change"
```
Commit changes with a clear message.

```sh
git push origin feature/x
```
Push the feature branch to GitHub to open a Pull Request.

## Files & ignore
```sh
echo "venv/" >> .gitignore
```
Add a typical virtualenv directory to .gitignore.

```sh
git rm --cached <file>
```
Remove a file from the repo but keep it locally (useful after updating .gitignore).

## Quick tips
- Use descriptive commit messages for easier history reading.
- Keep branches small and focused to simplify reviews.
- Use git stash to switch tasks without committing.
- Prefer git pull --rebase for a linear history when collaborating.
```// filepath: /home/evantampa/python_new/cheatsheet.md
// ...existing code...
# Git & GitHub Cheat Sheet — Ready to copy/paste with brief descriptions

Commands are shown on one line for easy copy/paste. A one-line description follows each command.

## Setup
```sh
git config --global user.name "Your Name"
```
Set your Git username (used in commits).

```sh
git config --global user.email "you@example.com"
```
Set your Git email (used in commits).

```sh
git config --list
```
Show current Git configuration.

## Helpful aliases
```sh
git config --global alias.co checkout
```
Create a short alias "git co" for "git checkout".

```sh
git config --global alias.br branch
```
Create "git br" alias for "git branch".

```sh
git config --global alias.st status
```
Create "git st" alias for "git status".

```sh
git config --global alias.lg "log --oneline --graph --decorate --all"
```
Create "git lg" to view a compact commit graph.

## Repo lifecycle
```sh
git init
```
Initialize a new local Git repository.

```sh
git clone <repo-url>
```
Copy a remote repository to your machine.

```sh
git remote add origin <repo-url>
```
Add a remote named "origin" pointing to a URL.

```sh
git push -u origin main
```
Push local branch "main" and set upstream to origin/main.

## Staging & commits
```sh
git status
```
Show current working tree status and staged changes.

```sh
git add <file>
```
Stage a specific file for the next commit.

```sh
git add .
```
Stage all changed files in the working directory.

```sh
git add -p
```
Interactively choose hunks to stage.

```sh
git commit -m "Short message"
```
Create a commit with a concise message.

```sh
git commit --amend --no-edit
```
Amend the last commit without changing its message.

## Branching & merging
```sh
git branch
```
List local branches.

```sh
git checkout -b feature/name
```
Create and switch to a new branch.

```sh
git checkout main
```
Switch to the main branch.

```sh
git merge feature/name
```
Merge changes from the feature branch into the current branch.

```sh
git branch -d feature/name
```
Delete a local branch that has been merged.

## Syncing with remote
```sh
git fetch
```
Download objects and refs from the remote without merging.

```sh
git pull
```
Fetch and merge remote changes into the current branch.

```sh
git pull --rebase
```
Fetch and rebase local commits on top of remote changes (keeps linear history).

```sh
git push origin feature/name
```
Push a local branch to the remote repository.

```sh
git push -u origin main
```
Push main and set it to track origin/main (first-time push).

## Undo & recovery
```sh
git restore --staged <file>
```
Unstage a file (move from index back to working tree).

```sh
git restore <file>
```
Discard local changes to a file (restore from HEAD).

```sh
git reset --soft HEAD~1
```
Undo last commit but keep changes staged.

```sh
git revert <commit-hash>
```
Create a new commit that undoes the specified commit (safe for public history).

## Stash
```sh
git stash
```
Save uncommitted changes to a stack and clean the working directory.

```sh
git stash list
```
Show saved stashes.

```sh
git stash pop
```
Apply the most recent stash and remove it from the stash list.

## Viewing history
```sh
git log --oneline
```
Compact list of commits (one line per commit).

```sh
git log --oneline --graph --decorate --all
```
Visualize commit history with a graph and refs.

## Tags & releases
```sh
git tag -a v1.0 -m "Release v1.0"
```
Create an annotated tag for a release.

```sh
git push origin --tags
```
Push tags to the remote repository.

## GitHub workflow (basic)
```sh
git checkout -b feature/x
```
Create branch for a new feature or fix.

```sh
git add .
```
Stage changes before committing.

```sh
git commit -m "Describe change"
```
Commit changes with a clear message.

```sh
git push origin feature/x
```
Push the feature branch to GitHub to open a Pull Request.

## Files & ignore
```sh
echo "venv/" >> .gitignore
```
Add a typical virtualenv directory to .gitignore.

```sh
git rm --cached <file>
```
Remove a file from the repo but keep