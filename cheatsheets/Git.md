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

