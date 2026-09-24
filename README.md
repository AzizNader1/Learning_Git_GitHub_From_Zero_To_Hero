# Git & GitHub: From Zero to Hero

![Guide](https://img.shields.io/badge/guide-zero--to--hero-blue) ![Level](https://img.shields.io/badge/level-beginner--%E2%86%92--master-green) ![Updated](https://img.shields.io/badge/updated-2026-orange) ![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen)

> **The complete, step-by-step, no-experience-required guide to version control.**
> Start knowing nothing. Finish thinking in commits, branches, pull requests, and CI pipelines.
> Zero to functional in one day. Zero to master with practice over a few weeks.

---

## Who This Guide Is For

- You have **never used Git or GitHub** in your life, and words like "commit" and "push" sound intimidating.
- You have *tried* Git before, got burned by a merge conflict or a scary error message, and quietly went back to emailing yourself `project_final_v3_REALLYFINAL.zip`.
- You know a handful of commands but copy-paste them blindly and want to actually **understand** what they do.
- You want to collaborate like professional developers do: branches, pull requests, code reviews, and automated tests.

No programming knowledge is required. Every concept is explained from first principles, every command comes with a realistic example and its output, and every part ends with an exercise you can do right now on your own machine.

## What You Will Learn

By the end of this guide you will be able to:

1. Explain what version control is and why every developer on Earth relies on it.
2. Install and configure Git on Windows, macOS, or Linux, and connect it securely to GitHub.
3. Create repositories, track changes, and write professional commit messages.
4. Branch, merge, and resolve merge conflicts without fear (or data loss).
5. Push your work to GitHub, collaborate through pull requests and code reviews.
6. Undo *anything* — recover "lost" commits, rewrite history safely, and rescue broken repos.
7. Use advanced tools: rebase, stash, cherry-pick, tags, hooks, bisect, and worktrees.
8. Automate your projects with GitHub Actions (CI/CD) and use power tools like the GitHub CLI.
9. Follow real-world best practices used by professional teams and open-source projects.
10. Contribute to open source and run your own projects like a pro.

## How to Use This Guide

- **Read in order the first time.** Each part builds on the previous one. Later parts reference earlier concepts.
- **Type every command yourself.** Muscle memory matters more than reading. Do the exercises.
- **Keep this page open as a reference.** Parts 11-13 are pure reference material (cheat sheets, FAQ, resources) — jump back there any time.
- **Time budget:** Parts 0-5 (the fundamentals) take roughly one focused day. Parts 6-10 (mastery) take another day of reading plus a few weeks of practice.

### Conventions Used

| Convention | Meaning |
|---|---|
| `code in backticks` | A command, filename, or code you type |
| Code blocks starting with `$` | Commands typed into your terminal (don't type the `$`) |
| **TIP:** | A shortcut or professional habit worth adopting |
| **WARNING:** | A common trap — read these carefully, they prevent disasters |
| **NOTE:** | Background info or context |
| **EXERCISE:** | Hands-on practice; solutions are hidden in collapsible sections |
| `<placeholders>` | Replace with your own values (e.g., `<your-username>`) |

### The Six Commands That Cover 90% of Daily Git

If you learn nothing else today, learn these (all explained fully in Parts 2 and 4):

```bash
git status                 # What is going on right now?
git add <file>             # Stage a change (put it in the "next save" box)
git commit -m "message"    # Save a snapshot of the staged changes
git pull                   # Download and integrate changes from GitHub
git push                   # Upload your commits to GitHub
git log --oneline          # Browse the history of your project
```

### The Learning Roadmap

```
  YOU ARE HERE                                                     MASTERY
      |                                                               |
      v                                                               v
 [Part 0]    [Part 1]     [Part 2]      [Part 3]    [Part 4]   [Part 5]
 concepts -> install & -> first repo -> branches  -> GitHub  -> collab &
             setup          & commits    & merges    & push     pull requests
      |____________________ DAILY DRIVER LEVEL _____________________________|
                              |
                              v
 [Part 6]      [Part 7]        [Part 8]        [Part 9]      [Part 10]
 undo &     -> rebase,      -> Actions,     -> conventions -> 5 guided
 recovery     stash, tags     CI/CD, gh CLI    & pro habits    projects
      |________________________ ADVANCED LEVEL _________________________________|
                              |
                              v
 [Part 11]      [Part 12]          [Part 13]
 cheat sheet -> error fixes  -> keep learning (you never stop)
      |_______________________ REFERENCE FOR LIFE ________________________________|
```

---

## Table of Contents

- [Part 0: The Big Picture](#part-0-the-big-picture)
  - [0.1 What Is Version Control?](#01-what-is-version-control)
  - [0.2 What Is Git?](#02-what-is-git)
  - [0.3 What Is GitHub?](#03-what-is-github)
  - [0.4 Git vs GitHub](#04-git-vs-github)
  - [0.5 How Git Thinks](#05-how-git-thinks)
  - [0.6 Vocabulary You Will See Everywhere](#06-vocabulary-you-will-see-everywhere)
- [Part 1: Installation and First Setup](#part-1-installation-and-first-setup)
  - [1.1 Installing Git](#11-installing-git)
  - [1.2 Verifying the Installation](#12-verifying-the-installation)
  - [1.3 Your Identity: The First-Time Configuration](#13-your-identity-the-first-time-configuration)
  - [1.4 Creating Your GitHub Account](#14-creating-your-github-account)
  - [1.5 Connecting Git to GitHub: HTTPS vs SSH](#15-connecting-git-to-github-https-vs-ssh)
  - [1.6 Setting Up SSH Keys Step by Step](#16-setting-up-ssh-keys-step-by-step)
  - [1.7 The GitHub CLI](#17-the-github-cli)
  - [1.8 Where to Get Help](#18-where-to-get-help)
- [Part 2: Git Fundamentals: Your First Repository](#part-2-git-fundamentals-your-first-repository)
  - [2.1 Creating a Repository: git init](#21-creating-a-repository-git-init)
  - [2.2 The Three Areas of Git](#22-the-three-areas-of-git)
  - [2.3 Checking the State: git status](#23-checking-the-state-git-status)
  - [2.4 Staging Changes: git add](#24-staging-changes-git-add)
  - [2.5 Saving a Snapshot: git commit](#25-saving-a-snapshot-git-commit)
  - [2.6 Anatomy of a Commit](#26-anatomy-of-a-commit)
  - [2.7 Ignoring Files: .gitignore](#27-ignoring-files-gitignore)
  - [2.8 Viewing History: git log and git show](#28-viewing-history-git-log-and-git-show)
  - [2.9 Seeing Exactly What Changed: git diff](#29-seeing-exactly-what-changed-git-diff)
  - [2.10 Exercise: Your First Repository](#210-exercise-your-first-repository)
- [Part 3: Branching and Merging](#part-3-branching-and-merging)
  - [3.1 What Is a Branch?](#31-what-is-a-branch)
  - [3.2 Why Branches Change Your Life](#32-why-branches-change-your-life)
  - [3.3 Creating and Switching Branches](#33-creating-and-switching-branches)
  - [3.4 HEAD: Where You Are Right Now](#34-head-where-you-are-right-now)
  - [3.5 Deleting and Renaming Branches](#35-deleting-and-renaming-branches)
  - [3.6 Merging](#36-merging)
  - [3.7 Merge Conflicts: The Complete Walkthrough](#37-merge-conflicts-the-complete-walkthrough)
  - [3.8 Branch Naming Conventions](#38-branch-naming-conventions)
  - [3.9 Branching Workflows Used by Teams](#39-branching-workflows-used-by-teams)
  - [3.10 Exercise: Branch Practice](#310-exercise-branch-practice)
- [Part 4: Remotes and Publishing to GitHub](#part-4-remotes-and-publishing-to-github)
  - [4.1 What Is a Remote?](#41-what-is-a-remote)
  - [4.2 Creating a Repository on GitHub](#42-creating-a-repository-on-github)
  - [4.3 Linking Your Local Repo: git remote](#43-linking-your-local-repo-git-remote)
  - [4.4 Uploading Your Work: git push](#44-uploading-your-work-git-push)
  - [4.5 Downloading Changes: git fetch and git pull](#45-downloading-changes-git-fetch-and-git-pull)
  - [4.6 Downloading a Whole Project: git clone](#46-downloading-a-whole-project-git-clone)
  - [4.7 Fork vs Clone](#47-fork-vs-clone)
  - [4.8 When Push Is Rejected](#48-when-push-is-rejected)
  - [4.9 Exercise: Publish Your Portfolio](#49-exercise-publish-your-portfolio)
- [Part 5: The GitHub Collaboration Workflow](#part-5-the-github-collaboration-workflow)
  - [5.1 The Golden Loop](#51-the-golden-loop)
  - [5.2 Issues: Your Project's To-Do List](#52-issues-your-projects-to-do-list)
  - [5.3 Pull Requests in Depth](#53-pull-requests-in-depth)
  - [5.4 Contributing to Someone Else's Repository](#54-contributing-to-someone-elses-repository)
  - [5.5 Merge, Squash, or Rebase?](#55-merge-squash-or-rebase)
  - [5.6 Keeping a Fork Up to Date](#56-keeping-a-fork-up-to-date)
  - [5.7 Code Review Etiquette](#57-code-review-etiquette)
  - [5.8 Protecting Branches and Team Settings](#58-protecting-branches-and-team-settings)
  - [5.9 GitHub Pages: A Free Website From Your Repo](#59-github-pages-a-free-website-from-your-repo)
  - [5.10 Exercise: The Full Collaboration Loop](#510-exercise-the-full-collaboration-loop)
- [Part 6: Undoing Things and Disaster Recovery](#part-6-undoing-things-and-disaster-recovery)
  - [6.1 The Safety-Net Mindset](#61-the-safety-net-mindset)
  - [6.2 Unstaging: git restore --staged](#62-unstaging-git-restore---staged)
  - [6.3 Discarding Local Changes: git restore](#63-discarding-local-changes-git-restore)
  - [6.4 git reset: Soft, Mixed, Hard](#64-git-reset-soft-mixed-hard)
  - [6.5 git revert: The Safe Undo](#65-git-revert-the-safe-undo)
  - [6.6 reset vs revert: Which One When?](#66-reset-vs-revert-which-one-when)
  - [6.7 git stash: Shelving Work in Progress](#67-git-stash-shelving-work-in-progress)
  - [6.8 git reflog: The Time Machine](#68-git-reflog-the-time-machine)
  - [6.9 Cleaning Untracked Files: git clean](#69-cleaning-untracked-files-git-clean)
  - [6.10 git cherry-pick](#610-git-cherry-pick)
  - [6.11 The Emergency Recovery Table](#611-the-emergency-recovery-table)
  - [6.12 Exercise: Disaster Drills](#612-exercise-disaster-drills)
- [Part 7: Intermediate to Advanced Git](#part-7-intermediate-to-advanced-git)
  - [7.1 git rebase](#71-git-rebase)
  - [7.2 The Golden Rule of Rebase](#72-the-golden-rule-of-rebase)
  - [7.3 Interactive Rebase: Rewriting History](#73-interactive-rebase-rewriting-history)
  - [7.4 Merge vs Rebase: The Decision](#74-merge-vs-rebase-the-decision)
  - [7.5 Tags and Releases](#75-tags-and-releases)
  - [7.6 Aliases: Build Your Own Shortcuts](#76-aliases-build-your-own-shortcuts)
  - [7.7 git blame: Who Wrote This Line?](#77-git-blame-who-wrote-this-line)
  - [7.8 git bisect: Binary Search for Bugs](#78-git-bisect-binary-search-for-bugs)
  - [7.9 Searching Your History](#79-searching-your-history)
  - [7.10 Submodules](#710-submodules)
  - [7.11 git worktree](#711-git-worktree)
  - [7.12 Cloning Big Repositories Efficiently](#712-cloning-big-repositories-efficiently)
  - [7.13 Git Hooks](#713-git-hooks)
  - [7.14 Line Endings and .gitattributes](#714-line-endings-and-gitattributes)
  - [7.15 Pushing Rewritten History Safely](#715-pushing-rewritten-history-safely)
- [Part 8: GitHub Power Tools](#part-8-github-power-tools)
  - [8.1 GitHub Actions: Automation for Everyone](#81-github-actions-automation-for-everyone)
  - [8.2 Your First Workflow, Line by Line](#82-your-first-workflow-line-by-line)
  - [8.3 Secrets: Storing Passwords Safely](#83-secrets-storing-passwords-safely)
  - [8.4 More Workflow Patterns](#84-more-workflow-patterns)
  - [8.5 Keeping Your Project Secure](#85-keeping-your-project-secure)
  - [8.6 Releases and Changelogs](#86-releases-and-changelogs)
  - [8.7 The GitHub CLI: GitHub From Your Terminal](#87-the-github-cli-github-from-your-terminal)
  - [8.8 Gists](#88-gists)
- [Part 9: Best Practices and Conventions](#part-9-best-practices-and-conventions)
  - [9.1 Atomic Commits and Small Pull Requests](#91-atomic-commits-and-small-pull-requests)
  - [9.2 Commit Message Conventions](#92-commit-message-conventions)
  - [9.3 Pull Request Description Template](#93-pull-request-description-template)
  - [9.4 Repository Housekeeping Files](#94-repository-housekeeping-files)
  - [9.5 Choosing a License](#95-choosing-a-license)
  - [9.6 The Top 10 Git Mistakes to Avoid](#96-the-top-10-git-mistakes-to-avoid)
  - [9.7 Team Conventions Checklist](#97-team-conventions-checklist)
- [Part 10: Guided Real-World Projects](#part-10-guided-real-world-projects)
  - [10.1 Project 1: Portfolio From Zero to a Live Website](#101-project-1-portfolio-from-zero-to-a-live-website)
  - [10.2 Project 2: The Full Feature Workflow](#102-project-2-the-full-feature-workflow)
  - [10.3 Project 3: Merge Conflict Surgery](#103-project-3-merge-conflict-surgery)
  - [10.4 Project 4: Automation with GitHub Actions](#104-project-4-automation-with-github-actions)
  - [10.5 Project 5: Your First Open-Source Contribution](#105-project-5-your-first-open-source-contribution)
  - [10.6 The Mastery Checklist](#106-the-mastery-checklist)
- [Part 11: The Complete Cheat Sheet](#part-11-the-complete-cheat-sheet)
  - [11.1 Command Reference by Category](#111-command-reference-by-category)
  - [11.2 How Do I...? (The Scenario Table)](#112-how-do-i-the-scenario-table)
  - [11.3 The Full Map of Git](#113-the-full-map-of-git)
  - [11.4 Glossary A to Z](#114-glossary-a-to-z)
- [Part 12: Troubleshooting and FAQ](#part-12-troubleshooting-and-faq)
- [Part 13: Resources and Next Steps](#part-13-resources-and-next-steps)
  - [13.1 Official Documentation](#131-official-documentation)
  - [13.2 Interactive Practice](#132-interactive-practice)
  - [13.3 Tools Worth Trying](#133-tools-worth-trying)
  - [13.4 Where Do You Go From Here?](#134-where-do-you-go-from-here)

---
# Part 0: The Big Picture

Before touching a single command, you need to understand four ideas: what version control is, what Git is, what GitHub is, and how Git actually thinks. Ten minutes of theory here will save you hours of confusion later. Everything else in this guide is just these ideas put into practice.

## 0.1 What Is Version Control?

Imagine you are writing an essay. You start with `essay.doc`. After a big revision you save it as `essay_v2.doc`. Your friend suggests changes, so you make `essay_v2_final.doc`. Then `essay_v2_final_fixed.doc`. Then `essay_v2_final_fixed_REALLY_final.doc`. Sound familiar?

This "file hoarding" approach has four fatal problems:

1. **No history.** Which version added that paragraph you now hate? Nobody knows. You end up opening every file to compare.
2. **No safety.** Delete or corrupt one file and that stage of your work is gone forever.
3. **No parallel work.** You cannot experiment with a bold rewrite without destroying your safe version.
4. **No collaboration.** If two people edit copies of the same file, merging their work by hand is a nightmare of copy-paste and mistakes.

**Version control** solves all four problems with one idea: a system that records a complete, timestamped snapshot of your project every time you tell it to. Each snapshot remembers exactly what every file looked like and who changed what. You can:

- Look at (or restore) the project as it existed at *any point in time*.
- Experiment fearlessly on isolated **branches** and merge back only what works.
- Synchronize work between many people and let the system combine their changes.
- Prove *when* a bug appeared and *who* introduced it (politely called "archaeology", impolitely called "blame").

Version control is not optional in modern software development — it is the foundation everything else sits on. And Git is the version control system that won.

## 0.2 What Is Git?

**Git** is a free, open-source **distributed version control system** created by Linus Torvalds in 2005 (the same person who created Linux — he built it in a few weeks to manage the Linux kernel's thousands of contributors).

Two words in that definition matter a lot:

- **Distributed:** every person who clones a project gets the *entire history* of the project on their own machine. You can commit, browse history, switch branches, and merge on a plane with no internet. Git is not a website or a service — it is a program that runs on your computer, working with a hidden folder inside your project called `.git`.
- **Snapshots, not diffs:** some older systems record *changes* ("line 3 was modified"). Git records complete **snapshots** of your whole project at each commit, and stores them efficiently so only changed files take extra space. This is why Git can jump to any version instantly.

**Key fact to burn into memory:** Git is a *local* tool. It works entirely on your machine. It does not need GitHub, the internet, or any account. GitHub only enters the picture when you want to *share*.

## 0.3 What Is GitHub?

**GitHub** (owned by Microsoft since 2018) is a **website that hosts Git repositories** in the cloud and layers a whole social/working platform on top of them:

- **Backup and sync:** your code lives on GitHub's servers; you push and pull between your laptop and GitHub.
- **Collaboration UI:** pull requests, code reviews, inline comments — the machinery of teamwork.
- **Project management:** issues (bug/feature tracker), projects (kanban boards), discussions, wikis.
- **Automation:** GitHub Actions (run tests and deployments automatically), security alerts, and much more.
- **Social layer:** stars, followers, forks, profiles. GitHub is effectively the "CV" of the software world — a public record of what you have built and contributed to.
- **Free hosting:** GitHub Pages hosts static websites for free, straight from a repository.

GitHub is the largest host of Git repositories (100+ million developers), but it is not the only one: **GitLab** and **Bitbucket** are similar platforms, and the skills you learn here transfer directly because they all speak Git underneath.

## 0.4 Git vs GitHub

People constantly mix these up. Here is the definitive distinction:

| | **Git** | **GitHub** |
|---|---|---|
| What is it? | A command-line tool (program) | A website / cloud platform |
| Where does it run? | On **your computer** | On the internet |
| Does it need the internet? | **No** — fully offline | **Yes** |
| What does it do? | Tracks versions: snapshots, branches, merges | Hosts repos, adds collaboration UI, automation, social features |
| Do you need an account? | No | Yes |
| Analogy | The *language* | The most popular *place where people speak it* |

**TIP:** Other analogies that work: Git is Microsoft Word's "track changes"; GitHub is Google Docs — the shared place where the document lives. Or: Git is the skill of writing; GitHub is the library that stores and shares the books.

## 0.5 How Git Thinks

To use Git without fear, internalize these four mental models.

### Model 1: The Snapshot Chain

Every time you `commit`, Git stores a snapshot of your whole project and links it to the snapshot that came before it. The result is a chain (technically a *graph*):

```
(Initial)  (Add header)  (Add footer)  (Fix typo)
    o----------o-------------o-------------o
   v1          v2            v3            v4   <- commits, each with a unique ID (hash)
```

Each commit gets a fingerprint called a **hash** (like `a1b2c3d...`), which identifies it forever. Because each commit points to its parent, Git can reconstruct the project at any point in time instantly.

### Model 2: The Three Areas

This is the single most important diagram in the entire guide. Git moves your files between **three areas**:

```
 WORKING DIRECTORY          STAGING AREA               REPOSITORY (history)
 (your normal files)        ("next commit" box)        (permanent snapshots)
                        git add                    git commit
  portfolio/    -------------------------------->  .git/ stores
  index.html    -------- staging ----->  snapshot   snapshots
  styles.css         index
      ^                   ^                          |
      |                   |                          |
  you edit           git restore              git reset / revert
  files here         --staged (unstage)       (move/undo history)

  <---- git checkout / git switch: move yourself to a different snapshot ---->
```

1. **Working directory:** the ordinary folder where you edit files. Git watches it and reports what changed.
2. **Staging area (also called the "index"):** a waiting room. You `git add` changes here to say "these specific changes belong in my next snapshot". This lets you commit *some* of your changes while leaving others out.
3. **Repository (`.git` folder):** the permanent database of snapshots. A `git commit` freezes everything in the staging area into a new snapshot, forever.

**Why a staging area?** So that one commit = one logical change. You edited five files but only two belong to the "fix login bug" change? Stage and commit only those two.

### Model 3: Branches Are Just Sticky Notes

A **branch** is not a copy of your files. It is a tiny movable label pointing at one commit. `main` points at the newest commit on the main line. Creating a `feature` branch costs nothing and takes microseconds — Git just writes a new label. "Switching branches" means "make my working directory look like the commit this label points to".

```
                (main)  <- a label pointing at a commit
                   |
  o---o---o---o---o        the main line of history
               \
                o---o---o  work done on a "feature" branch
                        |
                    (feature)  <- another label
```

HEAD (see Part 3) is a special label meaning "where I am standing right now".

### Model 4: Distributed = Everyone Has Everything

When you `clone` a project you download the entire history, not just the latest files. You and GitHub (and your teammates) each hold a full copy. `git push` sends your new commits to GitHub; `git pull` brings their new commits to you. There is no "master server" — just copies that agree to synchronize.

## 0.6 Vocabulary You Will See Everywhere

You will meet these words constantly. Skim now; each gets a full treatment later.

| Term | Plain-English meaning |
|---|---|
| **repository (repo)** | A project folder that is tracked by Git (contains the hidden `.git` database) |
| **commit** | A saved snapshot of the project, with message, author, and timestamp |
| **hash (SHA)** | The commit's unique ID, e.g. `a1b2c3d` |
| **branch** | A movable label pointing at a commit; an independent line of development |
| **merge** | Combining the changes of two branches into one |
| **clone** | Download a full copy of a remote repository to your machine |
| **remote** | A copy of your repo hosted elsewhere (usually GitHub); nicknamed `origin` |
| **push / pull** | Upload your commits / download and integrate others' commits |
| **fork** | Your personal server-side copy of someone else's GitHub repo |
| **pull request (PR)** | "Please review and merge my branch into the main project" — the collaboration unit |
| **staging area** | The waiting room for the next commit |
| **HEAD** | A pointer marking the commit you currently have checked out |
| **.gitignore** | A file listing paths Git should never track (secrets, build junk) |
| **origin / upstream** | Conventional names: `origin` = the repo you cloned from; `upstream` = the original project your fork came from |

**NOTE:** Do not try to memorize this now. It is repeated, with examples, in every part that follows. The table is here so that when a term appears and your memory fails, you know where to look.

---
# Part 1: Installation and First Setup

Goal of this part: Git installed and configured on your machine, a GitHub account created, and a secure connection between the two. Time needed: 30-45 minutes.

## 1.1 Installing Git

### Windows

1. Download the installer from the official site: **https://git-scm.com/download/win** (the download starts automatically).
2. Run the `.exe`. The installer shows many screens of options. Defaults are fine, with these notes:
   - **Choosing the default editor:** pick whatever you are comfortable with — "Use Visual Studio Code as Git's default editor" is a friendly choice if you have it; Notepad is fine too. (Vim is the default and confuses beginners — if you get trapped in Vim, press `Esc`, type `:q!`, press Enter to escape.)
   - **"Adjusting your PATH environment":** keep the recommended "Git from the command line and also from 3rd-party software".
   - **Choosing HTTPS transport backend:** "Use the OpenSSL library" is fine.
   - **"Configure line endings":** keep the default "Checkout Windows-style, commit Unix-style" (explained in Part 7.14).
3. Click through and finish. The installer also gives you **Git Bash** — a small Unix-style terminal with Git, which is the recommended terminal for this guide on Windows.

**TIP:** Windows 10/11 also lets you run `winget install --id Git.Git -e --source winget` in PowerShell to install the same thing without clicking through the wizard.

### macOS

Open Terminal (Cmd+Space, type "terminal") and try `git --version` first — macOS often already includes a Git stub, and if not, a dialog will offer to install the "Command Line Developer Tools". Accept it.

Alternatively, with Homebrew (the standard macOS package manager):

```bash
# Install Homebrew if you don't have it, then:
brew install git
```

### Linux (Debian/Ubuntu and friends)

```bash
sudo apt update
sudo apt install git -y
```

Linux (Fedora/RHEL):

```bash
sudo dnf install git -y
```

## 1.2 Verifying the Installation

Open a **new** terminal window (Git Bash on Windows, Terminal on macOS/Linux) and run:

```bash
git --version
```

Expected output (your version will be similar or newer):

```
git version 2.45.1
```

If you see a version number, Git is installed. If you see `command not found`, close and reopen the terminal, and if it still fails, reinstall or check your PATH.

**NOTE:** All commands in this guide work identically in Git Bash, macOS Terminal, and Linux terminals. Windows users: use **Git Bash**, not the old `cmd.exe`, for the best experience.

## 1.3 Your Identity: The First-Time Configuration

Git stamps every commit you make with your name and email. Set them once, globally, on every machine you use:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Use the **same email you will register on GitHub with** — this is what links your commits to your GitHub profile picture and contribution graph. Verify:

```bash
git config --global user.name        # prints: Your Name
git config --global user.email       # prints: you@example.com
```

A few more useful global settings:

```bash
# Modern default branch name. GitHub uses "main"; old tutorials say "master".
git config --global init.defaultBranch main

# The editor Git opens for commit messages and interactive rebase.
# Options: "code --wait" (VS Code), "notepad" (Windows), "nano" (beginner-friendly).
git config --global core.editor "code --wait"

# Pull with rebase by default (recommended by many pros; explained in Part 7).
git config --global pull.rebase true

# See every setting you have configured:
git config --global --list
```

**TIP:** `--global` writes to `~/.gitconfig` and applies to all your repositories. If you omit it (e.g. `git config user.email "work@company.com"`), the setting applies only to the repo you are currently in — perfect for separating a work identity from a personal one.

## 1.4 Creating Your GitHub Account

1. Go to **https://github.com/signup**.
2. Choose a **username carefully** — it becomes part of every URL you share (`github.com/<username>/<repo>`) and, fair or not, it is part of your professional identity. Short, lowercase, professional.
3. Use the same email you configured in Git above.
4. Pick the **Free plan** — it is genuinely generous: unlimited public *and* private repositories.
5. Verify your email (check inbox; GitHub will not activate your account until you do).

## 1.5 Connecting Git to GitHub: HTTPS vs SSH

When you `git push`, GitHub must verify you are really you. Two standard methods exist:

| | **HTTPS** | **SSH** |
|---|---|---|
| Repo URL looks like | `https://github.com/user/repo.git` | `git@github.com:user/repo.git` |
| Authentication | Username + a **Personal Access Token** (or a browser login handled by Git Credential Manager) | A **key pair** on your machine |
| Setup effort | Near zero on Windows/macOS (credential manager is bundled) | 5 minutes, once per machine |
| Day-to-day | You log in once; the credential manager remembers it | Never asked again, ever |

**TIP:** On Windows and macOS, the Git installer bundles a **credential manager** that pops up a browser login the first time you push and then remembers it. That is perfectly fine. SSH is beloved by power users because it is passwordless, works everywhere (including servers and CI), and never expires. Both work with everything in this guide — pick one and know the other exists.

## 1.6 Setting Up SSH Keys Step by Step

SSH uses cryptography: you keep a **private key** on your machine (never share it) and give GitHub the matching **public key** (safe to share). Follow along in your terminal.

**Step 1 — Generate a key pair.** Use the modern Ed25519 algorithm:

```bash
ssh-keygen -t ed25519 -C "you@example.com"
```

- `-C` adds a comment (your email) so you can recognize the key later.
- When asked where to save it, press **Enter** to accept the default (`~/.ssh/id_ed25519`).
- When asked for a **passphrase**: press Enter twice for no passphrase (simple), or type one for extra security (then it prompts once per session). Beginners: no passphrase is fine.

Output ends with a quirky ASCII key diagram — success. You now have two files:

```
~/.ssh/id_ed25519      <- PRIVATE key. Never share, never commit, never screenshot.
~/.ssh/id_ed25519.pub  <- PUBLIC key. This one goes to GitHub.
```

**WARNING:** The file *without* `.pub` is your private key. Treat it like a house key. The one *with* `.pub` is the safe one.

**Step 2 — Register the key with the SSH agent** (so you do not retype passphrases):

```bash
# Start the agent (macOS/Linux; Git Bash on Windows usually already has one)
eval "$(ssh-agent -s)"

# Add your key
ssh-add ~/.ssh/id_ed25519
```

**Step 3 — Copy your public key:**

```bash
cat ~/.ssh/id_ed25519.pub
```

This prints one long line starting with `ssh-ed25519` and ending with your email. Copy it. (Windows shortcut: `clip < ~/.ssh/id_ed25519.pub` copies it straight to your clipboard. macOS shortcut: `pbcopy < ~/.ssh/id_ed25519.pub`.)

**Step 4 — Add the key on GitHub:**

1. GitHub → click your profile picture (top-right) → **Settings**.
2. Left sidebar → **SSH and GPG keys** → **New SSH key**.
3. Title: anything ("My laptop"). Key type: "Authentication Key". Key: paste the public key.
4. **Add SSH key**. GitHub may ask you to confirm your password.

**Step 5 — Test the connection:**

```bash
ssh -T git@github.com
```

The *first* time, SSH asks if you trust github.com's fingerprint — type `yes`. On success you will see:

```
Hi <your-username>! You've successfully authenticated, but GitHub does not provide shell access.
```

That message is the success signal. Your machine and GitHub now trust each other.

**NOTE:** If you ever get `Permission denied (publickey)` later, Part 12 has the fix — usually the key is not in the agent or the wrong key was pasted into GitHub.

## 1.7 The GitHub CLI

`gh` is GitHub's official command-line tool: create repos, open pull requests, list issues, and check your CI — all from the terminal, all authenticated once. Install it now (optional but recommended):

```bash
# Windows:  winget install --id GitHub.cli
# macOS:    brew install gh
# Ubuntu:   see https://github.com/cli/cli/blob/trunk/docs/install_linux.md
```

Then authenticate once:

```bash
gh auth login
```

Answer the prompts: GitHub.com → SSH (or HTTPS) → login with a web browser. It prints a one-time code; open the URL it shows, enter the code, done. We will use `gh` throughout Part 8.

## 1.8 Where to Get Help

Two lifelines, both built in:

```bash
git help status     # opens the full manual page for a command
git status -h       # short cheat-sheet style help
```

And `https://git-scm.com/docs` hosts all documentation online. When a command confuses you, this is faster than searching the web.

**Checkpoint:** You now have (1) Git installed, (2) your name/email configured, (3) a GitHub account, (4) a working connection (SSH or HTTPS). Everything from here on is using the tool.

---
# Part 2: Git Fundamentals: Your First Repository

Goal of this part: create a real repository, understand the three areas in practice, and make your first commits. This part is the foundation of everything that follows — do it at the keyboard, not just in your head.

We will build a tiny portfolio website as our running example. It is deliberately simple (three files) so that Git, not the project, is the star. You can follow the exact same steps with any project you have.

## 2.1 Creating a Repository: git init

```bash
# 1. Make a folder for the project and go into it
mkdir my-portfolio
cd my-portfolio

# 2. Turn it into a Git repository
git init
```

Output:

```
Initialized empty Git repository in /home/you/my-portfolio/.git/
```

That single command created a hidden `.git` folder — the entire database of your project's history. Nothing else changed: your files are untouched, no files are tracked yet, and the repo is 100% local (nothing is on GitHub yet — that comes in Part 4).

**TIP:** `ls -a` lists hidden files — you can confirm `.git` exists. On Windows File Explorer, "Hidden items" must be enabled in the View menu to see it.

Verify the repo is alive:

```bash
git status
```

Output (yours may mention `master` instead of `main` — see 1.3 to set the default):

```
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

**WARNING:** Run `git init` in the **project root**, never in your home directory or `Documents`. Git will happily treat your entire hard drive as one repo, which is a disaster to untangle. If you ever accidentally do this: delete the wrongly created `.git` folder (e.g. `rm -rf ~/.git`), and nothing else is harmed.

## 2.2 The Three Areas of Git

Recall Model 2 from Part 0. Every file in your repo lives in one of three states:

| State | Meaning | Lives in |
|---|---|---|
| **Untracked** | Git has never seen this file | Working directory |
| **Tracked & unmodified** | File is committed and unchanged | Working directory = last snapshot |
| **Tracked & modified** | You changed it since the last commit | Working directory |
| **Staged** | Change is marked for the next commit | Staging area |

And the commands that move files between them — this diagram is worth re-drawing by hand:

```
  untracked ──git add──> staged ──git commit──> committed (unmodified)
                          │
  modified  ──git add────>│  (re-stage after more edits)
     ^                   │
     │<── edit file ─────┘
     │
     └──git restore (discard edits, back to last commit)
        git restore --staged (pull back out of staging)
```

## 2.3 Checking the State: git status

`git status` is your constant companion — run it before, during, and after everything. It answers: *where am I, what changed, what is staged?*

Create two files so we have something to track:

```bash
echo "# My Portfolio" > README.md
echo "<h1>Hello, I am learning Git</h1>" > index.html
```

Now check state:

```bash
git status
```

Output:

```
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        index.html

nothing added to commit but untracked files present (use "git add" to track)
```

Git sees both files but has been told to track *nothing* yet. Let's fix that.

**TIP:** `git status -s` gives a compact two-column view. Left column = staging status, right column = working directory status. `??` = untracked, `A` = newly staged, `M` = modified, `MM` = staged and then modified again.

## 2.4 Staging Changes: git add

`git add` copies the current state of files into the staging area — literally a "put this in my next snapshot" instruction.

```bash
git add README.md      # stage one file
git add index.html     # stage another
git add .              # stage everything in the current directory (the usual move)
git add -A             # stage ALL changes repo-wide: additions, edits, deletions
```

Check the effect:

```bash
git status
```

Output:

```
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
        new file:   index.html
```

Both files are now staged ("new file" because they were untracked before).

**Stage *part* of a file's changes?** `git add -p` walks you through each "hunk" of a modified file and asks `stage this hunk? (y/n)` — perfect for splitting a messy editing session into clean commits.

**Unstage something (change of plans):**

```bash
git restore --staged index.html   # modern command (Git 2.23+)
```

The file goes back to untracked/modified, but **your edits are untouched** — unstaging never destroys anything.

## 2.5 Saving a Snapshot: git commit

A commit permanently freezes the staged changes into history, with a message describing *why*.

```bash
git commit -m "Initial commit: add README and homepage"
```

Output:

```
[main (root-commit) e8a3f12] Initial commit: add README and homepage
 2 files changed, 2 insertions(+)
 create mode 100644 README.md
 create mode 100644 index.html
```

Reading that output: branch `main`, the *root commit* (the first one, ever), its hash starts with `e8a3f12`, 2 files changed, 2 lines added.

Now make a real change, stage it, and commit again:

```bash
echo "<p>Under construction, but improving weekly.</p>" >> index.html
git status          # shows index.html as "modified"
git add index.html
git commit -m "Add under-construction note to homepage"
```

**TIP:** Skip the staging step for *already-tracked* files with `git commit -am "message"` — the `-a` automatically stages every modification (but not brand-new untracked files; those still need an explicit `git add`).

**Writing the message in an editor:** run plain `git commit` (no `-m`) and your configured editor opens. Convention: first line ≤ 50 chars, blank line, then optional detail paragraphs. See Part 9.2 for the professional style.

**WARNING:** A commit is *local*. Nobody on the internet can see it until you `git push` (Part 4). Committing is saving; pushing is publishing.

## 2.6 Anatomy of a Commit

Inspect one with:

```bash
git show
```

Output (abbreviated):

```
commit e8a3f12a9c4d5b1f8e3a2c4b5d6e7f8a9b0c1d2e (HEAD -> main)
Author: Your Name <you@example.com>
Date:   Mon Sep 22 10:15:00 2026 +0200

    Initial commit: add README and homepage

diff --git a/README.md b/README.md
...
```

Every commit contains: a **hash** (unique ID), **parent(s)** (what came before), **author** (you), **committer**, **date**, and the **message**. The `(HEAD -> main)` tells you which branch points here — more on that in Part 3.

**Fix your last commit:** typo in the message, or forgot a file?

```bash
git commit --amend -m "Better message"        # rewrite the message
git add forgotten-file.html
git commit --amend --no-edit                   # fold the file into the last commit
```

**WARNING:** `--amend` replaces the last commit with a new one (new hash). That is safe **only if you have not pushed it yet**. Never amend commits others may already have (see Part 6 and 7.15).

## 2.7 Ignoring Files: .gitignore

Some files must never enter history: passwords and API keys (`.env`), build output (`dist/`, `*.o`), dependency folders (`node_modules/` — thousands of files, not your code), OS junk (`.DS_Store`, `Thumbs.db`), editor folders (`.vscode/` is a judgment call). Create a file named exactly `.gitignore` in the repo root:

```bash
# .gitignore — lines starting with # are comments

# Secrets
.env
*.pem

# Dependencies (huge, reproducible — not your code)
node_modules/

# Build output
dist/
build/
*.log

# OS junk
.DS_Store
Thumbs.db

# Python example
__pycache__/
*.pyc
.venv/

# Exception: track this one file despite the *.log rule above
!important.log
```

Pattern quick reference:

| Pattern | Ignores |
|---|---|
| `logs/` | any folder named `logs`, at any depth |
| `*.log` | every file ending in `.log` |
| `/build` | only the `build` folder in the repo root |
| `doc/*.md` | `.md` files directly inside `doc/` |
| `**/temp` | `temp` folders at any depth |
| `!keep.log` | *un*-ignore — an exception |

**TIP:** GitHub maintains an excellent template collection at **https://github.com/github/gitignore** — one per language/framework. Copy the one for your stack. `git config --global core.excludesfile ~/.gitignore_global` lets you ignore junk like `.DS_Store` across *all* your repos.

**WARNING:** `.gitignore` only affects *untracked* files. If you committed `debug.log` before adding the rule, Git keeps tracking it. Untrack it without deleting it:

```bash
git rm --cached debug.log
git commit -m "Stop tracking debug.log"
```

## 2.8 Viewing History: git log and git show

```bash
git log                          # full history: hash, author, date, message
git log --oneline                # one line per commit: short-hash + message
git log --oneline --graph --all  # ASCII graph of branches (use this constantly)
git log -3                       # only the last 3 commits
git log --stat                   # + which files changed and how many lines
git log -p                       # + the full diff of every commit (verbose!)
git log --author="Your Name"     # filter by author
git log --grep="homepage"        # filter by message keyword
git log index.html               # history of one file
```

`--oneline` output looks like:

```
c41f93b (HEAD -> main) Add under-construction note to homepage
e8a3f12 Initial commit: add README and homepage
```

The `HEAD -> main` marker shows your position. Press `q` to quit the pager.

`git show <hash>` displays one commit in full detail; `git show` with no argument shows the newest. Also useful: `git show <hash>:index.html` prints that file *as it was at that commit* — time travel for one file.

## 2.9 Seeing Exactly What Changed: git diff

`git diff` is your "what changed?" X-ray, at three levels:

```bash
git diff              # working directory  vs  staging area     (unstaged edits)
git diff --staged     # staging area       vs  last commit     (what WILL be committed)
git diff HEAD         # working directory  vs  last commit     (all uncommitted edits)
git diff main..other-branch   # compare two branches (Part 3)
```

Sample output — the universal format, worth learning to read once and forever:

```diff
diff --git a/index.html b/index.html
index 3f2a1bc..d4e5f6a 100644
--- a/index.html
+++ b/index.html
@@ -1,1 +1,2 @@
 <h1>Hello, I am learning Git</h1>
+<p>Under construction, but improving weekly.</p>
```

Translation: in `index.html`, near line 1, a line was added (lines with `+`; lines with `-` were removed; context lines have neither).

**TIP:** Many people run `git diff --staged` right before every commit — a final check that exactly what you *intended* to save is what you *are* saving. Make it a habit.

## 2.10 Exercise: Your First Repository

Do this from scratch, without looking back, then compare with the hidden solution:

1. Create a repo called `git-practice` (locally, no GitHub yet).
2. Create `notes.txt` with one line about what you learned today.
3. Check the status; stage and commit it.
4. Add a second line to `notes.txt`; view the diff; commit with a good message.
5. Look at your history in the one-line format.
6. Create a `.gitignore` that would ignore `*.tmp` files; commit it.
7. Make a file `scratch.tmp`; prove `git status` does not list it.

<details>
<summary>Show solution</summary>

```bash
mkdir git-practice && cd git-practice
git init
echo "Learned: snapshots, staging, commits" > notes.txt
git status                     # notes.txt is untracked
git add notes.txt
git commit -m "Add first learning note"
echo "Learned: git diff and git log" >> notes.txt
git diff                       # shows the added line
git add notes.txt
git commit -m "Add second learning note"
git log --oneline
echo "*.tmp" > .gitignore
git add .gitignore
git commit -m "Ignore temporary files"
touch scratch.tmp
git status                     # scratch.tmp is NOT listed
```

</details>

**Checkpoint:** You can create a repo, understand staged vs unstaged, commit with intention, ignore junk, and read history and diffs. That is genuinely 40% of daily Git use. Next: branches — where Git stops being a save button and becomes a superpower.

---
# Part 3: Branching and Merging

Branches are the feature that made Git famous. Goal of this part: create, switch, merge, and delete branches, and survive your first merge conflict on purpose.

## 3.1 What Is a Branch?

A branch is a **movable label pointing at one commit**. Not a copy of the project. Not a folder. A 41-byte file containing a commit hash.

```
                      main
                        |
   A --- B --- C --- D
                  \
                   E --- F
                        |
                     feature
```

- `main` and `feature` are just pointers. Creating a branch takes microseconds, regardless of project size.
- When you commit while standing on `feature`, the pointer moves to the new commit. `main` stays behind.
- Merging (see 3.6) reunites the two lines of development.

## 3.2 Why Branches Change Your Life

Without branches, you develop new features, fix bugs, and experiment *directly on your main line* — one bad edit can break the working version everyone depends on. With branches:

1. **Safety by isolation.** The main branch always holds a working state. All experiments live on branches; broken branches cost nothing.
2. **Instant context switching.** Bug report mid-feature? `git switch hotfix`, fix it, switch back — your half-finished feature is exactly where you left it.
3. **Parallel work.** Three teammates, three branches, zero interference.
4. **Reviewability.** A branch can be pushed and discussed as a pull request before it merges (Part 5).
5. **Cheap experiments.** Try a wild idea on a branch; if it fails, delete the branch and the idea vanishes without a trace.

**TIP:** The professional reflex: *never commit directly to `main` in a shared project.* Always branch. In a solo project it is still excellent practice for Part 5's workflow.

## 3.3 Creating and Switching Branches

Modern syntax (Git 2.23+, 2019 — learn this one) and the classic it replaces:

| Task | Modern command | Classic equivalent |
|---|---|---|
| List local branches | `git branch` | same |
| Create a branch (stay where you are) | `git branch feature/contact-form` | same |
| Switch to an existing branch | `git switch feature/contact-form` | `git checkout feature/contact-form` |
| Create **and** switch in one step | `git switch -c feature/contact-form` | `git checkout -b feature/contact-form` |
| Switch back to your previous branch | `git switch -` | `git checkout -` |

Practice on the portfolio repo:

```bash
git switch -c feature/about-page
git branch                 # lists branches; the current one is marked with *
```

Output:

```
* feature/about-page
  main
```

The `*` marks where you are. Commit something on the branch:

```bash
echo "<h2>About me</h2><p>I am learning Git seriously.</p>" > about.html
git add about.html
git commit -m "Add About page"
```

Now jump back and forth and *watch your files appear and disappear* — this is the moment the branch model clicks for most people:

```bash
git switch main          # about.html vanishes
ls                       # no about.html
git switch feature/about-page   # about.html returns
ls                       # about.html is back
```

**NOTE:** Nothing was duplicated. Git simply rewrites your working directory to match the commit each branch points to. Untracked files and uncommitted changes travel with you (Git will refuse a switch if it would overwrite your uncommitted edits — it never silently destroys work).

**TIP:** Branches can branch. A `feature/big-rewrite` branch can itself sprout `feature/experiment-42`. Keep trees shallow though — deep branch trees are merge pain.

## 3.4 HEAD: Where You Are Right Now

`HEAD` is Git's "YOU ARE HERE" marker: a pointer to the commit you currently have checked out (indirectly, via the current branch). `git log`'s `HEAD -> main` decoration says it out loud:

```
c41f93b (HEAD -> main, feature/about-page) Add About page
```

That line means: this commit is where `HEAD` is, `main` points here, and so does `feature/about-page`. When you commit on a branch, Git moves that branch's pointer forward and HEAD follows it.

## 3.5 Deleting and Renaming Branches

```bash
git branch -d feature/about-page      # delete (safe: refuses if unmerged)
git branch -D feature/about-page      # delete, force (unmerged work is abandoned)
git branch -m new-name                # rename the branch you are on
git branch -m old-name new-name       # rename another branch
git push origin --delete feature/x    # delete a branch on GitHub (Part 4)
```

**WARNING:** `-D` throws away commits that exist *only* on that branch. They linger in the reflog for a while (Part 6.8) but treat `-D` as a destructive button. `-d` (lowercase) is the safe default — use it.

## 3.6 Merging

Merging brings the changes of one branch into another. The **base branch** is where you want changes to end up; the **feature branch** has the changes.

```bash
git switch main                        # 1. stand on the base branch
git merge feature/about-page           # 2. merge the feature in
git branch -d feature/about-page       # 3. clean up the finished branch
```

### Fast-forward merges

If `main` has not moved since the branch was created, Git simply slides the `main` pointer forward — no new commit needed:

```
 BEFORE                          AFTER (fast-forward)
   main                              main
    |                                 |
A---B---C---D                  A---B---C---D---E
             \                              ^
              E---F                    (feature was already at E... 
                  |                      in this simple case F is absent)
              feature
```

You will see `Fast-forward` in the merge output.

### Three-way merges (a real merge commit)

If *both* branches advanced, Git creates a new **merge commit** with two parents, tying the lines together:

```
 BEFORE                              AFTER
   main                                main
    |                                   |
A---B---C---F                    A---B---C---F---M
         \                            \        /
          G---H                        G---H
              |                            |
          feature                     (deleted)
                          M = merge commit with parents F and H
```

The output mentions which strategy was used, e.g. `Merge made by the 'ort' strategy`. Merge commits are normal, expected, and safe.

## 3.7 Merge Conflicts: The Complete Walkthrough

A conflict happens when two branches changed the **same lines** of the **same file** in different ways, and Git cannot guess which version you want. This is not an emergency, an error, or data loss — it is Git asking for a human decision. You should *practice* it; we will now deliberately cause one.

**Setup — create the same edit on two branches:**

```bash
git switch main
echo "<h1>Best Portfolio Ever</h1>" > tagline.txt
git add tagline.txt
git commit -m "Set tagline on main"

git switch -c feature/new-tagline
echo "<h1>The Coolest Dev Alive</h1>" > tagline.txt
git add tagline.txt
git commit -m "Set a bolder tagline"

git switch main
git merge feature/new-tagline
```

**The conflict appears:**

```
Auto-merging tagline.txt
CONFLICT (add/add): Merge conflict in tagline.txt
Automatic merge failed; fix conflicts and then commit the result.
```

**Step 1 — see the situation.** `git status` now shows:

```
On branch main
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (each side's changes: git checkout --ours/--theirs <file>...)
        both added:      tagline.txt
```

**Step 2 — open the conflicted file.** Git has marked the two versions in the file itself:

```
<<<<<<< HEAD
<h1>Best Portfolio Ever</h1>
=======
<h1>The Coolest Dev Alive</h1>
>>>>>>> feature/new-tagline
```

- Between `<<<<<<< HEAD` and `=======`: the version on your **current branch** (where you merged *into* — "ours").
- Between `=======` and `>>>>>>> feature/new-tagline`: the version **coming in** ("theirs").

**Step 3 — resolve it by *editing the file*.** Keep one side, the other, or (often best) write a combination. Delete ALL the marker lines. For example:

```
<h1>The Coolest Dev Alive — Best Portfolio Ever</h1>
```

**Step 4 — stage the resolved file** (this is how you tell Git "this conflict is resolved"):

```bash
git add tagline.txt
```

**Step 5 — finish the merge:**

```bash
git commit          # Git pre-fills a "Merge branch 'feature/new-tagline'" message
```

Done. Repeat steps 2-4 for every file listed under "Unmerged paths".

**TIP — escape hatches:**

```bash
git merge --abort                       # stop everything, return to pre-merge state
git checkout --ours tagline.txt         # resolve the whole file: keep my version
git checkout --theirs tagline.txt       # resolve the whole file: take their version
git diff                                # during a conflict, shows the conflicting hunks
```

**NOTE:** Conflicts also appear during `git pull` — a pull is really a fetch + merge, and if your local and remote versions of a line differ, you get the same markers and the same procedure. Same with rebases (Part 7), except the wording flips: during rebase, "ours" means the branch being rebased *onto*, which is the opposite direction of what your intuition expects. When in a rebase: `--ours` = the base branch's version, `--theirs` = *your* branch's version.

**WARNING:** Before committing, search the project for leftover markers: `grep -rn "<<<<<<<" .` — a file resolved half-way is a classic rookie bug that gets committed and shipped.

## 3.8 Branch Naming Conventions

Branch names become URLs and commit messages (`Merge branch '...'`), so make them readable:

| Pattern | Example | Use |
|---|---|---|
| `feature/<short-name>` | `feature/contact-form` | new functionality |
| `fix/<issue>-<slug>` | `fix/142-login-crash` | bug fix, tied to issue #142 |
| `docs/<slug>` | `docs/readme-rewrite` | documentation |
| `chore/<slug>` | `chore/update-deps` | tooling, deps, config |
| `experiment/<slug>` | `experiment/dark-theme` | throwaway exploration |

Rules of thumb: lowercase, hyphen-separated, include the issue number if one exists, no personal names (`joes-branch` tells nobody anything).

## 3.9 Branching Workflows Used by Teams

How branches are organized across a team — three dominant patterns:

**GitHub Flow** (the default of this whole guide — simple, and what most modern teams use):

1. `main` is always deployable.
2. Every piece of work gets a short-lived branch off `main`.
3. Push the branch, open a pull request, discuss/review.
4. Merge (often squash) back to `main` and deploy; delete the branch.

**Git Flow** (older, release-heavy projects): long-lived `develop` branch, `feature/*` off develop, `release/*` branches, `hotfix/*` off `main`, version tags. Powerful ceremony; heavier than most projects need today. Know it exists; use it when a release cycle genuinely demands it.

**Trunk-based development:** everyone commits tiny changes straight to `main` (features hidden behind flags). Used by big-tech teams with strong test suites. Advanced; not for your first team.

## 3.10 Exercise: Branch Practice

1. On `main`, add a `contact.html` file; commit.
2. Create `feature/footer`, add a `footer.html`; commit twice (two small commits).
3. Switch to `main`, add a `README` improvement; commit — so both lines advanced.
4. Merge `feature/footer` into `main`. Observe that this time a real **merge commit** was created (both branches had moved).
5. Delete the merged branch.
6. Now manufacture a conflict like 3.7 (same file, same line, two branches) and resolve it keeping a combined version. Verify with `grep -rn "<<<<<<<" .` that no markers remain, then commit the merge.

<details>
<summary>Show solution sketch</summary>

```bash
git switch main
echo "email me at dev@example.com" > contact.html
git add contact.html && git commit -m "Add contact page"

git switch -c feature/footer
echo "(c) 2026 - built while learning Git" > footer.html
git add footer.html && git commit -m "Add site footer"
echo "footer v2" >> footer.html
git commit -am "Extend footer"

git switch main
echo "# My Portfolio - updates weekly" > README.md
git add README.md && git commit -m "Clarify README title"

git merge feature/footer        # -> Merge made by the 'ort' strategy
git log --oneline --graph       # admire the merge commit shape
git branch -d feature/footer

# conflict: repeat 3.7 with tagline.txt or README.md
git merge feature/new-tagline
# ... resolve markers in the editor ...
git add tagline.txt
git commit
```

</details>

**Checkpoint:** You can branch freely, understand pointers and HEAD, merge with both strategies, and resolve conflicts calmly. Next stop: putting your work on GitHub.

---
# Part 4: Remotes and Publishing to GitHub

Your repo so far lives only on your machine. Goal of this part: put it on GitHub (backup + sharing), learn push/pull/clone, and understand what to do when GitHub says "no".

## 4.1 What Is a Remote?

A **remote** is another copy of your repository that your local repo knows about — usually a copy hosted on GitHub. Your local repo can have any number of remotes, each with a nickname. By universal convention, the remote you cloned from or push your work to is nicknamed **`origin`**.

```
   your laptop                     GitHub
  --------------                 --------------
  my-portfolio  --git push-->    my-portfolio   (nicknamed "origin")
  (full history) <--git pull--   (full history)
```

Pushing sends *only the commits GitHub is missing* — tiny and fast even for big projects, because Git compares histories, not files.

## 4.2 Creating a Repository on GitHub

1. Log in and click the **+** (top-right) → **New repository**. (Or press `n` anywhere on github.com — GitHub has keyboard shortcuts.)
2. **Repository name:** `my-portfolio` — same as your local folder, to keep your sanity intact.
3. **Description (optional):** one sentence.
4. **Visibility:** Public (anyone can see; the default for portfolios and open source) or Private (only you and invited collaborators).
5. **Leave every checkbox empty** — no README, no .gitignore, no license. Your local repo already has commits; creating any file here would create *divergent histories* that refuse to merge cleanly (Part 12: "unrelated histories").
6. Click **Create repository**.

GitHub now shows you a page of suggested commands. You want the "...or push an existing repository from the command line" section. It is reproduced, with explanations, next.

## 4.3 Linking Your Local Repo: git remote

```bash
git remote add origin git@github.com:<your-username>/my-portfolio.git
```

- `origin` — the nickname you are giving this remote.
- The URL — SSH form (recommended if you set up keys in 1.6). HTTPS form is `https://github.com/<your-username>/my-portfolio.git`. You can find both on the GitHub repo page (green **Code** button).
- The command records the URL in your repo's config — nothing is transferred yet.

Inspect your remotes any time:

```bash
git remote -v
```

Output:

```
origin  git@github.com:yourname/my-portfolio.git (fetch)
origin  git@github.com:yourname/my-portfolio.git (push)
```

Housekeeping commands you may need someday:

```bash
git remote rename origin github     # rename a remote
git remote remove origin            # unlink a remote (does not touch your files)
git remote set-url origin <new-url> # e.g. switching HTTPS -> SSH later
git remote show origin              # detailed status: branches, tracking info
```

## 4.4 Uploading Your Work: git push

```bash
git push -u origin main
```

- `origin` — push to that remote.
- `main` — push this branch.
- `-u` (long form `--set-upstream`) — also links your local `main` to `origin/main` so that **from now on, plain `git push` and `git pull` know what to do**. You pass `-u` once, the very first time you push a branch.

Expected output:

```
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1.02 KiB | 1.02 MiB/s, done.
Total 9 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:yourname/my-portfolio.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

Refresh the GitHub page — your files and history are there. Congratulations: your work is now backed up and shareable.

**Pushing other branches works identically:**

```bash
git switch -c feature/about-page
# ... commit ...
git push -u origin feature/about-page
```

## 4.5 Downloading Changes: git fetch and git pull

The two directions of download — and the difference matters:

- `git fetch origin` — downloads new commits from GitHub into your repo... but **does not touch your files**. You get a private copy of the remote state (`origin/main`), which you can inspect or diff against. Safe, non-destructive, and a favorite of careful developers.
- `git pull` — `git fetch` **+ immediately merge** the remote branch into your current branch. Your files update to incorporate teammates' work.

```bash
git pull          # on a branch with -u set: fetch + merge origin/<this branch>
git pull origin main        # explicit form
git pull --rebase           # fetch + rebase instead of merge (see Part 7.1)
```

Edit on github.com to see it in action (yes, GitHub has a web editor): on your repo page, open `README.md`, click the pencil icon, add a line, **Commit changes**. Your remote is now ahead of your local repo. Back home:

```bash
git pull
# remote: Enumerating objects...
# Fast-forward — your local files now include the web edit
```

**TIP:** After a `fetch` (without merge), `git log main..origin/main` shows what the remote has that you do not — a nice "look before you leap".

## 4.6 Downloading a Whole Project: git clone

`git clone` copies a full repository — files *and entire history* — into a new folder on your machine. This is how you get other people's projects (or your own, onto a second machine):

```bash
git clone git@github.com:octocat/Hello-World.git          # SSH
git clone https://github.com/octocat/Hello-World.git      # HTTPS
```

Output:

```
Cloning into 'Hello-World'...
remote: Enumerating objects: 14, done.
remote: Total 14 (delta 0), reused 0 (delta 0), pack-reused 14
Receiving objects: 100% (14/14), done.
```

This creates `./Hello-World/`, checks out the default branch, and automatically sets `origin` to the URL you cloned from. Your `git push` rights depend on your permission on that repo (public repos: anyone can clone, only collaborators can push).

## 4.7 Fork vs Clone

These get confused constantly. The difference is *where* the copy lives and *who owns* it:

| | **clone** | **fork** |
|---|---|---|
| What it makes | A copy on **your computer** | A copy on **your GitHub account** |
| Where it happens | Terminal | GitHub website (the **Fork** button, top-right of a repo) |
| Typical purpose | Get a project to work on / use locally | Propose changes to a project you cannot push to |
| Can you push to it? | If you have permission on the repo | Always — it is *your* copy |

Forks exist for contribution: you fork someone's repo, push changes to *your fork*, and open a pull request asking the original project to merge them (the full ballet in Part 5.4).

## 4.8 When Push Is Rejected

Push this to memory now, because it *will* happen to you:

```
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:you/my-portfolio.git'
hint: Updates were rejected because the remote contains work that you do not have locally.
```

This is not an error, it is a **refusal to overwrite**. Your local repo is missing commits that exist on GitHub (you edited on the web, or a teammate pushed). Git is protecting those commits. The fix is the natural workflow you already know:

```bash
git pull              # fetch + merge the remote commits into your local branch
git push              # now the push is accepted
```

If `git pull` opens a merge-commit message editor, that means the histories needed a real merge — write/accept the message, save, close, then push. (Run `git config pull.rebase true` as shown in 1.3 and pulls become linear rebase-pulls instead.)

**WARNING:** Never "fix" a rejection with `git push --force` unless you deeply understand Part 7.15. Force-push overwrites the remote, erasing the commits you were missing. On shared branches, that destroys other people's work — the professional world has been burned by this enough that they invented `--force-with-lease` (Part 7.15).

## 4.9 Exercise: Publish Your Portfolio

1. Create the `my-portfolio` repo on GitHub (empty, per 4.2).
2. Link it as `origin` and push with `-u`.
3. Edit `README.md` **on the GitHub website**; commit there.
4. Locally, `git pull` and confirm the change arrived.
5. Create a branch `feature/social-links`, add `social.html`, push it (`-u`), and see it appear on GitHub.
6. Merge it locally into `main`, push `main`, then delete the remote branch: `git push origin --delete feature/social-links`.

<details>
<summary>Show solution sketch</summary>

```bash
# after creating the empty repo on GitHub:
git remote add origin git@github.com:<you>/my-portfolio.git
git push -u origin main

# ...edit README on github.com, commit...

git pull

git switch -c feature/social-links
echo "github.com/you | x.com/you" > social.html
git add social.html && git commit -m "Add social links page"
git push -u origin feature/social-links

git switch main
git merge feature/social-links
git push
git push origin --delete feature/social-links
```

</details>

**Checkpoint:** You can publish, sync, and clone; you know what remotes are; and a rejected push no longer frightens you. Everything from Part 5 onward is about doing this *together with other humans*.

---
# Part 5: The GitHub Collaboration Workflow

Goal of this part: master the professional loop — branch, commit, push, **pull request**, review, merge — plus issues, forks, and a free live website via GitHub Pages.

## 5.1 The Golden Loop

This is the rhythm of professional development, used by teams from two-person startups to the Linux kernel. Memorize the shape:

```
  main ──> branch ──> commit, commit ──> push branch ──> PULL REQUEST
                                                            |
   merge <────────── review, discuss, adjust <──────────────┘
     |
     v
   delete branch, repeat
```

1. **Branch** off `main` for one focused piece of work (3.8 naming).
2. **Commit** early and often, in small coherent steps.
3. **Push** the branch to GitHub.
4. **Open a pull request**: a page comparing your branch with `main`, with your description, and space for review discussion.
5. **Review**: teammates (or you, on your own PR) comment, request changes, approve.
6. **Merge** when approved. GitHub offers merge / squash / rebase (5.5).
7. **Delete the branch** — its history lives on in `main`'s history; the label is no longer needed.

**NOTE:** A pull request is not a Git command — it is a GitHub concept (GitLab and Bitbucket call it a "merge request"). It is a *conversation about a merge*, wrapped around your commits. You can open a PR from a branch of your own repo, or from a branch of your fork of someone else's repo.

## 5.2 Issues: Your Project's To-Do List

An **issue** is a thread on the repo's "Issues" tab: a bug report, feature request, or task. Every issue gets a number (`#142`) — and you will reference that number in branches (`fix/142-...`) and commits ("Fixes #142") to tie everything together.

Essentials:

- **New issue** → title + description (GitHub supports Markdown: code blocks, checklists, screenshots).
- **Labels** (right sidebar): `bug`, `enhancement`, `documentation`, `good first issue`, `help wanted` — labels power filtering and signal friendliness to newcomers.
- **Assignees**: who owns it. **Milestone**: which release. **Projects**: kanban board.
- Closing keywords: writing `Fixes #142` or `Closes #142` in a commit message or PR description **automatically closes the issue** when the code merges into the default branch.
- **Issue templates** (`.github/ISSUE_TEMPLATE/`): pre-fill bug reports with questions like "steps to reproduce", so reports arrive structured.

**TIP:** The "good first issue" label is the standard open-source handshake — it flags tasks suited to newcomers. Remember it for Part 10.5.

## 5.3 Pull Requests in Depth

**Opening one.** After pushing a branch, GitHub's repo page shows a friendly yellow bar: "feature/social-links had recent pushes — **Compare & pull request**". Click it. (Manual route: **Pull requests** tab → **New pull request** → choose base `main` ← compare `feature/social-links`.)

**A good PR description** (template in Part 9.3):

```markdown
## What does this PR do?
Adds an About page with a short bio and photo.

## Why is it needed?
Closes #12 (the About page was listed as a launch blocker).

## How was it tested?
Opened locally via `python -m http.server`; checked on mobile viewport.

## Screenshots
(before/after if UI-related)
```

**The conversation.** Reviewers comment on specific lines (click a line number in the **Files changed** tab), suggest changes, and leave an overall review: **Comment** / **Request changes** / **Approve**. The author pushes more commits to the same branch — the PR updates automatically. Back-and-forth continues until an approval.

**Checks.** If the repo has CI (Part 8), every PR shows test results. Red checks block good repos from merging.

**Merging.** The big green **Merge pull request** button (with a dropdown — next section). After merging, GitHub offers **Delete branch** — click it (local cleanup: `git switch main && git pull && git branch -d feature/...`).

**Draft PRs:** open a PR marked as a draft to share work-in-progress and gather early feedback without requesting a formal review. Mark "Ready for review" when done.

## 5.4 Contributing to Someone Else's Repository

The full ballet — this is *the* open-source workflow. You cannot push to `octocat/Spoon-Knife` (not your repo), so you go through a fork:

```
  upstream: octocat/Spoon-Knife ──fork──> origin: you/Spoon-Knife ──clone──> your laptop
                ^                                                        |
                |____________________ pull request _______________________|
                       (merge my fork's branch into upstream)
```

**Step by step:**

```bash
# 1. FORK: on github.com/octocat/Spoon-Knife, click "Fork" (top-right).
#    You now own github.com/you/Spoon-Knife.

# 2. CLONE your fork (not the original!):
git clone git@github.com:<you>/Spoon-Knife.git
cd Spoon-Knife

# 3. ADD the original repo as a second remote, named "upstream":
git remote add upstream https://github.com/octocat/Spoon-Knife.git
git remote -v        # origin -> your fork, upstream -> the original

# 4. Keep your copy current with the original:
git fetch upstream
git switch main
git merge upstream/main      # or: git rebase upstream/main  (Part 7)

# 5. Branch, commit, push to YOUR fork:
git switch -c docs/improve-readme
# ... make changes, commit ...
git push -u origin docs/improve-readme

# 6. OPEN the PR: on github.com/you/Spoon-Knife, "Compare & pull request".
#    Crucial: the PR goes from you/Spoon-Knife:docs/improve-readme
#    INTO octocat/Spoon-Knife:main. GitHub's compare page handles this,
#    but double-check the two repo names at the top of the PR form.

# 7. Review feedback arrives? Push more commits to the same branch —
#    the PR updates itself.
```

**TIP:** Read the project's `CONTRIBUTING.md` and existing PRs before opening yours — every project has house rules (style, commit format, what they want in the description).

## 5.5 Merge, Squash, or Rebase?

When you press the green button, GitHub offers three ways to merge (some repos enable only one — maintainers' choice):

| Button | Creates | History looks like | When |
|---|---|---|---|
| **Merge** | A merge commit tying your PR commits to main | All N commits + a merge commit; the true, full topology | When the individual commits are meaningful and well-formed |
| **Squash and merge** | ONE commit containing all PR changes | main gains exactly one commit per PR | Default favorite: messy WIP commits disappear; history stays clean |
| **Rebase and merge** | Your N commits, rewritten onto main (new hashes, no merge commit) | Linear history, every commit kept | Teams that want linear history and have disciplined commit hygiene |

**Beginner guidance:** squash-merge by default; you wrote "wip", "fix typo", "actually fix" commits on the branch — nobody needs those in history forever. Learn rebase-merge in Part 7.

## 5.6 Keeping a Fork Up to Date

Your fork does not auto-sync with the original. Options:

- **The button:** on your fork's page, GitHub shows "**Sync fork**" when you are behind — click it. Easiest.
- **The terminal:** the `upstream` remote from 5.4:

```bash
git fetch upstream
git switch main
git merge upstream/main
git push origin main        # update your fork on GitHub too
```

## 5.7 Code Review Etiquette

Reviews are conversations about code, and tone decides whether people learn or flee. The norms of healthy review culture:

- **Comment on the code, never the coder.** "This loop re-reads the file each pass — can we hoist it out?" not "you wrote an inefficient loop".
- **Ask, don't command.** "Could we extract this into a function?" beats "Extract this."
- **Explain the why.** "This will break when `name` is empty" is actionable; "wrong" is not.
- **Praise genuinely.** Flagging the good parts is not flattery — it teaches what *to* keep doing.
- **Suggest instead of demand.** GitHub's "Suggest changes" feature lets you propose an exact edit the author can accept with one click.
- **Distinguish blocking from taste.** "This must change: race condition" vs "nit: I'd rename this variable" — label your nits.

As the PR author: thank reviewers, respond to every comment (even just with a fix commit or "done, thanks"), and never take review comments personally — they are quality control, not judgment of you.

## 5.8 Protecting Branches and Team Settings

On a shared repo, **Settings → Branches → Add branch protection rule** (requires a paid plan for private repos; free for public) can enforce, on `main`:

- **Require a pull request before merging** — no more direct pushes to main.
- **Require approvals** (e.g., 1) — nothing merges without a reviewer's sign-off.
- **Dismiss stale approvals on new commits** — re-review after changes.
- **Require status checks to pass** — CI must be green (Part 8).
- **Restrict who can push** to protected branches.

This is how real teams stop accidents: even the repo owner cannot bypass the rules. Related settings worth knowing: **Collaborators** (Settings → Collaborators, add teammates), **CODEOWNERS** (Part 8.5, auto-assign the right reviewers by file path), and **default branch** choice (Settings → Branches).

## 5.9 GitHub Pages: A Free Website From Your Repo

GitHub will host a static website for free at `https://<you>.github.io/<repo>`:

1. Repo → **Settings → Pages**.
2. Under "Build and deployment": Source → **Deploy from a branch**.
3. Branch: `main`, folder: `/ (root)` → **Save**.
4. Wait 1-2 minutes, refresh — your site is live at the shown URL. (Your `index.html` is served.)

For a user-level homepage `https://<you>.github.io`, create a repo named exactly `<you>.github.io`. For anything fancier (custom domains, Jekyll, GitHub Actions deployment), GitHub Pages documentation is excellent and this taste of "my code is now a website" is motivation enough to explore.

## 5.10 Exercise: The Full Collaboration Loop

Solo simulation of the whole professional loop (works perfectly on your own repo):

1. Create an issue titled "Add projects section" — the work item.
2. Branch `feature/projects-section` referencing the issue number.
3. Add `projects.html` in 2-3 small commits.
4. Push and open a PR; in the description write "Closes #<issue-number>".
5. Review your own PR in the "Files changed" tab; leave one inline comment; fix it with another commit.
6. **Squash and merge**; confirm the issue auto-closed; delete the branch on GitHub.
7. Locally: switch to main, pull, delete the local branch.
8. Enable GitHub Pages and visit your live site.

**Checkpoint:** You can now operate the entire professional collaboration loop, in both directions (your repo, others' repos). Parts 6-7 turn you from a user into a surgeon: undoing, rewriting, and recovering.

---
# Part 6: Undoing Things and Disaster Recovery

Sooner or later you will commit something wrong, delete a branch you needed, or "lose" three hours of work. Goal of this part: a complete undo toolkit plus the mindset that keeps you calm. This is the part people wish they had read *before* the incident.

## 6.1 The Safety-Net Mindset

Three facts keep professionals calm:

1. **Every commit is nearly immortal.** Git objects are only truly deleted after ~30 days of being unreachable *and* a garbage collection — until then, the **reflog** (6.8) can almost always find them.
2. **Git refuses to destroy uncommitted work silently.** Almost every "scary" command asks, blocks, or fails rather than eats your files.
3. **The dangerous window is uncommitted changes.** Until you commit, edits exist only in your working directory — that is the state no time machine can recover. Professional habit: **commit early, commit often** — a "wip" commit you later clean up beats three lost hours. You can always rewrite history before pushing (Part 7.3); you cannot resurrect what was never committed.

**TIP:** The moment anything feels wrong: **stop typing commands**. Run `git status`, then `git reflog`. Most panic-destruction happens *while* panicking.

## 6.2 Unstaging: git restore --staged

Change of heart about what goes into the next commit — you staged `debug.log` by accident:

```bash
git restore --staged debug.log
```

The change leaves the staging area; your file edits are untouched. Unstage everything:

```bash
git restore --staged .
```

(Legacy equivalent you will see in older tutorials: `git reset HEAD <file>`.)

## 6.3 Discarding Local Changes: git restore

You edited `index.html`, the edit is bad, you want the file back exactly as it was at the last commit:

```bash
git restore index.html            # one file back to its committed state
git restore .                      # every tracked file back to committed state
git restore --source=HEAD~2 file   # time-travel: file as it was 2 commits ago
```

**WARNING:** This *discards uncommitted edits permanently*. Unlike commits, discarded working-directory changes are not in the reflog. Only run this on changes you have truly given up on. Git will refuse if the file is also staged — unstage first if that is intended.

## 6.4 git reset: Soft, Mixed, Hard

`git reset` moves the current branch to another commit, and its three modes decide what happens to your *content*:

```bash
git reset --soft HEAD~1    # move branch pointer back; keep changes STAGED
git reset --mixed HEAD~1   # move branch pointer back; keep changes UNSTAGED (default)
git reset --hard HEAD~1    # move branch pointer back; DELETE the changes
```

What "move back" means — `HEAD~1` is "the commit before HEAD", so this is "undo the last commit":

```
 BEFORE                              AFTER --soft/--mixed            AFTER --hard
    main                                main                          main
     |                                   |                              |
 A---B---C---D                     A---B---C---D                  A---B---C---D
             ^                                   ^                            ^
   (HEAD, commit D gone            (D's changes now sit         (D's changes are
    from the branch)                staged/unstaged)              gone entirely)
```

| Mode | Commit | Changes afterwards | Use case |
|---|---|---|---|
| `--soft` | removed from history | fully staged, ready to re-commit | "Recommit this properly / combine commits" |
| `--mixed` (default) | removed | present but unstaged | "Un-commit, let me re-select what belongs in it" |
| `--hard` | removed | **gone** | "That commit never happened" — local-only! |

Examples that earn their keep daily:

```bash
git reset --soft HEAD~3        # collapse the last 3 commits into one:
git commit -m "One clean commit"   # ...then commit the combined staged state

git reset --hard origin/main   # abandon ALL local commits and changes;
                               # become exactly what GitHub has (careful!)

git reset <hash>               # jump back to any commit (mixed default)
```

**WARNING:** `git reset --hard` is the one command in this part that truly deletes. Two safety rules: (1) only `--hard` on history *nobody else has* — it rewrites your branch; (2) when in doubt, `--soft`. You can always `--hard` later; you cannot un-`--hard`.

## 6.5 git revert: The Safe Undo

`reset` *deletes* history — fine locally, but forbidden on shared branches (others already built on those commits). **`git revert`** instead creates a **new commit that does the opposite** of a given commit:

```bash
git revert <hash>              # new commit undoing that one commit
git revert HEAD                # undo the most recent commit
git revert --no-commit HEAD~2..HEAD   # prepare ONE commit undoing a range
```

```
 BEFORE                        AFTER revert D
    main                          main
     |                             |
 A---B---C---D                A---B---C---D---R
                                (R = "revert" commit,
                                 which re-applies the
                                 inverse of D's changes)
```

History gains a commit; nothing is rewritten; teammates just `git pull` and get the reversal. This is the professional's undo on anything pushed.

## 6.6 reset vs revert: Which One When?

| Situation | Command |
|---|---|
| Last commit is wrong, **not pushed yet** | `git reset --soft HEAD~1`, fix, re-commit |
| Last N local commits should become one | `git reset --soft HEAD~N`, commit once |
| A commit, **already pushed/shared**, broke things | `git revert <hash>`, push |
| My branch is a mess, remote has the truth | `git reset --hard origin/main` (nuclear, local-only) |
| I want to see an old state, not change anything | `git switch --detach <hash>` (look around), then `git switch main` |

## 6.7 git stash: Shelving Work in Progress

You are mid-feature and something urgent arrives. `git stash` sweeps your uncommitted changes off the working directory into a safe stack, giving you a clean slate — without committing "wip" junk:

```bash
git stash                     # shelve uncommitted changes (tracked files)
git stash push -m "wip: hero animation"   # same, but labeled (do this)
git stash -u                  # include untracked files too

git stash list                # your stack of shelves
# stash@{0}: On main: wip: hero animation
# stash@{1}: On main: wip: contact form

git stash pop                 # restore the newest stash AND remove it from the stack
git stash apply stash@{1}     # restore a specific stash, keep it in the stack
git stash drop stash@{0}      # delete one stash
git stash clear               # nuke the whole stack (careful)

git stash branch fix/from-stash   # turn a stash into a real branch (best escape
                                  # from conflicts when popping)
```

Typical rescue flow:

```bash
git stash push -m "wip: hero animation"
git switch main && git switch -c fix/urgent-thing
# ... fix, commit, push ...
git switch feature/hero
git stash pop                 # your work-in-progress returns
```

**NOTE:** If `git stash pop` hits a conflict, the stash is *kept* (not dropped) — resolve the conflict, `git add`, and drop manually. Nothing is lost.

## 6.8 git reflog: The Time Machine

Here is the fact that changes everything: **Git records every position HEAD has ever been in**, in a log called the reflog — for at least 30 days. This is how you rescue "deleted" commits, branches, and even resets.

```bash
git reflog
```

Sample output:

```
a1b2c3d (HEAD -> main) HEAD@{0}: commit: Add projects page
e4f5a6b HEAD@{1}: commit (initial): Initial commit
e4f5a6b HEAD@{2}: reset: moving to HEAD~1     <- you reset away a commit here
f7a8b9c HEAD@{3}: commit: Add contact form    <- "lost" commit, still findable!
```

Reading it: "HEAD was at position X, then operation Y happened". Every line is a place you can return to. To rescue the "deleted" commit `f7a8b9c`:

```bash
git reset --hard f7a8b9c          # or, back to where you were:
git reset --hard HEAD@{3}
```

Rescue a deleted branch (its commits are still in the reflog):

```bash
git reflog                       # find the hash the branch pointed to
git switch -c rescued-branch <hash>
```

**TIP:** The beloved site **https://ohshitgit.com** catalogs exactly these rescue recipes. Bookmark it. When it says "dude, where's my commit", the answer is always `git reflog`.

**NOTE:** Reflog entries are local to *your* machine — that is why data lost from reflog + garbage collection is truly gone, and why the *only* true backup is having pushed your work to GitHub.

## 6.9 Cleaning Untracked Files: git clean

`git clean` deletes untracked files (new files Git has never seen). Always preview first:

```bash
git clean -n        # DRY RUN: what would be deleted?
git clean -f        # delete untracked files (no directories)
git clean -fd       # include untracked directories
git clean -fdx      # ALSO delete ignored files (node_modules etc.) - nuclear
```

**WARNING:** No reflog, no undo, no recycle bin — `git clean` is a straight delete. `-n` first, every time. Personally I prefer deleting files in the file explorer where I can see them.

## 6.10 git cherry-pick

Copy one specific commit from anywhere (another branch, a fork, a colleague's repo) onto your current branch:

```bash
git switch fix/hotfix
git cherry-pick <hash>            # applies that commit's changes here
git cherry-pick A^..B             # a range: A inclusive through B
git cherry-pick --abort           # mid-conflict escape
git cherry-pick --continue        # after resolving a conflict (then add files)
```

Classic use: a bug was fixed on `develop`, but `main` in production needs it *now* — `git switch main; git cherry-pick <fix-hash>; git push`. The commit is copied (new hash, same content), so both lines end up containing the fix.

**TIP:** `git log <branch>` works without switching: `git log develop` to find the hash. `gh pr checkout <number>` even lets you cherry-pick across clones of teammates' PR branches.

## 6.11 The Emergency Recovery Table

Print this. When disaster strikes, find your row:

| Disaster | The fix |
|---|---|
| "I committed the wrong thing, haven't pushed" | `git reset --soft HEAD~1`, fix, re-commit |
| "I want to change my last commit message" | `git commit --amend -m "new message"` (unpushed only) |
| "I committed a secret/password" (unpushed) | `git reset --soft HEAD~1`, remove from staging, add to `.gitignore`, recommit |
| "I PUSHED a secret" | **Rotate the secret immediately** (it is compromised), then rewrite history or `git revert`; GitHub support can purge cached views |
| "I deleted a branch I needed" | `git reflog` → find the hash → `git switch -c <branch> <hash>` |
| "I reset --hard and lost commits" | `git reflog` → `git reset --hard HEAD@{n}` |
| "My merge conflict is a mess, abort!" | `git merge --abort` (or `git rebase --abort`) |
| "I need to see an old version of a file" | `git show <hash>:path/to/file` |
| "I deleted a file (committed earlier)" | `git restore <path>` restores from HEAD |
| "I want to delete untracked junk" | `git clean -n` → `git clean -fd` |
| "I'm on detached HEAD and panicking" | `git switch main` (or `git switch -c rescue-branch` first) |
| "Everything is broken, make it match GitHub" | `git fetch && git reset --hard origin/main` (destroys local-only work — check `git status` first) |
| "My push was rejected" | `git pull` (resolve if needed), then `git push` (Part 4.8) |
| "I want yesterday's version of everything, but keep today as a branch" | `git switch -c todays-work` (save today), `git switch main`, `git reset --hard <yesterdays-hash>` |
| "I deleted the .git folder / repo corruption" | If you can still push... clone fresh, copy files over, commit. Then: `git fsck` for future warnings |

## 6.12 Exercise: Disaster Drills

Deliberately cause and survive four disasters (these drills turn panic into procedure):

1. **The bad commit:** commit a file `wrong.txt`, then undo it completely with `--soft`, then `--hard`. Note what happens to the file each time.
2. **The lost branch:** create a branch, commit to it, delete it with `-D`, then resurrect it via reflog.
3. **The stash cycle:** edit two files, stash with a message, verify a clean tree, pop the stash.
4. **The time machine:** `git reset --hard HEAD~2`, gasp, then restore everything via `git reflog`.

<details>
<summary>Show solution sketch</summary>

```bash
# 1
echo "oops" > wrong.txt && git add . && git commit -m "bad"
git reset --soft HEAD~1     # wrong.txt still staged
git status
git reset --hard HEAD~0     # careful: now file content still on disk (staged)
# for a true full-undo drill recommit then: git reset --hard HEAD~1 && git clean -f

# 2
git switch -c drill && echo x > drill.txt && git add . && git commit -m "work"
git switch main && git branch -D drill
git reflog                   # find drill's last commit hash
git switch -c drill <hash>   # resurrected

# 3
echo a > one.txt && echo b > two.txt
git stash push -m "drill stash"
git status                   # clean
git stash list
git stash pop

# 4
git log --oneline            # remember current HEAD hash
git reset --hard HEAD~2
git reflog                   # top entry = where you were
git reset --hard HEAD@{1}    # everything restored
```

</details>

**Checkpoint:** You now know how to undo anything: unstage, discard, reset, revert, stash, reflog, cherry-pick, clean. This knowledge is what separates "I use Git" from "I am calm in Git". Next: the professional's power tools.

---
# Part 7: Intermediate to Advanced Git

Goal of this part: the tools that mark a serious Git user — rebase (including interactive), tags, bisect, blame, hooks, worktrees — plus the etiquette of rewriting history.

## 7.1 git rebase

Rebase moves your branch's commits on top of another branch, as if you had started your work *after* those changes. The two great uses:

**Use 1 — update your branch with the latest main (the daily one):**

```
 BEFORE rebase                    AFTER rebase
      main                              main
       |                                 |
 A --- B --- C                      A --- B --- C
              \                                \
               D --- E (feature)                D' --- E' (feature)
               \                                /
                (your commits D,E              (D',E' are COPIES of D,E
                 started from B)                replayed on top of C)
```

```bash
git switch feature/my-thing
git rebase main        # replay my commits on top of main
```

Compare with merging main into your branch: a merge produces an M-shaped history with merge commits; a rebase produces a straight line, `A-B-C-D'-E'`. Both integrate the same changes — the difference is the *story the history tells*.

**Use 2 — linear history:** many teams prefer the straight line: every commit reads like a chronological journal with no "merge branch X" interruptions.

**During a rebase, conflicts can occur** (Git pauses at each replayed commit):

```bash
git rebase main
# CONFLICT ... fix the file, then:
git add <resolved-file>
git rebase --continue     # repeat per conflicted commit
git rebase --abort        # bail out, return to the pre-rebase state (always available)
```

**NOTE:** During a *rebase*, `--ours` / `--theirs` flip compared to a merge: `--ours` means the branch you are rebasing *onto* (main), `--theirs` means *your* commits being replayed. This bites everyone once.

## 7.2 The Golden Rule of Rebase

> **Never rebase commits that other people already have.**

Rebase copies commits (new hashes, same changes). If teammates built on the originals and you rewrite the branch underneath them, you create parallel histories: same changes twice, merge conflicts from hell, and teammates who lose trust in shared branches.

- Rebasing **your own unpushed (or own-fork) branch**: always fine. Do it constantly.
- Rebasing a **shared branch** like `main`/`develop`: never.
- When a PR requires updates, rebase your *feature branch* onto the *base branch*, never the other way around.

## 7.3 Interactive Rebase: Rewriting History

`git rebase -i` opens your editor with a *script* of your recent commits, letting you clean them up before the world sees:

```bash
git rebase -i HEAD~4        # "let me redo the last 4 commits"
```

The editor shows (oldest first):

```
pick a1b2c3d wip
pick d4e5f6a add hero
pick g7h8i9j fix typo
pick k0l1m2n wip wip

# Commands: p pick, r reword, e edit, s squash, f fixup, d drop
```

Edit the left column to build your new history, save, close:

| Command | Effect |
|---|---|
| `pick` | keep the commit as-is |
| `reword` | keep changes, edit the commit *message* |
| `edit` | pause here to change the commit's *content* (amend it) |
| `squash` | melt this commit INTO the one above it; combine messages |
| `fixup` | like squash, discard this commit's message |
| `drop` | delete the commit entirely |

Turn the four messy commits into one clean one:

```
pick a1b2c3d wip
squash d4e5f6a add hero
fixup g7h8i9j fix typo
fixup k0l1m2n wip wip
```

Save → Git replays the script → your branch now has one tidy commit. If a conflict interrupts, resolve, `git add`, `git rebase --continue`. `git rebase --abort` cancels everything.

**TIP:** This is the standard polish before opening a pull request (or after review, before squash-merge): "wip" commits are fine while you work; interactive rebase launders them into a clean series. Same golden rule applies: only rebase commits not yet in the shared repo.

## 7.4 Merge vs Rebase: The Decision

| Situation | Reach for | Why |
|---|---|---|
| Update my unpushed feature branch with main | `git rebase main` | cleanest linear branch; trivial conflicts at small sizes |
| Bring finished feature into main (terminal) | merge (often via GitHub PR) | recorded integration point; safe with others |
| My branch has junky WIP commits | `rebase -i` squash them | presentable history |
| A pushed personal branch needs fixing | fix locally + `push --force-with-lease` | no collaborators to hurt |
| A SHARED branch needs "fixing" | `git revert` — do not rewrite | never rewrite shared history |

Mantra: **rebase for private polish, merge for public integration.**

## 7.5 Tags and Releases

Tags are permanent labels on specific commits, used for versions:

```bash
git tag -a v1.0.0 -m "First stable release"    # annotated tag (use this kind)
git tag                                        # list
git tag v1.0-beta                              # lightweight tag (no message; avoid)
git push origin v1.0.0                         # push ONE tag
git push --tags                                # push all tags
git tag -d v1.0.0                              # delete locally
git push origin --delete v1.0.0                # delete on the remote
```

Tag the commit you are on (or add a hash at the end to tag any commit). To view a tagged release: `git checkout v1.0.0` puts you on a *detached HEAD* (looking, not developing — Part 12).

**Semantic versioning (semver)** — the numbering convention `vMAJOR.MINOR.PATCH`:
- **PATCH** (`v1.0.1`): bug fixes, no new features.
- **MINOR** (`v1.1.0`): new features, backward compatible.
- **MAJOR** (`v2.0.0`): breaking changes.

On GitHub, **Releases** (right sidebar of a repo, or `/releases`) wrap a tag in release notes and downloadable artifacts. Draft one: Releases → **Draft a new release** → choose/create tag → title → notes → publish. Tag + release notes + CI artifacts = how real software ships (Part 8.6 automates it).

## 7.6 Aliases: Build Your Own Shortcuts

Aliases turn multi-word commands into your personal shorthand, stored in `.gitconfig`:

```bash
git config --global alias.st "status"
git config --global alias.co "switch"
git config --global alias.cm "commit -m"
git config --global alias.last "log -1 HEAD --stat"
git config --global alias.undo "reset --soft HEAD~1"
git config --global alias.lg "log --oneline --graph --all --decorate"
```

Now `git lg` runs the best log format, `git undo` soft-drops the last commit. Some people carry a decade of aliases; three or four high-frequency ones is the sweet spot.

## 7.7 git blame: Who Wrote This Line?

```bash
git blame index.html               # every line: hash, author, date, line number
git blame -L 10,20 index.html      # just lines 10-20
git blame -e index.html            # show emails
```

Sample:

```
a1b2c3d (Alice 2026-08-14 10:22 12) <h1>Best Portfolio Ever</h1>
```

Blame answers "who last touched this line, in which commit" — the entry point for asking *why* (then `git show a1b2c3d`). The name is a historical joke; use it for archaeology, not accusation.

## 7.8 git bisect: Binary Search for Bugs

A bug exists in today's build but not in `v1.0` — introduced somewhere in between, across 300 commits. `git bisect` binary-searches: it checks out midpoints, you mark them good or bad, and it homes in on the culprit commit in ~log2(N) steps (300 commits → ~9 checks).

```bash
git bisect start
git bisect bad                 # current state has the bug
git bisect good v1.0.0         # that version was fine
# Git checks out a midpoint:
# Bisecting: 150 revisions left to test after this
# ... run the tests / reproduce the bug ...
git bisect good               # or: git bisect bad
# ... repeat a few times ...
# <hash> is the first bad commit
git bisect reset               # return to where you started
```

Power move: automate the verdict per step:

```bash
git bisect run npm test        # exit code 0 = good, non-zero = bad
```

Then `git show <hash>` to see exactly what change introduced the bug. This is the closest Git comes to feeling like magic.

## 7.9 Searching Your History

```bash
git log -S "initializeApp"          # commits where this string was ADDED/REMOVED (pickaxe)
git log -- index.html               # history touching one file
git log --grep="login" -i           # message search, case-insensitive
git grep "TODO"                     # search tracked files (current checkout)
git grep "TODO" v1.0.0              # search at an old tag... time-travel grep
git log --format="%h %an %s"        # custom output format
git shortlog -sn                    # commits per author, sorted
```

`git log -S` is the archaeologist's tool: find *the commit where a function appeared or vanished*.

## 7.10 Submodules

A submodule embeds another Git repo at a fixed commit inside your repo:

```bash
git submodule add https://github.com/example/themes.git themes/
git commit -m "Add themes submodule"
git clone --recurse-submodules <url>          # clones WITH submodules
git submodule update --init --recursive       # for an existing clone
```

**WARNING:** Submodules are notorious for confusing even experts: teammates must remember to `update --init` after pulls, and to re-point the parent repo when the submodule moves. Modern alternatives worth investigating first: Git subtrees, package managers (npm/pip/cargo), or vendoring scripts. Know submodules exist; reach for them last.

## 7.11 git worktree

A worktree gives you a **second working folder attached to the same repository**, with a *different branch checked out* — no stashing to switch context:

```bash
git worktree add ../portfolio-hotfix hotfix-branch   # new folder, that branch
# work in ../portfolio-hotfix while ../portfolio stays on feature work
git worktree list
git worktree remove ../portfolio-hotfix
```

Use cases: test your feature against a `main` build simultaneously; run long jobs on one branch while developing on another; review a PR without disturbing your editor state.

## 7.12 Cloning Big Repositories Efficiently

For huge histories (linux kernel scale), partial clones save time and disk:

```bash
git clone --depth 1 <url>           # shallow: latest snapshot only, no history
git clone --single-branch <url>     # only one branch
git clone --filter=blob:none <url>  # partial: fetch file contents on demand
git fetch --unshallow               # later, if you DO need the history
```

**NOTE:** Shallow clones break some history operations (`blame` past the cutoff, some merges); fine for reading/deploying, less so for contributing.

## 7.13 Git Hooks

Hooks are scripts Git runs automatically at specific points — local, per-repo, in `.git/hooks/` (never versioned by default):

```bash
# .git/hooks/pre-commit — runs before every commit; non-zero exit BLOCKS it
#!/bin/sh
if grep -rn "TODO" --include="*.py" .; then
  echo "COMMIT BLOCKED: resolve TODOs first"
  exit 1
fi
```

```bash
chmod +x .git/hooks/pre-commit      # hooks must be executable
```

Common uses: block "TODO"/debugger statements, run a linter, validate the commit message format. Popular frameworks (Husky for JS, pre-commit for Python) make hooks *versioned* and shareable with the whole team — raw `.git/hooks` do not travel with clones. GitHub-side equivalents (required status checks) live in Part 8.

## 7.14 Line Endings and .gitattributes

Windows ends lines with CRLF (`\r\n`); macOS/Linux/CI use LF (`\n`). Git translating between them causes those warnings and phantom "whole file changed" diffs. Fix once per OS:

```bash
git config --global core.autocrlf input    # macOS / Linux
git config --global core.autocrlf true     # Windows
```

The repo-side, portable fix — a `.gitattributes` file at the repo root:

```
* text=auto        # let Git normalize all text files to LF in the repo
*.bat text eol=crlf   # files that genuinely need CRLF
*.png binary       # never touch these
```

Commit that file and the whole team (and CI) stops fighting over invisible characters.

## 7.15 Pushing Rewritten History Safely

After any history rewrite (rebase, amend, filter) of an *already pushed* branch, plain `git push` is rejected (remote has the old commits). The professional replacement for `--force`:

```bash
git push --force-with-lease
```

`--force` overwrites blindly. `--force-with-lease` overwrites **only if nobody pushed to the remote since your last fetch** — if a teammate's commits appeared, it refuses, protecting you from erasing their work. Make it a reflex: rewritten branch → `push --force-with-lease`. (GitHub repo settings can even forbid plain force-pushes entirely.)

**Checkpoint:** Rebase, tags, bisect, hooks, worktrees, force-with-lease — this chapter is the "senior user" toolkit. Part 8 adds the automation layer that turns a repo into a self-running project.

---
# Part 8: GitHub Power Tools

Goal of this part: automate your repository with **GitHub Actions** (tests, builds, deployments), lock it down with GitHub's security features, and run GitHub from the terminal with `gh`. Everything here runs on GitHub's servers — free for public repos, with generous free minutes for private ones.

## 8.1 GitHub Actions: Automation for Everyone

**GitHub Actions** is GitHub's built-in automation engine: you describe *workflows* in YAML files, and GitHub runs them in fresh virtual machines when events happen (push, pull request, schedule, release...).

The vocabulary:

- **Workflow** — one YAML file in `.github/workflows/` describing an automated pipeline.
- **Event** — the trigger: `push`, `pull_request`, `schedule`, `release`, `workflow_dispatch` (manual run button)...
- **Job** — a set of steps running on one virtual machine ("runner").
- **Step** — one action: either a shell command (`run:`) or a reusable **action** (`uses:`) from the GitHub Marketplace (e.g. `actions/checkout`).

What people build with it: run tests on every push, deploy websites on merge to main, nightly builds, auto-label PRs, publish packages on release, and literally thousands more.

## 8.2 Your First Workflow, Line by Line

Create `.github/workflows/ci.yml` in your repo:

```yaml
name: CI                          # workflow name shown in the Actions tab

on:                               # WHEN to run
  push:
    branches: [main]              # on pushes to main
  pull_request:
    branches: [main]              # and on PRs targeting main

jobs:                             # WHAT to run
  test:
    runs-on: ubuntu-latest        # the virtual machine to use

    steps:
      - name: Check out the code
        uses: actions/checkout@v4  # marketplace action: clones your repo onto the runner

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:                      # inputs to that action
          node-version: '20'

      - name: Install dependencies
        run: npm ci                # plain shell command

      - name: Run tests
        run: npm test
```

Commit and push:

```bash
mkdir -p .github/workflows
# (save the file as .github/workflows/ci.yml)
git add .github/workflows/ci.yml
git commit -m "Add CI workflow"
git push
```

Then on GitHub: **Actions tab** → your "CI" workflow running live (each step's log streams as it runs) → green checkmark. From now on every push and PR shows its pass/fail status right next to the commit, and PRs carry the check into review.

No Node project? The pattern is identical for any stack: pick a `setup-*` action and your build commands:

```yaml
      - uses: actions/setup-python@v5
        with: { python-version: '3.12' }
      - run: pip install -r requirements.txt
      - run: pytest
```

**TIP:** Steal from the best: the `actions/` org, the Marketplace (thousands of ready actions), and any open-source repo's `.github/workflows/` folder are all copy-pasteable starting points.

## 8.3 Secrets: Storing Passwords Safely

Deploy keys, API tokens, and passwords must never be committed (6.11 — if you pushed one, *rotate it*). Store them as **repository secrets** and inject them into workflows at runtime:

1. Repo → **Settings → Secrets and variables → Actions → New repository secret**.
2. Name: `DEPLOY_TOKEN`, value: the token. (Encrypted; masked in logs if printed.)
3. Reference it in a workflow:

```yaml
      - name: Deploy
        run: ./deploy.sh
        env:
          DEPLOY_TOKEN: ${{ secrets.DEPLOY_TOKEN }}
```

Environments (Settings → Environments) add approval gates and scoped secrets for staging/production — the standard layer for serious deployments.

## 8.4 More Workflow Patterns

**Deploy a website on every push to main** (this is what modern GitHub Pages does — set Pages source to "GitHub Actions"):

```yaml
name: Deploy site
on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v5
      - uses: actions/upload-pages-artifact@v3
        with: { path: '.' }
      - id: deployment
        uses: actions/deploy-pages@v4
```

**A nightly job** (cron syntax, in UTC — this one is 03:00 daily):

```yaml
on:
  schedule:
    - cron: '0 3 * * *'
  workflow_dispatch: {}        # plus a manual "Run workflow" button
```

**Run tests on a matrix** (multiple versions at once — a superpower of CI):

```yaml
    strategy:
      matrix:
        node: [18, 20, 22]
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '${{ matrix.node }}' }
      - run: npm ci && npm test
```

**Manual approval for production deploys:** combine an `environment` with required reviewers (Settings → Environments → Protection rules).

**NOTE:** Runner minutes: free unlimited for public repos; private repos include 2,000 free minutes/month (beyond that, billed). Watch the Actions tab for usage.

## 8.5 Keeping Your Project Secure

GitHub ships security tooling you should switch on in **Settings → [tabs below]**:

- **Code security: Dependabot alerts** — GitHub scans your dependency manifests (`package-lock.json`, `requirements.txt`...) against vulnerability databases and opens alerts/PRs when a dependency has a known CVE. Enable "Dependabot version updates" and it even opens dependency-bump PRs monthly.
- **Secret scanning** — detects API keys accidentally pushed (works on public repos by default; enable "push protection" so the push is *blocked* before the secret lands).
- **CODEOWNERS** (`.github/CODEOWNERS`) — automatically assign the right reviewers by path:

```
# Lines: pattern -> owners (@users or @teams)
*                        @you
/src/auth/               @security-team
/.github/workflows/      @devops-lead
```

- **Branch protection** (5.8) — required reviews + required green checks.
- **Security advisories** — a private channel to report/fix/announce vulnerabilities in your own project.

## 8.6 Releases and Changelogs

1. Ship code: merge to `main`, tag locally, push the tag (7.5):

```bash
git tag -a v1.1.0 -m "Second feature release"
git push origin v1.1.0
```

2. On GitHub: **Releases → Draft a new release** → tag `v1.1.0` → title → notes → **Publish release**.

3. Automate the whole thing — a release workflow that builds artifacts and attaches them to the GitHub release when you push a tag:

```yaml
on:
  push:
    tags: ['v*']
permissions:
  contents: write
jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./build.sh
      - uses: softprops/action-gh-release@v2
        with:
          files: dist/*
```

Changelog discipline: `git log v1.0.0..v1.1.0 --oneline` prints exactly what shipped between two tags — paste-worthy raw material for release notes ("Keep a Changelog" format is the house style for humans).

## 8.7 The GitHub CLI: GitHub From Your Terminal

`gh` (installed and authenticated in 1.7) puts the whole GitHub website in your terminal. Greatest hits:

```bash
gh repo create my-app --public --source=. --push   # repo created + pushed in one shot
gh repo clone owner/repo
gh repo fork owner/repo --clone                    # fork + clone, wired to upstream

gh issue create --title "Login fails on Safari" --label bug
gh issue list --assigned @me
gh issue view 42

gh pr create --fill                                 # opens a PR for current branch,
                                                   # auto-filled from commits
gh pr list --state open
gh pr view 31 --web                                 # jump to the browser
gh pr checkout 31                                   # check out someone's PR locally!
gh pr checks 31                                     # CI status for a PR
gh pr merge 31 --squash --delete-branch             # merge + cleanup

gh browse                                           # open current repo in browser
gh api user                                         # raw GitHub API access
gh run watch                                        # live-watch your Actions run
gh release create v1.1.0 ./dist/*                   # release with artifacts
```

**TIP:** `gh`'s output is script-friendly — `gh pr list --json number,title` gives JSON for automation. `gh alias set` even lets you build your own subcommands.

## 8.8 Gists

**Gists** (gist.github.com) are single-file, version-tracked paste bins with Git underneath: create one from the + menu → paste → create. Secret gists are unlisted (not private — anyone with the URL). Every gist is a mini Git repo: `git clone https://gist.github.com/<id>.git`, edit, push — the world's most underestimated snippet-sharing tool. `gh gist create file.txt` does it from the terminal.

**Checkpoint:** Your repos can now test themselves, deploy themselves, and defend themselves, and you can drive GitHub without leaving the terminal. Part 9: behaving like a professional on teams.

---
# Part 9: Best Practices and Conventions

Goal of this part: the habits that make your history readable, your PRs mergeable, and your repos look professionally run — the difference between "knows the commands" and "works well in a team".

## 9.1 Atomic Commits and Small Pull Requests

**An atomic commit does exactly one thing.** One bug fixed, or one feature added, or one refactor applied — never "update stuff". Two questions to self-check before committing:

1. *If this commit needed to be reverted, would `git revert <it>` cleanly undo one logical change?*
2. *Could I describe the commit in one line under 50 characters without the word "and"?*

Why it matters: atomic commits are searchable (7.9), revertable (6.5), reviewable, and bisectable (7.8). A commit called "updates" is none of those things.

**Small PRs** follow the same logic at the bigger scale: a 60-line PR gets reviewed carefully today; a 2,000-line PR gets skimmed next week (or rubber-stamped, which is worse). Rule of thumb: aim for PRs a reviewer can process in 15-30 minutes. If the feature is big, ship it as a sequence of small PRs, or behind a feature flag.

**Commit often, push often, merge often.** Long-lived branches rot: the longer your branch lives, the further it drifts from main and the uglier the eventual merge. Integrate daily if you can (this is the core insight behind GitHub Flow and trunk-based development).

## 9.2 Commit Message Conventions

The industry-converging standard is **Conventional Commits** — a `type(scope): subject` format that is machine-parseable (changelog tools and semantic-release build releases from it):

```
type(scope): imperative summary under 50-72 chars

Optional body: explain WHY, wrapped at 72 chars. What changed is
visible in the diff; the message should carry the reasoning,
context, and links (issue numbers) the diff cannot.

Optional footer: BREAKING CHANGE: ... / Fixes #123
```

The types:

| Type | Use for | Example |
|---|---|---|
| `feat` | new feature | `feat(cart): add quantity selector` |
| `fix` | bug fix | `fix(auth): handle expired tokens gracefully` |
| `docs` | documentation | `docs: expand setup steps in README` |
| `style` | formatting only | `style: run prettier on src/` |
| `refactor` | no behavior change | `refactor(api): extract request builder` |
| `perf` | performance | `perf(list): memoize row rendering` |
| `test` | tests | `test(auth): cover token refresh path` |
| `chore` | tooling/deps | `chore: update dependencies` |
| `ci` | CI changes | `ci: cache node_modules between runs` |

Writing rules that matter more than the format:

- **Imperative mood:** "Add", "Fix", "Handle" — not "Added", "Fixes", "Fixed". Read the message as: *if I apply this commit, it will ___.*
- **Subject line** ≤ 50-72 characters, lowercase after the type, no trailing period.
- **Body explains why, not what.** The diff already says what.
- **Reference issues:** `Fixes #142` in the body/footer to close them automatically (5.2).

Good vs. forgettable:

```
fix: don't crash when cart is empty                      # findable, revertable, honest
update stuff                                             # archaeology pain
fix bug                                                  # which bug? where?
fix(cart): don't crash when cart is empty                # + scope: chef's kiss
```

## 9.3 Pull Request Description Template

Save as `.github/PULL_REQUEST_TEMPLATE.md` and every new PR starts pre-structured (the biggest single gift you can give your reviewers):

```markdown
## What does this PR do?
One paragraph, plain language.

## Why?
The problem/requirement. Link the issue: Closes #<n>.

## How did you test this?
Steps, commands, environments — how you know it works.

## Screenshots / demo
UI changes only, before/after.

## Checklist
- [ ] Tests added/updated
- [ ] Docs updated (README/CHANGELOG)
- [ ] No secrets or debug code left
- [ ] Commit messages follow the convention
```

## 9.4 Repository Housekeeping Files

A professionally run repo's root should contain some of:

| File | Purpose |
|---|---|
| `README.md` | Face of the project: what, why, quickstart, usage (see below) |
| `LICENSE` | The legal foundation — without it, "all rights reserved" by default |
| `CONTRIBUTING.md` | How to submit changes: setup, style, commit format, PR etiquette |
| `CODE_OF_CONDUCT.md` | Behavior rules for your community (GitHub generates one) |
| `CHANGELOG.md` | Human-readable history of releases ("Keep a Changelog" format) |
| `.gitignore` / `.gitattributes` | Junk and line-ending hygiene (2.7, 7.14) |
| `.github/` | Issue templates, PR template, workflows, CODEOWNERS, funding |

**README.md anatomy** — the order that works (this very document follows it!):

1. **Project name + one-line pitch** (the first thing anyone reads).
2. **Badges** (build status, version, license) — instant credibility signals.
3. **Screenshot or demo GIF** — a picture beats 200 words.
4. **Requirements + installation** — copy-pasteable commands.
5. **Usage** — minimal working example.
6. **Configuration** — options/env vars.
7. **Contributing** — pointer to CONTRIBUTING.md.
8. **License** — pointer to LICENSE.
9. **Credits / acknowledgements**.

Write the README for a stranger: they should go from zero to running your project without asking you anything.

## 9.5 Choosing a License

Nobody reads licenses until the day someone must. Quick guide (full comparisons at choosealicense.com; GitHub's "Choose a license" page adds them in one click):

| License | Spirit | You want it if... |
|---|---|---|
| **MIT** | Do anything, keep the copyright line | You want maximum adoption with zero ceremony (the default choice) |
| **Apache-2.0** | MIT + explicit patent grant | Patents are in play (corporate-friendly) |
| **GPL-3.0** | Copyleft: derivatives must stay open | You require derivatives to remain open source |
| **AGPL-3.0** | GPL + network use counts | You close the SaaS loophole |
| **MPL-2.0** | File-level copyleft | You want a middle path |
| **Unlicense / CC0** | Public domain dedication | You renounce everything |

**WARNING:** No LICENSE file = legally, nobody may copy/use/contribute. If you want an open project, add one today. Also: add **notices for assets you do not own** — a license in your repo covers *your* code only.

## 9.6 The Top 10 Git Mistakes to Avoid

1. **`git push --force` on a shared branch.** Erases teammates' commits. Use `--force-with-lease`, and only on your own branches (7.15).
2. **Committing secrets.** `.env` in history is a leaked credential — rotate, then clean (6.11). Prevent with push protection (8.5).
3. **Working for days without committing.** Uncommitted work is the only truly unrecoverable kind (6.1).
4. **Committing `node_modules/` or build output.** Bloats history forever; `.gitignore` from commit zero (2.7).
5. **"I'll fix it in a later commit" merge conflicts.** Pull (or rebase) at least daily; conflicts grow with time (4.8, 7.1).
6. **Committing straight to `main` on shared repos.** Bypasses review and protection; branch instead (5.8).
7. **Rewriting public history** (`amend`, `reset`, `rebase -i` on pushed commits). Breaks everyone's clones — golden rule (7.2).
8. **`git add .` blindly.** You stage junk and secrets. `git status` + `git diff --staged` before every commit (2.9).
9. **Ignoring error messages.** Git's hints ("updates were rejected because...") are genuinely good — read them before fighting the tool (Part 12).
10. **Panic-driven repository surgery.** When something breaks: `git status`, `git reflog`, *then* decide (6.1). And remember: if it's pushed, GitHub has a copy; clone fresh and compare.

## 9.7 Team Conventions Checklist

Pin this list in your team channel (or better: turn it into `CONTRIBUTING.md`):

- [ ] Default branch is `main`, protected, no direct pushes.
- [ ] Branch naming: `feature/…`, `fix/<issue>-…`, `docs/…` (3.8).
- [ ] Commit style: Conventional Commits, imperative, ≤ 50-char subjects (9.2).
- [ ] One logical change per commit; one concern per PR (9.1).
- [ ] PR template + required template for issues (9.3, 5.2).
- [ ] At least one approval + green CI required to merge (5.8, 8.2).
- [ ] Merge strategy agreed (usually squash) (5.5).
- [ ] `git pull --rebase` as team default (7.1); `.gitattributes` committed (7.14).
- [ ] Tags follow semver; releases get notes (7.5, 8.6).
- [ ] `.gitignore` covers local junk; secrets live in env vars / GitHub secrets (8.3).
- [ ] Nobody force-pushes shared branches, ever (7.15).
- [ ] PRs updated within a day or two of review feedback — no zombie PRs.

**Checkpoint:** Conventions are what "engineering maturity" actually means day to day. Part 10 makes you *practice* the entire guide end to end.

---
# Part 10: Guided Real-World Projects

Reading is not knowing — doing is. These five projects exercise the entire guide in sequence, each ending with something real: a live website, a merged PR, a resolved conflict, a self-testing repo, and an open-source contribution. Budget: Projects 1-3 in one sitting each (~30-60 min), Project 4 ~1 hour, Project 5 at your own pace.

## 10.1 Project 1: Portfolio From Zero to a Live Website

Build a small site from nothing, with proper history, published and live. Every command appears earlier in the guide — the test is doing it *without* looking (peek only when stuck).

1. `mkdir portfolio && cd portfolio && git init`
2. Create three files: `README.md` (title + one-liner), `index.html` (a heading and a paragraph), `style.css` (center the heading). Stage them all, one commit: `chore: initial project scaffold`... wait — that mixes docs and code. Better: two commits: `docs: add README` and `feat: add landing page with styles`. (You choose; that judgment is the exercise.)
3. Add `.gitignore` ignoring `*.log` and `.DS_Store`; commit `chore: add gitignore`.
4. Change the heading text; `git diff` to review; commit `feat: punchier headline`.
5. `git log --oneline --graph` — admire at least four honest commits.
6. On GitHub: new empty repo `portfolio`. Link it, push with `-u`.
7. Edit `README.md` via the GitHub web editor; commit there; locally `git pull`.
8. Settings → Pages → deploy from `main` / root. Visit `https://<you>.github.io/portfolio/` — your site, live, version controlled, and deployed by a push.
9. Branch `feature/contact-section`: add `contact.html` (an email link), two small commits, push the branch, merge into `main` locally, push, delete the remote branch.
10. Save the URL. This is your first deployable, reviewable, backed-up, public work. It goes on your CV.

## 10.2 Project 2: The Full Feature Workflow

The professional loop, executed end-to-end solo — including review on yourself.

1. In `portfolio`, create an issue: "Add projects section — showcase work" (label `enhancement`).
2. Branch off main: `feature/projects-section`.
3. Build `projects.html`: a list of 2-3 projects (titles + one-line descriptions). Three commits, properly separated: markup, styling, content.
4. `git log --oneline` on the branch. Run `git rebase -i HEAD~3` and squash commit 2 and 3 into commit 1 if they read as one change (7.3). Push with `-u`.
5. Open a pull request on GitHub (base `main` ← compare `feature/projects-section`). Description uses the Part 9.3 template, includes `Closes #<n>`.
6. In the **Files changed** tab, review your own diff like a stranger. Leave at least one inline comment on a real imperfection (e.g. a missing `<title>`).
7. Fix it with a follow-up commit on the branch; push; watch the PR update.
8. **Squash and merge** (5.5). Confirm the issue auto-closed and the branch button offers cleanup — delete it.
9. Locally: `git switch main && git pull && git branch -d feature/projects-section`.
10. Repeat once more from step 2 with a different section until the loop feels boring. Boring means *learned*.

## 10.3 Project 3: Merge Conflict Surgery

Practice makes conflicts a non-event. (Same drill as 3.7, now from scratch and with a three-way situation.)

1. In `portfolio`, on `main`, ensure `index.html` has a line `<footer>© 2026</footer>` committed.
2. Branch `feature/fancy-footer`. There, change that line to `<footer>© 2026 — v2, with style</footer>` and commit.
3. Back on `main`, change the *same line* to `<footer>© 2026 — maintained with Git</footer>` and commit. Both sides touched the same line.
4. `git merge feature/fancy-footer` → conflict. `git status` → read the unmerged list.
5. Open the file; study the `<<<<<<< / ======= / >>>>>>>` markers; resolve with a genuinely combined version containing both ideas. Delete every marker.
6. `grep -rn "<<<<<<<" .` → no output means clean. Stage, commit the merge.
7. Round two: `git merge --abort` practice. Re-create the conflict, then abort before resolving and confirm you are back to the pre-merge state.
8. Round three: during a conflict, use `git checkout --theirs <file>` to resolve the whole file in one command, then stage and commit.
9. Bonus: create the same conflict as a *push* rejection (edit on github.com AND locally the same line, try to push) and resolve it via `git pull`.

## 10.4 Project 4: Automation with GitHub Actions

Turn `portfolio` into a self-checking, auto-deploying project.

1. Create `.github/workflows/ci.yml` that lints/validates HTML (a simple starting check: a step that greps for required tags, or use `npm i -g html-validator` style tooling — any failing command counts). Ensure it triggers on push + PR to `main` (8.2).
2. Push a breaking change on a branch — a removed `</h1>` or a `exit 1` you plant in the check — open a PR, and watch the check go red. Then fix it and watch it go green. Feeling the red-green cycle *once* wires in what CI is for.
3. Add a second workflow: scheduled nightly (8.4) that simply echoes "still alive" and touches nothing (a canary).
4. Tag `v1.0.0` (annotated, with message), push the tag, and create a GitHub Release for it with real notes: run `git log --oneline` and summarize the highlights (8.6).
5. If you use Pages with the "GitHub Actions" source, replace it with a deploy workflow from 8.4 and push to main — watch it build and deploy in the Actions tab.
6. Enable Dependabot alerts + secret scanning in Settings (8.5). Zero cost, real protection.
7. Install `gh` if you have not, then from your terminal: `gh pr list`, `gh run watch`, `gh release view v1.0.0` — the browser-free experience.

## 10.5 Project 5: Your First Open-Source Contribution

The graduation exercise: contribute to a project you did not write.

1. **Find a project.** GitHub search → `label:"good first issue"` (or https://goodfirstissue.dev, or the "Explore" feed). Pick something you actually *use* — docs you noticed are unclear are the perfect first contribution.
2. Read their `README.md`, `CONTRIBUTING.md`, and 2-3 recent merged PRs. Every project has a culture; match it.
3. Comment on the issue: "I'd like to take this" — maintainers hate two people duplicating work.
4. Fork the repo (5.4). Clone *your fork*. Add `upstream`. Branch `fix/<issue>-<slug>` or `docs/<slug>` per their convention.
5. Make a small, focused change. One concern. One PR.
6. Self-review your diff; write the PR description in their house style, linking the issue (`Fixes #n` or `Closes #n` — check which the project uses).
7. Push to your fork; open the PR against the *original* repo. Triple-check the base repo and branch in the PR form.
8. Respond to review feedback politely and promptly; push follow-up commits to the same branch. If maintainers request changes, that is success, not failure — they are investing in your contribution.
9. If CI runs on your PR: keep it green.
10. When it merges: your public GitHub profile gains a contribution to a project you do not own — the strongest possible proof of the skills in this guide. Then do it again next month.

**TIP:** Documentation fixes (typos, dead links, unclear steps) are the single most welcome first contribution in open source. Start there; code contributions follow.

## 10.6 The Mastery Checklist

Tick these off over the coming weeks. Every box maps to a section you can revisit. When all boxes are honest ticks, you are no longer "learning Git" — you are a practitioner.

**Foundations**
- [ ] I can explain Git vs GitHub to a friend in one sentence each (0.4)
- [ ] I can draw the three areas and place `add`/`commit`/`restore` on the diagram (2.2)
- [ ] `git status` output tells me exactly what will be in my next commit (2.3)
- [ ] My commits are atomic, imperative, and under 50 characters (9.2)

**Branching & collaboration**
- [ ] I branch before any new work without thinking about it (3.2)
- [ ] A merge conflict slows me down for minutes, not hours (3.7)
- [ ] I have opened, reviewed (on myself or others), and merged a PR (5.3)
- [ ] I have contributed to a repository I do not own via fork + PR (5.4)

**Recovery & power tools**
- [ ] I have rescued a "deleted" commit with `git reflog` (6.8)
- [ ] I know which of reset/revert/stash fits a given situation in under 10 seconds (6.6)
- [ ] I rebase my feature branches onto main and know the golden rule (7.1-7.2)
- [ ] I have squashed WIP commits with interactive rebase before a PR (7.3)

**Automation & professionalism**
- [ ] A push of mine has triggered a CI workflow that ran tests (8.2)
- [ ] I have created an annotated tag and a GitHub release (7.5, 8.6)
- [ ] My repos carry README, LICENSE, .gitignore, and PR templates (9.4)
- [ ] I use `--force-with-lease` and can explain why (7.15)
- [ ] I can drive common GitHub tasks from `gh` without the browser (8.7)

**Judgment (the real mastery)**
- [ ] Given any mess, I run `git status` + `git reflog` before touching anything (6.1)
- [ ] I know which commands are safe on shared history and which are forbidden (7.2)
- [ ] I can read another team's conventions and adapt to them instead of imposing mine (9.7)
- [ ] I help teammates unstick themselves instead of judging their Git archaeology (5.7)

**Checkpoint:** Projects done, boxes ticking. Part 11 is the reference you will keep opening for the rest of your career.

---
# Part 11: The Complete Cheat Sheet

The reference section. No new concepts — just everything from Parts 0-10 compressed for daily use, plus scenarios and a glossary. Bookmark this part.

## 11.1 Command Reference by Category

### Setup and configuration

```bash
git config --global user.name "Name"       # identity for ALL repos
git config --global user.email "a@b.c"     # match your GitHub email
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
git config --global pull.rebase true        # pull = fetch + rebase
git config --global --list                  # audit settings
git config user.email "work@corp.com"       # per-repo override (no --global)
```

### Starting or getting a project

```bash
git init                                   # new repo, here
git clone <url>                            # full copy: files + history
git clone --depth 1 <url>                  # shallow: snapshot only
git clone --recurse-submodules <url>       # with submodules
```

### The daily loop

```bash
git status                                 # state of the world (run constantly)
git status -s                              # compact
git add <file|.|-A|-p>                     # stage (choose changes precisely)
git restore --staged <file>                # unstage
git commit -m "message"                    # snapshot the staged changes
git commit -am "message"                   # stage tracked modifications + commit
git commit --amend                         # fix the last (unpushed!) commit
git diff                                   # unstaged edits
git diff --staged                          # what the next commit will contain
git diff HEAD                              # all uncommitted edits
git log --oneline --graph --all --decorate # the best history view
git show <hash>                            # one commit in detail
```

### Branches

```bash
git branch                                 # list local
git branch -a                              # list local + remote
git switch <branch>                        # move to a branch
git switch -c <branch>                     # create + move
git switch -                               # previous branch
git branch -d <branch>                     # delete (safe)
git branch -D <branch>                     # delete (force)
git branch -m <new>                        # rename current
git merge <branch>                         # merge branch INTO current
git merge --abort                          # cancel a bad merge
git cherry-pick <hash>                     # copy one commit here
git rebase <base>                          # replay current branch onto base
git rebase -i HEAD~n                       # clean up last n commits
git rebase --continue / --abort
```

### Remotes

```bash
git remote -v                              # list remotes
git remote add origin <url>                # link
git remote add upstream <url>              # link the original of your fork
git remote set-url origin <url>            # change URL (e.g. to SSH)
git push -u origin <branch>                # first push of a branch
git push                                   # afterwards, on tracked branches
git push --force-with-lease                # after rewriting (own branches!)
git push origin --delete <branch>          # delete remote branch
git fetch [origin]                         # download, don't touch files
git pull                                   # fetch + merge (rebase if configured)
git pull --rebase
```

### Inspection and archaeology

```bash
git log -S "string"                        # commits adding/removing a string
git log --grep="word"                      # message search
git log --stat / -p                        # files / full diffs per commit
git log <file>                             # history of one file
git blame <file>                           # who wrote each line
git blame -L 10,20 <file>                  # lines 10-20 only
git grep "TODO" [<rev>]                    # search files (optionally in past)
git shortlog -sn                           # commits per author
git bisect start|bad|good|reset|run        # binary-search a bug
git tag                                    # list tags
git show v1.0.0                            # the tagged commit
```

### Undo and rescue

```bash
git restore <file>                         # discard uncommitted edits (careful)
git restore --source=<rev> <file>          # file as of an old revision
git reset --soft HEAD~1                    # undo commit, keep staged
git reset HEAD~1                           # undo commit, keep unstaged
git reset --hard HEAD~1                    # undo commit + changes (LOCAL only)
git reset --hard origin/main               # become exactly the remote
git revert <hash>                          # safe undo (pushed history OK)
git stash / push -m "msg" / list / pop / apply / drop
git stash -u                               # stash untracked too
git reflog                                 # the time machine
git clean -n / -fd                         # preview / delete untracked junk
```

## 11.2 How Do I...? (The Scenario Table)

The 34 situations you will actually face, in frequency order:

| I want to... | Run this |
|---|---|
| start tracking this folder | `git init` |
| start tracking + host it | `git init` → build → `git remote add origin <url>` → `git push -u origin main` |
| save my current work | `git add -A && git commit -m "..."` |
| save only some of my edits | `git add -p` (pick hunks) |
| see what I am about to commit | `git diff --staged` |
| see everything since last commit | `git diff HEAD` |
| undo my last commit, keep the work | `git reset --soft HEAD~1` |
| redo the last commit's message | `git commit --amend -m "..."` (unpushed) |
| add a file I forgot to the last commit | `git add <file> && git commit --amend --no-edit` |
| nuke my last commit entirely | `git reset --hard HEAD~1` (never if pushed) |
| undo a commit that is already pushed | `git revert <hash>` + push |
| unstage a file | `git restore --staged <file>` |
| throw away my edits to a file | `git restore <file>` (permanent!) |
| bring back a file from 3 commits ago | `git restore --source=HEAD~3 <file>` |
| combine my last 3 commits into 1 | `git reset --soft HEAD~3` → `git commit` (or `rebase -i`) |
| clean up messy commits before a PR | `git rebase -i HEAD~n` |
| move my WIP out of the way temporarily | `git stash push -m "wip"` → later `git stash pop` |
| get a colleague's PR locally | `gh pr checkout <n>` |
| update my branch with main | `git switch <b>` → `git rebase main` (own branch) |
| bring my unpushed work onto a new branch | `git switch -c new-branch` (commits follow; then reset the old one) |
| see an old version of one file | `git show <rev>:path/to/file` |
| see the project as of yesterday | `git switch --detach <hash>` (read-only; `git switch main` to return) |
| resurrect a commit/branch I deleted | `git reflog` → `git switch -c <b> <hash>` |
| find the commit that broke the build | `git bisect start` → bad/good... (7.8) |
| find who wrote this buggy line | `git blame <file>` |
| make my branch identical to remote | `git fetch && git reset --hard origin/<b>` |
| download but NOT merge remote changes | `git fetch` (inspect: `git log <b>..origin/<b>`) |
| stop tracking a file (keep locally) | `git rm --cached <file>` + commit + gitignore it |
| keep an empty folder | Git can't — add a `.gitkeep` file inside it |
| rename/move a file properly | `git mv old new` (records the move) |
| change the remote URL (HTTPS→SSH) | `git remote set-url origin <new>` |
| share one snippet, not a repo | a gist: `gh gist create <file>` |
| create a release | `git tag -a v1.0.0 -m "..."` → `git push origin v1.0.0` → GitHub Releases |
| publish a website of this repo | Settings → Pages → deploy from main (5.9) |
| contribute to someone else's project | fork → clone → branch → commit → push → PR (5.4) |
| run tests on every push | `.github/workflows/ci.yml` (8.2) |

## 11.3 The Full Map of Git

One diagram containing the whole guide — every command sits somewhere on this map. If you can redraw this from memory, you understand Git.

```
                          WORKING DIRECTORY (you edit files here)
                                 |        ^  git restore <file>
                    git add      |        |  (discard edits)
                    git add -p   |        |
                    git checkout --ours/--theirs (conflict resolution)
                                 v        |
                             [STAGING AREA]  <----- git restore --staged <file>
                                 |              (unstage; edits kept)
                    git commit   |  ^ git reset --soft (keep staged)
                                 |  | git reset (keep unstaged)
                                 v  | git reset --hard (DISCARD)
                        [REPOSITORY = .git database of snapshots]
                          |   ^  ^
          git merge  <----|   |  \----- git commit --amend
          git rebase <----|   \-------- git revert (anti-commit)
          git cherry-pick |
              |           |
              v           v
        LOCAL BRANCH POINTERS  <---- git switch, git branch -d
              (main, feature/..., HEAD)
                                 |
                    git push -u  |   git fetch
                    git push     v   ^
                    git push --force-with-lease   git pull (= fetch+merge)
                                 |   ^
                                 v   |
                      [REMOTE (origin on GitHub)]
                          branches, tags, releases, PRs, Actions

   SIDE DOORS:  git stash (park changes)   git reflog (time machine)
                git clean (delete untracked)   git bisect (bug hunt)
                git worktree (parallel checkout)   git tag (versions)
```

## 11.4 Glossary A to Z

| Term | Definition |
|---|---|
| **annotated tag** | A tag with message/metadata; the kind you want for releases |
| **bisect** | Binary search over history to find the commit that introduced a bug |
| **blame** | Per-line authorship of a file |
| **branch** | A movable pointer to a commit; an independent line of development |
| **cherry-pick** | Copy one commit from anywhere onto the current branch |
| **checkout** | Legacy verb: switch branch or restore files (modern: `switch`/`restore`) |
| **clone** | Full local copy of a remote repo (files + history) |
| **collaborator** | Person with push access to your GitHub repo |
| **commit** | An immutable snapshot of the project; the atom of Git history |
| **conflict** | Two branches changed the same lines; a human must choose |
| **detached HEAD** | HEAD on a commit instead of a branch (looking, not developing) |
| **diff** | The line-by-line difference between two states |
| **fast-forward** | Merge that just slides a branch pointer (no merge commit needed) |
| **fetch** | Download remote commits without changing your files |
| **fork** | Your GitHub-hosted copy of someone else's repo |
| **gitignore** | File listing paths Git must never track |
| **GitHub Pages** | Free static hosting served from a repo |
| **hash (SHA)** | A commit's unique fingerprint, e.g. `a1b2c3d` |
| **HEAD** | Pointer to what you currently have checked out |
| **hook** | Script auto-run by Git at a lifecycle point (pre-commit etc.) |
| **index** | Synonym for the staging area |
| **issue** | GitHub thread tracking a bug/task/feature request |
| **master** | Legacy default branch name; modern default is `main` |
| **merge commit** | Commit with two parents tying histories together |
| **origin** | Conventional nickname for the remote you cloned/push to |
| **pull request (PR)** | GitHub conversation proposing to merge a branch of changes |
| **rebase** | Replay commits on top of another base; history rewriting |
| **reflog** | Log of every HEAD movement; the rescue rope |
| **release** | GitHub packaging of a tag with notes and artifacts |
| **remote** | Another copy of the repo (usually on GitHub) |
| **repository (repo)** | A project under Git's control (`.git` + working files) |
| **revert** | New commit that undoes a given commit (shared-safe) |
| **squash** | Combining multiple commits into one |
| **stage** | Mark changes for the next commit (`git add`) |
| **stash** | Temporarily shelve uncommitted changes |
| **submodule** | A repo pinned inside another repo |
| **tag** | Permanent label on a commit, usually a version |
| **tracking branch** | Local branch linked to a remote branch (`-u`) |
| **trunk** | Synonym for the main line (main/master) |
| **upstream** | The *original* repo your fork came from; also "upstream branch" = remote counterpart |
| **working directory/tree** | Your normal folder: the files you actually edit |
| **worktree** | Additional working folder sharing one .git, on its own branch |

---
# Part 12: Troubleshooting and FAQ

Every error below is normal, common, and survivable — most people hit all of them in their first month. Find your message, apply the fix, move on. General rule before anything: run `git status` and *read the hint lines* Git prints — they are usually the correct answer.

## `fatal: not a git repository (or any of the parent directories): .git`

**Meaning:** you are not inside a repo. **Fix:** `cd` into your project folder (where `.git` lives), or `git init` if it genuinely is not a repo yet. Check with `ls -a` that a `.git` folder is present. Also make sure you did not `git init` in some ancestor folder by accident (2.1's warning).

## `Permission denied (publickey)` when pushing/pulling over SSH

**Meaning:** GitHub rejected your SSH key — none offered, wrong one, or agent not running. **Fix, in order:**

```bash
ssh -T git@github.com          # does the test itself fail?
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519     # load your key
cat ~/.ssh/id_ed25519.pub     # is THIS key added on github.com -> Settings -> SSH keys?
```

Also verify the remote URL uses SSH form (`git@github.com:...`), not HTTPS (`git remote -v`). If all else fails: switch to HTTPS and let the credential manager log you in — a perfectly good solution.

## `ERROR: Repository not found` / `fatal: unable to access ... : The requested URL returned error: 403`

**Meaning:** the URL is wrong, the repo is private and you lack access, or you lack push rights. **Fix:** re-copy the URL from the repo's green **Code** button; `git remote set-url origin <correct-url>`. Private repo: get the owner to invite you (Settings → Collaborators). It is also a typo'd repo name more often than anyone admits.

## `! [rejected] main -> main (fetch first)` / `failed to push some refs`

**Meaning:** the remote has commits you do not (Part 4.8). **Fix:**

```bash
git pull            # integrate the remote commits (resolve conflicts if asked)
git push
```

If the pull itself complains about unrelated histories (next entry), stop and check whether someone initialized the GitHub repo with a README while you also made local commits.

## `fatal: refusing to merge unrelated histories`

**Meaning:** your local repo and the remote have *zero commits in common* — usually two separate `git init`s (you committed locally AND created files on GitHub when making the repo). **Fix:** if both histories are genuinely wanted:

```bash
git pull origin main --allow-unrelated-histories
# resolve conflicts if any, then:
git push -u origin main
```

**Prevention:** when creating the GitHub repo to pair with an existing local repo, tick none of the "add README/license" boxes (4.2).

## `fatal: You are not currently on a branch` / "detached HEAD"

**Meaning:** you checked out a commit or tag instead of a branch — you are *looking at* the past (or a PR) rather than developing on a line. Detached HEAD is not an error; committing while detached is where trouble starts (commits float free of branches). **Fix:**

```bash
git switch main            # just go back
# ...or, if you did make commits you want to keep:
git switch -c my-new-branch      # they are safe on a branch now
```

## `Your branch is ahead of 'origin/main' by N commits`

Not an error — a status line: you have N unpushed commits. **Fix:** `git push`. ("Behind" → `git pull`. "diverged" → both: `git pull --rebase`, resolve if needed, `git push`.)

## `warning: LF will be replaced by CRLF` (or the reverse)

**Meaning:** Windows/Linux line-ending mismatch (7.14). Harmless but noisy. **Fix:**

```bash
git config --global core.autocrlf true     # on Windows
git config --global core.autocrlf input    # on macOS/Linux
```

Add a `.gitattributes` (`* text=auto`) to end it repo-wide. If a file shows as fully modified with no visible changes: `git add --renormalize .`

## Merge conflict markers got committed (I see `<<<<<<<` in files on GitHub)

**Fix:** fix the file content, `git add <file>`, `git commit -m "Resolve leftover markers"`. **Prevention:** before every conflict-resolution commit: `grep -rn "<<<<<<<" .` (3.7).

## `fatal: remote origin already exists`

**Meaning:** you ran `git remote add origin ...` twice. **Fix:** `git remote set-url origin <url>` — or check first with `git remote -v` (the existing origin may be correct already).

## `error: failed to push some refs ... hint: Updates were rejected because the tip of your current branch is behind` after history rewriting

**Meaning:** you rebased/amended an already-pushed branch (Part 7.15). **Fix (own branches only):**

```bash
git push --force-with-lease
```

If this is a shared branch, stop and coordinate — do not force-push.

## `error: Your local changes to the following files would be overwritten by merge/checkout`

**Meaning:** Git refuses to proceed because uncommitted edits would be destroyed. **Fix — pick one:**

```bash
git stash push -m "wip"      # save the work, proceed, then git stash pop
git commit -am "wip"         # commit the work, proceed
git restore <file>           # discard the edits (if they are unwanted)
```

This is Git protecting you, not failing you (6.1).

## `Merge branch 'x' of ...` messages everywhere / my history is a braid

Not an error — a style choice. If your team prefers linear history: `git config pull.rebase true` (pulls become rebases), rebase feature branches onto main before PRs (7.1), and use "Rebase and merge" or "Squash and merge" on GitHub (5.5).

## `fatal: bad object <hash>` / `error: object file ... is empty` / repo seems corrupted

**Fix ladder:**

```bash
git fsck                     # check integrity, see what it reports
# often the damage is limited and a fresh clone still works:
git clone <url> fresh-copy   # compare, move over uncommitted files, re-commit
```

Pushed work survives on GitHub — clone fresh, copy your uncommitted files in, commit, push. Local-only corruption with no remote copy: `git fsck --lost-found` may salvage objects. Moral: push your work (6.1).

## `error: lock file exists: .git/index.lock` / `Another git process seems to be running`

**Meaning:** a git process crashed and left its lock, or one is genuinely still running. **Fix:** make sure no git process is active (close IDEs' git panels), then delete the stale lock:

```bash
rm -f .git/index.lock
```

## `Please tell me who you are` before your first commit

You skipped Part 1.3. **Fix:**

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## GitHub asks for a password over HTTPS and rejects it

GitHub removed password authentication for Git operations. **Fix:** the password field expects a **Personal Access Token** — but the better path is the Git Credential Manager bundled with Git (browser login on first push) or SSH keys (1.5-1.6). A PAT is created at github.com → Settings → Developer settings → Personal access tokens, and stored by the credential manager after first use.

## `fatal: ambiguous argument 'HEAD'` (on a brand-new repo)

**Meaning:** there are no commits yet, so HEAD points at nothing. You probably ran `git log` or `git reset` before the first commit. **Fix:** make your first commit (`git add` + `git commit`) and the error disappears.

## FAQ — quick answers

**"Should I commit the lock file / package files / node_modules?"** — Commit lock files (`package-lock.json`, etc.): yes, reproducibility. `node_modules/` and virtualenvs: never (`.gitignore`). Built artifacts (`dist/`): usually no — build them in CI (Part 8).

**"I committed a huge file by mistake and pushed it."** — Remove it from history with `git filter-repo`, or `git rm --cached <file>` + commit if history bloat does not matter; then force-push (own repo), and rotate/remove any secrets it contained (6.11). On public repos, consider everything pushed to be public forever.

**"How do I ignore a file that is already tracked?"** — `git rm --cached <file>` + commit + add to `.gitignore` (2.7).

**"Why is my empty folder not committed?"** — Git tracks files, not directories. Drop a `.gitkeep` (empty file) inside it.

**"What is the difference between `git pull` and `git fetch`?"** — 4.5: fetch downloads only; pull downloads *and merges*.

**"Should I use `checkout`, `switch`, and `restore`?"** — `switch`/`restore` (2019) split `checkout`'s two jobs cleanly; learn the new ones, recognize the old one (3.3, 6.2).

**"Someone force-pushed and my branch is now weird."** — `git fetch`, compare (`git log HEAD..origin/main`), and coordinate with them; the reflog still has your local view (6.8). Team rule: nobody force-pushes shared branches (7.15).

**"Git is confusing in my IDE."** — IDEs wrap the same model in buttons; when the GUI confuses you, the terminal is ground truth (`git status`). VS Code's Source Control view is a good GUI companion to this guide — buttons map 1:1 to commands here.

---
# Part 13: Resources and Next Steps

You made it through the whole guide. This last part is your map of the wider world: where to keep learning, what tools to explore, and how to turn knowledge into permanent skill.

## 13.1 Official Documentation

| Resource | What it is |
|---|---|
| **git-scm.com/doc** | The official Git documentation, including the full online **Pro Git book** (free, excellent — the reference) |
| **docs.github.com** | GitHub's documentation: Actions, Pages, security, everything on the platform side |
| **lab.github.com → GitHub Skills** | Free interactive courses *on real repos* (Introduction to GitHub, Review PRs, GitHub Pages, Actions) — the closest thing to a sequel to this guide |
| **training.github.com** | GitHub's own cheat sheets (PDF one-pagers, in many languages) |
| **choosealicense.com** | Plain-language license chooser (9.5) |
| **keepachangelog.com** | The changelog format real projects use |

## 13.2 Interactive Practice

| Tool | Why it is worth your time |
|---|---|
| **learngitbranching.js.org** | The legendary visual Git sandbox: animated commit trees, guided levels for rebase/branch/merge. 30 minutes here makes the DAG model visceral. |
| **git-school.github.io/visualizing-git** | Type commands, watch the commit graph redraw live |
| **githowto.com** | Guided hands-on labs |
| **firsttimersonly.com** + **firstcontributions (github.com/firstcontributions)** | Gentle on-ramps for your first open-source PR (10.5) |
| **ohshitgit.com** | The emergency recipes from Part 6, as a site you can find in a panic |
| **your own playground repo** | Still the best trainer: `mkdir git-gym && cd git-gym && git init` — nothing you break there matters |

## 13.3 Tools Worth Trying

**Terminals and TUIs:**
- **lazygit** — a terminal UI for Git so good it becomes muscle memory (staging hunks, rebasing, cherry-picking in keystrokes)
- **gitui / tig** — same species, different flavors

**Desktop GUIs:**
- **VS Code built-in Git** (Source Control panel, plus the outstanding GitLens extension: inline blame, history, "who touched this line" on hover)
- **GitHub Desktop** — the friendly path; pairs perfectly with this guide's Part 5
- **GitKraken, Sourcetree, Fork, Tower** — polished full-featured clients (graph views teach the branch model well)

**CLI power-ups:**
- **gh** (Part 8.7) — GitHub in your terminal
- **git-delta** — beautiful, language-aware diffs
- **git-absorb / git fixup** — auto-fold fixes into their matching commits
- **gitfilter-repo** — the safe way to rewrite big history (removing secrets, giant files)

**Visualization and teaching:**
- **git-sim** — renders PNG diagrams of what a command *will* do before you run it

You do not need any of these — everything in this guide is plain Git — but watching a graph view draw your rebases accelerates the mental model dramatically.

## 13.4 Where Do You Go From Here?

The honest truth about mastery: you do not finish learning Git; you deepen. The knowledge in this guide becomes permanent the first time it saves you a full day of work — and it will. A concrete path for the next three months:

**This week**
- Finish Projects 1-3 from Part 10 if you have not.
- Convert one existing project (or your dotfiles, your notes, anything) into a repo and run it under GitHub Flow.
- Do one `git reflog` rescue drill so the reflex exists before you need it (6.12).

**This month**
- Project 4: CI on a repo you care about — green checks on your own work is a habit-forming feeling.
- Add LICENSE, CONTRIBUTING, PR and issue templates to your main repo (9.4) — it now looks like a run project, because it is.
- Project 5: your first real open-source contribution, even a two-line docs fix.

**Within three months**
- Second and third open-source contributions, graduating from docs to code.
- Automate a deployment end-to-end: PR → CI green → review → squash-merge → tag → release → deploy (8.4-8.6). That pipeline, working, is the modern definition of shipping software.
- Teach someone else the Part 0 diagrams. Explaining the three areas and branch pointers is the fastest way to find the gaps in your own model — and teaching is how this guide's author learned, too.

**Keep sharp**
- When a command surprises you, run it again in a scratch repo and watch what actually happened.
- Read the hints Git prints — they got dramatically good over the years.
- Occasionally read a beloved project's history (`git log` of a library you use): world-class commit messages are a free masterclass in communication.

And when one day a teammate stands frozen in front of a merge conflict or a "detached HEAD" message, you will be the one who walks over, runs `git status`, and calmly says — *we can fix this; everything in Git is recoverable, let me show you the reflog*.

That moment is when you know the zero-to-hero journey is complete.

## License of this guide

Share it freely: this guide is released under **CC BY 4.0** — copy it, adapt it, teach from it, keep the attribution. If it helped you, the best payment is passing it (or your own version, in your own words) to the next person starting from zero.

## Contribute to this guide

Found a typo, a stale command, or a better explanation? Open an issue or pull request — practicing Part 5.4 *on this document itself* is the most meta and most appropriate graduation exercise imaginable. PRs welcome.
