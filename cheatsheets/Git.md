# Git Cheat Sheet

### Global config git

Set the name and email that will be attached to your commits and tags

| Command | Description |
| ------ | ------ |
| `git config --global user.name "First name Last name"` | Set the username |
| `git config --global user.email "user@example.com"` | Set the email |

### Start a Project

| Command | Description |
| ------ | ------ |
| `git init <dir>` | Initialize an existing directory as a local Git repository |
| `git clone <url>` | Download a remope repository |

### Make a Change

| Command | Description |
| ------ | ------ |
| `git add <file>` | Add a file to staging |
| `git add .` | Stage all files |
| `git commit -m "Commit message"` | Commit all staged files to git |

### Basic Concepts

| Name | Description |
| ------ | ------ |
| `main:` | Default development branch |
| `origin:` | Defailt upstream repository |
| `HEAD:` | Current branch |
| `HEAD^:` | Parent of HEAD |
| `HEAD~4:` | Great-great grandparent of HEAD |

### Branches

| Name | Description |
| ------ | ------ |
| `git branch` | List all local branches |
| `git branch -r` | List all remote branches |
| `git branch -a` | List all branches (local and remote) |
| `git branch <branch-name>` | Create a new branch |
| `git checkout <branch-name>` | Switch to a branch and update the working directory |
| `git checkout -b <branch-name>` | Create a new branch and switch to it |
| `git branch -d <branch-name>` | Delete a merged branch |
| `git branch -D <branch-name>` | Delete a branch, whether merged or not |
| `git tab <tag-name>` | Add a tag to current commit (often used for new version releases) |

### Merging

| Name | Description |
| ------ | ------ |
| `git checkout b` & `git merge a` | Merge branch `A` into branch `B` |
| `git merge --squash a` | Merge and squash all commits into one new commit |

### Rebasing

| Name | Description |
| ------ | ------ |
| `git checkout fet-1` & `git rebase main` | Rebase `fet-1` branch onto main (to incorporate new changes made to main). Prevents unnecessary merge commits into `fet-1`, keeping history clean |
| `git rebase -i main` | Interactively clean up a branches commits before rebasing onto `main` |
| `git rebase -i HEAD~3` | Interactively rebase the last 3 commits on current branch |

### Undoing Things

| Name | Description |
| ------ | ------ |
| `git mv <existing_path> <new_path>` | Move and/or rename a file and stage move |
| `git rm <file>` | Remove a file from working directory and staging area, then stage the removal |
| `git rm --cached <file>` | Remove from staging area only |
| `git checkout <commit_hash>` | View a previous commit (READ ONLY) |
| `git revert <commit_hash>` | Create a new commit, reverting the changes from a specified commit |
| `git reset <commit_hash>` | Go back to a previous commit and delete all commits ahead of it (revert is safer) |
| `git reset --hard  <commit_hash>` | Go back to a previous commit and delete all commits ahead of it also delete workspace changes (BE VERY CAREFULL) |

### Review your Repository

| Name | Description |
| ------ | ------ |
| `git status` | List new or modified files not yet committed |
| `git log --oneline` | List commit history, with respective hash |
| `git log --all` | List all commit history, with respective hash |
| `git log --all --grapgh` | List all commit history, with respective hash in ASCII mode |
| `git diff` | Show changes to unstaged files |
| `git diff --cached` | Show changes to staged files |
| `git diff commit1_hash commit2_hash` | Show changes between two commits |
| `git show <hash>` | Show any object in Git in human-readable format |
| `git log --follow <file-name>` | Show the commits that changed file, even across renames |
