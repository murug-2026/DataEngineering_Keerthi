#### 1. What is Git?

Git is a free, open-source **distributed version control system**. It tracks every change made to files in a project, lets you go back to any earlier version, and lets many people work on the same project without overwriting each other's work.

#### 2. Where is it used?

- Software development (every major company and open-source project)
- Data science and research (code, notebooks, analysis scripts)
- Documentation and websites (docs, blogs, markdown notes)
- Team collaboration through hosting services such as **GitHub**, **GitLab** and **Bitbucket**

#### 3. Local repository vs Remote repository

| | Local repository | Remote repository |
|---|---|---|
| **Where it lives** | On your own computer (the `.git` folder inside your project) | On a server such as GitHub or GitLab |
| **Who uses it** | Only you | The whole team |
| **Needs internet?** | No | Yes |
| **Purpose** | Do your work and make commits | Share, back up and collaborate |
| **Typical name** | (your project folder) | `origin` |

#### 4. What is a branch?

A **branch** is an independent line of development. It lets you work on a feature or fix without touching the stable code. When you are done, you merge it back. The default branch is usually called `main` (older projects use `master`).

#### 5. How to create a branch from an existing main/master branch

```bash
git checkout main              # switch to main (use master if that is your default)
git pull origin main           # make sure main is up to date
git checkout -b my-new-branch  # create and switch to the new branch
```

Modern alternative:

```bash
git switch main
git switch -c my-new-branch
```

Check which branch you are on:

```bash
git branch
```

**In VS Code:** click the branch name at the bottom-left of the window, choose **Create new branch from...**, type a name, then pick `main`.

#### 6. Add, commit and push: meaning and process

| Step | Command | Meaning |
|---|---|---|
| **Add** (stage) | `git add <file>` | Selects the changes you want to include in the next snapshot. Moves them to the *staging area*. |
| **Commit** | `git commit -m "message"` | Saves a permanent snapshot of the staged changes in your **local** repository, with a message describing what changed. |
| **Push** | `git push origin <branch>` | Uploads your local commits to the **remote** repository so others can see them. |

Flow: **Working folder** → `git add` → **Staging area** → `git commit` → **Local repo** → `git push` → **Remote repo**

Adding a new file, modify an existing file, commit, push, and verify the remote is up to date.

### Setup (one time)

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Either clone an existing repo:

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

or start a new one:

```bash
mkdir demo-repo
cd demo-repo
git init
git remote add origin https://github.com/<your-username>/<your-repo>.git
```

### Step 1: Add a new file

```bash
echo "# My First File" > notes.md
git status                 # notes.md shows as "untracked"
```

### Step 2: Modify an existing file

Open `README.md` (create it if it does not exist), edit it, and save.

```bash
echo "Added a new line." >> README.md
git status                 # README.md shows as "modified"
```

### Step 3: Stage and commit

```bash
git add notes.md README.md      # or: git add .
git commit -m "Add notes.md and update README"
```

### Step 4: Push to remote

```bash
git push origin main
```

If this is a brand-new branch, use `git push -u origin <branch-name>` once. After that, plain `git push` works.

### Step 5: Check whether the remote is up to date

```bash
git status
```

You should see: `Your branch is up to date with 'origin/main'. nothing to commit, working tree clean`

More checks:

```bash
git fetch                       # download remote info without changing your files
git status                      # shows if you are ahead/behind
git log --oneline -5            # last 5 commits
git log origin/main --oneline   # commits on the remote
git diff main origin/main       # empty output means identical
```

Also open the repository page on GitHub and confirm your commit appears.

### Doing the same in VS Code (no commands)

1. Open the folder: **File → Open Folder**.
2. Create or edit files. A number badge appears on the **Source Control** icon (`Ctrl+Shift+G`).
3. Click **+** next to a file to stage it (or **+** next to *Changes* to stage all).
4. Type a message in the box and click **Commit**.
5. Click **Sync Changes** (or **Push**) to upload.
6. The bottom-left status bar shows ↑ (commits to push) and ↓ (commits to pull). When both are `0`, you are in sync.

### What is pull?

`git pull` downloads new commits from the remote repository and merges them into your current local branch. It is the same as running `git fetch` followed by `git merge`.

### How to get the latest changes made by others

