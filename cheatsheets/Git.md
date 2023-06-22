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

### Stashing

| Name | Description |
| ------ | ------ |
| `git stash` | Store modified and staged changes |
| `git stash -u` | Store modified, staged changes and untracked files |
| `git stash -a` | Store modified, staged, untracked and ignored files |
| `git stash save "comment"` | As abode, but add a comment |
| `git stash -p` | Partial stash. Stash just a single file, a collection of file, or individual changes from within files |
| `git stash list` | List all stashes |
| `git stash apply` | Re-apply the stash without deleting it |
| `git stash pop stash@{2}` | Re-apply the stash at index 2, then delete it from the stash list. Omit `stash@{n}` to pop the most recent stash |
| `git stash show stash@{1}` | Show the diff summary of stash 1 |
| `git stash drop stash@{1}` | Delete stash at index 1. Omit `stash@{n}` to delete last stash made |
| `git stash clear` | Delete all stashes |

### Synchronizing 

| Name | Description |
| ------ | ------ |
| `git remote add <alias> <url>` | Add a remote repository |
| `git remote` | View all remote connections |
| `git remote -v` | View all remote connections with URLs |
| `git remote remove <alias>` | Remove a connection |
| `git remote rename <old> <new>` | Rename a connection |
| `git fetch <alias>` | Fetch all branches from remote repository (no merge) |
| `git fetch <alias> <branch>` | Fetch a specific branch |
| `git pull` | Fetch the remote repositories copy of the current branch, then merge |
| `git pull --rebase <alias>` | Move (rebase) your local changes onto the top of new changes made to the remote repository (for clean, linear history) |
| `git push <alias>` | Upload local content to remote repo |
| `git push <alias> <branch>` | Upload to a branch (can then pull request) |

### Ignoring patterns

Preventing unintentional staging or committing of files

```
logs/
*.notes
pattern*/
```
Save a file with desired patterns as `.gitignote` with either direct string matches or wildcard globs.

`git config --global core.excludesfile [file]`
system wide ignore pattern for all local repositories
