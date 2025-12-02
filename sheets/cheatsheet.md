# Git & GitHub Cheat Sheet — Commands with one-line use

Commands are shown on one line for easy copy/paste. A one-line description follows each command.

## Setup
- `git config --global user.name "Your Name"` 
— Set your global Git commit name.  
- `git config --global user.email "you@example.com"` 
— Set your global Git commit email.  
- `git config --list` 
— Show current Git configuration.

## Repository
- `git init` 
— Initialize a new local Git repository.  
- `git clone <repo-url>` 
— Copy a remote repository to your machine.  
- `git remote add origin <repo-url>` 
— Add a remote named "origin" pointing to a URL.  
- `git remote set-url origin <url>` 
— Change the URL for the origin remote.

## Branching & workflow
- `git checkout -b feature/name` 
— Create and switch to a new branch for work.  
- `git checkout main` 
— Switch to the main branch.  
- `git branch` 
— List local branches.  
- `git branch -d feature/name` 
— Delete a local branch that has been merged.  
- `git merge feature/name` 
— Merge another branch into the current branch.  
- `git merge --no-ff feature/name` 
— Merge and always create a merge commit.  
- `git rebase main` 
— Reapply your branch commits on top of main to keep history linear.  
- `git rebase -i HEAD~5` 
— Interactively edit, squash, or reorder the last 5 commits.

## Staging & committing
- `git status` 
— Show working tree status and staged changes.  
- `git add <file>` 
— Stage a specific file for the next commit.  
- `git add .` 
— Stage all changes in the working directory.  
- `git add -p` 
— Interactively select hunks to stage.  
- `git commit -m "Short message"` 
— Create a commit with a concise message.  
- `git commit --amend --no-edit` 
— Amend the last commit without changing its message.

## Syncing with remote
- `git fetch` 
— Download objects and refs from the remote without merging.  
- `git pull` 
— Fetch and merge remote changes into the current branch.  
- `git pull --rebase` 
— Fetch and rebase local commits onto remote changes.  
- `git push origin feature/name` 
— Push a local branch to the remote.  
- `git push -u origin main` 
— Push main and set it to track origin/main.

## Undo & recovery
- `git restore <file>` 
— Discard local changes to a file (restore from HEAD).  
- `git restore --staged <file>` 
— Unstage a file (move from index back to working tree).  
- `git reset --soft HEAD~1` 
— Undo the last commit but keep changes staged.  
- `git reset --mixed HEAD~1` 
— Remove the last commit and unstage changes.  
- `git reset --hard <commit>` 
— Reset to a commit and discard all working changes.  
- `git revert <commit-hash>` 
— Create a new commit that undoes a previous commit.

## Stash
- `git stash` 
— Save uncommitted changes and clean the working directory.  
- `git stash push -m "msg"` 
— Save changes with a message for easier identification.  
- `git stash list` 
— List saved stashes.  
- `git stash pop` 
— Apply and remove the most recent stash.  
- `git stash drop stash@{1}` 
— Delete a specific stash entry.

## History & diffs
- `git log --oneline --graph --decorate --all` 
— Show a compact graphical commit history.  
- `git log --stat` 
— Show commits with file change summaries.  
- `git diff` 
— Show unstaged changes.  
- `git diff --staged` 
— Show staged changes ready to commit.  
- `git show <commit>` 
— Display a specific commit and its changes.  
- `git cherry-pick <commit-hash>` 
— Apply a specific commit onto the current branch.

## Tags & releases
- `git tag -a v1.0 -m "Release v1.0"` 
— Create an annotated tag for a release.  
- `git push origin v1.0` 
— Push a specific tag to the remote.  
- `git push origin --tags` 
— Push all local tags to the remote.

## SSH & GitHub
- `ssh-keygen -t ed25519 -C "you@example.com"` 
— Generate an SSH keypair for GitHub.  
- `cat ~/.ssh/id_ed25519.pub` 
— Show your public key for copying to GitHub.  
- `ssh -T git@github.com` 
— Test SSH authentication with GitHub.  
- `git remote set-url origin git@github.com:<user>/<repo>.git` 
— Switch the repo remote to SSH.

## Danger zone (use with caution)
- `git push --force` 
— Force push and overwrite remote history (can disrupt others).  
- `git push --force-with-lease` 
— Safer force push that prevents overwriting others’ work.  
- `git reset --hard <commit>` 
— Permanently discard commits and working changes.