```bash
git checkout main
git pull origin main
```

Or, if upstream tracking is set:

```bash
git pull
```

**Tip:** always pull *before* you start working and *before* you push, to avoid conflicts. If Git reports a **merge conflict**, open the conflicting files in VS Code, choose *Accept Current / Accept Incoming / Accept Both*, then `git add` and `git commit`.

**In VS Code:** click the **Sync** icon in the status bar, or use *Source Control → ⋯ → Pull*.

## Part 4: VS Code Basics

### Basic navigation

| Area | What it does |
|---|---|
| **Activity Bar** (far left) | Switch between Explorer, Search, Source Control, Run and Debug, Extensions |
| **Side Bar** | Shows the content of the selected Activity Bar item |
| **Editor** | Where you edit files; supports tabs and split view |
| **Panel** (bottom) | Terminal, Problems, Output, Debug Console |
| **Status Bar** (very bottom) | Current branch, sync state, line/column, language mode |

### Extensions

Open with `Ctrl+Shift+X`. Search, then click **Install**. Useful ones:

- **GitLens**: shows who changed each line and when
- **Git Graph**: visual branch history
- **Markdown All in One**: shortcuts, table of contents, preview
- **markdownlint**: catches Markdown style mistakes
- **Python** / **Jupyter**: for data science work
- **Prettier**: automatic code formatting

### Essential shortcuts (Windows/Linux, use `Cmd` instead of `Ctrl` on Mac)

| Shortcut | Action |
|---|---|
| `Ctrl+Shift+P` | Command Palette (run any command) |
| `Ctrl+P` | Quick open file by name |
| `Ctrl+B` | Show/hide side bar |
| `` Ctrl+` `` | Show/hide terminal |
| `Ctrl+S` | Save |
| `Ctrl+/` | Comment/uncomment line |
| `Ctrl+F` / `Ctrl+H` | Find / Replace |
| `Ctrl+Shift+F` | Search across all files |
| `Alt+↑ / Alt+↓` | Move line up/down |
| `Shift+Alt+↓` | Duplicate line |
| `Ctrl+D` | Select next occurrence of the word |
| `Ctrl+\` | Split editor |
| `Ctrl+Shift+G` | Source Control |
| `Ctrl+Shift+V` | Markdown preview |

### Opening the terminal and using multiple terminals

- **Open:** `` Ctrl+` `` or **Terminal → New Terminal**
- **New additional terminal:** click the **+** in the terminal panel, or `` Ctrl+Shift+` ``
- **Switch between terminals:** use the dropdown on the right of the panel, or the list of terminals at the side
- **Split terminal** (two side by side): click the split icon or press `Ctrl+Shift+5`
- **Choose shell:** click the **˅** next to **+** and pick Bash, PowerShell, Command Prompt, Git Bash, etc.
- **Close a terminal:** click the trash icon

## Part 5: Markdown Syntax

### Syntax cheat sheet

````markdown
# Heading 1
## Heading 2
### Heading 3

Normal text, **bold**, *italic*, ~~strikethrough~~ and `inline code`.

- Bullet item
- Another bullet
  - Nested bullet

1. Numbered item
2. Another numbered item

| Column A | Column B |
|----------|----------|
| Cell 1   | Cell 2   |

[Link text](https://example.com)
![Image alt text](image.png)
````

# Sample Markdown File

## Introduction

This is a **sample Markdown file** created to practise headers, text, bulleted lists and tables. Markdown is a lightweight way to format plain text.

### Why use Markdown?

- Simple to learn
- Readable even as plain text
- Used in README files, documentation and notes
  - GitHub renders it automatically
  - VS Code has a built-in preview

### Steps to follow

1. Create a file ending in `.md`
2. Write your content
3. Press `Ctrl+Shift+V` to preview

## Sample Table

| Tool | Purpose | Cost |
|------|---------|------|
| Git | Version control | Free |
| GitHub | Remote hosting | Free tier |
| VS Code | Code editor | Free |


```bash
git init                      # start a repo
git clone <url>               # copy a remote repo
git status                    # see changes
git add <file>                # stage
git commit -m "message"       # commit
git push origin <branch>      # upload
git pull origin <branch>      # download latest
git branch                    # list branches
git checkout -b <name>        # create + switch branch
git log --oneline             # history
```
