# Master Git and GitHub from A to Z

## Table of Contents

1. [Introduction to Version Control and Git](#chapter-1-introduction-to-version-control-and-git)
2. [Installing and Configuring Git](#chapter-2-installing-and-configuring-git)
3. [Git Fundamentals: Repositories, Commits, and Snapshots](#chapter-3-git-fundamentals-repositories-commits-and-snapshots)
4. [Understanding the Git Workflow](#chapter-4-understanding-the-git-workflow)
5. [Branching and Merging](#chapter-5-branching-and-merging)
6. [Remote Repositories and GitHub](#chapter-6-remote-repositories-and-github)
7. [GitHub Fundamentals](#chapter-7-github-fundamentals)
8. [Pull Requests and Code Reviews](#chapter-8-pull-requests-and-code-reviews)
9. [GitHub Issues and Project Management](#chapter-9-github-issues-and-project-management)
10. [Git Advanced Commands](#chapter-10-git-advanced-commands)
11. [Git Rebasing and Advanced Merging](#chapter-11-git-rebasing-and-advanced-merging)
12. [Git Stashing and Cherry-Picking](#chapter-12-git-stashing-and-cherry-picking)
13. [Git Reset, Revert, and Undo Operations](#chapter-13-git-reset-revert-and-undo-operations)
14. [Git Hooks and Automation](#chapter-14-git-hooks-and-automation)
15. [Git Aliases and Custom Commands](#chapter-15-git-aliases-and-custom-commands)
16. [GitHub Actions and CI/CD](#chapter-16-github-actions-and-cicd)
17. [GitHub Advanced Features](#chapter-17-github-advanced-features)
18. [Git Workflows and Branching Strategies](#chapter-18-git-workflows-and-branching-strategies)
19. [Collaboration Best Practices](#chapter-19-collaboration-best-practices)
20. [Troubleshooting and Recovery](#chapter-20-troubleshooting-and-recovery)
21. [Security Best Practices](#chapter-21-security-best-practices)
22. [Quick Reference Cheatsheet](#chapter-22-quick-reference-cheatsheet)
23. [Additional Resources](#chapter-23-additional-resources)

---

## Chapter 1: Introduction to Version Control and Git

### What is Version Control?

Version control, also known as source control or revision control, is a system that records changes to files over time so that you can recall specific versions later. It allows multiple people to work on the same project simultaneously, tracks every modification to the code, and provides the ability to revert to previous states if something goes wrong. Without version control, developers would have to manually manage different versions of files, leading to chaos, lost work, and impossible-to-track bugs.

Version control systems come in two main flavors: centralized and distributed. Centralized version control systems (CVCS) like Subversion (SVN) and Perforce use a single server that contains all the versioned files. Clients check out files from this central server, make changes, and commit them back. While this approach is simple to understand, it has significant drawbacks: if the central server goes down, nobody can collaborate; if the server's disk becomes corrupted, you lose everything unless you have backups.

Distributed version control systems (DVCS) like Git, Mercurial, and Darcs take a fundamentally different approach. Instead of a single central repository, every developer's working copy is a complete repository with full history. This means you can work offline, commit locally, and synchronize with others when ready. If any server dies, any client repository can be copied back to it to restore the server. This architecture makes DVCS much more robust and flexible than centralized systems.

### What is Git?

Git is a free, open-source distributed version control system created by Linus Torvalds in 2005 to manage the development of the Linux kernel. It has since become the most widely used version control system in the world, essential for modern software development. Git is designed to handle everything from small to extremely large projects with speed, efficiency, and data integrity.

What sets Git apart from other version control systems is its approach to storing data. Most VCS store information as a list of file-based changes (deltas). Git instead thinks of its data more like a series of snapshots of a miniature filesystem. Every time you commit, Git takes a picture of what all your files look like at that moment and stores a reference to that snapshot. If files haven't changed, Git doesn't store them again—just a link to the previous identical file already stored. This makes Git extremely fast and efficient.

Git also has incredible data integrity. Every file and commit is checksummed using SHA-1 hash, and this checksum is used to reference the file. It's impossible to change any file, date, or commit message without Git knowing about it. This means you can trust that your code history is accurate and hasn't been tampered with.

### Why Git Matters for Developers

Understanding Git deeply is crucial for any developer because it's the foundation of modern software collaboration. Nearly every software company uses Git, and proficiency with it is a non-negotiable skill. Beyond just "saving code," Git enables powerful workflows for feature development, bug fixing, release management, and team collaboration.

Git's branching model is particularly powerful. In many VCS, branching is expensive and slow because it involves copying all files. In Git, branches are incredibly lightweight—they're just pointers to specific commits. This encourages developers to create branches for every feature, experiment freely, and merge when ready. This workflow leads to cleaner code, better isolation of changes, and safer collaboration.

### Git vs Other Version Control Systems

| Feature | Git | SVN | Mercurial |
|---------|-----|-----|-----------|
| Architecture | Distributed | Centralized | Distributed |
| Offline Work | Full support | Limited | Full support |
| Branching | Lightweight (instant) | Heavy (directory copy) | Lightweight |
| Merging | Excellent | Challenging | Good |
| Speed | Very fast | Slower for remote ops | Fast |
| Learning Curve | Steep | Gentle | Moderate |
| Industry Adoption | Dominant | Legacy projects | Smaller community |
| Large Files | Git LFS extension | Built-in | Large Files Extension |

```
Centralized VCS Architecture:

                 +-----------------+
                 |  Central Server |
                 |   (Repository)  |
                 +--------+--------+
                          |
         +----------------+----------------+
         |                |                |
    +----v----+      +----v----+      +----v----+
    | Client  |      | Client  |      | Client  |
    |   A     |      |   B     |      |   C     |
    +---------+      +---------+      +---------+


Distributed VCS (Git) Architecture:

    +---------+      +---------+      +---------+
    | Repo A  |<---->| Repo B  |<---->| Repo C  |
    | (Full)  |      | (Full)  |      | (Full)  |
    +---------+      +---------+      +---------+
         ^                ^                ^
         |                |                |
         +----------------+----------------+
                    All repos are equal
              Any can act as "central"
```

---

## Chapter 2: Installing and Configuring Git

### Installing Git on Different Platforms

Git runs on all major operating systems, and installation is straightforward. On Windows, the official Git for Windows installer provides Git Bash, a command-line environment that gives you a Unix-like terminal experience with Git pre-installed. On macOS, Git comes pre-installed with Xcode Command Line Tools, or you can install it via Homebrew for the latest version. On Linux, Git is available through every distribution's package manager.

**Windows Installation:**
```bash
# Download from https://git-scm.com/download/win
# Or use winget (Windows Package Manager)
winget install Git.Git

# Or use Chocolatey
choco install git
```

**macOS Installation:**
```bash
# Install Xcode Command Line Tools (includes Git)
xcode-select --install

# Or using Homebrew (recommended for latest version)
brew install git

# Verify installation
git --version
```

**Linux Installation:**
```bash
# Debian/Ubuntu
sudo apt update
sudo apt install git

# Fedora
sudo dnf install git

# CentOS/RHEL
sudo yum install git

# Arch Linux
sudo pacman -S git

# Verify installation
git --version
```

### Initial Configuration

After installing Git, you need to configure your identity. Git uses this information to label commits with who made them. This is essential for collaboration—you want to know who wrote each piece of code. The configuration is stored in different levels: system-wide, user-level (global), and repository-level (local), with more specific settings overriding more general ones.

Git configuration is managed through the `git config` command. The most important settings are your name and email, which will be attached to every commit you make. These don't need to match your GitHub credentials exactly, but using the same email helps GitHub associate your commits with your account.

```bash
# Set your identity (required)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Set your default branch name (main instead of master)
git config --global init.defaultBranch main

# Set your default editor (for commit messages, etc.)
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "nano"         # Nano
git config --global core.editor "vim"          # Vim

# Configure line ending behavior (important for cross-platform teams)
# Windows (CRLF)
git config --global core.autocrlf true
# macOS/Linux (LF)
git config --global core.autocrlf input

# View all configurations
git config --list

# View specific configuration
git config user.name
git config user.email

# View configuration file locations
git config --list --show-origin

# Edit configuration directly
git config --global --edit
```

### Configuration Levels and Precedence

Git configurations exist at three levels, each with different scope and precedence. Understanding these levels helps you manage settings appropriately across different projects and machines.

| Level | File Location | Scope | Command Flag |
|-------|--------------|-------|--------------|
| System | `/etc/gitconfig` (Linux), `C:\ProgramData\Git\config` (Windows) | All users on system | `--system` |
| Global | `~/.gitconfig` (Linux/Mac), `C:\Users\<User>\.gitconfig` (Windows) | Current user | `--global` |
| Local | `.git/config` in repository | Current repository only | `--local` |

```bash
# System-level configuration (affects all users)
git config --system user.name "System Admin"

# Global-level configuration (your default identity)
git config --global user.name "Your Name"

# Local-level configuration (repository-specific)
git config --local user.name "Project-Specific Name"

# Configuration precedence: Local > Global > System
# More specific settings override more general ones
```

### Essential Global Configurations

Beyond basic identity, there are several configurations that significantly improve your Git experience. These include aliases for common commands, credential handling, and UI improvements.

```bash
# Useful aliases for common commands
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --oneline --graph --all'

# Better diff algorithm
git config --global diff.algorithm histogram

# Color output
git config --global color.ui auto

# Better push default (push only current branch)
git config --global push.default simple

# Pull with rebase instead of merge (cleaner history)
git config --global pull.rebase true

# Credential caching (remember credentials for some time)
# macOS
git config --global credential.helper osxkeychain

# Windows
git config --global credential.helper wincred

# Linux (cache for 1 hour)
git config --global credential.helper 'cache --timeout=3600'

# More informative log format
git config --global format.pretty "%C(yellow)%h%Creset %s %C(red)(%cr)%Creset %C(blue)<%an>%Creset"
```

### SSH Key Setup for GitHub

Using SSH keys for GitHub authentication is more secure and convenient than HTTPS with passwords. SSH keys use public-key cryptography: you keep a private key on your machine and give the public key to GitHub. GitHub then uses the public key to verify your identity without ever seeing your private key.

```bash
# Generate a new SSH key pair
ssh-keygen -t ed25519 -C "your.email@example.com"

# For older systems that don't support ed25519:
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"

# Start SSH agent
eval "$(ssh-agent -s)"

# Add SSH key to agent
ssh-add ~/.ssh/id_ed25519

# Copy public key to clipboard
# macOS
pbcopy < ~/.ssh/id_ed25519.pub

# Linux (with xclip)
xclip -sel clip < ~/.ssh/id_ed25519.pub

# Windows (PowerShell)
clip < ~/.ssh/id_ed25519.pub

# View public key (to copy manually)
cat ~/.ssh/id_ed25519.pub

# Test SSH connection to GitHub
ssh -T git@github.com

# Expected output:
# Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

### SSH Config for Multiple Accounts

When working with multiple GitHub accounts (personal and work), you need to configure SSH to use different keys for each account.

```bash
# Edit SSH config file
nano ~/.ssh/config

# Add the following configuration:
# Personal GitHub account
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_personal

# Work GitHub account
Host github-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_work

# Now you can clone work repos with:
git clone git@github-work:company/repo.git
```

---

## Chapter 3: Git Fundamentals: Repositories, Commits, and Snapshots

### What is a Git Repository?

A Git repository (or "repo") is a directory that contains your project files and the complete history of all changes made to those files. At its core, a Git repository is a data structure that stores snapshots of your project over time, along with metadata about who made each change, when, and why. Every repository is self-contained, meaning it has everything needed to track its complete history without relying on external servers.

When you initialize a Git repository, Git creates a hidden `.git` directory at the root of your project. This directory contains all the version control information: the object database (commits, trees, blobs), the index (staging area), configuration files, and hooks. Understanding what's inside this directory helps demystify how Git works under the hood.

```
Repository Structure:

my-project/
├── .git/                    # Git repository data
│   ├── HEAD                 # Points to current branch
│   ├── config               # Repository-specific config
│   ├── description          # For GitWeb (rarely used)
│   ├── hooks/               # Scripts for Git events
│   ├── info/                # Global exclude file
│   ├── objects/             # All data (commits, trees, blobs)
│   │   ├── pack/           # Packed objects
│   │   └── info/           # Object info
│   └── refs/                # Pointers to commits
│       ├── heads/          # Branch pointers
│       ├── tags/           # Tag pointers
│       └── remotes/        # Remote branch pointers
├── src/                     # Your project files
├── tests/
├── .gitignore              # Files to ignore
└── README.md
```

### Creating Repositories

You can create a Git repository in two ways: initializing a new repository in an existing directory, or cloning an existing repository from elsewhere. Initialization creates a new `.git` directory and starts tracking your project from scratch. Cloning copies an entire repository, including its complete history, to your local machine.

```bash
# Initialize a new repository in current directory
git init

# Initialize a new repository in a new directory
git init my-new-project

# Clone an existing repository via HTTPS
git clone https://github.com/username/repository.git

# Clone via SSH (recommended)
git clone git@github.com:username/repository.git

# Clone into a specific directory
git clone git@github.com:username/repository.git my-project

# Clone a specific branch
git clone --branch main git@github.com:username/repository.git

# Shallow clone (only recent history - useful for large repos)
git clone --depth 1 git@github.com:username/repository.git

# Clone a single branch (sparse)
git clone --single-branch --branch main git@github.com:username/repository.git
```

### Understanding Commits

A commit is a snapshot of your entire project at a specific point in time. Each commit captures the state of all tracked files and stores metadata including: the author (who made the change), the committer (who applied the change), a timestamp, and a commit message describing what changed and why. Commits are the fundamental building blocks of Git history.

Every commit has a unique 40-character SHA-1 hash identifier (like `a1b2c3d4e5f6...`). This hash is calculated from the commit's content and metadata, meaning that any change to a commit—even a single bit—produces a completely different hash. This property ensures data integrity: if anything in a commit changes, the hash changes, and Git can detect tampering.

```bash
# Stage files for commit
git add filename.txt          # Add specific file
git add .                     # Add all changes in current directory
git add -A                    # Add all changes in repository
git add -u                    # Add only modified/deleted files (not new)
git add -p                    # Interactive staging (review each change)

# View staging status
git status                    # Full status
git status -s                 # Short status

# Create a commit
git commit -m "Add user authentication feature"

# Stage and commit in one step (only for tracked files)
git commit -am "Update documentation"

# Create a commit with detailed message
git commit                    # Opens editor for multi-line message

# Commit message template:
# <type>(<scope>): <subject>
#
# <body>
#
# <footer>
#
# Example:
# feat(auth): add OAuth2 authentication
#
# Implements OAuth2 authentication flow with Google and GitHub providers.
# Includes token refresh logic and session management.
#
# Closes #123
```

### The Three States of Git

Git files can exist in three main states: modified, staged, and committed. Understanding these states is crucial because it explains Git's workflow and the commands you use to move files between states.

| State | Description | Location |
|-------|-------------|----------|
| **Modified** | File has changed but not staged | Working Directory |
| **Staged** | File is marked to go into next commit | Staging Area (Index) |
| **Committed** | File is safely stored in Git database | Repository (.git directory) |

```
Git File States and Transitions:

+------------------+     git add      +----------------+
|   Working        |  ------------>  |    Staging     |
|   Directory      |                 |     Area       |
|  (Modified)      |  <------------  |   (Staged)     |
+------------------+    git restore  +-------+--------+
                                            |
                                            | git commit
                                            v
                                    +----------------+
                                    |   Repository   |
                                    |  (Committed)   |
                                    +----------------+

The Staging Area allows you to:
- Choose exactly which changes to commit
- Review changes before committing
- Split large changes into logical commits
```

### The Git Object Model

Git is fundamentally a content-addressable filesystem. Everything stored in Git—commits, files, trees—is stored as objects identified by their SHA-1 hash. Understanding this model helps you understand Git's behavior and troubleshoot issues.

Git stores four types of objects:

**Blob (Binary Large Object):** Stores file contents. Note that blobs store content, not filenames—a file with the same content will have the same blob hash regardless of its name or location.

**Tree:** Stores directory structure. A tree contains references to blobs (files) and other trees (subdirectories) along with their names and permissions.

**Commit:** Stores a snapshot. A commit references a tree (the project root), plus metadata: author, committer, date, message, and parent commit(s).

**Tag:** Stores a named reference. An annotated tag references a commit and includes its own metadata (tagger, date, message).

```
Git Object Model Example:

Commit (a1b2c3d)
├── tree: def456 (root tree)
│   ├── blob: file1.txt (content hash: abc111)
│   ├── blob: file2.txt (content hash: abc222)
│   └── tree: src/ (hash: ghi789)
│       ├── blob: main.py (content hash: abc333)
│       └── blob: utils.py (content hash: abc444)
├── parent: previous_commit_hash
├── author: "John Doe <john@example.com>"
├── committer: "John Doe <john@example.com>"
└── message: "Add initial project structure"

The commit hash is computed from ALL of the above data.
Change anything, and the hash changes completely.
```

```bash
# Inspect Git objects
# View object type
git cat-file -t a1b2c3d    # Returns: commit

# View object content
git cat-file -p a1b2c3d    # Pretty-print content

# View object size
git cat-file -s a1b2c3d    # Size in bytes

# Find all objects in repository
find .git/objects -type f | head -20

# View the content of a blob
git cat-file -p abc111

# View tree structure
git cat-file -p def456
git ls-tree def456

# View commit details
git cat-file -p HEAD
```

### Anatomy of a Commit

Each commit contains a wealth of information beyond just the code changes. Understanding this structure helps you write better commits and use Git's history effectively.

```bash
# View full commit details
git show --format=fuller HEAD

# Example output:
# commit a1b2c3d4e5f6789012345678901234567890abcd
# Author:     John Doe <john.doe@example.com>
# AuthorDate: Mon Jan 15 10:30:00 2024 -0500
# Commit:     Jane Smith <jane.smith@example.com>
# CommitDate: Mon Jan 15 14:45:00 2024 -0500
#
#     Add user authentication feature
#     
#     Implements JWT-based authentication with refresh tokens.
#     Includes login, logout, and token refresh endpoints.
#     
#     Closes #123

# View commit as patch
git show HEAD

# View only file changes in commit
git show --stat HEAD

# View changes to specific file in commit
git show HEAD -- path/to/file.txt

# List all files in a commit
git diff-tree --no-commit-id --name-only -r HEAD

# View commit one-liner with graph
git log --oneline --graph -10
```

---

## Chapter 4: Understanding the Git Workflow

### The Basic Git Workflow

The basic Git workflow involves making changes in your working directory, staging the changes you want to include in your next commit, and then committing those changes. This cycle repeats throughout development. The staging area (also called the "index") acts as a preview area where you can review and modify your upcoming commit before it becomes permanent history.

This workflow gives you fine-grained control over your commits. You can modify multiple files but commit only some of them. You can even stage parts of a file's changes using `git add -p`. This flexibility helps you create clean, logical commits that tell a coherent story about your project's development.

```bash
# Complete workflow example
# 1. Check current status
git status

# Output example:
# On branch main
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#   modified:   src/main.py
#   modified:   src/utils.py
# 
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#   src/new_feature.py

# 2. Review changes before staging
git diff                    # View all unstaged changes
git diff src/main.py        # View changes in specific file

# 3. Stage changes
git add src/main.py         # Stage specific file
git add src/utils.py        # Stage another file
git add -p src/new_feature.py  # Interactive staging

# 4. Review staged changes
git diff --staged           # View all staged changes
git diff --cached           # Same as --staged

# 5. Commit staged changes
git commit -m "Implement user authentication"

# 6. View commit history
git log                     # Full log
git log --oneline -5        # Last 5 commits, one per line
```

### The Working Directory

The working directory is a single checkout of one version of the project. These files are pulled out of the compressed Git database and placed on disk for you to use or modify. Think of it as your sandbox where you make changes before they become part of Git history.

The working directory contains tracked files (files Git knows about), untracked files (files Git doesn't know about yet), and ignored files (files Git is configured to ignore). Understanding this distinction helps you manage what Git tracks.

```bash
# View working directory status
git status

# Short status format
git status -s

# Example output:
#  M src/main.py        # Modified (not staged)
# M  src/utils.py       # Modified and staged
# ?? src/new_file.py    # Untracked
# !! src/secret.key     # Ignored

# Show ignored files
git status --ignored

# View differences in working directory
git diff

# Discard changes in working directory (dangerous!)
git restore src/main.py
git checkout -- src/main.py    # Older syntax (still works)

# Clean untracked files (preview first!)
git clean -n                   # Dry run - show what would be deleted
git clean -f                   # Force delete untracked files
git clean -fd                  # Delete untracked files and directories
git clean -fx                  # Also delete ignored files
```

### The Staging Area (Index)

The staging area is one of Git's most powerful and distinctive features. It's a file (usually `.git/index`) that stores information about what will go into your next commit. The staging area lets you craft commits carefully, including only the changes you want, even if you've made many other changes.

Think of the staging area as a loading dock. You're preparing a shipment (commit) and the staging area is where you gather items before they're loaded onto the truck. You can add items, remove them, or modify them before finalizing the shipment.

```bash
# Add changes to staging area
git add file.txt              # Add specific file
git add .                     # Add all changes in current directory
git add -A                    # Add all changes in entire repo
git add -u                    # Add all tracked files that changed
git add -p                    # Patch mode - review each hunk

# Interactive staging
git add -i                    # Interactive mode with menu

# View what's staged
git diff --staged
git diff --cached             # Same as --staged

# Unstage files (remove from staging area)
git restore --staged file.txt
git reset HEAD file.txt       # Older syntax

# View staged files
git ls-files --stage

# Stage parts of a file (patch mode)
git add -p filename.txt

# Example patch session:
# Stage this hunk [y,n,q,a,d,e,?]?
# y - stage this hunk
# n - do not stage this hunk
# q - quit; do not stage this hunk or any remaining
# a - stage this hunk and all later hunks in the file
# d - do not stage this hunk or any later hunks in the file
# e - manually edit the current hunk
# ? - print help
```

### Viewing Differences

The `git diff` command is your primary tool for examining changes. It shows differences between various states: working directory vs staging area, staging area vs last commit, or between any two commits. Understanding diff output is essential for reviewing changes before committing.

```bash
# Basic diff commands
git diff                      # Working directory vs staging area
git diff --staged             # Staging area vs last commit
git diff HEAD                 # Working directory vs last commit
git diff HEAD~1 HEAD          # Between two commits

# Diff specific files
git diff -- path/to/file.txt
git diff HEAD -- path/to/file.txt

# Diff statistics only
git diff --stat
git diff --stat HEAD~5 HEAD

# Side-by-side diff (in terminal)
git diff --color-words
git diff --word-diff

# Show only names of changed files
git diff --name-only
git diff --name-only HEAD~1 HEAD

# Show renames
git diff -M                   # Detect renamed files
git diff -M --stat            # Show rename statistics

# Compare branches
git diff main feature-branch
git diff main...feature-branch  # Only changes on feature-branch

# Compare specific commits
git diff abc123 def456

# Using difftool (external diff viewer)
git difftool
git difftool --tool=vimdiff   # Use specific tool
```

### The .gitignore File

The `.gitignore` file specifies intentionally untracked files that Git should ignore. This is crucial for keeping generated files, sensitive information, and IDE-specific files out of your repository. A well-crafted `.gitignore` keeps your repository clean and avoids committing unnecessary files.

```bash
# .gitignore syntax examples

# Ignore all .log files
*.log

# But keep important.log even if it's a .log file
!important.log

# Ignore all files in any build directory
build/

# Ignore all .txt files in doc directory
doc/*.txt

# Ignore all .txt files anywhere under doc/
doc/**/*.txt

# Ignore files starting with a tilde (temp files)
*~

# Ignore OS generated files
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Ignore IDE files
.vscode/
.idea/
*.swp
*.swo

# Ignore build outputs
bin/
obj/
dist/
*.exe
*.dll

# Ignore dependency directories
node_modules/
vendor/
packages/

# Ignore environment files with secrets
.env
.env.local
.env.*.local
*.pem
*.key

# Ignore compiled Python files
__pycache__/
*.py[cod]
*$py.class

# Check what's being ignored
git check-ignore -v filename

# Show all ignored files
git status --ignored
git ls-files --others --ignored --exclude-standard
```

### Global gitignore

For files that should always be ignored across all your projects (like OS or IDE files), you can set up a global gitignore file.

```bash
# Create global gitignore file
touch ~/.gitignore_global

# Configure Git to use it
git config --global core.excludesfile ~/.gitignore_global

# Example global gitignore contents:
# .DS_Store
# .idea/
# .vscode/
# *.swp
# *~
```

---

## Chapter 5: Branching and Merging

### Understanding Branches

A branch in Git is simply a lightweight, movable pointer to a commit. The default branch name in Git is `main` (or historically `master`). When you make commits, the current branch pointer automatically moves forward to point to the new commit. Branches are fundamental to Git workflow because they allow you to diverge from the main line of development and continue working without affecting that main line.

What makes Git branches special is their lightweight nature. Unlike other VCS where branching involves copying entire directories, Git branches are just 41-byte files containing the SHA-1 hash of the commit they point to. This makes creating, switching, and deleting branches nearly instantaneous, regardless of repository size.

```
Branch Visualization:

Initial state:
main → A ← B ← C

After creating feature branch:
main → A ← B ← C
             ↑
        feature

After commits on both branches:
main    → A ← B ← C ← D
                   ↑
              feature → E ← F

The commits D, E, F are separate lines of development
that can later be merged together.
```

### Branch Operations

```bash
# List branches
git branch              # Local branches
git branch -r           # Remote branches
git branch -a           # All branches (local and remote)
git branch -v           # With last commit info
git branch -vv          # With upstream tracking info

# Create a new branch
git branch feature-login        # Create branch at current commit
git branch feature-login abc123 # Create branch at specific commit
git branch feature-login main   # Create branch from main

# Switch branches
git checkout feature-login      # Switch to existing branch
git switch feature-login        # Modern way to switch (Git 2.23+)
git checkout -b feature-login   # Create and switch in one command
git switch -c feature-login     # Modern create and switch

# Create branch from remote
git checkout -b feature-login origin/feature-login
git switch -c feature-login origin/feature-login

# Rename branches
git branch -m old-name new-name     # Rename branch
git branch -m new-name              # Rename current branch

# Delete branches
git branch -d feature-login         # Safe delete (checks for unmerged changes)
git branch -D feature-login         # Force delete
git push origin --delete feature-login  # Delete remote branch

# Track remote branch
git branch --track feature-login origin/feature-login
git branch -u origin/feature-login  # Set upstream for current branch
```

### Branching Workflows

Different branching strategies work for different teams and projects. Understanding common patterns helps you choose the right approach for your situation.

```bash
# Feature branch workflow
# Create a branch for each feature/bugfix
git checkout main
git pull origin main
git checkout -b feature/user-authentication

# Work on the feature
git add .
git commit -m "Add login form"
git add .
git commit -m "Add authentication logic"
git add .
git commit -m "Add session management"

# Push feature branch to remote
git push -u origin feature/user-authentication

# After PR is merged, clean up
git checkout main
git pull origin main
git branch -d feature/user-authentication
git push origin --delete feature/user-authentication

# Hotfix workflow
git checkout main
git checkout -b hotfix/critical-security-fix
# ... fix the issue ...
git commit -am "Fix critical security vulnerability"
git push -u origin hotfix/critical-security-fix
# Merge to main and any release branches
```

### Understanding Merging

Merging is the process of combining changes from different branches. When you merge, Git tries to automatically combine the changes. If the same lines were modified differently in both branches, Git can't automatically resolve it, resulting in a merge conflict that you must resolve manually.

There are two main types of merges: fast-forward merges (when there's a linear path) and three-way merges (when branches have diverged). Understanding these helps you predict merge behavior and choose the right approach.

```
Fast-Forward Merge:

Before merge:
main    → A ← B
             ↑
feature → C ← D

After fast-forward merge (git merge feature):
main    → A ← B ← C ← D
                   ↑
              feature

The main pointer simply moved forward.
No merge commit is created.


Three-Way Merge:

Before merge:
main    → A ← B ← C
             
feature → A ← D ← E

After three-way merge:
main    → A ← B ← C ←─┐
                      ↓ M (merge commit)
feature → A ← D ← E ←─┘

A new merge commit M is created with two parents.
```

```bash
# Basic merge operations
git checkout main          # Switch to target branch
git merge feature-login    # Merge feature into current branch

# Fast-forward only (fail if not possible)
git merge --ff-only feature-login

# No fast-forward (always create merge commit)
git merge --no-ff feature-login

# Merge with message
git merge feature-login -m "Merge feature-login into main"

# Abort a merge (if there are conflicts)
git merge --abort

# Check if branches are merged
git branch --merged main      # Branches merged into main
git branch --no-merged main   # Branches not merged into main

# Squash merge (combine all commits into one)
git merge --squash feature-login
git commit -m "Add login feature"
```

### Handling Merge Conflicts

Merge conflicts occur when Git cannot automatically resolve differences between branches. While conflicts can be intimidating, they're a normal part of collaborative development. Understanding how to resolve them is an essential Git skill.

```bash
# When a merge conflict occurs, Git marks the conflicting areas
# Example of a conflicted file:

# <<<<<<< HEAD
# console.log("This is from the current branch");
# =======
# console.log("This is from the branch being merged");
# >>>>>>> feature-branch

# The markers are:
# <<<<<<< HEAD - Start of current branch's changes
# ======= - Separator
# >>>>>>> branch-name - End of incoming branch's changes

# View conflicted files
git status

# View conflicts
git diff

# Resolve conflicts manually or using tools
# Option 1: Edit file directly, remove markers, keep desired code

# Option 2: Use merge tools
git mergetool               # Opens configured merge tool
git mergetool --tool=vimdiff

# Option 3: Accept one side entirely
git checkout --ours filename.txt      # Keep current branch version
git checkout --theirs filename.txt    # Keep incoming branch version

# After resolving conflicts
git add resolved-file.txt
git commit -m "Merge feature-branch and resolve conflicts"

# View merge base (common ancestor)
git merge-base main feature-branch

# Three-way diff during conflict
git checkout --conflict=diff3 filename.txt
```

### Advanced Merge Strategies

Git supports multiple merge strategies for different scenarios. Understanding these strategies helps you choose the right approach for complex merging situations.

```bash
# Recursive merge (default)
git merge feature-branch -s recursive

# Octopus merge (merge multiple branches at once)
git merge feature-a feature-b feature-c

# Ours merge (keep current branch, ignore incoming)
git merge -s ours feature-branch
# Useful when you want to mark branches as merged
# but discard their changes

# Subtree merge (merge a repo as a subdirectory)
git merge -s subtree repo-branch

# Strategy options with recursive
git merge -X ours feature-branch      # Prefer our version on conflict
git merge -X theirs feature-branch    # Prefer their version on conflict
git merge -X ignore-space-change feature-branch
```

---

## Chapter 6: Remote Repositories and GitHub

### Understanding Remote Repositories

Remote repositories are versions of your project hosted on the Internet or network somewhere. They allow you to collaborate with others by pushing your changes to a shared location and pulling others' changes to your local repository. Git supports multiple remotes, enabling you to push to different servers for different purposes (e.g., GitHub for collaboration, a private server for backup).

When you clone a repository, Git automatically creates a remote named `origin` pointing to the URL you cloned from. You can add more remotes as needed, rename them, or change their URLs. Understanding remotes is essential for collaboration and backup strategies.

```bash
# View remotes
git remote                    # List remote names
git remote -v                 # List remote names and URLs

# Example output:
# origin  https://github.com/user/repo.git (fetch)
# origin  https://github.com/user/repo.git (push)
# upstream  https://github.com/original/repo.git (fetch)
# upstream  https://github.com/original/repo.git (push)

# Add a remote
git remote add origin https://github.com/user/repo.git
git remote add upstream https://github.com/original/repo.git

# Rename a remote
git remote rename old-name new-name

# Remove a remote
git remote remove remote-name

# Change remote URL
git remote set-url origin https://github.com/user/new-repo.git

# Get detailed remote info
git remote show origin

# Prune deleted remote branches
git remote prune origin
```

### Fetching and Pulling

Fetching downloads data from a remote repository but doesn't modify your working directory. It updates your remote-tracking branches (like `origin/main`), letting you see what others have pushed without affecting your local work. Pulling is fetch plus merge—it downloads updates and immediately tries to merge them into your current branch.

```bash
# Fetch from remote
git fetch origin                    # Fetch from origin
git fetch --all                     # Fetch from all remotes
git fetch origin main               # Fetch specific branch
git fetch --prune origin            # Fetch and prune deleted branches

# Pull (fetch + merge)
git pull origin main                # Pull specific branch
git pull                            # Pull from tracked upstream

# Pull with rebase (cleaner history)
git pull --rebase origin main
git config --global pull.rebase true  # Make rebase default

# View fetched changes before merging
git fetch origin
git log HEAD..origin/main           # See what would be merged
git diff HEAD..origin/main          # See the diff

# Merge fetched changes
git merge origin/main
```

### Pushing Changes

Pushing sends your local commits to a remote repository. This is how you share your work with others and contribute to collaborative projects. The first push of a new branch requires setting up tracking; subsequent pushes can be done with just `git push`.

```bash
# Push to remote
git push origin main                # Push main to origin
git push                            # Push current branch to its upstream

# First push with tracking
git push -u origin feature-branch   # Push and set upstream
git push --set-upstream origin feature-branch

# Force push (dangerous - use carefully)
git push --force origin main        # Force push
git push --force-with-lease origin main  # Safer force push

# Push all branches
git push --all origin

# Push tags
git push origin v1.0.0              # Push specific tag
git push --tags                     # Push all tags

# Delete remote branch
git push origin --delete feature-branch

# Push to multiple remotes
git remote set-url --add --push origin https://github.com/user/repo1.git
git remote set-url --add --push origin https://github.com/user/repo2.git
```

### Understanding Remote-Tracking Branches

Remote-tracking branches are references to the state of remote branches. They're local references that you can't move directly—Git moves them whenever you fetch from the remote. They take the form `<remote>/<branch>` (e.g., `origin/main`).

```bash
# View remote-tracking branches
git branch -r

# View all branches (local and remote)
git branch -a

# View remote branch details
git show origin/main

# Create local branch from remote
git checkout -b local-branch origin/remote-branch
git switch -c local-branch origin/remote-branch

# Track a remote branch
git branch --track feature origin/feature
git branch -u origin/feature existing-branch

# View tracking relationships
git branch -vv

# Check what will be pushed/pulled
git diff main origin/main           # Difference between local and remote
git cherry -v origin/main           # Commits not yet pushed
```

---

## Chapter 7: GitHub Fundamentals

### What is GitHub?

GitHub is a web-based platform that hosts Git repositories and provides collaboration features for software development. While Git handles version control, GitHub adds social coding features: pull requests, issues, project boards, actions, and more. GitHub has become the de facto standard for open-source collaboration and is used by millions of developers worldwide.

GitHub extends Git with features that facilitate collaboration: code review through pull requests, issue tracking for bugs and features, project management with boards and milestones, continuous integration with Actions, and social features like starring, watching, and forking repositories.

### Creating and Managing Repositories

```bash
# Create a new repository on GitHub via CLI
gh repo create my-project --public
gh repo create my-project --private
gh repo create my-project --public --clone  # Create and clone

# Create from existing local repo
git init
git add .
git commit -m "Initial commit"
gh repo create my-project --public --source=. --remote=origin
git push -u origin main

# Clone a repository
gh repo clone user/repo
git clone https://github.com/user/repo.git

# Fork a repository (via web or CLI)
gh repo fork user/repo
gh repo fork user/repo --clone  # Fork and clone

# View repository info
gh repo view user/repo
gh repo view --web  # Open in browser
```

### Repository Settings and Configuration

GitHub repositories have many settings that control access, features, and behavior. Understanding these settings helps you configure repositories appropriately for your projects.

```
Key Repository Settings:

1. General Settings:
   - Repository name and description
   - Public/Private visibility
   - Website URL
   - Topics/tags for discoverability

2. Access Control:
   - Collaborators (individual access)
   - Teams (organization access)
   - Branch protection rules
   - Required reviewers

3. Features:
   - Issues (bug tracking)
   - Discussions (community forum)
   - Wiki (documentation)
   - Projects (project management)
   - Pages (static website hosting)

4. Security:
   - Security policy
   - Vulnerability alerts
   - Dependabot configuration
   - Secret scanning

5. Branches:
   - Default branch
   - Branch protection rules
   - Required status checks
```

### GitHub CLI (gh)

The GitHub CLI brings GitHub features to your terminal, allowing you to interact with issues, pull requests, releases, and more without leaving the command line.

```bash
# Install GitHub CLI
# macOS: brew install gh
# Windows: winget install GitHub.cli
# Linux: See https://github.com/cli/cli/blob/trunk/docs/install_linux.md

# Authenticate
gh auth login
gh auth status
gh auth logout

# Repository commands
gh repo create
gh repo clone
gh repo fork
gh repo view
gh repo list
gh repo delete

# Issue commands
gh issue create
gh issue list
gh issue view
gh issue close
gh issue comment

# Pull request commands
gh pr create
gh pr list
gh pr view
gh pr checkout
gh pr merge
gh pr review

# Release commands
gh release create
gh release list
gh release view
gh release download

# Workflow commands
gh workflow list
gh workflow run
gh run view
gh run watch

# Gist commands
gh gist create
gh gist list
gh gist view
```

### Understanding Forks

A fork is a personal copy of another user's repository. Forks let you freely experiment with changes without affecting the original project. Most commonly, forks are used to propose changes to someone else's project (open-source contributions) or to use someone else's project as a starting point for your own.

```bash
# Fork workflow for contributing to open source

# 1. Fork the repository (creates your-name/repo)
gh repo fork original-owner/repo --clone

# 2. Add upstream remote to keep your fork updated
cd repo
git remote add upstream https://github.com/original-owner/repo.git

# 3. Keep your fork updated
git fetch upstream
git checkout main
git merge upstream/main

# 4. Create feature branch
git checkout -b feature/my-contribution

# 5. Make changes and commit
git add .
git commit -m "Add awesome feature"

# 6. Push to your fork
git push origin feature/my-contribution

# 7. Create pull request
gh pr create --repo original-owner/repo \
    --title "Add awesome feature" \
    --body "Description of the changes"

# 8. After PR is merged, clean up
git checkout main
git pull upstream main
git branch -d feature/my-contribution
git push origin --delete feature/my-contribution

# Sync fork after original repo updates
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

### GitHub Repository Structure Best Practices

```
Recommended Repository Structure:

my-project/
├── .github/
│   ├── workflows/          # GitHub Actions workflows
│   │   ├── ci.yml
│   │   └── deploy.yml
│   ├── ISSUE_TEMPLATE/     # Issue templates
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   ├── PULL_REQUEST_TEMPLATE.md
│   ├── CODEOWNERS          # Code ownership rules
│   ├── CONTRIBUTING.md     # Contribution guidelines
│   ├── FUNDING.yml         # Sponsorship info
│   └── SECURITY.md         # Security policy
├── src/                    # Source code
├── tests/                  # Test files
├── docs/                   # Documentation
├── .gitignore
├── LICENSE
├── README.md
├── CHANGELOG.md
└── CODE_OF_CONDUCT.md
```

---

## Chapter 8: Pull Requests and Code Reviews

### Understanding Pull Requests

A pull request (PR) is a proposal to merge changes from one branch into another. It's GitHub's mechanism for code review and discussion before integrating changes. Pull requests enable team members to review code, discuss modifications, request changes, and ultimately approve or reject the proposed changes before they become part of the main codebase.

Pull requests are more than just merge requests—they're collaboration hubs. Each PR contains the code changes, a description, review comments, status checks (CI/CD results), and a discussion thread. This creates a permanent record of why changes were made and how decisions were reached.

### Creating Pull Requests

```bash
# Create PR using GitHub CLI
gh pr create --title "Add user authentication" \
             --body "Implements JWT-based authentication"

# Create PR with more options
gh pr create --title "Add user authentication" \
             --body-file pr_description.md \
             --base main \
             --head feature/auth \
             --assignee @me \
             --label "feature,security" \
             --reviewer user1,user2

# Create PR from fork
gh pr create --repo original-owner/repo \
             --head my-fork:feature-branch

# Create draft PR (work in progress)
gh pr create --draft --title "WIP: Add feature"

# Convert draft to ready for review
gh pr ready PR_NUMBER

# View PR in browser
gh pr view PR_NUMBER --web
```

### Pull Request Templates

Creating a PR template ensures consistent, useful information with every pull request.

```markdown
<!-- .github/PULL_REQUEST_TEMPLATE.md -->

## Description
<!-- Describe your changes in detail -->

## Type of Change
- [ ] Bug fix (non-breaking change fixing an issue)
- [ ] New feature (non-breaking change adding functionality)
- [ ] Breaking change (fix or feature causing existing functionality to change)
- [ ] Documentation update

## Related Issues
<!-- Link to related issues: Fixes #123, Closes #456 -->

## Testing
<!-- Describe how you tested your changes -->

## Screenshots (if applicable)
<!-- Add screenshots here -->

## Checklist
- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes

## Additional Notes
<!-- Any other information that is important to reviewers -->
```

### Code Review Process

Code review is a critical quality gate in software development. It catches bugs, ensures code quality, shares knowledge among team members, and maintains consistency across the codebase.

```bash
# View PR details
gh pr view PR_NUMBER

# Checkout PR locally for review
gh pr checkout PR_NUMBER

# View PR diff
gh pr diff PR_NUMBER

# Add review
gh pr review PR_NUMBER --approve
gh pr review PR_NUMBER --request-changes --body "Please fix..."
gh pr review PR_NUMBER --comment --body "Looks good, just a question..."

# View PR checks
gh pr checks PR_NUMBER

# Watch PR for updates
gh pr watch PR_NUMBER

# Merge PR
gh pr merge PR_NUMBER --merge      # Create merge commit
gh pr merge PR_NUMBER --squash     # Squash commits
gh pr merge PR_NUMBER --rebase     # Rebase and merge

# Close PR without merging
gh pr close PR_NUMBER
gh pr close PR_NUMBER --comment "Closing because..."
```

### Review Best Practices

When reviewing code, consider these aspects:

```
Code Review Checklist:

1. Functionality
   - Does the code do what it's supposed to do?
   - Are edge cases handled?
   - Is error handling appropriate?

2. Code Quality
   - Is the code readable and maintainable?
   - Are names descriptive and consistent?
   - Is there unnecessary complexity?
   - Are there code duplications?

3. Testing
   - Are there appropriate tests?
   - Do tests cover edge cases?
   - Are tests meaningful (not just for coverage)?

4. Performance
   - Are there potential performance issues?
   - Are database queries efficient?
   - Are there memory leaks?

5. Security
   - Is user input validated?
   - Are there potential injection vulnerabilities?
   - Are sensitive data handled properly?

6. Documentation
   - Is the code properly documented?
   - Are complex algorithms explained?
   - Is the API documentation updated?

7. Style
   - Does code follow project conventions?
   - Is formatting consistent?
```

### Review Comments and Suggestions

```markdown
<!-- Review comment examples -->

<!-- Suggesting code changes -->
```suggestion
// Suggested replacement code
const result = processData(input);
```

<!-- Pointing out issues -->
**Issue**: This function is missing error handling.

**Suggestion**: Consider adding try-catch or returning a Result type.

<!-- Asking for clarification -->
**Question**: Why was this approach chosen over the alternative?

<!-- Providing context -->
**Context**: This pattern is used elsewhere in the codebase. Consider refactoring
to a shared utility function for consistency.

<!-- Approval comment -->
Great work! The implementation is clean and well-tested. Just one minor
suggestion inline, but it can be addressed in a follow-up if needed.

🚀 Approved
```

---

## Chapter 9: GitHub Issues and Project Management

### Understanding Issues

GitHub Issues is a tracking system for bugs, feature requests, and tasks. Each issue is a discussion thread where team members can communicate about a specific piece of work. Issues can be labeled, assigned, linked to pull requests, and organized into projects. They're the foundation of project management on GitHub.

```bash
# Create issue
gh issue create --title "Bug: Login fails on mobile" \
                --body "Description of the issue..."

# Create issue with options
gh issue create --title "Feature: Add dark mode" \
                --body "Users have requested dark mode support..." \
                --assignee @me \
                --label "enhancement,UI" \
                --milestone "v2.0" \
                --project "Roadmap"

# List issues
gh issue list
gh issue list --state open
gh issue list --assignee @me
gh issue list --label bug
gh issue list --milestone "v2.0"
gh issue list --search "login"

# View issue
gh issue view ISSUE_NUMBER
gh issue view ISSUE_NUMBER --web

# Close/reopen issue
gh issue close ISSUE_NUMBER
gh issue reopen ISSUE_NUMBER

# Comment on issue
gh issue comment ISSUE_NUMBER --body "I'm working on this."

# Edit issue
gh issue edit ISSUE_NUMBER --title "New title" --body "New body"

# Add labels
gh issue edit ISSUE_NUMBER --add-label "priority-high"
gh issue edit ISSUE_NUMBER --remove-label "priority-low"
```

### Issue Templates

Issue templates ensure that bug reports and feature requests contain all necessary information.

```markdown
<!-- .github/ISSUE_TEMPLATE/bug_report.md -->
---
name: Bug report
about: Report a bug to help us improve
title: '[BUG] '
labels: bug
assignees: ''
---

## Describe the Bug
A clear and concise description of what the bug is.

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

## Expected Behavior
A clear and concise description of what you expected to happen.

## Actual Behavior
A clear and concise description of what actually happened.

## Screenshots
If applicable, add screenshots to help explain your problem.

## Environment
- OS: [e.g. Windows, macOS, Linux]
- Browser: [e.g. Chrome, Firefox, Safari]
- Version: [e.g. 1.0.0]

## Additional Context
Add any other context about the problem here.

## Possible Solution
If you have suggestions on how to fix the bug, please describe them here.
```

```markdown
<!-- .github/ISSUE_TEMPLATE/feature_request.md -->
---
name: Feature request
about: Suggest a new feature
title: '[FEATURE] '
labels: enhancement
assignees: ''
---

## Is Your Feature Request Related to a Problem?
A clear and concise description of what the problem is.

## Describe the Solution You'd Like
A clear and concise description of what you want to happen.

## Describe Alternatives You've Considered
A clear and concise description of any alternative solutions or features you've considered.

## Additional Context
Add any other context or screenshots about the feature request here.

## Impact
How would this feature benefit users?
```

### Labels and Milestones

Labels categorize issues and PRs, making it easy to filter and prioritize work. Milestones group issues into deliverables or time-based goals.

```bash
# Create labels (using GitHub CLI)
gh label create "priority-critical" --color "FF0000" --description "Critical priority"
gh label create "priority-high" --color "FF6600" --description "High priority"
gh label create "priority-medium" --color "FFCC00" --description "Medium priority"
gh label create "priority-low" --color "00FF00" --description "Low priority"

# Common label categories:
# Type: bug, enhancement, feature, documentation, test
# Priority: priority-critical, priority-high, priority-medium, priority-low
# Status: in-progress, blocked, needs-review, needs-testing
# Size: size-small, size-medium, size-large
# Area: backend, frontend, database, API, UI

# List labels
gh label list

# Create milestones
gh milestone create "v1.0" --title "Version 1.0" --description "First release"
gh milestone create "Sprint 1" --due-date "2024-03-01"

# View milestones
gh milestone list

# Add issue to milestone
gh issue edit ISSUE_NUMBER --milestone "v1.0"
```

### GitHub Projects

GitHub Projects provides project management capabilities including Kanban boards, tables, and roadmaps. Projects can span multiple repositories and integrate closely with issues and pull requests.

```
GitHub Projects Features:

1. Board View (Kanban)
   - Columns for status (Backlog, In Progress, Done)
   - Drag and drop items between columns
   - Custom columns for your workflow

2. Table View
   - Spreadsheet-like view of items
   - Sort, filter, group by any field
   - Custom fields for metadata

3. Roadmap View
   - Timeline visualization
   - Date-based planning
   - Milestone tracking

4. Automation
   - Auto-move items when PR opens
   - Auto-close issues when PR merges
   - Custom workflows with Actions

5. Insights
   - Burn-up charts
   - Velocity tracking
   - Cycle time metrics
```

```bash
# Project commands (using GitHub CLI)
gh project create --owner @me --title "Q1 Roadmap"
gh project list --owner @me
gh project view PROJECT_NUMBER

# Add issue to project
gh project item-add PROJECT_NUMBER --url https://github.com/user/repo/issues/123

# List project items
gh project item-list PROJECT_NUMBER

# Edit project item
gh project item-edit --project-id PROJECT_ID --id ITEM_ID --field-id FIELD_ID --value "In Progress"
```

### Linking Issues and Pull Requests

You can link issues to PRs to show relationships and automatically close issues when PRs merge.

```markdown
<!-- Linking keywords in PR/commit messages -->

<!-- Closes the issue when PR is merged -->
Closes #123
Fixes #123
Resolves #123

<!-- References the issue without closing -->
Related to #123
See #123
Ref #123

<!-- Multiple issues -->
Closes #123, #124, #125

<!-- Cross-repository linking -->
Closes owner/repo#123
```

---

## Chapter 10: Git Advanced Commands

### Git Log Advanced Usage

The `git log` command has many options for viewing history in different formats and filtering by various criteria.

```bash
# Basic log formats
git log                        # Full log
git log --oneline              # One line per commit
git log --oneline -10          # Last 10 commits

# Graphical view
git log --graph --oneline --all    # Graph of all branches
git log --graph --oneline --decorate

# Detailed formats
git log --pretty=oneline       # Hash and title
git log --pretty=short         # Hash, title, author, date
git log --pretty=full          # Include committer
git log --pretty=fuller        # Include both author and committer dates
git log --pretty=format:"%h %an %s"  # Custom format

# Custom format examples
git log --pretty=format:"%C(yellow)%h%Creset %s %C(cyan)(%cr)%Creset %C(blue)<%an>%Creset"
# Output: a1b2c3d Fix login bug (2 days ago) <John Doe>

# Format placeholders:
# %H = commit hash
# %h = abbreviated commit hash
# %T = tree hash
# %t = abbreviated tree hash
# %P = parent hashes
# %p = abbreviated parent hashes
# %an = author name
# %ae = author email
# %ad = author date
# %ar = author date, relative
# %cn = committer name
# %ce = committer email
# %cd = committer date
# %s = subject
# %b = body

# Filter by author
git log --author="John"
git log --author="john@example.com"

# Filter by message
git log --grep="bug"
git log --grep="fix" --grep="bug"  # OR logic
git log --grep="fix" --and --grep="bug"  # AND logic

# Filter by date
git log --since="2024-01-01"
git log --until="2024-01-31"
git log --after="2 weeks ago"
git log --before="yesterday"

# Filter by file
git log -- path/to/file.txt
git log -p -- path/to/file.txt    # Show patches
git log --stat -- path/to/file.txt  # Show statistics

# Show file changes
git log --stat              # Show diffstat for each commit
git log --shortstat         # Show summary of changes
git log --name-only         # Show changed files
git log --name-status       # Show changed files with status

# Show merge commits
git log --merges            # Only merge commits
git log --no-merges         # No merge commits

# Show range
git log main..feature       # Commits on feature not on main
git log origin/main..HEAD   # Commits to be pushed

# Show commits by content
git log -S "function_name"  # Commits that added/removed string
git log -G "regex_pattern"  # Commits matching regex
git log -S "bug" --oneline  # Find when "bug" was introduced/removed

# Follow file renames
git log --follow -- path/to/file.txt

# Show blame information
git blame file.txt
git blame -L 10,20 file.txt  # Lines 10-20
git blame -w file.txt        # Ignore whitespace
```

### Git Grep and Search

Git grep searches through tracked files in your repository. It's often faster than system grep because it only searches tracked files and can search specific commits.

```bash
# Basic search
git grep "search_term"

# Search in specific files
git grep "function_name" -- "*.py"
git grep "TODO" -- "*.js" "*.ts"

# Search in specific commit/branch
git grep "bug" main
git grep "bug" HEAD~5

# Show line numbers
git grep -n "search_term"

# Show only filenames
git grep -l "search_term"

# Count matches
git grep -c "search_term"

# Pattern matching
git grep -e "pattern"
git grep -E "regex_pattern"  # Extended regex

# Search with context
git grep -A 5 "function_name"  # 5 lines after
git grep -B 5 "function_name"  # 5 lines before
git grep -C 5 "function_name"  # 5 lines around

# Search in all branches
git grep "term" $(git branch -a --format='%(refname)')

# Find uncommitted changes
git grep "term" --cached  # Search staged files
```

### Git Bisect

Git bisect is a powerful tool for finding which commit introduced a bug. It performs a binary search through your commit history, narrowing down the problematic commit efficiently.

```bash
# Start bisect
git bisect start

# Mark current commit as bad (has bug)
git bisect bad

# Mark known good commit
git bisect good v1.0.0
# Or use commit hash
git bisect good a1b2c3d

# Git will checkout a middle commit
# Test and mark as good or bad
git bisect good   # If bug not present
git bisect bad    # If bug present

# Continue until Git finds the culprit
# Git will show: "a1b2c3d is the first bad commit"

# When done, reset bisect
git bisect reset

# Automated bisect with script
git bisect start
git bisect bad HEAD
git bisect good v1.0.0
git bisect run test.sh  # Script exits 0 for good, non-0 for bad

# Example test script:
#!/bin/bash
npm test  # Run your test suite
# Exit 0 if tests pass (good), non-0 if fail (bad)

# Bisect with skip (for commits that can't be tested)
git bisect skip  # Skip current commit
```

### Git Blame

Git blame shows who modified each line of a file and in which commit. While the name sounds negative, it's actually a valuable tool for understanding code history and finding context.

```bash
# Basic blame
git blame file.txt

# Show email addresses
git blame -e file.txt

# Show specific line range
git blame -L 10,20 file.txt
git blame -L 10,+5 file.txt   # 5 lines starting at 10
git blame -L "/function/",+20 file.txt  # 20 lines after regex match

# Ignore whitespace changes
git blame -w file.txt

# Detect moved lines
git blame -M file.txt         # Detect moved lines
git blame -M -C file.txt      # Detect moved/copied lines

# Show previous version
git blame -C -C -C file.txt   # Try harder to find origin

# Blame specific commit
git blame abc123 file.txt

# Follow renames
git blame --follow file.txt
```

---

## Chapter 11: Git Rebasing and Advanced Merging

### Understanding Rebasing

Rebasing is the process of moving or combining a sequence of commits to a new base commit. Unlike merging, which creates a merge commit, rebasing rewrites the commit history by creating new commits for each original commit. This results in a linear project history that can be cleaner and easier to understand.

Rebasing is powerful but comes with important caveats. Because it rewrites history, you should never rebase commits that have been pushed to a shared repository. The golden rule of rebasing: rebase local commits that haven't been shared, merge commits that have been shared.

```
Rebase vs Merge Visualization:

Original:
main    → A ← B ← C
             ↑
feature → D ← E

After merge:
main    → A ← B ← C ← M (merge commit)
                   ↑
feature → D ← E ← ┘

After rebase (feature onto main):
main    → A ← B ← C
                   ↑
feature → D' ← E'  (new commits with same changes)

Rebase creates new commits D' and E' that apply D and E's
changes on top of C, resulting in a linear history.
```

```bash
# Basic rebase
git checkout feature
git rebase main         # Rebase feature onto main

# Rebase interactive (choose how to handle each commit)
git rebase -i main
git rebase -i HEAD~5    # Rebase last 5 commits

# Interactive rebase commands:
# pick (p)   = use commit
# reword (r) = use commit, but edit the message
# edit (e)   = use commit, but stop for amending
# squash (s) = use commit, but meld into previous commit
# fixup (f)  = like squash, but discard this commit's message
# drop (d)   = remove commit
# exec (x)   = run command
# break (b)  = stop here
# label (l)  = label current HEAD
# reset (t)  = reset HEAD to label
# merge (m)  = create merge commit

# Example interactive rebase:
# pick a1b2c3d Add feature A
# squash e4f5g6h Fix feature A
# pick i7j8k9l Add feature B
# reword m0n1o2p Add feature C
# drop q3r4s5t Debug code

# After squash/fixup, commits become one
# After reword, you can change commit message
# After drop, commit is removed

# Continue rebase after resolving conflicts
git rebase --continue

# Skip current commit (during rebase)
git rebase --skip

# Abort rebase
git rebase --abort

# Rebase onto specific commit
git rebase --onto main feature-old feature-new
# Takes commits from feature-old..feature-new and puts them on main
```

### Squashing Commits

Squashing combines multiple commits into one, creating a cleaner history. This is especially useful before merging a feature branch with many small "WIP" commits.

```bash
# Squash last N commits into one
git rebase -i HEAD~3

# In the editor:
# pick abc1234 First commit
# squash def5678 Second commit  (change 'pick' to 'squash')
# squash ghi9012 Third commit   (change 'pick' to 'squash')
# Save and close

# Git will prompt for the combined commit message

# Squash all commits in a branch
git checkout feature
git rebase -i main

# Change all but first to 'squash' or 'fixup'

# Squash with fixup (uses first commit's message)
git rebase -i --autosquash main
# Use 'fixup!' or 'squash!' prefix in commit messages for autosquash

# Example:
# git commit -m "Add feature"
# git commit -m "fixup! Add feature"  # Will be squashed automatically
```

### Rebase vs Merge: When to Use Each

| Scenario | Recommended Approach | Reason |
|----------|---------------------|--------|
| Local feature branch | Rebase | Clean history before sharing |
| Updating feature with main changes | Rebase | Linear history, easier to review |
| Integrating shared branch | Merge | Preserves shared history |
| Pull request before merge | Rebase | Cleaner commit history |
| Hotfix to production | Merge | Clear audit trail |
| Long-running branch sync | Merge | Avoid repeated conflicts |

```bash
# Best practice: rebase local, merge shared

# Local feature development
git checkout -b feature
# ... make commits ...
git fetch origin
git rebase origin/main  # Keep up to date
# ... more commits ...
git push -u origin feature  # Now it's shared

# After PR review, before merge
git fetch origin
git rebase origin/main  # Update with latest
# Resolve any conflicts
git push --force-with-lease origin feature

# Project maintainer merges:
git checkout main
git merge --no-ff feature  # Create merge commit for history
```

### Advanced Merge Techniques

```bash
# Merge with ours/theirs strategy for specific files
git checkout main
git merge feature
# If there's a conflict in config file and you want to keep main's version:
git checkout --ours config/settings.json
git add config/settings.json
git commit

# Or for entire merge:
git merge -X ours feature   # Auto-resolve with our version
git merge -X theirs feature # Auto-resolve with their version

# Merge with custom driver
# In .git/config or .gitattributes:
# [merge "ours"]
#     name = "Always keep ours"
#     driver = true
# *.txt merge=ours

# Virtual merge base (for complex histories)
git merge-base --octopus branch1 branch2 branch3

# Merge without committing
git merge --no-commit feature
# Review the merge
git merge --abort  # Or git commit to complete

# Merge with verification
git merge --verify-signatures feature  # Verify signed commits
```

---

## Chapter 12: Git Stashing and Cherry-Picking

### Git Stash

Stashing temporarily saves your uncommitted changes so you can switch branches or work on something else. The stash is saved as a commit-like object in the Git object database, and you can apply it back later.

```bash
# Basic stash
git stash                    # Stash all tracked file changes
git stash push -m "WIP: feature"  # Named stash

# Stash including untracked files
git stash -u                 # Include untracked files
git stash --include-untracked

# Stash only specific files
git stash push -m "message" -- path/to/file.txt

# Stash with patch mode
git stash -p                 # Interactively select hunks to stash

# List stashes
git stash list

# Example output:
# stash@{0}: On main: WIP: feature
# stash@{1}: On develop: Experimental changes
# stash@{2}: WIP on main: a1b2c3d Add something

# Show stash details
git stash show               # Show latest stash stats
git stash show -p            # Show latest stash diff
git stash show stash@{1}     # Show specific stash

# Apply stash
git stash apply              # Apply latest stash (keeps stash)
git stash apply stash@{1}    # Apply specific stash
git stash pop                # Apply and remove latest stash

# Apply and handle conflicts
git stash apply
# If there are conflicts, resolve them, then:
git stash drop               # Manually drop if needed

# Drop stash
git stash drop               # Drop latest stash
git stash drop stash@{1}     # Drop specific stash

# Clear all stashes
git stash clear

# Create branch from stash
git stash branch new-branch stash@{0}
# Creates new branch at the commit where stash was created,
# applies the stash, and drops it if successful
```

### Git Cherry-Pick

Cherry-pick applies the changes introduced by some existing commits. This is useful when you want to bring specific commits from one branch to another without merging the entire branch.

```bash
# Cherry-pick a single commit
git cherry-pick abc123

# Cherry-pick multiple commits
git cherry-pick abc123 def456
git cherry-pick abc123..def456  # Range (exclusive start)

# Cherry-pick without committing
git cherry-pick -n abc123
git cherry-pick --no-commit abc123

# Cherry-pick with custom commit message
git cherry-pick -e abc123  # Edit message before committing
git cherry-pick -m "Apply fix from main" abc123

# Cherry-pick and preserve original author
git cherry-pick -x abc123  # Appends original commit hash to message

# Handle cherry-pick conflicts
git cherry-pick abc123
# ... conflicts occur ...
git status                  # See conflicted files
# Resolve conflicts
git add .
git cherry-pick --continue
# Or abort
git cherry-pick --abort

# Cherry-pick from another repository
git remote add other-repo https://github.com/user/repo.git
git fetch other-repo
git cherry-pick other-repo/main

# Cherry-pick range of commits
git cherry-pick main~3..main  # Last 3 commits from main
```

### When to Use Stash and Cherry-Pick

```
Use Cases for Stash:

1. Switching branches temporarily
   - Working on feature A, need to fix bug in main
   - Stash, switch, fix, switch back, apply

2. Pulling changes while having local modifications
   - Local changes conflict with pull
   - Stash, pull, apply stash

3. Saving work in progress
   - Not ready to commit
   - Stash with descriptive message

4. Testing with clean working directory
   - Stash changes to test something
   - Apply stash to continue work


Use Cases for Cherry-Pick:

1. Hotfix backporting
   - Fix applied to main
   - Cherry-pick to release branch

2. Selective feature adoption
   - Feature branch has many commits
   - Only want specific improvements

3. Recovering lost commits
   - Commit made on wrong branch
   - Cherry-pick to correct branch

4. Conflict-free integration
   - Avoid merge complexities
   - Apply specific changes cleanly
```

```bash
# Practical example: Hotfix backport

# Bug was fixed on main
git checkout main
git log --oneline -5
# abc1234 Fix critical security bug

# Backport to release branch
git checkout release/v1.0
git cherry-pick abc1234
git push origin release/v1.0

# Practical example: Commit to wrong branch
git checkout feature-a
# Oops, made commit that should be on feature-b
git log --oneline -1
# def5678 Feature B work (accidentally on feature-a)

# Cherry-pick to correct branch
git checkout feature-b
git cherry-pick def5678
git checkout feature-a
git reset HEAD~1  # Remove from feature-a
```

---

## Chapter 13: Git Reset, Revert, and Undo Operations

### Understanding Reset

Git reset moves the HEAD pointer to a specified commit, optionally modifying the index and working directory. The behavior depends on the mode used. Understanding reset is crucial for undoing operations and manipulating commit history.

```
Reset Modes:

--soft
- Moves HEAD pointer
- Staging area unchanged
- Working directory unchanged
- Use: Redo commit with different message/staging

--mixed (default)
- Moves HEAD pointer
- Resets staging area
- Working directory unchanged
- Use: Unstage commits, keep changes

--hard
- Moves HEAD pointer
- Resets staging area
- Resets working directory
- Use: Completely discard commits (dangerous!)

--keep
- Moves HEAD pointer
- Resets staging area
- Working directory reset only if no local changes
- Use: Reset without losing local changes
```

```bash
# Soft reset (keeps changes staged)
git reset --soft HEAD~1     # Undo last commit, keep staged
git reset --soft abc123     # Reset to specific commit, stage changes

# Mixed reset (default - unstage changes)
git reset HEAD~1            # Undo last commit, unstage changes
git reset abc123            # Reset to commit, changes in working dir
git reset HEAD              # Unstage all staged changes
git reset -- file.txt       # Unstage specific file

# Hard reset (discard all changes)
git reset --hard HEAD~1     # Undo last commit, discard changes
git reset --hard abc123     # Reset to commit, discard everything
git reset --hard origin/main  # Reset to match remote

# Keep reset (abort if local changes would be lost)
git reset --keep HEAD~1

# Reset specific file to specific commit
git checkout abc123 -- path/to/file.txt
git restore --source=abc123 path/to/file.txt  # Modern syntax

# View what would be reset
git diff HEAD HEAD~1         # Preview changes before reset
```

### Git Revert

Unlike reset, which moves the HEAD pointer, revert creates a new commit that undoes the changes from a previous commit. This is safer for shared history because it doesn't rewrite existing commits.

```bash
# Revert the last commit
git revert HEAD

# Revert specific commit
git revert abc123

# Revert multiple commits
git revert abc123 def456

# Revert range
git revert main~3..main      # Revert last 3 commits on main

# Revert without committing
git revert -n abc123
git revert --no-commit abc123

# Edit commit message before reverting
git revert -e abc123

# Revert merge commit
git revert -m 1 abc123       # -m 1 keeps first parent's changes

# Abort revert
git revert --abort

# Continue revert after resolving conflicts
git revert --continue
```

### Undo Operations Comparison

| Operation | Use Case | Affects History | Safe for Shared Branches |
|-----------|----------|-----------------|-------------------------|
| `git reset --soft` | Redo commit with different staging | Rewrites | No |
| `git reset --mixed` | Unstage changes, keep working | Rewrites | No |
| `git reset --hard` | Discard everything | Rewrites | No |
| `git revert` | Undo commit safely | New commit | Yes |
| `git commit --amend` | Fix last commit | Rewrites last | No |

```bash
# Scenario: Undo last local commit (not pushed)
git reset --soft HEAD~1
# Make changes, stage, commit again

# Scenario: Undo last shared commit (already pushed)
git revert HEAD
git push origin main

# Scenario: Remove file from last commit
git reset HEAD~1 -- file.txt
git commit --amend --no-edit

# Scenario: Fix commit message
git commit --amend -m "New message"

# Scenario: Add forgotten file to last commit
git add forgotten-file.txt
git commit --amend --no-edit

# Scenario: Completely discard all local changes
git checkout -- .              # Discard working directory changes
git clean -fd                  # Remove untracked files
# Or
git reset --hard HEAD
git clean -fd

# Scenario: Restore deleted file
git checkout HEAD -- deleted-file.txt
git restore deleted-file.txt   # Modern syntax
```

### Reflog: Your Safety Net

The reflog records when the tips of branches and other references were updated. It's your safety net when you've made a mistake with reset or rebase.

```bash
# View reflog
git reflog
git reflog show HEAD

# Example output:
# abc1234 HEAD@{0}: reset: moving to HEAD~1
# def5678 HEAD@{1}: commit: Add feature
# ghi9012 HEAD@{2}: checkout: moving from feature to main
# ...

# View reflog for specific branch
git reflog show feature-branch

# Recover from hard reset
git reset --hard HEAD@{1}   # Go back to previous state

# Recover deleted branch
git reflog
# Find commit where branch was deleted
git checkout -b recovered-branch abc123

# Recover from bad rebase
git reflog
git reset --hard HEAD@{5}   # Go back to before rebase

# Expire reflog entries (garbage collection)
git reflog expire --expire=30.days.ago --all
git gc --prune=now
```

---

## Chapter 14: Git Hooks and Automation

### Understanding Git Hooks

Git hooks are scripts that run automatically at specific points in Git's workflow. They allow you to customize Git's behavior, enforce policies, and automate tasks. Hooks are stored in `.git/hooks/` and can be client-side (run on your machine) or server-side (run on the server receiving pushes).

```
Client-Side Hooks:

Pre-commit:
- Runs before commit message is entered
- Use: Check code style, run tests, lint

Prepare-commit-msg:
- Runs before commit message editor opens
- Use: Populate message with template

Commit-msg:
- Runs after commit message is entered
- Use: Validate commit message format

Post-commit:
- Runs after commit is completed
- Use: Notification, logging

Pre-rebase:
- Runs before rebase
- Use: Prevent rebasing pushed commits

Post-rewrite:
- Runs after commits are rewritten (rebase, amend)
- Use: Cleanup after history rewrite

Post-checkout:
- Runs after checkout
- Use: Setup environment, npm install

Post-merge:
- Runs after merge
- Use: Install dependencies

Pre-push:
- Runs before push
- Use: Run tests, prevent pushing failing code

Pre-auto-gc:
- Runs before automatic garbage collection
- Use: Prevent GC in certain situations


Server-Side Hooks:

Pre-receive:
- Runs when receiving push
- Use: Enforce policies, reject invalid pushes

Update:
- Runs for each branch being updated
- Use: Per-branch policies

Post-receive:
- Runs after push is accepted
- Use: Deploy, notification, CI trigger
```

### Creating Hooks

```bash
# Hook files are in .git/hooks/
# They must be executable

# List available hook templates
ls .git/hooks/

# Example: Pre-commit hook
cat > .git/hooks/pre-commit << 'EOF'
#!/bin/bash

# Run tests before commit
echo "Running tests..."
npm test

if [ $? -ne 0 ]; then
    echo "Tests failed. Commit aborted."
    exit 1
fi

# Check for console.log
if git diff --cached | grep -q "console.log"; then
    echo "Found console.log. Please remove before committing."
    exit 1
fi

echo "Pre-commit checks passed!"
exit 0
EOF

chmod +x .git/hooks/pre-commit

# Example: Commit-msg hook (validate format)
cat > .git/hooks/commit-msg << 'EOF'
#!/bin/bash

commit_msg=$(cat "$1")

# Check commit message format: type(scope): message
if ! echo "$commit_msg" | grep -qE "^(feat|fix|docs|style|refactor|test|chore)(\(.+\))?: .{10,}"; then
    echo "Invalid commit message format!"
    echo "Format: type(scope): message (at least 10 chars)"
    echo "Types: feat, fix, docs, style, refactor, test, chore"
    echo "Example: feat(auth): add JWT authentication"
    exit 1
fi

exit 0
EOF

chmod +x .git/hooks/commit-msg

# Example: Pre-push hook
cat > .git/hooks/pre-push << 'EOF'
#!/bin/bash

protected_branch="main"
current_branch=$(git branch --show-current)

if [ "$current_branch" = "$protected_branch" ]; then
    echo "Direct push to $protected_branch is not allowed!"
    echo "Please create a feature branch and submit a pull request."
    exit 1
fi

exit 0
EOF

chmod +x .git/hooks/pre-push
```

### Shared Hooks with Husky

Husky is a popular tool for managing Git hooks in a way that can be shared across the team. Hooks defined in package.json are automatically set up when team members run npm install.

```bash
# Install Husky
npm install husky --save-dev

# Initialize Husky
npx husky init

# Add pre-commit hook
echo "npm test" > .husky/pre-commit

# Add commit-msg hook
echo "npx commitlint --edit \$1" > .husky/commit-msg

# Husky configuration in package.json
{
  "scripts": {
    "prepare": "husky install"
  }
}

# Example hooks with lint-staged
npm install lint-staged --save-dev

# package.json
{
  "lint-staged": {
    "*.js": "eslint --fix",
    "*.css": "stylelint --fix",
    "*.{js,css,md}": "prettier --write"
  }
}

# .husky/pre-commit
#!/bin/bash
. "$(dirname "$0")/_/husky.sh"
npx lint-staged
```

### Git Hook Templates

You can create hook templates that are automatically copied to new repositories.

```bash
# Set template directory
git config --global init.templatedir ~/.git-templates

# Create template directory
mkdir -p ~/.git-templates/hooks

# Create hook template
cat > ~/.git-templates/hooks/pre-commit << 'EOF'
#!/bin/bash
# Your default pre-commit checks
EOF

chmod +x ~/.git-templates/hooks/pre-commit

# Apply to existing repository
git init  # Re-initialize to copy templates
```

---

## Chapter 15: Git Aliases and Custom Commands

### Git Aliases

Aliases are shortcuts for Git commands. They can simplify complex commands, create new workflows, and save typing. Aliases can be defined globally or per-repository.

```bash
# Basic aliases
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
git config --global alias.visual 'log --oneline --graph --all'

# Useful aliases for common operations
git config --global alias.lg "log --oneline --graph --all --decorate"
git config --global alias.lp "log --oneline --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'"
git config --global alias.wdiff "diff --color-words"
git config --global alias.amend "commit --amend --no-edit"
git config --global alias.undo "reset HEAD~1 --mixed"
git config --global alias.stash-all "stash save --include-untracked"
git config --global alias.pushf "push --force-with-lease"
git config --global alias.contributors "shortlog --summary --numbered"

# Alias for viewing conflicted files
git config --global alias.conflicts "diff --name-only --diff-filter=U"

# Alias for viewing untracked files
git config --global alias.untracked "ls-files --others --exclude-standard"

# Alias to discard all local changes
git config --global alias.discard "!git checkout -- . && git clean -fd"

# Complex alias with shell command (use !)
git config --global alias.current-branch "!git rev-parse --abbrev-ref HEAD"
git config --global alias.all-branches "!git for-each-ref --sort=-committerdate --format='%(refname:short)' refs/heads/"

# Alias for creating backup branch
git config --global alias.backup "!f() { git branch backup-$(date +%Y%m%d-%H%M%S) $1; }; f"

# Alias for interactive rebase
git config --global alias.ri "rebase -i"

# Alias for finding who to blame
git config --global alias.whatchanged-whom '!git log --format="%an" -- "$1" | sort | uniq -c | sort -rn'

# View all aliases
git config --global --get-regexp alias

# Edit aliases directly
git config --global --edit
```

### Custom Git Commands

You can create custom Git commands by creating scripts named `git-<name>` in your PATH. Git will then recognize `git <name>` as a command.

```bash
# Create a custom git command
# File: ~/bin/git-current-branch

#!/bin/bash
# Shows current branch name
git rev-parse --abbrev-ref HEAD

# Make executable
chmod +x ~/bin/git-current-branch

# Now you can use:
git current-branch

# More complex custom command: git-cleanup
#!/bin/bash
# File: ~/bin/git-cleanup
# Removes merged branches and prunes remote references

echo "Fetching and pruning remote branches..."
git fetch --prune

echo "Removing local branches merged into main..."
git branch --merged main | grep -v "^\*\|main\|master\|develop" | xargs -n 1 git branch -d

echo "Removing local branches merged into develop..."
git branch --merged develop | grep -v "^\*\|main\|master\|develop" | xargs -n 1 git branch -d

echo "Cleanup complete!"

# Custom command: git-stats
#!/bin/bash
# File: ~/bin/git-stats
# Shows repository statistics

echo "=== Repository Statistics ==="
echo "Total commits: $(git rev-list --count HEAD)"
echo "Total contributors: $(git shortlog -sn | wc -l)"
echo "Total branches: $(git branch -a | wc -l)"
echo "Total tags: $(git tag | wc -l)"
echo ""
echo "Top contributors:"
git shortlog -sn | head -5
echo ""
echo "Most changed files:"
git log --pretty=format: --name-only | sort | uniq -c | sort -rg | head -5

# Custom command: git-start
#!/bin/bash
# File: ~/bin/git-start
# Starts a new feature branch

if [ -z "$1" ]; then
    echo "Usage: git start <branch-name>"
    exit 1
fi

git checkout main
git pull origin main
git checkout -b "feature/$1"
echo "Created and switched to feature/$1"
```

### Useful Alias Collections

```bash
# Add to ~/.gitconfig

[alias]
    # Basic shortcuts
    st = status
    co = checkout
    br = branch
    ci = commit
    df = diff
    dc = diff --cached
    
    # Log aliases
    lg = log --oneline --graph --all
    lp = log --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
    ll = log --pretty=format:'%C(yellow)%h%Cred%d %Creset%s%Cblue [%cn]' --decorate --numstat
    
    # Branch aliases
    bd = branch -d
    bD = branch -D
    ba = branch -a
    bm = branch --merged
    
    # Diff aliases
    dw = diff --word-diff
    ds = diff --staged
    dn = diff --name-only
    
    # Stash aliases
    sl = stash list
    sa = stash apply
    sp = stash pop
    ss = stash save
    
    # Undo aliases
    undo = reset HEAD~1 --mixed
    unstage = reset HEAD --
    discard = checkout --
    
    # Sync aliases
    pom = push origin main
    fom = fetch origin main
    rom = rebase origin/main
    
    # Info aliases
    who = shortlog -sn
    what = diff --stat
    where = rev-parse --abbrev-ref HEAD
    when = log --format='%cd' --date=short -1
    
    # Cleanup aliases
    cleanup = "!git branch --merged | grep -v '\\*\\|main\\|master\\|develop' | xargs -n 1 git branch -d"
    prune-all = "!git remote | xargs git remote prune"
```

---

## Chapter 16: GitHub Actions and CI/CD

### Understanding GitHub Actions

GitHub Actions is GitHub's continuous integration and continuous deployment (CI/CD) platform. It allows you to automate your software development workflows directly in your GitHub repository. Workflows are defined in YAML files and can be triggered by various events like pushes, pull requests, or scheduled times.

Workflows are composed of jobs, which run on virtual machines (runners), and jobs contain steps that execute commands or actions. Actions are reusable units of code that can be shared across workflows and repositories.

```
GitHub Actions Hierarchy:

Workflow
├── Job 1 (runs-on: ubuntu-latest)
│   ├── Step 1: Checkout code
│   ├── Step 2: Setup Node.js
│   ├── Step 3: Install dependencies
│   ├── Step 4: Run tests
│   └── Step 5: Build
├── Job 2 (depends on Job 1)
│   ├── Step 1: Deploy to staging
│   └── Step 2: Run E2E tests
└── Job 3 (depends on Job 2)
    └── Step 1: Deploy to production
```

### Creating Workflows

```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    
    strategy:
      matrix:
        node-version: [18.x, 20.x]
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v4
    
    - name: Setup Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v4
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Run linter
      run: npm run lint
    
    - name: Run tests
      run: npm test -- --coverage
    
    - name: Build
      run: npm run build
    
    - name: Upload coverage
      uses: codecov/codecov-action@v3
      with:
        token: ${{ secrets.CODECOV_TOKEN }}

  # .NET CI Workflow
  dotnet-build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Setup .NET
      uses: actions/setup-dotnet@v4
      with:
        dotnet-version: '8.0.x'
    
    - name: Restore dependencies
      run: dotnet restore
    
    - name: Build
      run: dotnet build --configuration Release --no-restore
    
    - name: Test
      run: dotnet test --configuration Release --no-build --verbosity normal
```

### Workflow Triggers

```yaml
# Trigger on push to any branch
on: push

# Trigger on push to specific branches
on:
  push:
    branches: [ main, develop ]

# Trigger on pull request
on:
  pull_request:
    branches: [ main ]

# Trigger on schedule (cron syntax)
on:
  schedule:
    - cron: '0 0 * * *'  # Every day at midnight UTC

# Trigger on multiple events
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  workflow_dispatch:  # Manual trigger
  release:
    types: [ published ]

# Trigger on file paths
on:
  push:
    paths:
      - 'src/**'
      - 'tests/**'
    paths-ignore:
      - 'docs/**'
      - '*.md'

# Trigger on tags
on:
  push:
    tags:
      - 'v*'

# Using environment variables in triggers
on:
  workflow_dispatch:
    inputs:
      environment:
        description: 'Environment to deploy to'
        required: true
        default: 'staging'
        type: choice
        options:
          - staging
          - production
```

### Advanced Workflow Features

```yaml
# .github/workflows/deploy.yml
name: Deploy

on:
  push:
    branches: [ main ]

env:
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  build-and-push:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
    
    outputs:
      image-tag: ${{ steps.meta.outputs.tags }}
    
    steps:
    - name: Checkout
      uses: actions/checkout@v4
    
    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v3
    
    - name: Log in to Container Registry
      uses: docker/login-action@v3
      with:
        registry: ${{ env.REGISTRY }}
        username: ${{ github.actor }}
        password: ${{ secrets.GITHUB_TOKEN }}
    
    - name: Extract metadata
      id: meta
      uses: docker/metadata-action@v5
      with:
        images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}
        tags: |
          type=sha
          type=ref,event=branch
          type=semver,pattern={{version}}
    
    - name: Build and push
      uses: docker/build-push-action@v5
      with:
        context: .
        push: true
        tags: ${{ steps.meta.outputs.tags }}
        labels: ${{ steps.meta.outputs.labels }}
        cache-from: type=gha
        cache-to: type=gha,mode=max

  deploy:
    needs: build-and-push
    runs-on: ubuntu-latest
    environment: production
    
    steps:
    - name: Deploy to production
      run: |
        echo "Deploying ${{ needs.build-and-push.outputs.image-tag }}"
        # Add deployment commands

  notify:
    needs: [build-and-push, deploy]
    runs-on: ubuntu-latest
    if: always()
    
    steps:
    - name: Send Slack notification
      uses: 8398a7/action-slack@v3
      with:
        status: ${{ job.status }}
        fields: repo,message,commit,author,action,eventName,ref,workflow
      env:
        SLACK_WEBHOOK_URL: ${{ secrets.SLACK_WEBHOOK }}
```

### Secrets and Environment Variables

```yaml
# Using secrets
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - name: Deploy
      env:
        API_KEY: ${{ secrets.API_KEY }}
        DATABASE_URL: ${{ secrets.DATABASE_URL }}
      run: |
        echo "Deploying with secure configuration"
        # Use environment variables

# Using environments with protection rules
jobs:
  deploy-production:
    runs-on: ubuntu-latest
    environment:
      name: production
      url: https://myapp.example.com
    steps:
    - name: Deploy
      run: echo "Deploying to production"

# Environment variables at different levels
env:
  GLOBAL_VAR: 'available to all jobs'

jobs:
  job1:
    runs-on: ubuntu-latest
    env:
      JOB_VAR: 'available to all steps in job1'
    steps:
    - name: Step
      env:
        STEP_VAR: 'available only to this step'
      run: |
        echo $GLOBAL_VAR
        echo $JOB_VAR
        echo $STEP_VAR
```

---

## Chapter 17: GitHub Advanced Features

### GitHub Packages

GitHub Packages allows you to publish and consume packages within your organization or publicly. It supports npm, Maven, Gradle, Docker, NuGet, and RubyGems.

```yaml
# Publish npm package to GitHub Packages
# .github/workflows/publish.yml
name: Publish Package

on:
  release:
    types: [created]

jobs:
  publish:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
    steps:
    - uses: actions/checkout@v4
    
    - uses: actions/setup-node@v4
      with:
        node-version: '20.x'
        registry-url: 'https://npm.pkg.github.com'
        scope: '@your-org'
    
    - run: npm ci
    - run: npm publish
      env:
        NODE_AUTH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

```bash
# Configure npm to use GitHub Packages
# .npmrc
@your-org:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${NPM_TOKEN}

# Install package from GitHub Packages
npm install @your-org/package-name
```

### GitHub Pages

GitHub Pages hosts static websites directly from your repository. It's perfect for documentation, portfolios, and project sites.

```yaml
# .github/workflows/pages.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4
    
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: '20.x'
    
    - name: Install and build
      run: |
        npm ci
        npm run build
    
    - name: Setup Pages
      uses: actions/configure-pages@v4
    
    - name: Upload artifact
      uses: actions/upload-pages-artifact@v3
      with:
        path: ./dist
    
  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
    - name: Deploy to GitHub Pages
      id: deployment
      uses: actions/deploy-pages@v4
```

### GitHub Codespaces

Codespaces provides instant, configurable development environments in the cloud. Define your environment in a configuration file for consistent development across your team.

```yaml
# .devcontainer/devcontainer.json
{
  "name": "My Project",
  "image": "mcr.microsoft.com/devcontainers/dotnet:8.0",
  "features": {
    "ghcr.io/devcontainers/features/node:1": {
      "version": "20"
    },
    "ghcr.io/devcontainers/features/docker-in-docker:2": {}
  },
  "extensions": [
    "ms-dotnettools.csharp",
    "ms-dotnettools.csdevkit",
    "dbaeumer.vscode-eslint"
  ],
  "postCreateCommand": "dotnet restore && npm install",
  "forwardPorts": [5000, 5001, 3000],
  "customizations": {
    "vscode": {
      "settings": {
        "editor.formatOnSave": true,
        "editor.defaultFormatter": "ms-dotnettools.csharp"
      }
    }
  }
}
```

### GitHub Security Features

```
GitHub Security Features:

1. Dependabot
   - Automated dependency updates
   - Security vulnerability alerts
   - Pull request creation for updates

2. Code Scanning
   - Identify vulnerabilities in code
   - Integration with CodeQL
   - Third-party tool integration

3. Secret Scanning
   - Detect secrets pushed to repository
   - Partner alerts for exposed credentials
   - Custom patterns for organization

4. Security Policy
   - SECURITY.md file
   - Vulnerability reporting guidelines
   - Security advisories

5. Branch Protection
   - Required status checks
   - Required reviews
   - Signed commit requirements
```

```yaml
# .github/dependabot.yml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
    open-pull-requests-limit: 10
    reviewers:
      - "your-team"
    labels:
      - "dependencies"
  
  - package-ecosystem: "nuget"
    directory: "/"
    schedule:
      interval: "weekly"
  
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "monthly"
```

```yaml
# .github/workflows/codeql.yml
name: CodeQL

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  schedule:
    - cron: '0 0 * * 0'

jobs:
  analyze:
    runs-on: ubuntu-latest
    permissions:
      actions: read
      contents: read
      security-events: write

    steps:
    - name: Checkout
      uses: actions/checkout@v4

    - name: Initialize CodeQL
      uses: github/codeql-action/init@v3
      with:
        languages: csharp, javascript

    - name: Build
      run: dotnet build

    - name: Perform CodeQL Analysis
      uses: github/codeql-action/analyze@v3
```

---

## Chapter 18: Git Workflows and Branching Strategies

### Git Flow

Git Flow is a branching model that defines strict branching types and merge rules. It's well-suited for projects with scheduled release cycles and multiple versions in production.

```
Git Flow Branches:

main        - Production-ready code
develop     - Integration branch for features
feature/*   - New features (branched from develop)
release/*   - Release preparation (branched from develop)
hotfix/*    - Emergency fixes (branched from main)
```

```bash
# Git Flow workflow using git-flow extensions
# Install git-flow: apt install git-flow (Linux), brew install git-flow (Mac)

# Initialize git flow in repository
git flow init

# Start a feature
git flow feature start my-feature

# Work on feature...
git add .
git commit -m "Add feature"

# Finish feature (merges to develop)
git flow feature finish my-feature

# Start a release
git flow release start v1.0.0

# Finish release (merges to main and develop, creates tag)
git flow release finish v1.0.0

# Start a hotfix
git flow hotfix start critical-fix

# Finish hotfix (merges to main and develop)
git flow hotfix finish critical-fix
```

### GitHub Flow

GitHub Flow is a simpler, branch-based workflow optimized for continuous deployment. It's ideal for web applications that deploy frequently.

```
GitHub Flow:

1. Create branch from main
2. Add commits
3. Open pull request
4. Review and discuss
5. Deploy for testing
6. Merge to main
7. Deploy to production
```

```bash
# GitHub Flow example

# 1. Update main and create feature branch
git checkout main
git pull origin main
git checkout -b feature/add-search

# 2. Make changes and commit
git add .
git commit -m "Add search functionality"

# 3. Push and create PR
git push -u origin feature/add-search
gh pr create --title "Add search functionality" --body "Implements search..."

# 4. After approval, merge
gh pr merge --squash

# 5. Update local main
git checkout main
git pull origin main

# 6. Delete feature branch
git branch -d feature/add-search
```

### Trunk-Based Development

Trunk-Based Development emphasizes keeping branches short-lived and merging frequently to a single main branch (trunk). This minimizes merge conflicts and encourages continuous integration.

```
Trunk-Based Development:

main (trunk)
├── Feature A (hours to days)
├── Feature B (hours to days)
└── Feature C (hours to days)

Rules:
- All development on main or short-lived branches
- Feature flags for incomplete features
- Continuous integration on every commit
- Direct commits or very short-lived branches
```

### Choosing a Workflow

| Workflow | Best For | Pros | Cons |
|----------|----------|------|------|
| Git Flow | Scheduled releases, multiple versions | Clear structure, handles multiple versions | Complex, long-lived branches |
| GitHub Flow | Continuous deployment, web apps | Simple, fast, collaborative | No support for multiple versions |
| Trunk-Based | Continuous integration, experienced teams | Fast feedback, less merge conflict | Requires feature flags, discipline |

---

## Chapter 19: Collaboration Best Practices

### Commit Message Conventions

Good commit messages are essential for understanding project history and automating changelog generation.

```
Conventional Commits Format:

<type>(<scope>): <description>

[optional body]

[optional footer(s)]

Types:
- feat: New feature
- fix: Bug fix
- docs: Documentation changes
- style: Code style changes (formatting, etc.)
- refactor: Code refactoring
- perf: Performance improvement
- test: Adding or modifying tests
- chore: Maintenance tasks
- ci: CI/CD changes
- build: Build system changes

Examples:

feat(auth): add OAuth2 authentication

Implements OAuth2 authentication flow with Google and GitHub providers.
Includes token refresh logic and session management.

Closes #123

fix(api): resolve rate limiting issue

The API was returning 429 errors prematurely due to incorrect
rate limit counter initialization.

Fixes #456

docs(readme): update installation instructions

Add Docker installation method and troubleshooting section.
```

### Code Review Guidelines

```
Code Review Best Practices:

For Authors:
1. Keep PRs small and focused
2. Write clear descriptions
3. Self-review before requesting review
4. Respond to all comments
5. Be open to suggestions

For Reviewers:
1. Review promptly
2. Be constructive and specific
3. Distinguish between required changes and suggestions
4. Explain reasoning
5. Approve when satisfied

Comment Examples:

# Constructive feedback:
"Consider extracting this logic into a separate function for reusability.
This pattern appears in multiple places in the codebase."

# Question for understanding:
"Why was this approach chosen over using the existing utility?"

# Suggestion:
"Suggestion: You could use Array.map() here instead of the for loop
for a more functional style. No change required if you prefer current approach."

# Required change:
"This function is missing error handling for the case where the API
returns null. Please add a null check before accessing properties."
```

### Branch Naming Conventions

```
Branch Naming Patterns:

Feature branches:
- feature/JIRA-123-add-user-authentication
- feature/add-dark-mode

Bug fix branches:
- fix/JIRA-456-login-crash
- fix/memory-leak-in-parser

Hotfix branches:
- hotfix/critical-security-vulnerability
- hotfix/v1.2.1-database-connection

Release branches:
- release/v1.0.0
- release/2024.01

Documentation branches:
- docs/api-reference
- docs/installation-guide

Experiment branches:
- experiment/new-caching-strategy
- spike/performance-optimization

Best Practices:
- Use lowercase letters and hyphens
- Include ticket/issue number when applicable
- Be descriptive but concise
- Use consistent prefixes
```

---

## Chapter 20: Troubleshooting and Recovery

### Common Issues and Solutions

```bash
# Issue: Accidentally committed to wrong branch
# Solution: Cherry-pick or reset

# On wrong branch with commit
git checkout feature-wrong
git log --oneline -1  # Note the commit hash

# Move to correct branch
git checkout feature-correct
git cherry-pick <commit-hash>

# Remove from wrong branch
git checkout feature-wrong
git reset --hard HEAD~1

# Issue: Merge conflicts during rebase
# Solution: Resolve and continue
git rebase main
# Conflicts occur
git status  # See conflicted files
# Resolve conflicts in editor
git add resolved-file.txt
git rebase --continue
# Or abort if stuck
git rebase --abort

# Issue: Push rejected (non-fast-forward)
# Solution: Pull with rebase or force push (careful!)
git pull --rebase origin main
git push origin main

# If you're sure you want to overwrite remote:
git push --force-with-lease origin main

# Issue: Large file committed accidentally
# Solution: Remove from history using BFG or git filter-branch

# Using BFG Repo-Cleaner (recommended)
bfg --delete-folders large-folder
git reflog expire --expire=now --all
git gc --prune=now --aggressive

# Using git filter-branch
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch path/to/large/file" \
  --prune-empty --tag-name-filter cat -- --all

# Issue: Committed sensitive data
# Solution: Remove from history and rotate credentials

# 1. Remove file from history
git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch config/secrets.yml" \
  --prune-empty --tag-name-filter cat -- --all

# 2. Force push
git push origin --force --all

# 3. Rotate all exposed credentials immediately

# Issue: Detached HEAD state
# Solution: Create branch or checkout existing
git checkout -b new-branch-name
# Or return to previous branch
git checkout main

# Issue: Lost commits after reset
# Solution: Use reflog to recover
git reflog
git reset --hard HEAD@{n}  # n is the index from reflog
```

### Performance Issues

```bash
# Repository is slow
# Solution: Optimize and clean up

# Check repository size
git count-objects -vH

# Run garbage collection
git gc

# Aggressive garbage collection
git gc --aggressive --prune=now

# Repack objects
git repack -a -d -f --depth=250 --window=250

# Remove unreferenced objects
git prune --expire=now

# Clean up remote tracking branches
git remote prune origin

# Partial clone (for large repos)
git clone --filter=blob:none --sparse https://github.com/user/large-repo.git
cd large-repo
git sparse-checkout init --cone
git sparse-checkout set src/components

# Shallow clone
git clone --depth 1 https://github.com/user/repo.git

# Fetch single branch
git clone --single-branch --branch main https://github.com/user/repo.git
```

### Debugging Git

```bash
# Enable Git debugging
GIT_TRACE=1 git status
GIT_TRACE=1 git fetch

# More verbose output
GIT_TRACE=2 GIT_SSH_COMMAND="ssh -vvv" git fetch

# Check SSH connection
ssh -vT git@github.com

# Verify Git configuration
git config --list --show-origin

# Check repository integrity
git fsck
git fsck --full

# Verify objects
git verify-pack -v .git/objects/pack/*.idx

# Debug hooks
GIT_TRACE=1 git commit -m "test"
```

---

## Chapter 21: Security Best Practices

### Protecting Sensitive Information

```bash
# Never commit sensitive files
# Add to .gitignore

# Secrets
.env
.env.local
.env.*.local
*.pem
*.key
secrets.yml
credentials.json

# Use environment variables or secret managers

# Pre-commit hook to prevent secrets
#!/bin/bash
# .git/hooks/pre-commit

# Check for potential secrets
if git diff --cached | grep -E "(password|api_key|secret|token)\s*=\s*['\"]"; then
    echo "Warning: Potential secret detected in commit!"
    echo "Please review and remove sensitive information."
    exit 1
fi

# Use git-secrets tool
git secrets --install
git secrets --register-aws
```

### Signed Commits and Tags

```bash
# Setup GPG signing
# Install GPG
# macOS: brew install gnupg
# Linux: apt install gnupg

# Generate GPG key
gpg --full-generate-key

# List GPG keys
gpg --list-secret-keys --keyid-format=long

# Configure Git to use GPG key
git config --global user.signingkey <KEY-ID>
git config --global commit.gpgsign true
git config --global tag.gpgsign true

# Tell GPG program location
git config --global gpg.program gpg

# Sign a commit
git commit -S -m "Signed commit"

# Sign a tag
git tag -s v1.0.0 -m "Signed tag"

# Verify signatures
git tag -v v1.0.0
git log --show-signature

# GitHub: Add GPG key to account
gpg --armor --export <KEY-ID>
# Copy output and add to GitHub Settings > SSH and GPG keys
```

### SSH Key Management

```bash
# Use ED25519 for new keys (more secure and faster)
ssh-keygen -t ed25519 -C "your.email@example.com"

# Protect private key
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519

# Use SSH agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Configure SSH for multiple keys
# ~/.ssh/config
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519
    IdentitiesOnly yes

Host github-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_work
    IdentitiesOnly yes

# Test connection
ssh -T git@github.com
```

### Branch Protection Rules

```
GitHub Branch Protection Settings:

For main/master branch:

1. Require a pull request before merging
   - Require approvals (1-6 reviewers)
   - Dismiss stale pull request approvals
   - Require review from Code Owners
   - Restrict who can push

2. Require status checks to pass
   - Require branches to be up to date
   - Required checks: CI tests, lint, security scan

3. Require conversation resolution

4. Require signed commits

5. Require linear history

6. Include administrators (apply rules to admins)

7. Restrict force pushes

8. Allow force pushes (for specific scenarios)

9. Allow deletions

Code Owners (.github/CODEOWNERS):
# All files in /src/
/src/ @org/frontend-team

# All files in /api/
/api/ @org/backend-team

# Infrastructure files
/infrastructure/ @org/devops-team

# Documentation
*.md @org/docs-team
```

---

## Chapter 22: Quick Reference Cheatsheet

### Essential Commands

| Category | Command | Description |
|----------|---------|-------------|
| **Setup** | `git init` | Initialize repository |
| | `git clone <url>` | Clone repository |
| | `git config --global user.name "Name"` | Set username |
| | `git config --global user.email "email"` | Set email |
| **Basic** | `git status` | Show working tree status |
| | `git add <file>` | Stage file |
| | `git add .` | Stage all changes |
| | `git commit -m "message"` | Create commit |
| | `git commit -am "message"` | Stage and commit tracked files |
| **Branching** | `git branch` | List branches |
| | `git branch <name>` | Create branch |
| | `git checkout <branch>` | Switch branch |
| | `git checkout -b <branch>` | Create and switch |
| | `git switch <branch>` | Switch branch (new) |
| | `git switch -c <branch>` | Create and switch (new) |
| | `git branch -d <branch>` | Delete branch |
| **Merging** | `git merge <branch>` | Merge branch |
| | `git merge --no-ff <branch>` | Merge with commit |
| | `git merge --abort` | Abort merge |
| **Remote** | `git remote -v` | List remotes |
| | `git remote add <name> <url>` | Add remote |
| | `git fetch <remote>` | Fetch from remote |
| | `git pull <remote> <branch>` | Pull changes |
| | `git push <remote> <branch>` | Push changes |
| | `git push -u <remote> <branch>` | Push and set upstream |
| **History** | `git log` | Show history |
| | `git log --oneline` | Compact history |
| | `git log --graph --all` | Visual history |
| | `git show <commit>` | Show commit details |
| | `git diff` | Show changes |
| | `git diff --staged` | Show staged changes |
| **Undo** | `git reset HEAD~1` | Undo last commit (keep changes) |
| | `git reset --hard HEAD~1` | Undo last commit (discard) |
| | `git revert <commit>` | Create undo commit |
| | `git restore <file>` | Discard file changes |
| | `git restore --staged <file>` | Unstage file |
| **Stash** | `git stash` | Stash changes |
| | `git stash list` | List stashes |
| | `git stash pop` | Apply and remove stash |
| | `git stash apply` | Apply stash (keep) |
| **Rebase** | `git rebase <branch>` | Rebase onto branch |
| | `git rebase -i HEAD~n` | Interactive rebase |
| | `git rebase --continue` | Continue rebase |
| | `git rebase --abort` | Abort rebase |

### GitHub CLI Quick Reference

| Command | Description |
|---------|-------------|
| `gh auth login` | Authenticate with GitHub |
| `gh repo create` | Create repository |
| `gh repo clone <repo>` | Clone repository |
| `gh repo fork <repo>` | Fork repository |
| `gh pr create` | Create pull request |
| `gh pr list` | List pull requests |
| `gh pr checkout <num>` | Checkout PR locally |
| `gh pr merge <num>` | Merge pull request |
| `gh issue create` | Create issue |
| `gh issue list` | List issues |
| `gh release create` | Create release |
| `gh workflow list` | List workflows |
| `gh run watch` | Watch workflow run |

### File Status Codes

| Code | Meaning |
|------|---------|
| `??` | Untracked file |
| `A` | Added (staged) |
| `M` | Modified |
| `D` | Deleted |
| `R` | Renamed |
| `C` | Copied |
| `U` | Updated but unmerged |
| `!` | Ignored |

---

## Chapter 23: Additional Resources

### Official Documentation

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Documentation](https://docs.github.com)
- [GitHub Skills](https://skills.github.com/) - Interactive courses

### Books

- "Pro Git" by Scott Chacon and Ben Straub (free online)
- "Git for Teams" by Emma Jane Westby
- "GitHub For Dummies" by Sarah Guthals

### Tools

| Tool | Purpose |
|------|---------|
| GitKraken | Visual Git client |
| Sourcetree | Free Git GUI |
| GitHub Desktop | Official GitHub client |
| Tower | Commercial Git client |
| Lazygit | Terminal UI for Git |
| tig | Text-mode interface for Git |
| gitflow | Git Flow extensions |
| git-secrets | Prevent committing secrets |
| BFG Repo-Cleaner | Remove large files from history |

### Learning Resources

- [Learn Git Branching](https://learngitbranching.js.org/) - Interactive visualization
- [Oh My Git!](https://ohmygit.org/) - Game for learning Git
- [GitHub Learning Lab](https://lab.github.com/) - Hands-on courses
- [Atlassian Git Tutorials](https://www.atlassian.com/git)

### Community

- [GitHub Community Forum](https://github.community)
- [Stack Overflow git tag](https://stackoverflow.com/questions/tagged/git)
- [r/git subreddit](https://www.reddit.com/r/git/)

---

## Conclusion

Mastering Git and GitHub is fundamental to modern software development. This guide has covered everything from basic concepts to advanced techniques, providing you with the knowledge to effectively manage code, collaborate with teams, and contribute to projects of any scale.

Key takeaways:

1. **Git is about snapshots, not differences** - Understanding this mental model makes Git's behavior more predictable
2. **Branches are lightweight** - Create branches freely for features, experiments, and fixes
3. **Commit often, push regularly** - Small, frequent commits make history more useful and merges easier
4. **Use pull requests for collaboration** - They provide code review, discussion, and CI integration
5. **Write meaningful commit messages** - Future you (and your teammates) will thank you
6. **Learn to use the reflog** - It's your safety net when things go wrong
7. **Never force push to shared branches** - Unless you really know what you're doing
8. **Automate with hooks and Actions** - Let computers catch mistakes before humans do

Continue practicing these concepts in real projects to build muscle memory and intuition for Git's workflows.
