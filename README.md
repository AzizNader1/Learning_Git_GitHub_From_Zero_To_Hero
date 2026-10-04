# Git & GitHub: From Zero to Hero

![Guide](https://img.shields.io/badge/guide-zero--to--hero-blue)
![Level](https://img.shields.io/badge/level-beginner%20%E2%86%92%20master-green)
![Updated](https://img.shields.io/badge/updated-2026-orange)
![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen)
![License](https://img.shields.io/badge/license-CC--BY--4.0-lightgrey)

> **The complete, step-by-step, no-experience-required guide to version control.**
>
> Start knowing nothing. Finish thinking in commits, branches, pull requests, and CI pipelines.
>
> **Zero → functional in one day. Zero → master with practice over a few weeks.**

---

## Who This Guide Is For

- You have **never used Git or GitHub** in your life, and words like *commit*, *push*, *pull request* sound intimidating.
- You have *tried* Git before, got burned by a merge conflict or a scary error message, and quietly went back to emailing yourself `project_final_v3_REALLYFINAL.zip`.
- You know a handful of commands but copy-paste them blindly and want to actually **understand** what they do.
- You want to collaborate like professional developers do: branches, pull requests, code reviews, and automated tests.

No programming knowledge is required. Every concept is explained from first principles, every command comes with a realistic example **and** its expected terminal output, and every chapter ends with a **"Your Turn"** exercise you can do right now on your own machine.

---

## What You Will Learn

By the end of this guide you will be able to:

1. Explain what version control is and why every developer on Earth relies on it.
2. Install and configure Git on Windows, macOS, or Linux, and connect it securely to GitHub.
3. Create repositories, track changes, and write professional commit messages.
4. Branch, merge, and resolve merge conflicts without fear (or data loss).
5. Push your work to GitHub, open pull requests, and review other people's code.
6. Use advanced tools: `rebase`, `cherry-pick`, `bisect`, `stash`, `reflog`, hooks, submodules.
7. Automate anything with GitHub Actions (CI/CD), including tests, builds, and deploys.
8. Recover from disasters: deleted branches, bad merges, force-pushes, corrupted repos.
9. Contribute to open-source projects with proper etiquette.
10. Build a real, deployed portfolio website end-to-end using everything above.

---

## How to Use This Guide

**Read in order.** Each chapter assumes you have done the previous one. Concepts stack: you cannot understand a pull request without first understanding branches, and you cannot understand branches without first understanding commits.

**Type the commands yourself.** Reading `git commit -m "..."` is not the same as typing it. Muscle memory matters. Every command in this guide is meant to be run on your own machine in a real terminal.

**Do the exercises.** Each chapter ends with a **"Your Turn"** section. Skipping them is like reading about swimming without ever getting in the water.

**Refer back.** Chapters 14 (Cheat Sheet) and 15 (Troubleshooting) are designed to be searched, not read. When you hit an error in three months, jump there.

### Conventions Used

| Style | Meaning |
|---|---|
| `inline code` | A command, file name, or literal text you type exactly. |
| ```bash ... ``` | A terminal block. Lines starting with `$ ` you type; lines without `$ ` are output. Lines starting with `# ` are comments — do not type them. |
| > Blockquote | A note, warning, or aside from the author. |
| **Bold** | Important term introduced for the first time. |
| *Italics* | Emphasis. |

### The Six Commands That Cover 90% of Daily Git

If you only learn six commands today, learn these. The rest of the guide explains them properly:

```bash
git status          # What changed? What's staged? What branch am I on?
git add <file>      # Stage changes (tell Git "I want to save this next")
git commit -m "..." # Save a snapshot with a message
git push            # Upload commits to GitHub
git pull            # Download commits from GitHub
git log --oneline   # See the history of commits
```

### The Learning Roadmap

| Stage | Chapters | What you can do at the end |
|---|---|---|
| 🌱 Beginner | 0 – 2 | Talk about Git, install it, make your first commits. |
| 🌿 Intermediate | 3 – 6 | Branch, merge, push to GitHub, open a pull request. |
| 🌳 Advanced | 7 – 9 | Rebase, recover from disasters, automate with CI/CD. |
| 🎯 Mastery | 10 – 13 | Use GUIs, follow best practices, build real projects, contribute to open source. |
| 📚 Reference | 14 – 16 | Find any command, fix any error, find what to learn next. |

---

## Table of Contents

- [Chapter 0 — The Big Picture: What, Why, and History](#chapter-0--the-big-picture-what-why-and-history)
  - [0.1 What Is Version Control?](#01-what-is-version-control)
  - [0.2 A Brief History of Version Control](#02-a-brief-history-of-version-control)
  - [0.3 What Is Git?](#03-what-is-git)
  - [0.4 What Is GitHub?](#04-what-is-github)
  - [0.5 Git vs GitHub](#05-git-vs-github)
  - [0.6 What Git Provides You](#06-what-git-provides-you)
  - [0.7 Why You Should Use Git & GitHub](#07-why-you-should-use-git--github)
  - [0.8 How Git Thinks (Four Mental Models)](#08-how-git-thinks-four-mental-models)
  - [0.9 Vocabulary You Will See Everywhere](#09-vocabulary-you-will-see-everywhere)
  - [0.10 Your Turn](#010-your-turn)
- [Chapter 1 — Installation & First Setup](#chapter-1--installation--first-setup)
- [Chapter 2 — Git Fundamentals: Your First Repository](#chapter-2--git-fundamentals-your-first-repository)
- [Chapter 3 — Git Internals: What's Actually Inside `.git`](#chapter-3--git-internals-whats-actually-inside-git)
- [Chapter 4 — Branching and Merging](#chapter-4--branching-and-merging)
- [Chapter 5 — Remotes and Publishing to GitHub](#chapter-5--remotes-and-publishing-to-github)
- [Chapter 6 — The GitHub Collaboration Workflow](#chapter-6--the-github-collaboration-workflow)
- [Chapter 7 — Undoing Things and Disaster Recovery](#chapter-7--undoing-things-and-disaster-recovery)
- [Chapter 8 — Intermediate to Advanced Git](#chapter-8--intermediate-to-advanced-git)
- [Chapter 9 — GitHub Actions: Automation for Everyone](#chapter-9--github-actions-automation-for-everyone)
- [Chapter 10 — GUI Clients, Tools & Editor Integrations](#chapter-10--gui-clients-tools--editor-integrations)
- [Chapter 11 — Best Practices and Conventions](#chapter-11--best-practices-and-conventions)
- [Chapter 12 — Guided Real-World Projects](#chapter-12--guided-real-world-projects)
- [Chapter 13 — Open-Source Contribution Workflow](#chapter-13--open-source-contribution-workflow)
- [Chapter 14 — The Complete Cheat Sheet](#chapter-14--the-complete-cheat-sheet)
- [Chapter 15 — Troubleshooting and FAQ](#chapter-15--troubleshooting-and-faq)
- [Chapter 16 — Resources, Glossary & Next Steps](#chapter-16--resources-glossary--next-steps)

---


# Chapter 0 — The Big Picture: What, Why, and History

> **Goal of this chapter:** Before touching a single command, you should be able to explain *what* version control is, *why* it exists, *how* it evolved, and *what* Git and GitHub actually are — to a friend who has never heard of them.

This chapter is intentionally command-free. Read it on the bus, in bed, or while waiting for your code to compile. Everything here is conceptual scaffolding that will make the commands in later chapters feel obvious rather than arbitrary.

---

## 0.1 What Is Version Control?

**Version control** is a system that records changes to a file or set of files over time, so that you can recall specific versions later.

That is the entire definition. Everything else — Git, GitHub, branches, pull requests — is just engineering on top of this single idea.

### The problem it solves

You have written an essay. You save it as `essay.docx`. You make some edits, then realise you deleted a paragraph you actually needed. You:

1. Hit **Ctrl+Z** fifty times hoping to recover it.
2. Realise you also saved and closed the file. Ctrl+Z no longer works.
3. Search your email for `essay_v2.docx`, `essay_v2_final.docx`, `essay_v2_REAL_FINAL.docx`, `essay_v2_FINAL_I_PROMISE.docx` …
4. Cry a little.

Now multiply this by:
- Multiple files (a website has hundreds).
- Multiple people editing the same files at the same time.
- A history going back years.

Without version control, this is chaos. With version control, every change is a discrete, named, timestamped, reversible step.

### The five questions version control answers

A good version control system lets you answer these five questions at any time, for any file, instantly:

1. **What changed?** — a precise, line-by-line diff
2. **When?** — exact timestamp
3. **Who?** — which author
4. **Why?** — the commit message
5. **How do I get back to a previous state?** — by checking out an older version

If your current workflow cannot answer all five, you do not have version control — you have hope.

---

## 0.2 A Brief History of Version Control

Knowing where Git came from will make its design feel less arbitrary. Many of Git's quirks are direct responses to problems earlier systems had.

### The Pre-Version-Control Era (before 1970s)

People literally kept source code on punched cards. "Undo" meant re-punching a corrected card. There was no concept of history — only the latest stack of cards existed. If you dropped the box, the project was gone.

### First Generation: Local Diffs (1972 — SCCS)

**SCCS** (Source Code Control System), built at Bell Labs by Marc Rochkind in 1972, was the first widely-used VCS. It stored deltas — the *differences* between versions — in a single file. To reconstruct version 47, you applied deltas 1→2→3→…→47 sequentially.

**Limitation:** it worked on one file at a time, and only locally. There was no concept of "a project" or "a server".

### Second Generation: Centralized (1982 — 1990)

Two systems dominated the 1980s and 1990s:

- **RCS** (Revision Control System, 1982) — improved SCCS, still single-file, still local.
- **CVS** (Concurrent Versions System, 1986) and later **Subversion** (SVN, 2000) — introduced the **central server** model. Every developer had a working copy on their machine, but the canonical history lived on a single server. To commit, you had to talk to the server.

**Centralized model:**

```
        [ Central Server ]
        /       |        \
   [ Alice ] [ Bob ] [ Carol ]
   working   working  working
    copy      copy     copy
```

**Strength:** conceptually simple. Everyone checks out from one source of truth.

**Weakness:** the server is a single point of failure. If the server is down, nobody can commit. If the server's disk dies and there is no backup, the entire project history is gone. Working offline is impossible.

In 2002, the Linux kernel team started using a proprietary VCS called **BitKeeper**. It was distributed, fast, and free for open-source use. Things were good — for a while.

### The BitKeeper Schism (April 2005)

In 2005, BitMover (the company behind BitKeeper) revoked the free license for the Linux community after some community members tried to reverse-engineer the protocol. Linus Torvalds, the creator of Linux, found himself unable to use BitKeeper and unwilling to go back to CVS.

On **3 April 2005**, Linus announced he would build a replacement. He had three non-negotiable requirements:

1. **Distributed** — every clone is a full backup, with full history.
2. **Fast** — diffing and branching must be cheaper than the competition.
3. **Ironclad integrity** — it must be cryptographically impossible to silently corrupt history.

He also wanted it done quickly. He started coding on **3 April 2005**. He announced the first self-hosting version on **7 April 2005** — four days later. The first official release, **Git 1.0**, came out in **December 2005**.

The name "git" is British slang for an unpleasant person. Linus joked: *"I'm an egotistical bastard, and I name all my projects after myself. First Linux, now Git."* The man page defines `git` as "the stupid content tracker".

### Third Generation: Distributed (2005 — today)

Git was not the only distributed VCS, but it won. The other contenders were:

- **Mercurial (hg)** — also born in 2005, in response to the BitKeeper schism. Cleaner design, easier to learn, but slower for huge repositories.
- **Bazaar (bzr)** — Canonical/Ubuntu's entry, 2005. Powerful but slow.
- **Darcs** — academic, elegant theory, never achieved wide adoption.

Git won for three reasons:
1. **Speed** — its data model (snapshots, not diffs) made common operations O(1).
2. **The Linux kernel used it** — which gave it instant credibility and a huge contributor base.
3. **GitHub (2008)** — gave it a social, friendly home that nobody else had. More on that below.

### The GitHub Era (2008 — today)

In 2008, three developers — **Tom Preston-Werner**, **Chris Wanstrath**, and **PJ Hyett** — launched **GitHub**, a web platform that hosted Git repositories and added collaboration features on top: pull requests, issues, code review, social following. Git was a tool for engineers; GitHub made it approachable for designers, writers, researchers, and students.

By 2011, GitHub had overtaken SourceForge and Google Code. By 2018, Microsoft acquired GitHub for **$7.5 billion**. As of 2025, GitHub hosts over **200 million repositories** and is used by over **100 million developers**. It is the default place code lives on the internet.

---

## 0.3 What Is Git?

**Git** is a free, open-source, distributed version control system that runs on your computer. It is a command-line tool (though many GUIs wrap it) that records snapshots of your files and lets you navigate their history.

Three properties make Git special:

### 1. Distributed

There is no "server" in the traditional sense. When you `git clone` a repository, you download the *entire history* of the project — every commit, every branch, every tag. Your local copy is a first-class citizen. You can commit, branch, merge, and explore history entirely offline.

### 2. Snapshot-based, not delta-based

Older systems (CVS, SVN, Perforce) stored *changes*: "line 17 was changed from `foo` to `bar`". To reconstruct file X at version 100, you applied 100 deltas in order.

Git stores **snapshots**. Each commit is a complete picture of every file at that moment. Files that didn't change are not re-stored — Git just stores a pointer to the previous version. This makes branching and merging dramatically faster, because branches are not copies of files; they are just pointers to commits.

```
Older VCS (delta-based):
  v1: file = "abc"
  v2: delta: replace "b" with "B"        → reconstruct by applying deltas
  v3: delta: insert "X" at position 0

Git (snapshot-based):
  v1: file = "abc"                        → full content stored
  v2: file = "aBc"                        → full content stored (or pointer if unchanged)
  v3: file = "XaBc"                       → full content stored
```

### 3. Cryptographic integrity

Every object in Git — every blob, tree, commit — is identified by a **SHA-1 hash** (Git is migrating to SHA-256) of its content. If a single byte anywhere in the history is corrupted, the hashes will not match and Git will refuse to operate. This is why Git users say *"you can't lose history with Git"* — corruption is mathematically detectable.

### What Git is NOT

- Git is **not** a backup system (though it can be used as one). It tracks files you tell it to track.
- Git is **not** GitHub. Git is the engine; GitHub is one of many websites that hosts Git repositories.
- Git is **not** a deployment system. It deploys *code*, not running services (you need CI/CD for that — Chapter 9).
- Git is **not** specifically for programmers. People use it to version novels, legal contracts, academic papers, configuration files, and even legislation.

---

## 0.4 What Is GitHub?

**GitHub** is a web platform (a company, owned by Microsoft since 2018) that hosts Git repositories in the cloud and adds collaboration features on top of bare Git.

If Git is the engine of a car, GitHub is the road network: a shared place where everyone drives their Git-powered cars together. You can use Git perfectly well without GitHub (many teams use GitLab, Bitbucket, Gitea, or just a bare server). But GitHub is the most popular, and it adds significant value:

| Feature | What it gives you |
|---|---|
| **Hosted repositories** | Your code lives on `github.com`, accessible from any browser. |
| **Pull requests (PRs)** | A structured way to propose changes and review them before merging. |
| **Issues** | A built-in bug tracker / to-do list. |
| **Wiki & Pages** | Free documentation hosting and a free static website from your repo. |
| **GitHub Actions** | A CI/CD platform — run tests, build, deploy automatically. |
| **Forks** | A one-click way to copy someone else's repo into your account. |
| **Code review** | Inline comments on diffs, approvals, requested changes. |
| **GitHub CLI (`gh`)** | Do all of the above from the terminal. |
| **Gists** | Tiny snippets you want to share quickly. |
| **Projects** | A Kanban board for issues and PRs. |
| **Codespaces** | A full VS Code environment running in the cloud, in seconds. |

### Other Git hosting platforms (for context)

| Platform | Owner | Distinctive feature |
|---|---|---|
| **GitLab** | GitLab Inc. | Built-in CI/CD, can self-host the entire platform. |
| **Bitbucket** | Atlassian | Tight integration with Jira. |
| **Gitea / Forgejo** | Open source | Lightweight, self-hosted, no vendor lock-in. |
| **Codeberg** | Non-profit | Privacy-first, EU-based. |
| **Azure DevOps** | Microsoft | Enterprise pipelines + boards, used by .NET teams. |

You can switch between them — they all speak Git. Your `git push` command is the same; only the URL changes.

---

## 0.5 Git vs GitHub

People new to this world conflate Git and GitHub all the time. Here is the simplest way to keep them straight:

| | Git | GitHub |
|---|---|---|
| What is it? | A tool (a program) | A website (a service) |
| Where does it run? | On your computer | On servers in the cloud |
| Who owns it? | The open-source community (maintained by the Git project) | Microsoft |
| Do I need an account? | No — just install it | Yes — sign up at github.com |
| Can I use it offline? | Yes — fully | No — needs internet |
| Can I use it without the other? | Yes — try GitLab or your own server | No — GitHub only hosts Git repos |
| What is its job? | Track file changes | Host Git repos and add collaboration features |

A useful analogy: **Git is the recorder; GitHub is the radio station.** You can record music without ever going on air. But if you want people to hear it, the radio station is where you publish.

---

## 0.6 What Git Provides You

Let's get concrete. Here is what you actually get when you start using Git on a project:

### 1. A time machine for your files

You can move your entire project back to any point in its history with one command. You can compare today's version with last month's version, line by line. You can find out exactly when a bug was introduced and by whom.

### 2. Safe experimentation with branches

A **branch** is a parallel timeline. You can create a branch called `experiment-redesign`, do wildly destructive work on it, and your `main` branch stays untouched. If the experiment works, you merge it. If it doesn't, you delete the branch and nothing happened.

### 3. A distributed backup

Every clone of your repository contains the full history. If your laptop dies tomorrow, you `git clone` from GitHub and you are back where you were. If GitHub disappears tomorrow (it won't), you still have the full history on your laptop.

### 4. The ability to collaborate without overwriting

Git is built for parallel work. Alice and Bob can edit the same file at the same time. When they merge, Git combines their changes automatically if they touched different parts of the file. If they touched the same line, Git pauses and asks a human to decide — this is called a **merge conflict** (Chapter 4).

### 5. An audit trail

Every commit records author, timestamp, and message. Every line of code can be traced back to the commit that introduced it (`git blame`). If a regulator asks "who changed this code, when, and why?" — Git answers in seconds.

### 6. A release management system

You can tag commits: `v1.0`, `v1.1`, `v2.0`. Each tag is a fixed, named point in history. When you publish version 2.0, you tag the commit and the release is locked — anyone who checks out that tag gets the exact code you shipped.

### 7. A foundation for automation

Because commits are structured, machines can act on them. "When a commit lands on `main`, run the tests. If they pass, deploy to production." This is CI/CD, and it would be impossible without version control.

---

## 0.7 Why You Should Use Git & GitHub

If you are still wondering whether version control is worth the effort, here are the concrete reasons you should adopt Git and GitHub today:

### For an individual developer

- **You will never lose code again.** Every change is preserved; every deletion is reversible.
- **You can experiment freely.** Branches let you try things without risk.
- **You can work from any machine.** Push from your laptop, pull on your desktop, continue on a colleague's machine.
- **Your portfolio becomes discoverable.** A GitHub profile with real projects is the modern CV for software roles.

### For a team

- **Parallel work without chaos.** Multiple developers can work on the same codebase simultaneously.
- **Code review before merge.** Catch bugs and spread knowledge before code reaches `main`.
- **Continuous integration.** Tests run automatically on every push; broken code is caught within minutes, not weeks.
- **Onboarding is faster.** A new hire can read the commit history to understand *why* the code is the way it is, not just *what* it does.

### For an open-source project

- **Anyone can contribute.** Fork → branch → PR → review → merge. No access grants needed up-front.
- **Transparent history.** Every decision is public and traceable.
- **Distributed load.** Hundreds of contributors can submit changes; maintainers review and merge at their own pace.

### For non-developers

- **Writers** version manuscripts (the `git-book` community uses Git extensively).
- **Lawyers** version contracts (every clause change is a commit).
- **Researchers** version datasets and analysis scripts (reproducibility).
- **Designers** version design files (with the right tools).
- **Governments** version legislation (e.g., the US Code is on GitHub).

Git is not just for code. It is for *any* file whose history matters.

---

## 0.8 How Git Thinks (Four Mental Models)

Git has a reputation for being confusing. The confusion usually comes from trying to use it without a mental model. Here are four models that, taken together, explain 95% of Git behaviour.

### Model 1 — The Snapshot Chain

A Git repository is a chain of **snapshots**. Each snapshot is a complete picture of every tracked file at one moment in time. Each snapshot remembers its parent(s). The chain of snapshots *is* the history.

```
Snapshot 1     Snapshot 2     Snapshot 3     Snapshot 4
"Initial"  ←── "Add README" ←── "Fix typo" ←── "Add tests"
 (parent:∅)    (parent: 1)    (parent: 2)    (parent: 3)
```

To go "back in time", you just walk the parent pointers. There is no special "history" data structure — history *is* the chain.

### Model 2 — The Three Areas

Git tracks your files in three areas. Almost every Git confusion reduces to "which area is this in?".

```
┌──────────────────┐      ┌──────────────────┐      ┌──────────────────┐
│  Working Directory│  ──> │  Staging Area    │  ──> │  Repository      │
│                  │      │   (Index)        │      │   (commits)      │
│  Your actual     │      │  "Next commit"   │      │  Saved snapshots │
│  files on disk    │      │   is being built │      │  in .git/        │
│                  │      │                  │      │                  │
│  git status      │      │  git add         │      │  git commit      │
│  git diff        │      │  git restore -S  │      │  git log         │
└──────────────────┘      └──────────────────┘      └──────────────────┘
        ▲                                                    │
        │              git checkout / git restore             │
        └────────────────────────────────────────────────────┘
```

| Area | Where it lives | What's in it | Command to inspect |
|---|---|---|---|
| Working directory | Your actual files on disk | The files you edit | `git status`, `git diff` |
| Staging area (index) | `.git/index` | The *next* commit, being assembled | `git diff --staged` |
| Repository | `.git/objects` | Saved commits, the immutable history | `git log`, `git show` |

Commands move changes between these areas:
- `git add` moves changes *from* working dir *to* staging.
- `git commit` moves changes *from* staging *to* the repository.
- `git checkout` / `git restore` moves changes *from* the repository *back to* the working dir.

That's it. Master this triangle and 90% of Git clicks.

### Model 3 — Branches Are Just Sticky Notes

In older VCSs, a branch was a copy of the entire project. Slow and expensive.

In Git, **a branch is just a small file containing a 40-character commit hash** — a sticky note pointing at the latest commit on that line of work. That's why creating or deleting a branch in Git takes microseconds: you're just moving a sticky note.

```
       (commit)──(commit)──(commit)   ← branch "main" points here
                              ▲
                              │
                          [main]   ← a sticky note
                          
       (commit)──(commit)              ← branch "feature" points here
                          ▲
                          │
                       [feature]  ← another sticky note
```

Creating a branch = adding a sticky note. Switching branches = moving your working directory to match what the sticky note points at. Merging a branch = moving the sticky note forward.

### Model 4 — Distributed = Everyone Has Everything

In a centralized VCS, only the server has the full history. In Git, every clone has the complete history — every commit, every branch, every tag.

```
       GitHub (origin)
        │  ▲
   push  │  │  pull
        ▼  │
   ┌────────────┐
   │ Your laptop │  ← has full history
   │ (local repo)│
   └────────────┘
        ▲  │
   pull  │  │  push
        │  ▼
   ┌────────────┐
   │ Coworker's  │  ← also has full history
   │   laptop    │
   └────────────┘
```

This means:
- You can commit, branch, merge, and explore history offline.
- Every clone is a backup.
- You can have multiple remotes (your fork, the upstream project, a backup server) and sync between them.

---

## 0.9 Vocabulary You Will See Everywhere

You will see these words repeatedly from Chapter 1 onward. Skim them now; bookmark this section.

| Term | Plain-English meaning |
|---|---|
| **Repository (repo)** | A folder Git is tracking. Contains your files and a hidden `.git` directory with all the history. |
| **Working directory** | The actual files you see and edit on disk, right now. |
| **Staging area / index** | The "shopping cart" of changes you have selected for the next commit. |
| **Commit** | A saved snapshot, identified by a 40-character SHA-1 hash. |
| **Hash (SHA)** | A fingerprint of a commit. e.g. `a1b2c3d4e5...`. Short forms (`a1b2c3d`) work in most commands. |
| **Branch** | A movable pointer to a commit. Cheap to create, cheap to delete. |
| **`HEAD`** | A special pointer that says "you are here". Points to the current branch. |
| **Tag** | A *fixed* pointer to a specific commit. Used for releases: `v1.0`, `v2.3.7`. |
| **Remote** | Another Git repository you sync with. Usually named `origin`. |
| **`origin`** | The default name Git gives to the remote you cloned from. |
| **`upstream`** | Convention: the *original* project's remote (when you forked). |
| **Fork** | A server-side copy of someone else's repo, owned by you. GitHub concept, not Git. |
| **Clone** | A local copy of a repo, including all its history. |
| **Pull request (PR)** | A proposal: "please merge my branch into yours". GitHub concept, not Git. |
| **Merge** | Combining two branches' histories. |
| **Merge conflict** | When two branches changed the same lines and Git cannot auto-merge. |
| **Rebase** | Replaying commits on top of another branch. (Chapter 8.) |
| **Diff** | A line-by-line display of what changed between two versions. |
| **Stash** | A temporary shelf for uncommitted changes. |
| **Reflog** | A log of where `HEAD` has been — your safety net for "I messed up". |
| **Hooks** | Scripts that run automatically before/after Git events (e.g. pre-commit). |
| **Blame** | Show which commit last touched each line of a file. |
| **Bisect** | Binary-search through commits to find which one introduced a bug. |
| **Fast-forward** | A merge where the target branch just moves forward to the source commit, no merge commit needed. |
| **Detached HEAD** | When `HEAD` points at a commit, not a branch. Usually happens when you check out an old commit. |
| **Submodule** | A Git repo nested inside another Git repo. |
| **Worktree** | Multiple working directories sharing the same `.git` directory. |

---

## 0.10 Your Turn

Before moving on, take five minutes to write down — in your own words — answers to these questions. Don't peek at the chapter above.

1. What problem does version control solve, in one sentence?
2. Name three things Git stores about each commit.
3. What is the difference between Git and GitHub?
4. Why is Git called "distributed"? What does that buy you?
5. What are the three areas of Git, and what command moves changes *between* them?

If you can answer all five without looking, you are ready for Chapter 1. If not, re-read the relevant section — the rest of the guide depends on these foundations.

**Next up: Chapter 1 — Installation & First Setup.** We will install Git on your operating system, configure your identity, set up SSH keys, and connect your local Git to your GitHub account. By the end of Chapter 1 you will be ready to make your first commit.

---
---


# Chapter 1 — Installation & First Setup

> **Goal of this chapter:** Get Git installed on your computer, configure your identity, set up an SSH key, sign up for GitHub, and verify everything works. By the end of this chapter, you will be ready to create your first repository in Chapter 2.

This chapter is mostly setup — once it's done, you never have to do it again. Take your time, follow every step, and verify each command's output before moving to the next.

---

## 1.1 Installing Git

Git runs on Windows, macOS, and Linux. Installation differs by operating system.

### Windows

The recommended installer is **Git for Windows**, which includes Git itself plus **Git Bash** — a Unix-style terminal that makes Windows behave like a real development environment.

1. Go to <https://git-scm.com/download/win>. The download should start automatically.
2. Run the installer. The defaults are sensible for a beginner. **Keep all defaults** unless you have a specific reason to change them. Notable options:
   - **Default editor** — pick VS Code if installed, otherwise Notepad++.
   - **"Use Git from the Windows Command Prompt"** — leave at default (lets you use `git` in PowerShell too).
   - **Line ending conversions** — leave at "Checkout Windows-style, commit Unix-style" (`core.autocrlf=true`). This avoids the dreaded `LF will be replaced by CRLF` warning.
3. After installation, open **Git Bash** from the Start menu. You should see a Unix-style prompt:
   ```text
   user@machine MINGW64 ~
   $
   ```

### macOS

The easiest way on macOS is via **Homebrew** (the de-facto macOS package manager).

1. If you don't have Homebrew, install it first. Open Terminal and paste:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Then install Git:
   ```bash
   brew install git
   ```

If you don't want Homebrew, an alternative is to install **Xcode Command Line Tools** (which bundles Git):

```bash
xcode-select --install
```

A dialog will pop up; click **Install**. Wait. Done.

### Linux (Debian/Ubuntu and derivatives)

```bash
sudo apt update
sudo apt install git
```

For Fedora / RHEL:

```bash
sudo dnf install git
```

For Arch:

```bash
sudo pacman -S git
```

### Verifying the installation

Open a terminal (Git Bash on Windows, Terminal on macOS/Linux) and run:

```bash
git --version
```

You should see something like:

```text
git version 2.46.0
```

If you see `command not found`, Git is not in your `PATH`. On Windows, install Git for Windows; on macOS/Linux, re-check the install steps above.

---

## 1.2 Your Identity: The First-Time Configuration

Every Git commit records **who made it**. Git needs to know your name and email. This is set once and used for every commit you ever make on this machine.

### Setting your name and email

```bash
git config --global user.name "Your Real Name"
git config --global user.email "you@example.com"
```

**Line by line:**

- `git config` — the command that reads/writes Git settings.
- `--global` — write to `~/.gitconfig` (your user-level config), so it applies to every repo on this machine. Without `--global`, the setting applies only to the current repo (stored in `.git/config`).
- `user.name` — the setting key. Use your real name (or whatever name you want on your commits). Quote it if it contains spaces.
- `user.email` — the email. **Use the same email as your GitHub account** so GitHub can link your commits to your profile. If you want privacy, GitHub offers a `noreply` email address — see section 1.4 below.

### Verifying your config

```bash
git config --global --list
```

Sample output:

```text
user.name=Aziz Nader
user.email=aziz@example.com
core.editor=code --wait
init.defaultbranch=main
```

You can also read the raw config file:

```bash
cat ~/.gitconfig
```

Sample output:

```ini
[user]
    name = Aziz Nader
    email = aziz@example.com
[core]
    editor = code --wait
[init]
    defaultBranch = main
```

### A few more useful global settings

```bash
# Use "main" as the default branch name. Old tutorials say "master";
# GitHub and the wider community moved to "main" in 2020.
git config --global init.defaultBranch main

# The editor Git opens for commit messages and interactive rebase.
# Options:
#   "code --wait"   — VS Code (recommended if installed)
#   "nano"          — beginner-friendly terminal editor
#   "notepad"       — Windows Notepad
#   "vim" / "nvim"  — power-user editors
git config --global core.editor "code --wait"

# Pull with rebase by default (cleaner history; explained in Chapter 8).
git config --global pull.rebase true

# Make "push" push the current branch only (avoids surprises).
git config --global push.default current

# Color output — on by default in modern Git, but explicit is safe.
git config --global color.ui auto
```

After all of the above, your `~/.gitconfig` should look something like:

```ini
[user]
    name = Aziz Nader
    email = aziz@example.com
[init]
    defaultBranch = main
[core]
    editor = code --wait
[color]
    ui = auto
[pull]
    rebase = true
[push]
    default = current
```

---

## 1.3 Creating Your GitHub Account

1. Go to <https://github.com/signup>.
2. Pick a **username** carefully. It becomes your public identity: `github.com/yourusername`. Avoid throwaway names — recruiters, collaborators, and future-you will see this.
3. Use an email you check regularly; GitHub sends security and notification emails.
4. Choose the **Free** plan. You do not need a paid plan for any feature in this guide.
5. Verify your email (click the link GitHub sends you). Without verification, you cannot push code.

### Setting your GitHub profile

Spend 15 minutes on your profile — it pays off:

- **Profile picture** — a clear photo or avatar. People trust faces more than default identicons.
- **Bio** — one line: what you do, what you're learning.
- **Pinned repositories** — pin 4–6 of your best projects. These show up at the top of your profile.

### (Optional) Keep your email private

By default, commits include your email address. If you don't want that public, GitHub offers a no-reply email:

1. Go to <https://github.com/settings/emails>.
2. Tick **"Keep my email addresses private"**.
3. Copy the email GitHub generates, e.g. `12345+aziz@users.noreply.github.com`.
4. Use that email in your `git config`:

   ```bash
   git config --global user.email "12345+aziz@users.noreply.github.com"
   ```

5. Also tick **"Block command line pushes that expose my email"** to enforce it.

Now your commits will be linked to your GitHub profile, but your real email stays private.

---

## 1.4 Connecting Git to GitHub: HTTPS vs SSH

When you push or pull from GitHub, you have to authenticate. Two options:

| | HTTPS | SSH |
|---|---|---|
| URL looks like | `https://github.com/you/repo.git` | `git@github.com:you/repo.git` |
| Authentication | Username + **Personal Access Token** (passwords no longer work) | SSH key pair (public + private) |
| Setup effort | Easy (just generate a token) | One-time setup, then never think about it again |
| Recommendation | Good for getting started | **Recommended** — set up once, use forever |

We'll set up **both**, then default to SSH because it's smoother long-term.

---

## 1.5 Setting Up SSH Keys Step by Step

An **SSH key pair** is two files: a *private key* (which stays on your computer, never shared) and a *public key* (which you give to GitHub). When you push, Git signs the request with your private key; GitHub verifies it with your public key. No password ever travels.

### Step 1 — Generate a key pair

```bash
ssh-keygen -t ed25519 -C "you@example.com"
```

**Line by line:**

- `ssh-keygen` — the key-generation program (ships with OpenSSH, which is installed by default on macOS/Linux and on Windows via Git Bash).
- `-t ed25519` — key type. Ed25519 is modern, fast, and short. (Older guides use `-t rsa -b 4096`, which still works but is older tech.)
- `-C "you@example.com"` — a comment. Convention: your email. It's just a label baked into the public key, not used for authentication.

You'll be prompted:

```text
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/you/.ssh/id_ed25519):
```

Press **Enter** to accept the default location.

```text
Enter passphrase (empty for no passphrase):
```

Optional but recommended: a passphrase encrypts your private key so a stolen laptop doesn't expose your key. If you set one, you'll be asked for it whenever the key is used (but you can configure an agent to remember it).

### Step 2 — Start the SSH agent and add your key

```bash
# Start the agent (macOS/Linux; on Git Bash for Windows it's usually auto-started)
eval "$(ssh-agent -s)"

# Add your private key to the agent
ssh-add ~/.ssh/id_ed25519
```

**Line by line:**

- `eval "$(ssh-agent -s)"` — starts `ssh-agent`, a background process that holds your key in memory. The `eval` runs the agent's output as a shell command, setting environment variables so `ssh` can find the agent.
- `ssh-add ~/.ssh/id_ed25519` — loads your private key into the agent. If you set a passphrase, you'll enter it once; the agent remembers it for the session.

On macOS, to make the agent remember your passphrase across reboots, edit `~/.ssh/config`:

```text
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

### Step 3 — Copy your public key

```bash
cat ~/.ssh/id_ed25519.pub
```

Output is one long line starting with `ssh-ed25519`:

```text
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... you@example.com
```

**Copy that entire line.** (Note the `.pub` extension — that's the *public* key. The private key has no extension and never leaves your machine.)

### Step 4 — Add the key to GitHub

1. Go to <https://github.com/settings/keys>.
2. Click **New SSH key**.
3. **Title:** "Personal Laptop" or whatever describes this machine.
4. **Key type:** Authentication Key.
5. **Key:** paste the line you copied.
6. Click **Add SSH key**. GitHub may ask for your password to confirm.

### Step 5 — Test the connection

```bash
ssh -T git@github.com
```

The first time you connect, you'll see:

```text
The authenticity of host 'github.com (140.82.114.4)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Type **yes**. (This adds GitHub to your `known_hosts` file so you won't see this again.)

Then you'll see:

```text
Hi aziznader! You've successfully authenticated, but GitHub does not provide shell access.
```

That last sentence sounds scary but is correct — GitHub doesn't give you a shell, only Git access. You're in.

---

## 1.6 Personal Access Tokens (for HTTPS)

If you'd rather use HTTPS instead of SSH, you need a **Personal Access Token (PAT)** because GitHub stopped accepting account passwords for Git operations in August 2021.

### Creating a PAT

1. Go to <https://github.com/settings/tokens>.
2. **Generate new token → Generate new token (classic)**.
3. **Note:** "Git access from laptop".
4. **Expiration:** pick 90 days or "No expiration" if you don't want to renew (less secure).
5. **Scopes:** tick `repo` (full control of private repositories). That's enough for this guide.
6. Click **Generate token**.
7. **Copy the token immediately.** You won't be able to see it again after leaving the page.

### Using the PAT

The first time you `git push` over HTTPS, Git will prompt:

```text
Username for 'https://github.com': aziznader
Password for 'https://aziznader@github.com': [paste your PAT here]
```

Git will store it (on macOS via Keychain, on Windows via Credential Manager, on Linux via `libsecret`) so you won't have to enter it again.

If Git doesn't remember it, configure credential storage explicitly:

```bash
# macOS (uses Keychain)
git config --global credential.helper osxkeychain

# Windows (uses Credential Manager; default in Git for Windows)
git config --global credential.helper manager

# Linux (uses libsecret; install it if needed)
git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
```

---

## 1.7 The GitHub CLI

The **GitHub CLI (`gh`)** lets you do GitHub-y things from the terminal: create repos, open pull requests, list issues, view Actions logs, etc. It complements Git but is not a replacement.

### Installing `gh`

```bash
# Windows (PowerShell or Git Bash)
winget install --id GitHub.cli

# macOS
brew install gh

# Linux (Debian/Ubuntu)
# See https://github.com/cli/cli/blob/trunk/docs/install_linux.md for the official source
# Quick version:
sudo apt install gh
```

Verify:

```bash
gh --version
```

### Authenticating `gh`

```bash
gh auth login
```

You'll be guided through an interactive prompt:

```text
? What account do you want to log into? GitHub.com
? What is your preferred protocol for Git operations on this host? SSH
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser
```

The last option opens a browser, gives you a one-time code, and you paste it. Done. From now on, `gh` and `git` both know who you are.

Verify:

```bash
gh auth status
```

Output:

```text
github.com
  ✓ Logged in to github.com account aziznader
  - Active account: true
  - Git operations protocol: ssh
  - Token: gho_************************************
  - Logged in to github.com account aziznader (keyring)
```

---

## 1.8 Choosing Your Editor

If you don't already have a code editor, install **Visual Studio Code** (VS Code):

- <https://code.visualstudio.com/> — free, runs everywhere, and integrates beautifully with Git.

After installing, open VS Code and run the command palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) → **Shell Command: Install 'code' command in PATH**. Now you can open any folder in VS Code from the terminal:

```bash
code .                    # open current folder
code some-file.txt       # open a file
code .git/config         # peek at Git's config (useful for debugging)
```

Tell Git to use VS Code for commit messages and interactive rebase:

```bash
git config --global core.editor "code --wait"
git config --global credential.helper manager   # Windows only — already default
```

The `--wait` flag is critical: it makes Git pause until you close the VS Code tab before continuing. Without it, Git thinks you finished editing immediately.

---

## 1.9 Where to Get Help

You will forget commands. Everyone does. The pros just know how to look things up. Two ways:

### `git help` and `git <command> --help`

```bash
git help               # list of common commands
git help commit        # full manual for `git commit`
git commit --help      # same thing, different syntax
git help -a            # list ALL commands (there are ~150)
git help -g            # list concept guides (e.g. "git help tutorial")
```

The manual pages are excellent and include examples. Use them.

### The Pro Git book (free online)

The official, free, comprehensive Git reference is the **Pro Git book** by Scott Chacon and Ben Straub:

<https://git-scm.com/book>

Read it online, download the PDF, or buy the print edition. Chapters 1–5 cover 99% of what you'll ever need.

---

## 1.10 Your Turn

Verify your setup by doing the following in order. Don't skip — every step is a checkpoint.

1. **Open a terminal** (Git Bash on Windows) and run:
   ```bash
   git --version
   ```
   Confirm you see a version `2.30` or higher.

2. **Check your identity:**
   ```bash
   git config --global user.name
   git config --global user.email
   ```
   Both should print the values you set. If either is empty, redo section 1.2.

3. **Generate an SSH key** (if you haven't), add it to GitHub, and test:
   ```bash
   ssh -T git@github.com
   ```
   You should see the `Hi <username>!` message.

4. **Install the GitHub CLI** and verify your login:
   ```bash
   gh auth status
   ```

5. **Install VS Code** (if you don't have a preferred editor) and configure Git to use it:
   ```bash
   git config --global core.editor "code --wait"
   ```

When all five checks pass, you are ready for Chapter 2. In the next chapter you will create your first real repository, make changes, stage them, commit them, and view the history — all the core mechanics of Git.

**Next up: Chapter 2 — Git Fundamentals: Your First Repository.**

---
---


# Chapter 2 — Git Fundamentals: Your First Repository

> **Goal of this chapter:** Create your first Git repository, understand the **working directory → staging area → repository** flow, write a commit, and explore history. By the end of this chapter, you will have a working local Git repo with at least three commits and a `.gitignore` file.

This is the most important chapter in the entire guide. Read it twice. Type every command. Don't move on until each step's output matches what's shown here.

---

## 2.1 Creating a Repository: `git init`

### Step 1 — Make a folder for the project

```bash
mkdir my-first-repo
cd my-first-repo
```

**Line by line:**

- `mkdir my-first-repo` — "make directory". Creates a folder named `my-first-repo` in your current location.
- `cd my-first-repo` — "change directory". Moves into that folder.

### Step 2 — Turn it into a Git repository

```bash
git init
```

Expected output:

```text
Initialized empty Git repository in /Users/you/my-first-repo/.git/
```

**What just happened?**

Git created a hidden folder called `.git/` inside your project. This folder *is* the repository — everything Git knows about your project lives in there. Your actual files (the ones you edit) live in the parent folder and are *not* the repository; they are your working copy.

Verify the `.git/` folder exists:

```bash
ls -a
```

Expected output (on macOS/Linux; Windows Git Bash similar):

```text
.    ..    .git
```

`-a` shows hidden files (those starting with `.`). You should see `.git`. Don't touch it manually unless you know exactly what you're doing — Chapter 3 explores it.

### The full directory structure right now

```
my-first-repo/
└── .git/                  ← the repository (Git's database)
    ├── HEAD               ← pointer to current branch
    ├── config             ← local Git config
    ├── description        ← placeholder text (rarely used)
    ├── hooks/             ← sample hook scripts
    ├── info/              ← global gitignore patterns
    ├── objects/           ← all the actual data (blobs, trees, commits)
    └── refs/              ← pointers: branches (heads/), tags (tags/)
```

---

## 2.2 The Three Areas of Git

Before making commits, internalize this picture. It is the most important diagram in the entire guide.

```
┌──────────────────────┐      ┌──────────────────────┐      ┌──────────────────────┐
│  Working Directory   │      │  Staging Area        │      │  Repository (.git)   │
│                      │      │   (the "index")      │      │                     │
│  Your actual files   │      │  The next commit,    │      │  Saved commits,     │
│  on disk — the ones  │      │  being assembled     │      │  immutable history  │
│  you edit            │      │                      │      │                     │
│                      │      │                      │      │                     │
│   git status         │ ───> │   git add <file>     │ ───> │   git commit        │
│   git diff           │      │   git restore --staged│    │   git log            │
│                      │ <─── │                      │ <─── │                     │
│                      │      │                      │      │                     │
└──────────────────────┘      └──────────────────────┘      └──────────────────────┘
```

**Mental shortcut:** think of it as a meal being cooked.

- **Working directory** = the ingredients on your counter, in any state.
- **Staging area** = the tray of ingredients you've measured out for the next dish.
- **Repository** = the dish, plated and served (cannot be un-plated).

`git add` moves ingredients from counter → tray. `git commit` moves tray → plate. You can rearrange the tray as much as you want before serving.

---

## 2.3 Checking the State: `git status`

`git status` is the most-run command in Git. Run it constantly. It tells you:
- Which branch you're on
- What's in the working directory (modified, untracked, deleted)
- What's in the staging area
- What Git suggests you do next

Run it now (in your fresh repo):

```bash
git status
```

Expected output:

```text
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

**Reading the output:**

- `On branch main` — you are on the `main` branch. (We configured `init.defaultBranch = main` in Chapter 1.)
- `No commits yet` — the repo has no history.
- `nothing to commit` — there's nothing in the working directory to track.

Now let's create a file and re-run `git status`:

```bash
echo "# My First Repo" > README.md
git status
```

`echo "# My First Repo" > README.md` writes the line `# My First Repo` into a new file called `README.md`. The `>` redirects output to a file.

New `git status` output:

```text
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)
```

**Reading the output:**

- `Untracked files:` — Git sees `README.md` exists, but isn't tracking it yet.
- The line `(use "git add <file>..." to include in what will be committed)` is a hint: Git is telling you the next command to run.

Notice that Git doesn't automatically track new files — you have to opt in with `git add`. This is a feature, not a bug: it prevents you from accidentally committing sensitive files like `.env`.

---

## 2.4 Staging Changes: `git add`

`git add` moves a change from the **working directory** to the **staging area**.

```bash
git add README.md
git status
```

Output:

```text
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```

**Reading the output:**

- `Changes to be committed:` — this section lists what's in the staging area, ready for the next commit.
- `new file: README.md` — Git sees this as a brand-new file (because no previous commit contains it).

### Other forms of `git add`

| Command | What it does |
|---|---|
| `git add README.md` | Stage one specific file. |
| `git add README.md LICENSE.txt` | Stage multiple specific files. |
| `git add .` | Stage everything in the current directory (and below). Most common form. |
| `git add -A` | Stage everything in the entire repo, including deletions. |
| `git add -u` | Stage modifications and deletions, but **not** new files. |
| `git add -p` | Stage *part* of a file (interactive). Walks you through each hunk. |
| `git add *.md` | Stage all Markdown files (shell expands the wildcard). |

### `git add -p` — the power user's friend

`-p` stands for "patch". It interactively asks, for each chunk of changes, whether you want to stage it. This lets you create *clean* commits by staging only the changes that belong together.

Example session:

```bash
echo "line 1" >> README.md
echo "line 2" >> README.md
echo "line 3" >> README.md
git add -p README.md
```

Git will show:

```text
diff --git a/README.md b/README.md
index abc1234..def5678 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,4 @@
 # My First Repo
+line 1
+line 2
+line 3
(1/1) Stage this hunk [y,n,q,a,d,s,e,?]? 
```

Press `?` for help:

```text
y - stage this hunk
n - do not stage this hunk
q - quit; do not stage this hunk or any of the remaining ones
a - stage this hunk and all later hunks in the file
d - do not stage this hunk or any of the later hunks in the file
s - split the current hunk into smaller hunks
e - manually edit the current hunk
? - print help
```

Press `s` to split, then `y`/`n` for each piece. This is how pros make atomic commits (Chapter 11).

---

## 2.5 Saving a Snapshot: `git commit`

```bash
git commit -m "Initial commit: add README"
```

Expected output:

```text
[main (root-commit) 9fceb52] Initial commit: add README
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
```

**Line by line:**

- `git commit` — the commit command. Takes everything currently in the staging area and saves it as a new snapshot in history.
- `-m "Initial commit: add README"` — the commit message. `-m` means "use this string as the message" instead of opening your editor. Without `-m`, Git opens your editor (VS Code in our setup) for a multi-line message.
- `[main (root-commit) 9fceb52]` — confirmation. `main` is the branch, `(root-commit)` means this is the first commit (no parent), and `9fceb52` is the short hash identifying this commit.
- `1 file changed, 1 insertion(+)` — summary of what changed: one new file, one line added.
- `create mode 100644 README.md` — the file was newly created. `100644` is a Unix permission (regular file, read/write for owner, read for others).

### Anatomy of a good commit message

| Bad | Good | Why |
|---|---|---|
| `update` | `Add password reset flow to login page` | Specific, actionable, describes what and why |
| `fix` | `Fix null pointer in user profile lookup` | Tells the reader exactly what was fixed |
| `asdf` | `Refactor auth module for testability` | Searchable months later |
| `WIP` | `Add tests for the password reset flow` | A stranger reading the log should understand |

We'll cover commit message conventions in depth in Chapter 11. For now: **the message describes *why* the change was made, not what changed** — Git already shows what changed via `git diff`.

### Multi-line commit messages

For longer messages, omit `-m` and let Git open your editor:

```bash
git commit
```

In VS Code, type a one-line summary on the first line, leave a blank line, then a paragraph explaining the change:

```text
Add password reset flow

Implements the forgot-password feature end-to-end:
- New route /password/reset
- Email sending via the existing mailer
- Token expiry after 1 hour
- Tests for happy path and expired token
```

Save and close the editor. Git commits.

Alternatively, multiple `-m` flags become separate paragraphs:

```bash
git commit -m "Add password reset flow" -m "Implements forgot-password end-to-end: route, email, token expiry, tests."
```

---

## 2.6 Anatomy of a Commit

A commit is more than a snapshot of files. It is a record of six things:

1. **A 40-character SHA-1 hash** (the commit's ID, computed from its contents)
2. **A pointer to the parent commit(s)** (usually one; merge commits have two)
3. **A tree** (the snapshot: which files exist, with which content)
4. **Author name and email**
5. **Author timestamp**
6. **Committer name and email + timestamp** (usually same as author)
7. **The commit message**

You can inspect any commit with `git show`:

```bash
git show
```

Sample output (abbreviated):

```text
commit 9fceb528d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c (HEAD -> main)
Author: Aziz Nader <aziz@example.com>
Date:   Sat Oct 5 10:32:14 2025 +0200

    Initial commit: add README

diff --git a/README.md b/README.md
new file mode 100644
index 0000000..abc1234
--- /dev/null
+++ b/README.md
@@ -0,0 +1 @@
+# My First Repo
```

**Reading the output:**

- `commit 9fceb52...` — the full 40-char hash. Git shows the short form (`9fceb52`) by default in most commands.
- `(HEAD -> main)` — `HEAD` (where you are) currently points to `main`, which points to this commit.
- `Author:` — who wrote the change.
- `Date:` — when (in your local timezone; the raw stored value is Unix epoch).
- `Initial commit: add README` — the message.
- `diff --git ...` — the actual changes this commit introduced, in unified diff format. `+` lines are additions, `-` lines are deletions.

---

## 2.7 Ignoring Files: `.gitignore`

Most projects have files that should **never** be tracked:

- **Secrets:** `.env`, API keys, passwords
- **Dependencies:** `node_modules/`, `vendor/` (huge, reproducible from `package.json`)
- **Build output:** `dist/`, `build/`, `*.o`, `*.class`
- **OS junk:** `.DS_Store` (macOS), `Thumbs.db` (Windows)
- **Editor configs:** `.vscode/`, `.idea/` (subjective; some teams track them)

Git uses a file called `.gitignore` (in the repo root) to know what to skip.

### Creating a `.gitignore`

```bash
cat > .gitignore << 'EOF'
# .gitignore — lines starting with # are comments

# Secrets
.env
.env.local
*.pem

# Dependencies (huge, reproducible — don't track)
node_modules/
vendor/

# Build output
dist/
build/
*.log

# OS junk
.DS_Store
Thumbs.db

# Editor / IDE
.vscode/
.idea/

# Python example
__pycache__/
*.pyc
.venv/

# Exception: track this one file despite the *.log rule above
!important.log
EOF
```

**Reading the patterns:**

- `.env` — ignores any file literally named `.env` (anywhere in the tree).
- `node_modules/` — ignores any folder named `node_modules` (the trailing `/` means "folder only").
- `*.log` — wildcard: any file ending in `.log`.
- `dist/` — folder, anywhere.
- `.DS_Store` — common macOS junk file.
- `!important.log` — `!` *negates* a pattern, so `important.log` is tracked even though `*.log` would otherwise ignore it.

### Useful `.gitignore` templates

GitHub maintains a giant collection of starter `.gitignore` files for every language/framework at <https://github.com/github/gitignore>. Copy the one for your stack as a starting point.

### What if I already committed a file I want to ignore?

`.gitignore` only affects *untracked* files. If a file is already tracked, you must first untrack it:

```bash
git rm --cached .env             # untrack but keep on disk
git commit -m "Stop tracking .env (added to .gitignore)"
```

`--cached` is critical — without it, `git rm` deletes the file from disk too. With `--cached`, it removes only from Git's index; the file stays on your computer.

---

## 2.8 Viewing History: `git log` and `git show`

### `git log`

Lists commits, newest first:

```bash
git log
```

Sample output:

```text
commit 9fceb528d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c (HEAD -> main)
Author: Aziz Nader <aziz@example.com>
Date:   Sat Oct 5 10:32:14 2025 +0200

    Initial commit: add README
```

Useful variations:

```bash
git log --oneline              # one line per commit (short hash + message)
git log --oneline --graph      # ASCII graph of branches/merges
git log --oneline --graph --all  # include ALL branches
git log -5                     # last 5 commits
git log --stat                 # show files changed in each commit
git log -p                     # show the actual diff of each commit
git log --author="Aziz"        # only commits by author
git log --since="2 weeks ago"  # only recent commits
git log -- README.md           # only commits that touched README.md
git log -S "function foo"      # commits that added/removed the string "function foo"
```

The most-used combination for daily work:

```bash
git log --oneline --graph --all --decorate
```

Sample output for a real project:

```text
* 9fceb52 (HEAD -> main) Add password reset tests
* 4d2c1ab Add password reset flow
* a1b2c3d Refactor auth module
| * 7e8f9ab (feature/dark-mode) Add dark mode toggle
| * 3c4d5e6 Initial dark mode styles
|/
* 5f6a7b8 Initial commit
```

### `git show`

`git show` displays everything about a single commit: metadata + diff.

```bash
git show                    # shows the latest commit
git show 9fceb52            # shows a specific commit by hash
git show HEAD               # same as `git show` — HEAD is "current commit"
git show HEAD~1             # the commit BEFORE HEAD (parent)
git show HEAD~~             # two commits before
git show main               # the commit at the tip of `main`
git show README.md          # shows the latest change to README.md (file)
```

---

## 2.9 Seeing Exactly What Changed: `git diff`

`git diff` shows line-by-line differences. There are three common forms:

### 1. Working directory vs. staging area

```bash
git diff
```

Shows changes in your working directory that are **not yet staged**.

### 2. Staging area vs. last commit

```bash
git diff --staged
# or equivalently:
git diff --cached
```

Shows changes that **are** staged but not yet committed.

### 3. Any two commits

```bash
git diff HEAD~3 HEAD              # last 3 commits' worth of changes
git diff a1b2c3d 9fceb52          # between two specific commits
git diff main feature/login       # between two branches
```

### Reading a diff

```text
diff --git a/README.md b/README.md
index abc1234..def5678 100644
--- a/README.md
+++ b/README.md
@@ -1,3 +1,4 @@
 # My First Repo
 
+This is a new paragraph.
 Some existing content.
```

**Reading line by line:**

- `diff --git a/README.md b/README.md` — comparing two versions of `README.md`. `a/` is the old version, `b/` is the new.
- `index abc1234..def5678 100644` — internal Git hashes for the old and new versions; `100644` is the file mode.
- `--- a/README.md` and `+++ b/README.md` — markers showing which file is which.
- `@@ -1,3 +1,4 @@` — a "hunk header". ` -1,3 ` means "starting at line 1 of the old version, 3 lines". ` +1,4 ` means "starting at line 1 of the new version, 4 lines".
- ` # My First Repo` — context line (unchanged). Starts with a space.
- `+This is a new paragraph.` — added line. Starts with `+`.
- `-Some old line.` — deleted line. Starts with `-` (not in this example).

### Word-level diff (for prose)

For text files where line diffs are too coarse:

```bash
git diff --word-diff
```

Shows additions as `{+added+}` and deletions as `{-removed-}` inline.

---

## 2.10 A Second and Third Commit

Let's make two more commits to build up a real history.

```bash
echo "" >> README.md
echo "This is a project I'm building while learning Git." >> README.md
git status
git add README.md
git commit -m "Add project description to README"
```

Output of the commit:

```text
[main 4d2c1ab] Add project description to README
 1 file changed, 2 insertions(+)
```

And a third:

```bash
mkdir src
echo 'console.log("Hello, Git!");' > src/index.js
git add src/index.js
git commit -m "Add hello-world entry point"
git log --oneline
```

`git log --oneline` now shows:

```text
4d2c1ab Add hello-world entry point
a1b2c3d Add project description to README
9fceb52 Initial commit: add README
```

You now have a real, three-commit Git repository. This is the foundation everything else builds on.

---

## 2.11 Your Turn

Do this exercise on your own machine. Don't skip it — the next chapter assumes you've done it.

1. Create a new repo called `git-practice` in your home folder.

2. Create a `README.md` with one line: `# Git Practice`.

3. Initialize Git and make your first commit: `Initial commit`.

4. Add a `.gitignore` with these contents:
   ```
   *.log
   .env
   .DS_Store
   ```

5. Create a file `notes.txt`, write something in it, and commit it: `Add personal notes`.

6. Modify `README.md` (add a line), check `git status`, stage only the README, and commit: `Expand README with description`.

7. Run `git log --oneline --graph --all` and confirm you see three commits.

8. Run `git show HEAD` and read the output. Identify the hash, the author, the date, the message, and the diff.

9. Create a file `secret.env` with content `PASSWORD=hunter2`. Verify with `git status` that it appears as untracked. Add `.env` to your `.gitignore`. Verify with `git status` again — it should disappear from untracked files. (Note: `*.env` would also work; `.env` only matches files literally named `.env`. Adjust to taste.)

10. Bonus: stage *part* of a file with `git add -p`. Create a file `multiline.txt` with 5 lines, modify 3 of them, and use `git add -p` to stage only 2.

When all ten steps pass, you have graduated from "never used Git" to "uses Git locally". Chapter 3 takes you inside `.git/` to understand *how* Git stores everything — which makes branching and merging feel natural rather than magical.

**Next up: Chapter 3 — Git Internals: What's Actually Inside `.git`.**

---
---


# Chapter 3 — Git Internals: What's Actually Inside `.git`

> **Goal of this chapter:** Demystify the `.git/` directory. Understand blobs, trees, commits, and refs. By the end, branching and merging in Chapter 4 will feel obvious — they're just moving pointers around.

This chapter is **optional for everyday use** but **essential for true understanding**. You can use Git for years without knowing what's in `.git/`, but every confusing Git error will remain confusing until you do.

---

## 3.1 The `.git/` Directory Tour

In your repo, run:

```bash
ls -la .git/
```

You'll see something like:

```text
total 64
drwxr-xr-x   10 you  staff   320 Oct  5 10:32 .
drwxr-xr-x    4 you  staff   128 Oct  5 10:35 ..
-rw-r--r--    1 you  staff    23 Oct  5 10:32 HEAD
-rw-r--r--    1 you  staff   137 Oct  5 10:32 config
-rw-r--r--    1 you  staff    73 Oct  5 10:32 description
drwxr-xr-x   14 you  staff   448 Oct  5 10:32 hooks
-rw-r--r--    1 you  staff   178 Oct  5 10:32 index          ← staging area
drwxr-xr-x    3 you  staff    96 Oct  5 10:32 info
drwxr-xr-x    4 you  staff   128 Oct  5 10:32 logs
drwxr-xr-x    3 you  staff    96 Oct  5 10:32 objects        ← all the data
drwxr-xr-x    4 you  staff   128 Oct  5 10:32 refs          ← branches & tags
```

| Path | Purpose |
|---|---|
| `HEAD` | A single line: the branch you're currently on. |
| `config` | This repo's local config (overrides `~/.gitconfig`). |
| `description` | Placeholder used by old GitWeb; ignore. |
| `hooks/` | Sample hook scripts (Chapter 8). |
| `index` | Binary file: the staging area. |
| `info/` | Global excludes (like `.gitignore` but for you only). |
| `logs/` | The **reflog**: where `HEAD` has been. Safety net. |
| `objects/` | All blobs, trees, commits. The actual database. |
| `refs/` | Pointers: branches (`refs/heads/`) and tags (`refs/tags/`). |

---

## 3.2 Three Kinds of Objects

Git stores **three types of objects** in `.git/objects/`:

1. **Blob** — the content of a file (just the bytes; not even the file name).
2. **Tree** — a directory listing (file names + permissions + blob hashes, or sub-tree hashes).
3. **Commit** — a snapshot of a tree, plus metadata (parent, author, message).

Each object is identified by a 40-character SHA-1 hash of its content. **Hashing the same content always produces the same hash**, which is how Git deduplicates and detects corruption.

### Object 1: the Blob

A blob is the content of a file at one moment. Let's see one.

```bash
git hash-object README.md
```

Output (a 40-char hash):

```text
9fceb528d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c
```

`git hash-object` computes what hash Git *would* give the file if you added it. The actual blob object is stored in `.git/objects/9f/ceb528d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c` (first 2 chars = folder, remaining 38 = file name; this shards the objects to avoid one giant directory).

To see the contents of any object:

```bash
git cat-file -p 9fceb52
```

Output (the file's content):

```text
# My First Repo
```

`-p` means "pretty-print". For a blob, that's just the content.

### Object 2: the Tree

A tree is a directory. It lists the files and subdirectories in that directory, with their hashes.

```bash
git cat-file -p main^{tree}
```

`main^{tree}` is Git syntax for "the tree object that the commit at the tip of `main` points to".

Sample output:

```text
100644 blob 9fceb528d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c    README.md
040000 tree 4b825dc642cb6eb9a060e54bf8d69288fbee4904    src
```

Reading each line:
- `100644` — file mode (regular file, rw-r--r--).
- `040000` — directory mode.
- `blob` / `tree` — object type.
- `9fceb52...` — the SHA-1 of the blob (or sub-tree).
- `README.md` / `src` — the name in this directory.

So a tree is just a list of `(mode, type, hash, name)` tuples.

### Object 3: the Commit

```bash
git cat-file -p HEAD
```

Sample output:

```text
tree 4b825dc642cb6eb9a060e54bf8d69288fbee4904
parent a1b2c3d4e5f6789012345678901234567890abcd
author Aziz Nader <aziz@example.com> 1728114734 +0200
committer Aziz Nader <aziz@example.com> 1728114734 +0200

Add password reset tests
```

Reading line by line:
- `tree ...` — the top-level tree of this snapshot.
- `parent ...` — the commit this one builds on. (Merge commits have two `parent` lines.)
- `author ...` — who wrote the change, and when (Unix timestamp + timezone).
- `committer ...` — who applied the commit (usually same as author; differs on rebases/cherry-picks).
- Blank line.
- The commit message.

### How they fit together

```
   Commit (HEAD)
     │
     ├─── tree (root)
            ├─── blob (README.md content)
            ├─── tree (src/)
            │      └── blob (src/index.js content)
            └─── blob (LICENSE content)
```

A commit points to a tree, the tree points to blobs (and sub-trees), blobs hold the actual file content. **Branches are just files containing a commit hash. Tags are similar.** That's the whole model.

---

## 3.3 Hashes, Short Hashes, and `rev-parse`

Every Git object has a 40-character SHA-1 hash. You almost never type the full hash — Git accepts any unambiguous prefix.

```bash
git show 9fceb52          # 8 chars — fine
git show 9fceb            # 5 chars — usually fine, may be ambiguous
git show 9f               # 2 chars — too short, ambiguous
```

To get a hash from a friendly name:

```bash
git rev-parse HEAD         # full 40-char hash of HEAD
git rev-parse main         # hash of the commit at the tip of main
git rev-parse main~3       # hash of main's great-grandparent
```

`HEAD~3` is shorthand for "three commits before HEAD". `~` walks first parents; `^` walks any parent (relevant for merge commits which have multiple parents — `HEAD^2` is the second parent).

---

## 3.4 Branches and Tags Are Just Files

A **branch** is a file in `.git/refs/heads/` containing a commit hash.

```bash
cat .git/refs/heads/main
```

Output:

```text
4d2c1ab9d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c
```

That's it. The entire existence of `main` is this 41-byte file. Creating a branch = creating a similar file. Switching branches = changing which file `HEAD` points to.

A **tag** is the same idea, but in `.git/refs/tags/`. The difference: tags don't move (by convention), branches do.

There's also `HEAD`:

```bash
cat .git/HEAD
```

Output:

```text
ref: refs/heads/main
```

`HEAD` is a pointer to a *branch*. (In "detached HEAD" state, it points directly to a commit hash.)

### Why this matters

Once you internalize that **branches are 41-byte files**, several "mysterious" Git behaviours become obvious:

- **Branching is instant.** You're writing a 41-byte file. No copying.
- **Deleting a branch is instant.** Just `rm` the file.
- **Switching branches is fast.** Just update `HEAD` and rewrite the working directory.
- **`main` is not special.** It's a branch like any other. (It's just the conventional default name.)
- **You can rename branches freely.** It's just renaming a file. (Use `git branch -m old new`.)

---

## 3.5 The Index (Staging Area)

The staging area is a binary file at `.git/index`. You don't read it directly — you use `git add`, `git status`, `git diff --staged` — but it's worth knowing what's in it.

Conceptually, the index is a list of `(path, mode, blob-hash)` tuples for every file that would be in the next commit. When you run `git add README.md`, Git:

1. Computes the blob hash of `README.md`'s current content.
2. Stores the blob in `.git/objects/` if it's not already there.
3. Updates the index entry for `README.md` to point at that blob.

When you commit, Git builds a tree from the index, wraps it in a commit object, and updates the current branch.

### Peeking at the index

```bash
git ls-files                  # list all tracked files
git ls-files -s               # list with mode, hash, stage (verbose)
```

Sample `-s` output:

```text
100644 9fceb528d4e4c5b8b3e8b7c6f5a4d3c2b1a09182c 0    README.md
100644 8baef1b4abc414c5d8b3e8b7c6f5a4d3c2b1a0918 0    src/index.js
```

The middle column is the blob hash. If you see `1` or `2` in the last column instead of `0`, you have an unresolved merge conflict (Chapter 4).

---

## 3.6 The Reflog: Your Safety Net

Git records every place `HEAD` has been in a log called the **reflog**. This is what makes Git so safe — even "lost" commits can usually be recovered.

```bash
git reflog
```

Sample output:

```text
4d2c1ab HEAD@{0}: commit: Add hello-world entry point
a1b2c3d HEAD@{1}: commit: Add project description to README
9fceb52 HEAD@{2}: commit (initial): Initial commit: add README
```

Each line: `<commit-hash> <ref-position>: <action>: <message>`.

`HEAD@{0}` is *now*. `HEAD@{1}` is *one operation ago*. And so on.

### Recovering a "deleted" commit

Suppose you accidentally `git reset --hard HEAD~1` (we'll cover this in Chapter 7). You "lost" the most recent commit. But the reflog still has it:

```bash
git reflog
# 9fceb52 HEAD@{0}: reset: moving to HEAD~1
# 4d2c1ab HEAD@{1}: commit: Add hello-world entry point   ← the "lost" commit
```

To recover:

```bash
git reset --hard 4d2c1ab     # move HEAD back to the lost commit
```

The commit isn't deleted by `reset` — only the branch pointer moves. The commit object is still in `.git/objects/`. It will be truly deleted only when Git runs **garbage collection** (typically after 30 days of being unreferenced). Until then, it's recoverable.

---

## 3.7 Garbage Collection

Git periodically compresses unreferenced objects and deletes them. This is `git gc`.

```bash
git gc                       # clean up now
git gc --aggressive          # more thorough, slower
git gc --prune=now           # delete unreachable objects immediately
```

You almost never need to run this manually. Git runs it automatically when:
- The number of loose objects exceeds a threshold.
- After `git pull` and certain other commands.

The reason: garbage collection makes the repo smaller and faster, but it permanently deletes unreferenced commits. Until `gc` runs, **everything is recoverable via the reflog**.

---

## 3.8 Packfiles (How Git Stores History Efficiently)

If Git stored every version of every file as a separate blob, large repos would explode. Git periodically packs many objects into a single **packfile** (`.git/objects/pack/*.pack`) with delta compression: only the differences between versions are stored.

You don't need to understand packfiles to use Git, but knowing they exist explains why `du -sh .git` is often *much smaller* than the sum of all your file changes.

```bash
git count-objects -v
```

Sample output:

```text
count: 87
size: 1240
in-pack: 5234
packs: 3
size-pack: 8920
prune-packable: 0
garbage: 0
size-garbage: 0
```

`count` is loose objects; `in-pack` is objects inside packfiles. Most mature repos have the majority of objects in packs.

---

## 3.9 Putting It Together: A Walkthrough

Let's trace what happens when you edit a file, stage it, and commit. Every step corresponds to a real change in `.git/`.

1. You edit `README.md`. **Working directory only.** No `.git` changes.

2. You run `git add README.md`. Git:
   - Hashes the file content → blob hash, e.g. `def5678...`.
   - Stores the blob in `.git/objects/de/f5678...`.
   - Updates the index entry for `README.md` to point at this blob.

3. You run `git commit -m "Update README"`. Git:
   - Builds a tree from the index → tree hash.
   - Builds a commit object pointing at that tree, with the parent = current `HEAD`'s commit, the author info, the message.
   - Stores the commit object.
   - Updates `.git/refs/heads/main` to the new commit hash.
   - Updates `.git/logs/HEAD` (the reflog) with the new entry.

4. `git push` (we'll cover in Chapter 5). Git:
   - Computes which commits the remote is missing.
   - Bundles them (and their blobs/trees) into a packfile.
   - Sends the packfile over the wire.
   - The remote unpacks and updates its own `refs/heads/main`.

This is *the entire mental model of Git*. Every command from here on is a high-level wrapper around these primitives.

---

## 3.10 Your Turn

1. Open your `git-practice` repo from Chapter 2. Run `ls -la .git/` and identify each entry (HEAD, config, objects/, refs/, index).

2. Run `git cat-file -p HEAD` and identify the tree, parent, author, committer, and message.

3. Run `git cat-file -p HEAD^{tree}` to see the top-level tree. Note the blobs (files) and trees (subdirectories).

4. Take the hash of one of the blobs (e.g. the README blob hash from the tree listing). Run `git cat-file -p <hash>` and confirm you see the file content.

5. Run `git ls-files -s` and look at the index. Notice that the hashes there match the tree's blob hashes.

6. Make two more commits, then run `git reflog`. Confirm you can see every operation you did.

7. Run `git rev-parse HEAD` and `git rev-parse main`. They should be identical (because `HEAD` points to `main`).

8. Open `.git/refs/heads/main` in a text editor (or `cat` it) and confirm the hash matches.

If you completed all 8 steps, you have x-ray vision into Git. Branching will now feel natural.

**Next up: Chapter 4 — Branching and Merging.** We'll create branches, switch between them, merge them, and (gasp) hit our first merge conflict — and resolve it without panic.

---
---


# Chapter 4 — Branching and Merging

> **Goal of this chapter:** Master branches — Git's most powerful feature. Create, switch, rename, delete branches. Merge them. Hit and resolve merge conflicts. By the end, you'll know what "git checkout -b feature/dark-mode" *means*, not just what it *does*.

This chapter is where Git starts to pay off. Branches transform version control from "I have history" to "I have parallel universes of my project, and I can move between them at will".

---

## 4.1 What Is a Branch?

In Chapter 3 we saw the truth: **a branch is a 41-byte file containing a commit hash**. That's it. No copy of the files. No "branch folder". Just a pointer to the latest commit on that line of work.

Visually:

```
   (C1) ── (C2) ── (C3)                  ← commits
                       ▲
                       │
                     [main]              ← branch "main" points to C3
```

When you commit on `main`, Git:
1. Creates commit C4 with parent = C3.
2. Moves the `main` pointer forward to C4.

```
   (C1) ── (C2) ── (C3) ── (C4)
                               ▲
                               │
                             [main]
```

That's all "moving forward on main" means.

A **second branch** is just another pointer:

```
   (C1) ── (C2) ── (C3) ── (C4)            ← main
                    │
                    └─ (C3') ── (C3'')      ← feature
                                 ▲
                                 │
                              [feature]
```

C3' and C3'' are commits on `feature` whose parent is C3 (the point where `feature` branched off). `main` keeps marching forward independently.

---

## 4.2 Why Branches Change Your Life

Branches let you try things without fear. Real examples:

- **"I want to refactor the auth module, but I'm not sure it'll work."** → Make a `refactor/auth` branch. If it works, merge. If not, delete the branch; `main` is untouched.
- **"I'm halfway through a feature and there's a production bug."** → Stash or commit your work on `feature/login`, switch to `main`, branch off `hotfix/prod-crash`, fix, merge, deploy, switch back to `feature/login` and continue.
- **"Two of us are working on the same project."** → Alice on `feature/cart`, Bob on `feature/search`. Both branch from `main`. Merge both back when done.

Without branches, you'd be emailing ZIPs of "the version that has the new login but not the cart changes". With branches, this is automatic.

---

## 4.3 Creating and Switching Branches

### Listing branches

```bash
git branch
```

Output:

```text
* main
```

The `*` marks the current branch. (You're on `main` because that's the default.)

### Creating a branch (without switching)

```bash
git branch feature/dark-mode
```

`git branch <name>` creates the branch pointer at the current commit but **does not switch to it**. You're still on `main`.

```bash
git branch
```

Output:

```text
* main
  feature/dark-mode
```

### Switching to a branch

There are two equivalent commands:

```bash
git checkout feature/dark-mode        # classic syntax (still works everywhere)
git switch feature/dark-mode          # modern syntax (Git 2.23+, clearer intent)
```

After either:

```bash
git branch
```

Output:

```text
  main
* feature/dark-mode
```

### Create-and-switch in one step

```bash
git checkout -b feature/dark-mode      # classic
git switch -c feature/dark-mode         # modern (-c for "create")
```

Both create the branch *and* switch to it. This is what you'll do 90% of the time.

**Reading the command:**

- `git switch` — switch branches.
- `-c feature/dark-mode` — `c` for "create". Creates the branch before switching.

### Naming branches

Conventions vary by team, but common patterns:

| Pattern | Example | When to use |
|---|---|---|
| `feature/<short-name>` | `feature/password-reset` | New feature work |
| `bugfix/<short-name>` | `bugfix/login-crash` | Bug fix |
| `hotfix/<short-name>` | `hotfix/prod-memory-leak` | Urgent production fix |
| `chore/<short-name>` | `chore/upgrade-dependencies` | Maintenance, no user-facing change |
| `docs/<short-name>` | `docs/api-reference` | Documentation only |
| `release/<version>` | `release/2.1.0` | Preparing a specific release |

Use `/` to group. Use `-` (kebab-case) for multi-word names. Avoid spaces and uppercase.

---

## 4.4 `HEAD`: Where You Are Right Now

`HEAD` is a special pointer that says "you are here". Normally `HEAD` points to a branch (which points to a commit):

```
HEAD ─→ refs/heads/main ─→ commit C4
```

When you commit, Git updates the branch `HEAD` points to (so `main` moves to C5, and `HEAD` transitively does too).

When you `git checkout <commit-hash>` (not a branch), `HEAD` points directly at that commit:

```
HEAD ─→ commit C2  (no branch involved)
```

This is called **detached HEAD** state. It's not dangerous, but any commits you make here are not on any branch and will be "lost" when you switch away (until you create a branch from them). Git will warn you:

```text
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.
```

To recover from detached HEAD after making commits you want to keep:

```bash
git branch save-my-work      # create a branch at this commit
git switch main              # safely switch away
```

Now `save-my-work` is a regular branch with your commits.

---

## 4.5 Deleting and Renaming Branches

### Deleting a branch (after merging)

```bash
git switch main
git branch -d feature/dark-mode       # -d for "delete (safe)"
```

`-d` (lowercase) refuses to delete if the branch hasn't been merged — it's a safety check.

```text
error: The branch 'feature/dark-mode' is not fully merged.
If you are sure you want to delete it, run 'git branch -D feature/dark-mode'.
```

### Forcing deletion

```bash
git branch -D feature/dark-mode        # -D for "force delete"
```

Use `-D` when you abandoned the branch and don't care about its commits.

### Renaming a branch

```bash
git branch -m feature/dark-mode feature/theme-switch
```

`-m` for "move" (like `mv`). Renames the branch in place. If you've already pushed the old name to GitHub, you'll need to delete the remote branch and push the new one (Chapter 5).

### Renaming the branch you're currently on

```bash
git branch -m new-name       # renames the current branch to "new-name"
```

---

## 4.6 Merging

Merging brings changes from one branch into another. Two kinds of merge:

### 1. Fast-forward merge

When the target branch is a direct descendant of the source (no diverging commits), Git just moves the pointer forward.

Setup:

```bash
git switch main
git checkout -b feature/add-favicon      # branch off main
echo "<link rel='icon' href='/favicon.ico'>" >> index.html
git add index.html
git commit -m "Add favicon link"
git switch main
```

State before merge:

```
(C1) ── (C2) ── (C3)                       ← main
                    │
                    └── (C4 favicon)       ← feature/add-favicon
```

Now merge:

```bash
git merge feature/add-favicon
```

Output:

```text
Updating a1b2c3d..4d2c1ab
Fast-forward
 index.html | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 index.html
```

State after merge:

```
(C1) ── (C2) ── (C3) ── (C4 favicon)       ← main
                                          ↑
                                  feature/add-favicon (still here)
```

`main` just moved forward. No merge commit was created. Git calls this a **fast-forward merge**.

### 2. Three-way merge (when histories diverged)

When both branches have new commits since they diverged, Git creates a **merge commit** with two parents.

Setup:

```bash
git switch main
git checkout -b feature/footer
echo "<footer>© 2025</footer>" >> index.html
git add index.html
git commit -m "Add footer"

git switch main
echo "<!-- main branch change -->" >> index.html
git add index.html
git commit -m "Update index.html on main"
```

State:

```
(C1) ── (C2) ── (C3) ── (C5 main update)        ← main
                    │
                    └── (C4 footer)              ← feature/footer
```

Now merge:

```bash
git switch main
git merge feature/footer
```

Git tries to merge. If no conflict (changes were in different parts of the file), it opens your editor for a merge commit message:

```text
Merge branch 'feature/footer'
```

Save and close. New state:

```
(C1) ── (C2) ── (C3) ── (C5 main update) ── (C6 merge commit)   ← main
                    │                            ┌────┘
                    └── (C4 footer) ─────────────┘
```

`C6` is the **merge commit** — it has *two* parents: `C5` (from main) and `C4` (from feature/footer).

Output:

```text
Merge made by the 'ort' strategy.
 index.html | 1 +
 1 file changed, 1 insertion(+)
```

### Force no fast-forward (always create a merge commit)

```bash
git merge --no-ff feature/footer
```

`--no-ff` ensures a merge commit is created even when a fast-forward would be possible. This preserves the "this came from a feature branch" history, which many teams prefer.

---

## 4.7 Merge Conflicts: The Complete Walkthrough

A **merge conflict** happens when two branches changed the *same lines* of the *same file* in incompatible ways. Git cannot decide which version wins, so it pauses and asks you.

### Setting up a conflict

```bash
git switch main
git checkout -b conflict-practice

# Edit the same line in two different ways
echo "Version A" > greeting.txt
git add greeting.txt
git commit -m "Set greeting to Version A"

git switch main
echo "Version B" > greeting.txt
git add greeting.txt
git commit -m "Set greeting to Version B"

# Now try to merge conflict-practice into main
git merge conflict-practice
```

Output:

```text
Auto-merging greeting.txt
CONFLICT (add/add): Merge conflict in greeting.txt
Automatic merge failed; fix conflicts and then commit the result.
```

### What's in the file now?

```bash
cat greeting.txt
```

Output:

```text
<<<<<<< HEAD
Version B
=======
Version A
>>>>>>> conflict-practice
```

Reading the markers:

- `<<<<<<< HEAD` — start of "our" side (the branch you're on, `main`).
- `Version B` — the content on `main`.
- `=======` — the divider.
- `Version A` — the content from `conflict-practice`.
- `>>>>>>> conflict-practice` — end of "their" side.

### Resolving the conflict

Edit the file to the final desired content. You can pick one side, the other, both, or something new. Remove all the `<<<<<<<`, `=======`, `>>>>>>>` markers.

For example, change it to:

```text
Version A and B combined
```

Save the file.

### Marking as resolved

```bash
git add greeting.txt
git status
```

Output:

```text
On branch main
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        modified:   greeting.txt
```

```bash
git commit
```

Git opens your editor with a default message:

```text
Merge branch 'conflict-practice'
```

Save and close. The merge is complete.

### Aborting a merge

If you don't want to deal with the conflict right now:

```bash
git merge --abort
```

Returns you to the pre-merge state. The working directory is clean again.

### Tools that make conflicts easier

For simple conflicts, edit the file directly. For complex conflicts with many files:

- **`git mergetool`** — opens a visual merge tool (configurable; common ones: VS Code, Meld, KDiff3, Beyond Compare).
- **VS Code** — has built-in 3-way merge UI when you open a conflicted file. Click "Accept Current", "Accept Incoming", or "Accept Both" right above each conflict block.

```bash
git config --global merge.tool code
git config --global mergetool.code.cmd 'code --wait $MERGED'
```

Then `git mergetool` opens VS Code.

### Tips for resolving conflicts calmly

1. **Don't panic.** Git hasn't lost anything; the conflict markers show you both versions.
2. **Read the diff.** Understand *what* each side wanted before deciding.
3. **Talk to your teammate.** If the conflict is on a teammate's branch, ask them which version they intended.
4. **Run the tests after resolving.** A merge that compiles is not the same as a merge that works.
5. **Commit small branches.** Long-lived branches accumulate conflicts. Short branches rarely conflict.

---

## 4.8 Branch Naming Conventions

Conventions vary, but these are widely accepted:

| Prefix | Purpose | Example |
|---|---|---|
| `feature/` | New functionality | `feature/password-reset` |
| `bugfix/` or `fix/` | Bug fix | `fix/login-redirect-loop` |
| `hotfix/` | Urgent production fix | `hotfix/prod-crash-2025-10` |
| `chore/` | Maintenance, no user-facing change | `chore/upgrade-react` |
| `docs/` | Documentation only | `docs/api-reference-update` |
| `refactor/` | Code restructuring, no behaviour change | `refactor/extract-auth-service` |
| `experiment/` | Trying something out | `experiment/serverless-version` |
| `release/` | Preparing a release | `release/2.1.0` |

Include a ticket number if your team uses a tracker:

```text
feature/PROJ-123-password-reset
```

This makes the branch auto-link to the Jira ticket in many tools.

---

## 4.9 Branching Workflows Used by Teams

Different teams structure their branches differently. Three common patterns:

### 1. GitHub Flow (simplest)

- One long-lived branch: `main`.
- All work happens on short-lived feature branches.
- Each feature branch → PR → merge to `main`.
- `main` is always deployable.

Best for: small teams, web apps that deploy continuously.

### 2. Git Flow (more structured)

- Two long-lived branches: `main` (production) and `develop` (next release).
- Feature branches off `develop`.
- `release/x.y.z` branches for release prep.
- `hotfix/` branches off `main` for urgent production fixes, merged back to both `main` and `develop`.

Best for: products with versioned releases (mobile apps, desktop software).

### 3. Trunk-Based Development

- Everyone commits directly to `main` (or very short-lived branches).
- Feature flags hide unfinished work from users.
- Continuous deployment.

Best for: mature teams with strong CI/CD, deploying many times per day.

**Recommendation for beginners:** start with **GitHub Flow**. It's the simplest and works for 95% of projects.

---

## 4.10 Visualizing Branches

### ASCII in the terminal

```bash
git log --oneline --graph --all --decorate
```

Sample output:

```text
* 9fceb52 (HEAD -> main) Merge branch 'feature/footer'
|\
| * 4d2c1ab Add footer
* | a1b2c3d Update index.html on main
|/
* 5f6a7b8 Initial commit
```

Reading:
- `*` is a commit.
- `|`, `\`, `/` show the branching/merging structure.
- `(HEAD -> main)` shows where pointers are.

### Pretty log alias

Many people alias this:

```bash
git config --global alias.lg "log --oneline --graph --all --decorate"
```

Now `git lg` gives you the pretty graph.

### Browser visualisation

GitHub.com shows branch graphs at **Insights → Network** for any repo. Easier to read for big histories.

---

## 4.11 Cherry-Picking a Commit

Sometimes you want one specific commit from another branch, not the whole branch:

```bash
git switch main
git cherry-pick <commit-hash>
```

`git cherry-pick` takes the changes from a single commit and applies them to your current branch as a new commit. Useful for:
- Backporting a bug fix to a release branch.
- Pulling a single commit you want without merging a long branch.

Note: the new commit has a different hash than the original (because it has a different parent and timestamp).

---

## 4.12 Your Turn

1. In your `git-practice` repo, create a branch `feature/credits`. Add a file `CREDITS.md` with your name. Commit. Switch back to `main`.

2. Verify with `git log --oneline --graph --all` that `feature/credits` has a commit `main` doesn't.

3. Merge `feature/credits` into `main`. Verify it's a fast-forward merge (because `main` hasn't moved since the branch was created).

4. Now create two branches from `main`: `feature/a` and `feature/b`. On each, modify the *same line* of `notes.txt` differently. Commit on each. Switch back to `main`, merge `feature/a` (should succeed). Merge `feature/b` — you should get a conflict.

5. Resolve the conflict by combining both changes (e.g. write "Feature A and Feature B" on the conflicting line). `git add` the file, then `git commit` to finish the merge.

6. Inspect the merge commit with `git show HEAD`. Notice the `Merge:` line showing two parent hashes.

7. Create a third branch `feature/c` with a single commit, then cherry-pick that commit onto `main` without merging the whole branch.

8. Delete the merged branches with `git branch -d`. Confirm only `main` remains.

If all steps worked, you have graduated from "I can use Git locally" to "I can use Git like a developer". Next, we connect your local work to GitHub.

**Next up: Chapter 5 — Remotes and Publishing to GitHub.**

---
---


# Chapter 5 — Remotes and Publishing to GitHub

> **Goal of this chapter:** Connect your local repository to GitHub. Push commits up. Pull commits down. Clone existing repos. Understand what "remotes" are. By the end, your code will be visible on github.com and you'll know how to sync between machines.

Until now, everything has lived on your computer. That's powerful, but it misses the point of Git: collaboration. In this chapter, you'll connect your local repo to a remote — usually GitHub — and learn the dance of pushing and pulling.

---

## 5.1 What Is a Remote?

A **remote** is another Git repository that yours knows about. Typically it's a server (GitHub, GitLab, your company's server), but it can be any Git repo — even one on a USB stick.

Your local repo can have multiple remotes. By convention, the main one is called `origin`. If you've **forked** a project, you'll typically have:
- `origin` — your fork (which you can push to).
- `upstream` — the original project (which you can pull from but not push to).

Listing remotes:

```bash
git remote -v
```

`-v` for "verbose" — shows URLs. Sample output for a fresh local repo:

```text
(empty)
```

No remotes yet. Let's add one.

---

## 5.2 Creating a Repository on GitHub

There are two ways to start: from the GitHub website, or from the `gh` CLI.

### Method 1: GitHub website

1. Go to <https://github.com/new>.
2. **Repository name:** `my-first-repo` (must be unique in your account, can have hyphens).
3. **Description:** optional one-liner.
4. **Public or Private:** pick Public for this exercise.
5. **Initialize with README:** **leave unchecked**. We already have files locally; checking this creates a `README.md` on GitHub, which means our local and remote histories are unrelated — we'd have to merge them (doable but confusing for the first time).
6. **.gitignore:** pick "Node" if you want one; we already have ours.
7. **License:** pick "MIT License" if you want one; otherwise leave None.
8. **Create repository**.

GitHub shows you a page with commands for connecting an existing local repo:

```bash
git remote add origin git@github.com:yourname/my-first-repo.git
git branch -M main
git push -u origin main
```

Copy these — we'll use them next.

### Method 2: GitHub CLI

If you've authenticated `gh` (Chapter 1), creating a remote repo from the terminal is one command:

```bash
gh repo create my-first-repo --public --source=. --remote=origin --push
```

**Reading the command:**

- `gh repo create my-first-repo` — name on GitHub.
- `--public` — visibility.
- `--source=.` — use the current local directory as the source.
- `--remote=origin` — name the new remote `origin`.
- `--push` — push immediately.

If it works, you'll see:

```text
✓ Created repository yourname/my-first-repo on github.com
✓ Added remote "origin"
✓ Pushed commits to the "main" branch
```

Skip to section 5.4 — you're done.

---

## 5.3 Linking Your Local Repo: `git remote add`

If you used Method 1 (created an empty repo on GitHub), you need to link your local repo to it manually.

```bash
git remote add origin git@github.com:yourname/my-first-repo.git
```

**Line by line:**

- `git remote add` — adds a new remote.
- `origin` — the local nickname for this remote. Convention: always `origin` for the primary.
- `git@github.com:yourname/my-first-repo.git` — the SSH URL (recommended; Chapter 1 set this up).

The HTTPS equivalent:

```bash
git remote add origin https://github.com/yourname/my-first-repo.git
```

Verify:

```bash
git remote -v
```

Output:

```text
origin  git@github.com:yourname/my-first-repo.git (fetch)
origin  git@github.com:yourname/my-first-repo.git (push)
```

The same URL appears twice because Git distinguishes "fetch" (download from) and "push" (upload to). Most of the time they're the same.

### Changing a remote URL

If you need to switch from HTTPS to SSH (or vice versa):

```bash
git remote set-url origin git@github.com:yourname/my-first-repo.git
```

### Renaming a remote

```bash
git remote rename origin upstream      # rename "origin" to "upstream"
```

### Removing a remote

```bash
git remote remove origin
```

---

## 5.4 Uploading Your Work: `git push`

```bash
git push -u origin main
```

**Line by line:**

- `git push` — upload local commits to a remote.
- `-u` (or `--set-upstream`) — tells Git to remember that `main` locally tracks `main` on `origin`. You only do this once per branch; afterwards, plain `git push` and `git pull` work without arguments.
- `origin` — the remote name.
- `main` — the branch name.

First-time output:

```text
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (12/12), 1.34 KiB | 1.34 MiB/s, done.
Total 12 (delta 1), reused 0 (delta 0), pack-reused 0
To github.com:yourname/my-first-repo.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
```

**Reading the output:**

- `Enumerating objects: 12` — Git counted 12 objects (commits, trees, blobs) to send.
- `Compressing objects: 100%` — Git packed them.
- `* [new branch] main -> main` — the remote created a new branch `main` to match yours.
- `branch 'main' set up to track 'origin/main'` — future `git push`/`pull` on `main` will know what to do.

### Subsequent pushes

After `-u` is set, just:

```bash
git push
```

That's it. Pushes any new local commits on the current branch to its tracked remote branch.

---

## 5.5 Downloading Changes: `git fetch` and `git pull`

Two commands download from a remote. They differ subtly but importantly.

### `git fetch` — download but don't merge

```bash
git fetch
```

Downloads new commits from the remote into a separate area (`origin/main`, etc.), but **does not change your working directory or `main`**. Your local `main` is untouched.

Use `git fetch` when you want to see what changed before deciding to merge.

```bash
git fetch
git log origin/main --oneline      # see what's on the remote
git diff main origin/main          # see the diff
git merge origin/main              # merge when ready
```

### `git pull` — fetch + merge

```bash
git pull
```

Equivalent to `git fetch` followed by `git merge origin/main` (or `git rebase origin/main` if you set `pull.rebase=true` in Chapter 1). Updates your working directory immediately.

```bash
git pull
```

Sample output (after a web edit on GitHub):

```text
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 718 bytes | 179.00 KiB/s, done.
From github.com:yourname/my-first-repo
   9fceb52..4d2c1ab  main        -> origin/main
Updating 9fceb52..4d2c1ab
Fast-forward
 README.md | 2 ++
 1 file changed, 2 insertions(+)
```

**Reading the output:**

- `From github.com:yourname/my-first-repo` — fetching from your remote.
- `9fceb52..4d2c1ab main -> origin/main` — your local view of remote `main` (`origin/main`) updated from `9fceb52` to `4d2c1ab`.
- `Updating 9fceb52..4d2c1ab` — your local `main` is being updated too.
- `Fast-forward` — your `main` had no diverging commits, so it just moved forward.

### When to use which

- `git fetch` — you want to look before you leap. Useful in collaborative repos where someone else might have pushed something unexpected.
- `git pull` — you trust the remote and just want to be up to date. Most common for solo work.

---

## 5.6 Downloading a Whole Project: `git clone`

`git clone` downloads a remote repo and all its history to your computer, in one command. Used when you want to start working on an existing project.

```bash
git clone git@github.com:yourname/my-first-repo.git
```

This creates a folder `my-first-repo/` in your current directory, with all files and full history, and `origin` set to the cloned URL.

Sample output:

```text
Cloning into 'my-first-repo'...
remote: Enumerating objects: 24, done.
remote: Counting objects: 100% (24/24), done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 24 (delta 4), reused 22 (delta 2), pack-reused 0
Receiving objects: 100% (24/24), 4.55 KiB | 1.51 MiB/s, done.
Resolving deltas: 100% (4/4), done.
```

### Cloning into a specific folder

```bash
git clone git@github.com:yourname/my-first-repo.git my-folder
```

Creates `my-folder/` instead of `my-first-repo/`.

### Cloning a specific branch

```bash
git clone -b develop git@github.com:yourname/repo.git
```

Checks out the `develop` branch after cloning.

### Shallow clone (just the latest commit)

For huge repos where you don't need history:

```bash
git clone --depth 1 git@github.com:torvalds/linux.git
```

Downloads only the latest commit. Saves gigabytes on big repos. Useful for CI; not recommended if you need history.

---

## 5.7 Fork vs Clone

People confuse these. Important distinction:

| | Clone | Fork |
|---|---|---|
| What it does | Downloads a copy to your computer | Creates a copy on GitHub under your account |
| Where it happens | Locally | On github.com |
| Permissions needed | Read access (public repos: anyone) | Read access (same) |
| Can you push back? | Only if you have write access to the original | Yes — to your fork; then PR to original |
| Git concept? | Yes | No, GitHub-specific |

Typical open-source flow:

1. **Fork** `octocat/Spoon-Knife` on github.com → `yourname/Spoon-Knife` (your copy on GitHub).
2. **Clone** your fork locally → `my-first-repo/` (your copy on your laptop).
3. Make changes locally, commit, **push to your fork** (`origin`).
4. Open a **pull request** from `yourname/Spoon-Knife` to `octocat/Spoon-Knife`.

We'll cover step 4 in Chapter 6.

### Forking from the CLI

```bash
gh repo fork octocat/Spoon-Knife --clone
```

Forks on GitHub and clones locally in one step.

---

## 5.8 When Push Is Rejected

Sometimes you'll see this:

```bash
git push
```

```text
To github.com:yourname/my-first-repo.git
 ! [rejected]            main -> main (fetch first)
error: failed to push some refs to 'github.com:yourname/my-first-repo.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. ...
```

**What it means:** someone (possibly you, on another machine, or via GitHub's web editor) pushed commits to `origin/main` that you don't have locally. Git refuses to overwrite them.

**Fix:** pull first, then push.

```bash
git pull
# (resolve any conflicts if prompted)
git push
```

`git pull` will either fast-forward (if your local and remote commits are independent), or create a merge commit (if they diverged). After pulling, your local `main` includes the remote's commits, so the push will succeed.

---

## 5.9 Tracking Branches

When you `git push -u origin main`, Git sets up a **tracking relationship**: your local `main` "tracks" `origin/main`. This lets `git push` and `git pull` work without arguments.

To see all tracking relationships:

```bash
git branch -vv
```

Output:

```text
* main          9fceb52 [origin/main] Merge branch 'feature/footer'
  feature/x     a1b2c3d Add experimental feature
```

`[origin/main]` shows that `main` tracks `origin/main`. `feature/x` has no tracking branch (you'd need `git push -u origin feature/x` to set one).

---

## 5.10 Pushing and Pulling Tags

Tags (covered in Chapter 8) need explicit pushing:

```bash
git push origin v1.0          # push one tag
git push origin --tags         # push all tags
```

`git pull` does not pull tags by default in older Git versions; modern Git (2.20+) does. To be safe:

```bash
git fetch --tags
```

---

## 5.11 Your Turn

1. Create a new repo on GitHub called `my-first-repo` (or use `gh repo create`).

2. Connect your local `git-practice` repo from earlier chapters to it:

   ```bash
   git remote add origin git@github.com:yourname/my-first-repo.git
   git branch -M main     # ensure branch is called "main" (in case it was "master")
   git push -u origin main
   ```

3. Open the repo on github.com. Verify you can see all your commits and files.

4. On github.com, click the pencil icon on `README.md`, add a line, and commit the change directly on GitHub.

5. Back in your terminal:

   ```bash
   git fetch
   git log origin/main --oneline -3      # see the new commit on the remote
   git diff main origin/main             # see what changed
   git pull                              # merge it into your local main
   ```

6. Make a new commit locally and push it. Verify on github.com that it appears.

7. Try to push when there's an upstream change. Edit `README.md` on github.com, then locally edit a different line, commit, and `git push`. You should get the "rejected" error. Run `git pull` then `git push` to resolve.

8. Clone your own repo into a *different* folder (simulating a second machine):

   ```bash
   cd ..
   git clone git@github.com:yourname/my-first-repo.git my-first-repo-copy
   cd my-first-repo-copy
   git log --oneline     # confirm you have full history
   ```

9. Make a commit in the copy, push it, switch back to the original, and pull. Now both copies are in sync — you've simulated working from two machines.

If all 9 steps worked, your local repo and GitHub are wired up correctly. Chapter 6 teaches you the professional collaboration workflow: issues, pull requests, code review.

**Next up: Chapter 6 — The GitHub Collaboration Workflow.**

---
---


# Chapter 6 — The GitHub Collaboration Workflow

> **Goal of this chapter:** Master the social side of Git — issues, pull requests, code reviews, branch protection. By the end, you can collaborate on a project with a team or contribute to open source.

Git is the engine; this chapter is the steering wheel. Most professional Git work is not "commit and push" — it's "open an issue, branch, push, open a PR, get reviewed, address feedback, merge". This is the loop.

---

## 6.1 The Golden Loop

Almost all collaborative Git work follows this pattern:

```
  ┌──────────────────────────────────────────────────────────┐
  │                                                          │
  │   1. Open an issue (describe what needs to be done)       │
  │                  ↓                                       │
  │   2. Create a branch off main                            │
  │                  ↓                                       │
  │   3. Make commits on the branch                          │
  │                  ↓                                       │
  │   4. Push the branch to your fork (or origin)            │
  │                  ↓                                       │
  │   5. Open a pull request                                 │
  │                  ↓                                       │
  │   6. Code review: address feedback with more commits     │
  │                  ↓                                       │
  │   7. CI runs tests automatically                          │
  │                  ↓                                       │
  │   8. Merge the PR into main                              │
  │                  ↓                                       │
  │   9. Delete the branch                                   │
  │                  ↓                                       │
  │  10. Close the issue (auto-closed if PR says "closes #N")│
  │                                                          │
  └──────────────────────────────────────────────────────────┘
```

We'll walk through each step.

---

## 6.2 Issues: Your Project's To-Do List

An **issue** is a thread on github.com for tracking anything: a bug, a feature request, a question, a discussion.

### Opening an issue

1. Go to your repo on github.com → **Issues** tab → **New issue**.
2. **Title:** one-line summary ("Login button doesn't work on Safari").
3. **Body:** describe what happened, what you expected, steps to reproduce, screenshots.
4. Labels (if any): `bug`, `enhancement`, `good first issue`, etc.
5. **Submit new issue**.

GitHub assigns it a number (e.g. `#42`). You can reference it from commits and PRs.

### Issue templates

Many repos have issue templates — pre-filled forms for bug reports, feature requests, etc. They live in `.github/ISSUE_TEMPLATE/`. To create one for your repo:

```bash
mkdir -p .github/ISSUE_TEMPLATE
cat > .github/ISSUE_TEMPLATE/bug-report.md << 'EOF'
---
name: Bug report
about: Report a bug
title: "[BUG] "
labels: bug
assignees: ''
---

## Describe the bug
A clear description of what the bug is.

## To reproduce
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '...'
3. See error

## Expected behavior
What you expected to happen.

## Screenshots
If applicable, add screenshots.

## Environment
 - OS: [e.g. macOS 14]
 - Browser: [e.g. Chrome 118]
 - Version: [e.g. 1.2.3]
EOF
```

Now when someone opens an issue, they'll see this template.

### From the CLI

```bash
gh issue create --title "Login button broken on Safari" --body "Steps: ..."
gh issue list
gh issue view 42
gh issue close 42
```

---

## 6.3 Pull Requests in Depth

A **pull request** (PR) is a proposal: "please merge my branch into yours". It's not a Git concept — it's a GitHub feature. But it's the heart of professional Git collaboration.

### Anatomy of a PR

A PR contains:
- A **source branch** (your feature work).
- A **target branch** (usually `main`).
- A **title** (one-line summary).
- A **description** (what changed, why, how to test).
- A **diff** of all commits.
- A **discussion thread** for review comments.
- **CI checks** (tests run automatically).
- **Reviewers** assigned.
- **Status** (open / merged / closed).

### Opening a PR

After pushing your branch:

#### From the web

GitHub shows a yellow banner: "Compare & pull request". Click it. Fill in title and description, assign reviewers, and **Create pull request**.

#### From the CLI

```bash
gh pr create --title "Add password reset flow" --body "Closes #42"
```

This opens a PR from your current branch to `main` on `origin`. `--body "Closes #42"` auto-closes issue #42 when the PR merges.

### PR description template

A good PR description is a small document. Common structure:

```markdown
## What does this PR do?
Implements the password reset flow end-to-end.

## Why is it needed?
Users currently cannot recover forgotten passwords (issue #42).

## How was it tested?
- Added 12 unit tests covering all branches of `resetPassword()`.
- Manual test: requested reset for `test@example.com`, verified email arrived, clicked link, set new password, logged in successfully.

## Screenshots
![reset-flow](https://example.com/screenshot.png)

## Checklist
- [x] Tests pass
- [x] Code follows style guide
- [x] Documentation updated
- [x] No new linting warnings
```

To make this appear by default for every PR in your repo, add a file `.github/PULL_REQUEST_TEMPLATE.md` with the template content.

### Listing and viewing PRs

```bash
gh pr list                    # open PRs in your repo
gh pr list --state closed     # recently merged/closed
gh pr view 42                 # view PR #42
gh pr view 42 --web           # open it in the browser
gh pr checkout 42             # check out the PR's branch locally (for testing)
gh pr diff 42                 # see the diff
```

---

## 6.4 Code Review

A PR is reviewed by other developers before merging. Their job: catch bugs, suggest improvements, share knowledge, ensure the code fits the project.

### Commenting on a PR

On the github.com PR page:
- **Files changed** tab shows the diff line-by-line.
- Hover any line → **+** icon → add an inline comment.
- Comments can be **single** (just a note) or part of a **review**.

### Submitting a review

A reviewer submits one of:
- **Comment** — feedback without blocking merge.
- **Approve** — looks good, merge it.
- **Request changes** — must be addressed before merging.

### Addressing feedback

When a reviewer asks for changes:
1. Checkout the PR's branch locally (or use `gh pr checkout 42`).
2. Make the requested changes.
3. Commit and push to the same branch.

```bash
git switch feature/password-reset
# ... edit, address feedback ...
git add .
git commit -m "Address review feedback: extract validation logic"
git push
```

The PR automatically updates with your new commits. The reviewer re-reviews.

### Merge, squash, or rebase?

When merging a PR, GitHub offers three strategies:

| Strategy | What it does | When to use |
|---|---|---|
| **Merge commit** | Creates a merge commit joining your branch into main. Preserves all individual commits. | When commits are meaningful and well-organised. |
| **Squash and merge** | Combines all your commits into one new commit on main. | When your branch has many tiny "fix typo" / "address feedback" commits you don't want in main's history. |
| **Rebase and merge** | Replays your commits onto main without a merge commit. Linear history. | When you want a clean, linear history and your commits are well-organised. |

For most projects: **squash and merge** is the most beginner-friendly default.

---

## 6.5 Contributing to Someone Else's Repository

To contribute to a repo you don't have write access to (e.g. open source):

### Step 1: Fork on github.com

Go to the repo → **Fork** (top right). GitHub creates a copy under your account: `yourname/their-repo`.

### Step 2: Clone your fork

```bash
git clone git@github.com:yourname/their-repo.git
cd their-repo
```

### Step 3: Add the original as `upstream`

```bash
git remote add upstream https://github.com:original-owner/their-repo.git
git remote -v
```

Output:

```text
origin    git@github.com:yourname/their-repo.git (fetch)
origin    git@github.com:yourname/their-repo.git (push)
upstream  https://github.com:original-owner/their-repo.git (fetch)
upstream  https://github.com:original-owner/their-repo.git (push)
```

You push to `origin` (your fork). You pull from `upstream` (the original) to stay in sync.

### Step 4: Keep your fork current

Periodically:

```bash
git switch main
git fetch upstream
git merge upstream/main       # or: git rebase upstream/main
git push origin main          # update your fork on github.com
```

### Step 5: Branch, commit, push to your fork

```bash
git switch -c docs/improve-readme
# ... edit README ...
git commit -am "Improve README installation section"
git push -u origin docs/improve-readme
```

### Step 6: Open the PR on github.com

Go to your fork on github.com → **Compare & pull request**.

**Critical detail:** check the base and head at the top of the PR form:
- **base repository:** `original-owner/their-repo`
- **base:** `main`
- **head repository:** `yourname/their-repo`
- **compare:** `docs/improve-readme`

This means: "merge from my fork's `docs/improve-readme` branch into the original repo's `main`".

### Step 7: Address feedback

If reviewers ask for changes, push more commits to the same branch:

```bash
git switch docs/improve-readme
# ... edit ...
git commit -am "Address review feedback"
git push
```

The PR updates automatically. No need to open a new one.

---

## 6.6 Keeping a Fork Up to Date

After you've had a fork for a while, it falls behind the original. To sync:

```bash
git switch main
git fetch upstream
git merge upstream/main
git push origin main
```

Or with `gh`:

```bash
gh repo sync yourname/their-repo --source original-owner/their-repo
```

---

## 6.7 Code Review Etiquette

Code review is a social activity. Some norms:

### For reviewers

- **Be kind.** Comment on the code, not the person. "This could be simplified by…" not "Why did you do this?".
- **Be specific.** Vague: "this is bad". Useful: "this loop is O(n²); using a Set for `seen` would make it O(n)".
- **Distinguish must-fix from nice-to-have.** Use prefixes: `[must]`, `[nit]`, `[question]`, `[praise]`.
- **Praise good code.** Especially from juniors. A `praise` comment boosts morale.
- **Ask, don't tell.** "Have you considered using X?" instead of "Use X".
- **Approve promptly when ready.** Don't block merges with optional nits.

### For authors

- **Self-review before requesting reviewers.** Read your own diff. Catch the obvious stuff first.
- **Write a good PR description.** Reviewers shouldn't have to guess your intent.
- **Keep PRs small.** A 50-line PR gets reviewed in 5 minutes. A 500-line PR sits for days.
- **Respond to every comment.** Either fix it, push back politely, or mark as "will do in a follow-up".
- **Don't take feedback personally.** Reviewers are improving the code, not attacking you.

---

## 6.8 Protecting Branches and Team Settings

To prevent accidents, GitHub lets you **protect branches**. Common rules:
- Disallow direct pushes to `main` (force PRs).
- Require PR reviews before merge (e.g. at least 1 approval).
- Require CI to pass before merge.
- Disallow force-pushes.
- Require linear history (no merge commits).

### Setting up a branch protection rule

1. Repo → **Settings** → **Branches** → **Add branch protection rule**.
2. **Branch name pattern:** `main`.
3. Tick:
   - **Require a pull request before merging** (set required approvals to 1 or 2).
   - **Require status checks to pass** (pick your CI workflow).
   - **Require branches to be up to date before merging**.
   - **Do not allow bypassing the above settings**.
4. **Create**.

Now nobody — not even you, the repo owner — can push directly to `main`. All changes go through PRs.

### From the CLI

```bash
gh api -X PUT repos/yourname/repo/branches/main/protection \
  -F required_pull_request_reviews.required_approving_review_count=1 \
  -F required_pull_request_reviews.dismiss_stale_reviews=true \
  -F enforce_admins=false \
  -F restrictions= \
  -F required_linear_history=true
```

The CLI is powerful but verbose; the web UI is usually easier.

---

## 6.9 GitHub Pages: A Free Website From Your Repo

GitHub Pages is a free static-site hosting service. It serves files from a repo as a website at `https://yourname.github.io/repo-name/`.

### Quick setup

1. Repo → **Settings** → **Pages**.
2. **Source:** Deploy from a branch.
3. **Branch:** `main` / `/(root)` → **Save**.
4. Wait ~1 minute.
5. Visit `https://yourname.github.io/repo-name/`.

If you have an `index.html` in your repo root, it's served as the homepage.

### Personal site

Every GitHub account gets one personal site at `https://yourname.github.io/`. Create a repo named **exactly** `yourname.github.io` and push an `index.html`:

```bash
git clone git@github.com:yourname/yourname.github.io.git
cd yourname.github.io
echo "<h1>Hello, world!</h1>" > index.html
git add index.html
git commit -m "Initial homepage"
git push
```

Visit `https://yourname.github.io/` in a minute.

---

## 6.10 Your Turn

This is the most important exercise in the guide. You will simulate the full collaboration loop end-to-end.

1. Create a new repo on github.com called `pr-practice`.

2. Clone it locally:

   ```bash
   git clone git@github.com:yourname/pr-practice.git
   cd pr-practice
   ```

3. Create an `index.html` with basic HTML. Commit and push to `main`.

4. On github.com, **open an issue**: "Add an About section" — describe what you want.

5. Locally, **create a branch** `feature/about-section`. Add an `<section id="about">` to `index.html`. Commit.

6. Push the branch: `git push -u origin feature/about-section`.

7. On github.com, **open a pull request** from `feature/about-section` → `main`. In the description, write `Closes #1` (assuming the issue is #1).

8. **Self-review your diff.** Read every line. Imagine you're a reviewer who didn't write it.

9. **Merge the PR** (using "Squash and merge" if available).

10. On github.com, verify the issue was **auto-closed** by the merge.

11. Locally:

    ```bash
    git switch main
    git pull
    git branch -d feature/about-section      # delete the local branch
    ```

12. (Optional) On github.com, set up branch protection on `main` requiring a PR. Try to push directly to `main` — you should be blocked.

13. (Optional) Create a second PR to add a CSS file. This time, **request a review from yourself** (or a friend) before merging. Add a review comment on a specific line of the diff.

If you completed all 13 steps, you have done the full professional Git/GitHub workflow that engineers do every day. You can collaborate.

**Next up: Chapter 7 — Undoing Things and Disaster Recovery.** Even pros make mistakes. This chapter shows you how to undo them — sometimes hours later, sometimes after pushing — without losing work.

---
---


# Chapter 7 — Undoing Things and Disaster Recovery

> **Goal of this chapter:** Recover from any mistake — without losing work. Unstage changes, discard changes, undo commits, undo merges, recover "deleted" branches, fix a force-push disaster. By the end, Git errors will make you calm, not panicked.

The single most important fact in Git: **almost nothing is ever truly lost.** Commits live in `.git/objects/` until garbage collection runs (default: 30 days after they become unreferenced). The reflog records every place `HEAD` has been. This chapter is your toolkit for getting back anything.

---

## 7.1 The Safety-Net Mindset

Before we start, internalize this:

1. **Calm down.** The data is almost certainly still there.
2. **Stop typing destructive commands.** Don't `rm -rf`, don't `git reset --hard` blindly. Think first.
3. **Check the reflog.** `git reflog` shows every place `HEAD` has been. Your "lost" commit is probably there.
4. **Commit before you fix.** If you have changes in your working directory that you might lose, `git stash` them first (section 7.7).

---

## 7.2 Unstaging: `git restore --staged`

You `git add`-ed a file you didn't mean to stage. You want to remove it from the staging area but keep the changes in your working directory.

```bash
git restore --staged README.md
# older equivalent (still works):
git reset HEAD README.md
```

`--staged` says "restore from `HEAD` to the staging area" — meaning, make the staging area match what's already committed. Your working-directory changes are untouched.

For all staged files at once:

```bash
git restore --staged .
```

---

## 7.3 Discarding Local Changes: `git restore`

You made changes to `README.md`, decided you hate them, and want the file back to its last-committed state.

```bash
git restore README.md
# older equivalent (still works):
git checkout -- README.md
```

**Warning:** this discards your uncommitted changes permanently. There's no undo for working-directory changes that were never staged or committed.

To discard all changes in the working directory:

```bash
git restore .
```

---

## 7.4 `git reset`: Soft, Mixed, Hard

`git reset` moves the current branch pointer to a different commit. It has three modes that differ in what they do to the staging area and working directory.

```
                          Staging area    Working directory
                          ─────────────    ─────────────────
git reset --soft  HEAD~1  unchanged       unchanged
git reset         HEAD~1  reset           unchanged
git reset --hard  HEAD~1  reset           reset
```

### Setup

Let's say `main` has three commits: C1 → C2 → C3. You're on `main` and `HEAD` is at C3.

```
(C1) ── (C2) ── (C3)   ← main, HEAD
```

### `git reset --soft HEAD~1`

Moves `main` back one commit (to C2), but the staging area and working directory are untouched.

```
(C1) ── (C2)   ← main, HEAD
            └── (C3)   ← still in staging, "as if you just committed"
```

**Use case:** you committed too early and want to amend the commit (combine more changes into it):

```bash
git reset --soft HEAD~1
# make more changes, stage them
git commit -m "Updated message"
```

### `git reset HEAD~1` (default mode: "mixed")

Moves `main` back to C2 and **unstages** changes (they're now back in the working directory).

```
(C1) ── (C2)   ← main, HEAD
            └── (C3)   ← still in working directory, unstaged
```

**Use case:** you committed the wrong files and want to re-stage them differently:

```bash
git reset HEAD~1
git add specific-file.txt
git commit -m "Better message"
```

### `git reset --hard HEAD~1`

Moves `main` back to C2 and **discards** all changes in both staging and working directory.

```
(C1) ── (C2)   ← main, HEAD
            (C3)   ← gone from working directory AND staging
                    (but still in .git/objects until gc runs — see section 7.8)
```

**Use case:** you really want to throw away the last commit and its changes:

```bash
git reset --hard HEAD~1
```

**⚠ Warning:** `--hard` is the only `reset` mode that loses data from the working directory. Use it carefully. If you have uncommitted changes you want to keep, `git stash` first.

---

## 7.5 `git revert`: The Safe Undo

`git reset` rewrites history. If you've already pushed the commit you want to "undo", rewriting history means **force-pushing**, which breaks everyone else's repo. The safe alternative is `git revert`, which creates a *new* commit that undoes an older one.

```bash
git revert <commit-hash>
```

Example:

```
(C1) ── (C2) ── (C3) ── (C4 revert of C2)   ← main
```

`C4` is a new commit that does the *opposite* of `C2`. The history is preserved; nothing is rewritten. Safe to push.

Reading the output:

```bash
git revert a1b2c3d
```

```text
[main 7d8e9f0] Revert "Add broken feature"
 1 file changed, 1 deletion(-)
 create mode 100644 some-file.txt
```

For reverting a merge commit:

```bash
git revert -m 1 <merge-commit-hash>
```

`-m 1` tells Git which parent to keep (parent 1 = the branch you merged into).

---

## 7.6 `reset` vs `revert`: Which One When?

| Situation | Use |
|---|---|
| You committed locally, haven't pushed, want to undo | `git reset` (rewrites only your local history) |
| You committed and pushed, want to undo for everyone | `git revert` (adds an undo commit; safe to push) |
| You want to undo multiple commits and combine them into one | `git reset --soft` then recommit |
| You want to throw away uncommitted changes in working directory | `git restore .` (not reset) |
| You want to test an old commit, then come back | `git checkout <hash>` (detached HEAD), then `git switch main` |

Rule of thumb: **if it's been pushed, revert. If it hasn't, reset.**

---

## 7.7 `git stash`: Shelving Work in Progress

You're halfway through a feature when an urgent bug comes in. You don't want to commit half-done work, but you can't switch branches with uncommitted changes either.

`git stash` saves your uncommitted changes to a temporary shelf and reverts your working directory to `HEAD`.

```bash
git stash
```

Output:

```text
Saved working directory and index state WIP on main: 9fceb52 Initial commit
```

Your working directory is now clean. Switch branches, fix the bug, switch back.

### Listing stashes

```bash
git stash list
```

Output:

```text
stash@{0}: WIP on main: 9fceb52 Initial commit
stash@{1}: WIP on feature/x: 4d2c1ab Add footer
```

### Viewing a stash

```bash
git stash show -p stash@{0}      # -p for patch (diff)
```

### Applying a stash

```bash
git stash apply                  # apply the most recent stash (stash@{0})
git stash apply stash@{1}        # apply a specific stash
```

`apply` keeps the stash on the shelf. To apply *and* remove:

```bash
git stash pop                    # apply stash@{0} and drop it
```

### Dropping a stash

```bash
git stash drop stash@{0}         # remove one
git stash clear                  # remove all (careful!)
```

### Stashing untracked files

By default, `git stash` ignores untracked (new) files. Include them with:

```bash
git stash -u                     # include untracked files
git stash -a                     # include untracked AND ignored files
```

### Stashing with a message

```bash
git stash push -m "wip: hero animation"
```

Makes `git stash list` more readable.

---

## 7.8 `git reflog`: The Time Machine

The **reflog** records every place `HEAD` and other refs have been. It's local (not pushed), and expires after 30–90 days. This is your ultimate safety net.

```bash
git reflog
```

Sample output:

```text
4d2c1ab HEAD@{0}: commit: Add hello-world entry point
a1b2c3d HEAD@{1}: reset: moving to HEAD~1
9fceb52 HEAD@{2}: commit: Add project description to README
5f6a7b8 HEAD@{3}: commit (initial): Initial commit: add README
```

Each entry is a snapshot of where `HEAD` was at one point in time.

### Recovering a "lost" commit

Suppose you `git reset --hard HEAD~1` and then realised you actually wanted to keep that commit:

```bash
git reflog
# 4d2c1ab HEAD@{0}: reset: moving to HEAD~1
# 9fceb52 HEAD@{1}: commit: Add hello-world entry point   ← I want this back
```

```bash
git reset --hard 9fceb52
# or equivalently:
git reset --hard HEAD@{1}
```

`HEAD@{1}` is shorthand for "the reflog entry at index 1" — one operation ago.

### Recovering a deleted branch

```bash
git branch deleted-branch 9fceb52      # recreate branch at this commit
# or:
git switch -b recovered-branch HEAD@{2}
```

---

## 7.9 Cleaning Untracked Files: `git clean`

`git clean` removes untracked files (those not yet added to Git). Use carefully — there's no undo.

```bash
git clean -n          # dry run: shows what would be deleted, deletes nothing
git clean -f          # force: actually delete untracked files
git clean -fd         # also delete untracked directories
git clean -fdx        # also delete ignored files (e.g. node_modules, dist/)
```

**Always run `-n` (dry run) first.** Read the list of files. Confirm none are precious. Then run `-f`.

---

## 7.10 `git cherry-pick`

`git cherry-pick` takes a commit from one branch and applies it as a new commit on your current branch.

```bash
git switch main
git cherry-pick a1b2c3d      # apply commit a1b2c3d onto main
```

Use cases:
- A bug fix on `develop` that you also need on `main` (backporting).
- A single useful commit on a branch you otherwise don't want to merge.
- Applying someone else's commit to your branch.

Cherry-picking multiple commits:

```bash
git cherry-pick a1b2c3d 4d2c1ab 9fceb52     # three commits, in order
git cherry-pick a1b2c3d..4d2c1ab            # range (exclusive of a1b2c3d, inclusive of 4d2c1ab)
```

If a conflict occurs, resolve as usual, then:

```bash
git add .
git cherry-pick --continue
# or:
git cherry-pick --abort       # give up
```

---

## 7.11 The Emergency Recovery Table

| Situation | Command |
|---|---|
| I staged a file I didn't mean to | `git restore --staged <file>` |
| I want to discard uncommitted changes | `git restore <file>` (or `git restore .` for all) |
| I committed too early, want to add more | `git reset --soft HEAD~1` then edit + add + commit |
| I committed and want to undo locally | `git reset HEAD~1` (mixed) or `--hard` to also discard changes |
| I committed and pushed, want to undo safely | `git revert <commit-hash>` then `git push` |
| I want to undo the last commit but keep changes | `git reset --soft HEAD~1` |
| I lost uncommitted work after `git stash` | `git stash list` then `git stash apply stash@{0}` |
| I deleted a branch by mistake | `git reflog` to find the hash, then `git branch <name> <hash>` |
| I `reset --hard` and lost commits | `git reflog` to find hash, then `git reset --hard <hash>` |
| I `reset --hard` AND ran `git gc --prune=now` | Likely gone. Restore from backup or remote. |
| I force-pushed and overwrote remote commits | GitHub staff can sometimes recover via support ticket; otherwise gone. |
| I committed a secret (password, key) | Use BFG Repo-Cleaner or `git filter-repo`, then force-push. **Rotate the secret immediately** regardless. |
| My repo is corrupted (`git fsck` reports errors) | `git fsck --full`; if salvageable, fix objects; otherwise `git clone` fresh from remote. |
| I'm in detached HEAD and made commits | `git branch save-my-work` then `git switch main` |
| I merged the wrong branch | `git reset --hard HEAD~1` (if not pushed) or `git revert -m 1 <merge-hash>` (if pushed) |
| I want to swap my last two commits | `git rebase -i HEAD~2` and reorder |

---

## 7.12 Removing a Secret from History

If you accidentally committed a password, simply removing it in a new commit is **not enough** — the secret is still in the old commit's diff, forever accessible via `git log -p`.

The standard tool for rewriting history to remove secrets is **`git filter-repo`** (modern replacement for BFG Repo-Cleaner and `git filter-branch`).

```bash
# Install
pip install git-filter-repo

# Remove a specific file from all of history
git filter-repo --path secrets.env --invert-paths

# Remove all instances of a string from all files in history
echo "MY_PASSWORD=hunter2" > passwords.txt
git filter-repo --replace-text passwords.txt
```

After rewriting, force-push:

```bash
git push --force
```

**Then rotate the secret.** Assume it's compromised; rewriting history doesn't help if someone already cloned your repo.

---

## 7.13 `git fsck`: File System Check

`git fsck` verifies the integrity of your `.git/` directory:

```bash
git fsck
```

Sample clean output:

```text
Checking object directories: 100% (256/256), done.
```

If there are errors, you'll see `missing blob`, `dangling commit`, etc. Dangling commits are usually old, unreferenced commits — they're fine (they'll be GC'd eventually) but they're also what you'd want to look at if you lost something.

---

## 7.14 Your Turn

Practice recovering from disasters in a sandbox. **Use a throwaway repo** — do these in `git-practice` only after backing up.

1. Make 5 commits. Run `git reset --hard HEAD~2`. Confirm your last 2 commits are gone from `git log`. Then use `git reflog` and `git reset --hard HEAD@{2}` to recover them.

2. Stage a file, then unstage it without losing the working-directory changes: `git restore --staged`.

3. Make changes to a file. Run `git stash`. Confirm working directory is clean. Run `git stash pop`. Confirm your changes are back.

4. Make 3 commits and push them. Then `git revert HEAD~1` to undo the middle one. Push. Verify on github.com that the revert appears as a new commit, not a rewrite.

5. Create a branch `feature/will-delete`, commit on it, switch back to main, and delete the branch with `git branch -D feature/will-delete`. Recover it using `git reflog` + `git branch`.

6. (Caution: use a sandbox repo.) Make a commit containing a "secret" (just text). Then use `git filter-repo --path secrets.txt --invert-paths` to remove it from history. Verify with `git log -p` that the secret is gone.

7. Run `git fsck` on your repo. It should report no errors.

If you can confidently recover from each scenario above, Git disasters no longer scare you. The remaining chapters add power tools.

**Next up: Chapter 8 — Intermediate to Advanced Git.** Rebase, interactive rebase, hooks, submodules, bisect, blame — the tools that separate casual users from Git experts.

---
---


# Chapter 8 — Intermediate to Advanced Git

> **Goal of this chapter:** Master rebase, interactive rebase, tags, aliases, blame, bisect, submodules, worktrees, hooks, line endings, and safe history rewriting. These are the tools that separate "uses Git" from "expert with Git".

This chapter is denser than the previous ones. Take your time. Try every command.

---

## 8.1 `git rebase`

`git rebase` is alternative to `git merge` for combining branches. It "replays" your commits on top of another branch, producing a linear history.

### The scenario

You branched off `main` to make `feature/x`. While you worked, `main` moved forward. You want to update `feature/x` to include `main`'s latest commits.

```
Before rebase:
       (C1) ── (C2) ── (C3) ── (C4)              ← main
                          │
                          └── (C5) ── (C6)         ← feature/x

After `git rebase main` on feature/x:
       (C1) ── (C2) ── (C3) ── (C4)              ← main
                                     │
                                     └── (C5') ── (C6')   ← feature/x
```

Notice `C5'` and `C6'` — these are **new commits** with new hashes, even though the changes are the same as `C5` and `C6`. The originals (`C5`, `C6`) still exist in `.git/objects/` (recoverable via reflog) but are no longer on `feature/x`.

### Running a rebase

```bash
git switch feature/x
git rebase main
```

Git replays each commit on `feature/x` on top of `main`. If a commit applies cleanly, great. If it conflicts:

```text
CONFLICT (content): Merge conflict in some-file.txt
error: could not apply 4d2c1ab...
```

Resolve the conflict (just like a merge conflict), then:

```bash
git add some-file.txt
git rebase --continue
```

Or abort:

```bash
git rebase --abort
```

Or skip the conflicting commit:

```bash
git rebase --skip
```

---

## 8.2 The Golden Rule of Rebase

**Never rebase commits that have been pushed and shared with others.**

Rebase creates new commit hashes. If you've pushed `feature/x` and a teammate has based work on it, rebasing `feature/x` rewrites history — your teammate's repo is now broken.

The rule:
- **Public branches (`main`, `develop`)**: never rebase. Always merge.
- **Private branches (your own feature branches that nobody else uses)**: rebase freely.

If you must rewrite a pushed branch, communicate with everyone who has it first.

---

## 8.3 Interactive Rebase: Rewriting History

`git rebase -i` lets you edit the commit history of your branch. You can:
- **Reorder** commits.
- **Squash** multiple commits into one.
- **Reword** commit messages.
- **Edit** the contents of an old commit.
- **Drop** commits you don't want.

### Starting an interactive rebase

```bash
git rebase -i HEAD~3
```

This opens your editor with the last 3 commits:

```text
pick 9fceb52 Add hello-world entry point
pick 4d2c1ab Add project description to README
pick a1b2c3d Fix typo in README

# Rebase commands:
# p, pick   = use commit
# r, reword = use commit, but edit the commit message
# e, edit   = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup  = like "squash", but discard this commit's log message
# x, exec   = run command using shell
# d, drop   = remove commit
#
# These lines can be re-ordered; they are executed top-to-bottom.
```

### Common use cases

**Squash the bottom commit into the top one:**

Change:
```text
pick 9fceb52 Add hello-world entry point
pick 4d2c1ab Add project description to README
pick a1b2c3d Fix typo in README
```

To:
```text
pick 9fceb52 Add hello-world entry point
squash 4d2c1ab Add project description to README
pick a1b2c3d Fix typo in README
```

Save and close. Git opens another editor to combine the messages.

**Reword a commit:**

Change `pick` to `reword` (or just `r`):
```text
reword 9fceb52 Add hello-world entry point
pick 4d2c1ab Add project description to README
```

Save, close. Git opens the editor for that commit's message.

**Drop a commit:**

Change `pick` to `drop` (or just delete the line).

**Split a commit:**

Change `pick` to `edit`. Git pauses at that commit. You can then:
```bash
git reset HEAD~             # unstage the commit's changes
# stage them in pieces
git add file1.txt
git commit -m "First part"
git add file2.txt
git commit -m "Second part"
git rebase --continue
```

---

## 8.4 Merge vs Rebase: The Decision

| | Merge | Rebase |
|---|---|---|
| History | Preserves all commits, including merge commits | Linear, no merge commits |
| Conflict resolution | Once, at merge time | Per commit, during rebase |
| Rewrites history? | No | Yes |
| Safe to do after push? | Yes | No (Golden Rule) |
| Best for | Public branches, shared history | Private feature branches before merging |

**Typical pro workflow:**
1. Branch `feature/x` from `main`.
2. As `main` moves, occasionally `git rebase main` on `feature/x` to stay up-to-date.
3. Before opening a PR, `git rebase -i main` to squash/cleanup your commits.
4. Open PR; merge with **squash-and-merge** or **rebase-and-merge**.

Result: clean, linear `main` history where each commit is meaningful.

---

## 8.5 Tags and Releases

A **tag** is a fixed pointer to a specific commit. Used for releases (`v1.0`, `v2.3.7`).

### Lightweight tags

```bash
git tag v1.0
```

Just a 41-byte file pointing to the current commit. No metadata.

### Annotated tags (recommended)

```bash
git tag -a v1.0 -m "Release 1.0: initial public release"
```

Creates a tag object with author, date, and message. Stored in `.git/refs/tags/v1.0`.

### Tagging a specific commit

```bash
git tag -a v0.9 -m "Beta release" 9fceb52
```

### Listing and inspecting tags

```bash
git tag                       # list all tags
git tag -l "v1.*"             # list tags matching pattern
git show v1.0                 # show tag details + the commit it points to
```

### Pushing tags

Tags are NOT pushed by `git push`. Push explicitly:

```bash
git push origin v1.0          # one tag
git push origin --tags        # all tags
```

### Deleting tags

```bash
git tag -d v1.0                       # local
git push origin --delete v1.0         # remote
```

### GitHub Releases

A GitHub **Release** is a tag plus a release page (notes, downloadable binaries). To create:

1. Push the tag to GitHub.
2. Repo → **Releases** → **Draft a new release**.
3. **Choose a tag** (or create one).
4. **Release title:** `v1.0 — Initial release`.
5. **Description:** changelog (you can use `gh` to auto-generate).
6. **Attach binaries** (zip, .deb, .exe, etc.).
7. **Publish release**.

Or via CLI:

```bash
gh release create v1.0 --notes "Initial public release."
gh release create v1.1 --generate-notes      # auto-generate from commits
```

---

## 8.6 Aliases: Build Your Own Shortcuts

If you find yourself typing the same long command, alias it.

### Inline aliases

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.lg "log --oneline --graph --all --decorate"
git config --global alias.last "log -1 HEAD"
git config --global alias.unstage "restore --staged"
```

Now you can type:

```bash
git co main
git lg
git ci -m "Add feature"
git unstage file.txt
```

### Aliases that run shell commands

Prefix with `!`:

```bash
git config --global alias.cleanup '!git branch --merged | grep -v main | xargs git branch -d'
```

Now `git cleanup` deletes all merged branches except `main`.

---

## 8.7 `git blame`: Who Wrote This Line?

`git blame` shows, for each line of a file, which commit last touched it and who wrote it.

```bash
git blame README.md
```

Sample output:

```text
9fceb528 (Aziz Nader 2025-10-05 10:32:14 1) # My First Repo
a1b2c3d4 (Aziz Nader 2025-10-05 10:45:02 2)
a1b2c3d4 (Aziz Nader 2025-10-05 10:45:02 3) This is a project I'm building while learning Git.
```

Reading each line:
- `9fceb528` — commit hash.
- `(Aziz Nader 2025-10-05 10:32:14 1)` — author, date, line number.
- The line content.

Useful flags:

```bash
git blame -L 10,20 README.md      # only lines 10-20
git blame -w README.md             # ignore whitespace changes
git blame -C README.md             # detect lines moved from other files
```

GitHub's web UI shows blame: click **Blame** on any file.

---

## 8.8 `git bisect`: Binary Search for Bugs

`git bisect` finds which commit introduced a bug by binary search. Suppose the latest commit has a bug but `v1.0` (100 commits ago) worked. `bisect` walks you through ~7 commits (log2 of 100) instead of all 100.

### Manual bisect

```bash
git bisect start
git bisect bad                  # mark current commit as buggy
git bisect good v1.0            # mark v1.0 as known-good
```

Git checks out a midpoint:

```text
Bisecting: 50 revisions left to test after this
[abc1234] Some commit message
```

Run your tests. If they pass:

```bash
git bisect good
```

If they fail:

```bash
git bisect bad
```

Git checks out another midpoint. Repeat ~7 times. Eventually:

```text
abc1234 is the first bad commit
```

End the session:

```bash
git bisect reset
```

### Automated bisect

Give bisect a script that returns 0 (good) or non-zero (bad):

```bash
git bisect start HEAD v1.0
git bisect run npm test          # or any test command
```

Git runs the tests, checks out commits, narrows the range automatically, and reports the first bad commit.

---

## 8.9 Searching Your History

### Search commit messages

```bash
git log --grep="password"        # commits with "password" in message
git log --grep="password" -i     # case-insensitive
git log --grep="fix" --author="Aziz"      # combined filters
```

### Search code (in tracked files)

```bash
git grep "TODO"                  # files containing "TODO" in current state
git grep -n "function"           # with line numbers
```

### Search across all history

```bash
git log -S "function foo"       # commits that added/removed the string "function foo"
git log -G "function.*foo"      # commits matching a regex
```

`-S` is "pickaxe" — finds commits where the count of occurrences of a string changed. Perfect for "when was this function added?".

### Who added this line, when, and in which commit?

```bash
git blame -L <line>,<line> <file>
```

Or on github.com, click **Blame** on any file.

---

## 8.10 Submodules

A **submodule** is a Git repo nested inside another Git repo. Useful when your project depends on an external repo that you want to keep separate (not vendor).

### Adding a submodule

```bash
git submodule add https://github.com/owner/external-repo.git libs/external
git commit -m "Add external-repo as a submodule"
```

This adds:
- A clone of `external-repo` at `libs/external`.
- A `.gitmodules` file at the project root recording the mapping.
- A gitlink entry in the index pointing at a specific commit of the submodule.

### Cloning a repo with submodules

```bash
git clone --recurse-submodules https://github.com/you/main-repo.git
```

Without `--recurse-submodules`, the submodule folders are empty. To populate them after the fact:

```bash
git submodule update --init --recursive
```

### Updating a submodule

```bash
cd libs/external
git switch main
git pull
cd ../..
git add libs/external
git commit -m "Update external submodule to latest"
```

### Removing a submodule

```bash
git submodule deinit -f libs/external
rm -rf .git/modules/libs/external
git rm -f libs/external
git commit -m "Remove external submodule"
```

Submodules have a reputation for being fiddly. For many use cases, **package managers** (npm, pip, cargo) are simpler. Use submodules only when you specifically need a separate Git repo nested inside yours.

---

## 8.11 `git worktree`

`git worktree` lets you have **multiple working directories** for the same repository, each checked out to a different branch. Useful when you need to work on two branches simultaneously without cloning twice.

```bash
git worktree add ../project-hotfix hotfix/urgent-bug
```

This creates a new working directory at `../project-hotfix` with the `hotfix/urgent-bug` branch checked out. They share the same `.git/` (so commits in either show up in both immediately).

```bash
cd ../project-hotfix
# ... fix the bug, commit ...
cd ../project
git worktree list
# /Users/you/project          9fceb52 [main]
# /Users/you/project-hotfix   4d2c1ab [hotfix/urgent-bug]

git worktree remove ../project-hotfix      # when done
```

---

## 8.12 Cloning Big Repositories Efficiently

For huge repos (Linux kernel, Chromium), a full clone is multi-GB. Strategies:

### Shallow clone (just the latest commit)

```bash
git clone --depth 1 https://github.com/torvalds/linux.git
```

You get the latest commit only. Saves gigabytes. Cannot see history older than one commit.

### Blobless clone (all commits, file contents fetched on demand)

```bash
git clone --filter=blob:none https://github.com/torvalds/linux.git
```

Downloads all commits and trees but fetches blobs (file contents) only when you check them out. Great for browsing history without downloading every version of every file.

### Treeless clone (even more aggressive)

```bash
git clone --filter=tree:none https://github.com/torvalds/linux.git
```

Only fetches trees when needed. Best for very large repos where you'll only touch a small portion.

### Partial checkout (only certain directories)

```bash
git clone --filter=blob:none --no-checkout https://github.com/torvalds/linux.git
cd linux
git sparse-checkout init --cone
git sparse-checkout set Documentation drivers/gpu
git checkout main
```

You now have only `Documentation/` and `drivers/gpu/` from Linux on disk.

---

## 8.13 Git Hooks

**Hooks** are scripts that Git runs automatically before or after certain events (commit, push, receive, etc.). Stored in `.git/hooks/`.

### Hook types

| Hook | When it runs | Use case |
|---|---|---|
| `pre-commit` | Before a commit is created | Lint, format, run tests |
| `prepare-commit-msg` | After the commit message is prepared | Insert ticket number into message |
| `commit-msg` | After the message is finalized | Validate message format |
| `post-commit` | After commit is created | Notify CI, send slack message |
| `pre-push` | Before pushing | Run tests, prevent pushing to `main` |
| `pre-rebase` | Before rebasing | Stop rebase of public branches |
| `post-merge` | After a merge | Re-install dependencies |

### Example: a pre-commit hook that runs tests

```bash
# .git/hooks/pre-commit
#!/bin/sh
echo "Running tests before commit..."
npm test
if [ $? -ne 0 ]; then
  echo "❌ Tests failed. Commit aborted."
  exit 1
fi
echo "✅ Tests passed."
exit 0
```

Make it executable:

```bash
chmod +x .git/hooks/pre-commit
```

Now every `git commit` runs the tests first. If they fail, the commit is aborted.

### Sharing hooks

`.git/hooks/` is not tracked by Git (it's per-clone). To share hooks with a team, store them in your repo (e.g. `.githooks/`) and configure Git to use that directory:

```bash
git config core.hooksPath .githooks
```

Add this to your setup script (`Makefile`, `package.json` postinstall, README).

### Pre-commit framework (recommended)

The [pre-commit](https://pre-commit.com/) framework manages hooks as code. Define hooks in a YAML file:

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.6.0
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
      - id: check-added-large-files
  - repo: https://github.com/pycqa/black
    rev: 24.3.0
    hooks:
      - id: black
```

Install once:

```bash
pip install pre-commit
pre-commit install
```

Now hooks are versioned, shareable, and reproducible across the team.

---

## 8.14 Line Endings and `.gitattributes`

Different operating systems use different line endings:
- **Unix/Linux/macOS:** `\n` (LF)
- **Windows:** `\r\n` (CRLF)

This causes annoying diffs and the warning `LF will be replaced by CRLF`.

### The `.gitattributes` solution

Create a `.gitattributes` file in your repo root:

```text
* text=auto eol=lf
*.bat text eol=crlf
*.sh text eol=lf
*.png binary
*.jpg binary
```

Reading:
- `* text=auto eol=lf` — for all text files, normalise to LF in the repo (regardless of OS).
- `*.bat text eol=crlf` — Windows batch files use CRLF.
- `*.png binary` — treat as binary, don't touch line endings.

Commit this file once; everyone on the team gets consistent line endings automatically.

---

## 8.15 Pushing Rewritten History Safely

After a `rebase`, `commit --amend`, or interactive rebase, your local branch has different commit hashes than the remote. A normal `git push` is rejected:

```text
! [rejected]    feature/x -> feature/x (non-fast-forward)
```

To push the rewritten history:

```bash
git push --force-with-lease
```

**`--force-with-lease`** is the safe version of `--force`. It only force-pushes if nobody else has pushed commits you don't have. If someone did push, it refuses — protecting you from overwriting their work.

**Avoid plain `git push --force`.** It overwrites unconditionally and can destroy teammates' work. Always prefer `--force-with-lease`.

---

## 8.16 Your Turn

1. In your `git-practice` repo, create a `feature/x` branch. Make 3 commits with deliberately bad messages (`fix`, `update`, `stuff`). Run `git rebase -i HEAD~3` and squash them into one with a clean message.

2. Tag the current commit as `v1.0` (annotated). Push the tag to GitHub. Verify it appears in the **Tags** tab on github.com.

3. Create a GitHub Release for `v1.0` using `gh release create`.

4. Pick a file in your repo. Run `git blame` on it. Identify which commit last touched line 1.

5. Set up `git bisect`: introduce a "bug" (e.g. change a string to "BROKEN") in commit 5 of 10. Use bisect to find which commit introduced the change.

6. Configure the alias `git lg` and use it. Configure `git co`, `git ci`, `git st`.

7. Add a pre-commit hook that runs `git diff --check` (catches trailing whitespace). Test it by trying to commit a file with trailing whitespace — the hook should block the commit.

8. Add a `.gitattributes` file declaring `*.md text eol=lf`. Commit it.

9. Find an old commit of yours that you'd like to "improve". Use `git rebase -i` to reword its message. Force-push with `--force-with-lease`.

If you've done all 9, you're now an advanced Git user. The next chapter takes you into GitHub Actions and CI/CD — automating the boring stuff.

**Next up: Chapter 9 — GitHub Actions: Automation for Everyone.**

---
---


# Chapter 9 — GitHub Actions: Automation for Everyone

> **Goal of this chapter:** Automate everything. Run tests on every push, build artifacts, deploy to production, schedule cron jobs, and more — all with GitHub Actions, GitHub's built-in CI/CD platform.

**GitHub Actions** is a CI/CD platform built into GitHub. You write workflows in YAML files; GitHub runs them on its servers (or yours) when events happen (push, PR, schedule, manual trigger). It's free for public repos (with limits for private).

---

## 9.1 What Is CI/CD?

- **CI (Continuous Integration):** Every push automatically runs tests. Bugs are caught within minutes, not weeks.
- **CD (Continuous Deployment / Delivery):** Every successful CI run can be deployed to staging or production automatically.

Without CI/CD:
- Developer commits broken code → merges to main → bug reaches production → customer reports → days of debugging.

With CI/CD:
- Developer commits broken code → CI runs tests → tests fail → push rejected/PR blocked → developer fixes immediately.

---

## 9.2 Your First Workflow, Line by Line

Workflows live in `.github/workflows/`. Let's create one that runs on every push and prints "Hello, World!".

### Step 1: Create the file

```bash
mkdir -p .github/workflows
```

Create `.github/workflows/hello.yml` with this content:

```yaml
name: Hello World

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  say-hello:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Print greeting
        run: echo "Hello, World! This is my first GitHub Action."
```

### Step 2: Commit and push

```bash
git add .github/workflows/hello.yml
git commit -m "Add hello-world GitHub Actions workflow"
git push
```

### Step 3: Watch it run

On github.com → **Actions** tab. You'll see a run starting. Click into it. After ~30 seconds, it should be green ✅.

### Line-by-line explanation

```yaml
name: Hello World
```
The workflow's display name. Shows up in the Actions UI.

```yaml
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]
```
**Triggers.** This workflow runs on push to `main` and on PRs targeting `main`.

```yaml
jobs:
  say-hello:
```
A workflow has one or more **jobs**. Each job runs in parallel by default. This one is named `say-hello`.

```yaml
    runs-on: ubuntu-latest
```
The runner: a GitHub-hosted Ubuntu VM. Other options: `ubuntu-latest`, `windows-latest`, `macos-latest`, or self-hosted runners.

```yaml
    steps:
      - name: Checkout code
        uses: actions/checkout@v4
```
**Steps** run sequentially within a job. The first uses `actions/checkout@v4` — a pre-built action that clones your repo onto the runner. Without this, your repo isn't on the runner.

```yaml
      - name: Print greeting
        run: echo "Hello, World! This is my first GitHub Action."
```
The `run` directive executes a shell command. You can run any shell command here: `npm test`, `make`, `python script.py`, etc.

---

## 9.3 Secrets: Storing Passwords Safely

Workflows often need credentials: API tokens, deploy keys, database passwords. **Never put them in your code or YAML.** Store them as GitHub **secrets**.

### Adding a secret

1. Repo → **Settings** → **Secrets and variables** → **Actions** → **New repository secret**.
2. **Name:** `API_TOKEN`.
3. **Secret:** the actual value.
4. **Add secret**.

Or via CLI:

```bash
gh secret set API_TOKEN --body "your-secret-value-here"
```

### Using a secret in a workflow

```yaml
name: Use Secret

on: push

jobs:
  use-secret:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Use the secret
        env:
          API_TOKEN: ${{ secrets.API_TOKEN }}
        run: |
          echo "The token starts with: ${API_TOKEN:0:4}..."
          curl -H "Authorization: Bearer $API_TOKEN" https://api.example.com/data
```

The `${{ secrets.API_TOKEN }}` expression injects the secret into the env var. Logs show `***` instead of the value — secrets are masked in output.

### Secret scopes

- **Repository secrets:** only this repo.
- **Environment secrets:** tied to a deployment environment (`staging`, `production`).
- **Organization secrets:** shared across repos in an org.

---

## 9.4 More Workflow Patterns

### Pattern 1: Run tests for a Node.js project

```yaml
name: CI

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [18, 20, 22]
    steps:
      - uses: actions/checkout@v4
      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm ci
      - run: npm run lint
      - run: npm test
      - run: npm run build
```

**`matrix`** runs the job multiple times — once per Node version. If any fails, the workflow fails.

### Pattern 2: Deploy to GitHub Pages

```yaml
name: Deploy to Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
      - run: npm ci
      - run: npm run build
      - uses: actions/upload-pages-artifact@v3
        with:
          path: ./dist

  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment: github-pages
    steps:
      - uses: actions/deploy-pages@v4
```

After this runs, your site is live at `https://yourname.github.io/repo-name/`.

### Pattern 3: Scheduled job (cron)

```yaml
name: Nightly Cleanup

on:
  schedule:
    - cron: '0 2 * * *'   # every day at 02:00 UTC

jobs:
  cleanup:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: ./scripts/cleanup.sh
```

Cron syntax: `minute hour day-of-month month day-of-week`. The `'0 2 * * *'` means minute=0, hour=2, every day, every month, every weekday.

### Pattern 4: Manual trigger

```yaml
name: Manual Deploy

on:
  workflow_dispatch:
    inputs:
      environment:
        description: 'Target environment'
        required: true
        default: 'staging'
        type: choice
        options:
          - staging
          - production

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Deploy
        run: ./deploy.sh ${{ github.event.inputs.environment }}
```

On github.com → **Actions** → choose workflow → **Run workflow** button appears.

### Pattern 5: Cache dependencies

```yaml
      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'npm'
```

Or for Python:

```yaml
      - uses: actions/setup-python@v5
        with:
          python-version: '3.12'
          cache: 'pip'
```

Caching dependencies dramatically speeds up subsequent runs (from minutes to seconds).

---

## 9.5 Workflow Syntax Cheat Sheet

| Key | Purpose |
|---|---|
| `name:` | Workflow display name |
| `on:` | Triggers (push, pull_request, schedule, workflow_dispatch, etc.) |
| `jobs:` | Defines jobs (each runs on its own runner) |
| `runs-on:` | Runner OS (ubuntu-latest, windows-latest, macos-latest) |
| `needs:` | Job dependencies (run after another job) |
| `steps:` | List of steps in a job |
| `uses:` | Run an action (pre-built or from a repo) |
| `with:` | Inputs to an action |
| `run:` | Run a shell command |
| `env:` | Environment variables |
| `if:` | Conditional execution |
| `strategy.matrix:` | Run across multiple configs |
| `permissions:` | Fine-grained token permissions |
| `timeout-minutes:` | Kill job if it runs too long |
| `continue-on-error:` | Don't fail workflow if this step fails |

---

## 9.6 Keeping Your Project Secure

### Code owners

A `CODEOWNERS` file in `.github/` or repo root specifies who reviews changes to which paths:

```text
# .github/CODEOWNERS

# Default owners
*                       @you

# Frontend team owns these
/src/components/        @frontend-team

# Backend team owns these
/src/api/               @backend-team

# Security-critical paths require both teams
/src/api/auth/          @frontend-team @backend-team
```

GitHub automatically requests review from the owners when a PR touches their paths.

### Dependabot

Automatically opens PRs when your dependencies have security vulnerabilities:

1. Repo → **Settings** → **Code security and analysis** → **Dependabot alerts** → Enable.
2. **Dependabot security updates** → Enable.

Create `.github/dependabot.yml` to also get version-update PRs:

```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "weekly"
  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "monthly"
```

---

## 9.7 Releases and Changelogs

Generate release notes automatically from PRs since the last release:

```bash
gh release create v1.1 --generate-notes
```

GitHub scans merged PRs since the previous tag and generates a markdown changelog grouped by labels.

You can customise the template at `.github/release.yml`:

```yaml
changelog:
  categories:
    - title: 🎉 New Features
      labels: [feature, enhancement]
    - title: 🐛 Bug Fixes
      labels: [bug, fix]
    - title: 📚 Documentation
      labels: [documentation]
    - title: ⬆️ Dependencies
      labels: [dependencies]
    - title: Other Changes
      labels: ["*"]
```

---

## 9.8 The GitHub CLI: GitHub From Your Terminal

A recap of useful `gh` commands:

```bash
# Repos
gh repo create <name> --public --source=. --push
gh repo clone owner/repo
gh repo view --web
gh repo fork owner/repo --clone

# Pull requests
gh pr create --title "..." --body "..."
gh pr list
gh pr view 42
gh pr checkout 42
gh pr merge 42 --squash --delete-branch
gh pr diff 42

# Issues
gh issue create --title "..." --body "..."
gh issue list
gh issue view 42
gh issue close 42

# Actions
gh run list
gh run view <run-id>
gh run view <run-id> --log     # full logs
gh run rerun <run-id>

# Releases
gh release create v1.0 --generate-notes
gh release upload v1.0 ./dist/app.zip
gh release download v1.0

# Secrets
gh secret set NAME --body "value"
gh secret list

# Gists
gh gist create file.txt --public
gh gist list
```

---

## 9.9 Gists

A **gist** is a small Git repo on gist.github.com for sharing snippets.

```bash
# Create a gist from a file
gh gist create snippet.py --public --desc "Quick Python snippet"

# From stdin
echo "print('hello')" | gh gist create - --public

# List your gists
gh gist list

# View one
gh gist view <gist-id>
```

Gists are full Git repos — you can `git clone` them, fork them, etc.

---

## 9.10 Your Turn

1. In your `pr-practice` repo, add a workflow at `.github/workflows/ci.yml` that runs `echo "Tests passed"` on every push. Verify on github.com that it runs and turns green.

2. Add a `matrix` strategy to run on Node 18, 20, and 22 (even if you don't have a Node project, this proves the matrix works).

3. Add a manual trigger (`workflow_dispatch`) with an input `environment` (staging or production). Verify the **Run workflow** button appears.

4. Set a repository secret `MY_NAME` to your name. Modify the workflow to print `Hello, ${{ secrets.MY_NAME }}!` (use an `env:` block to inject it). Confirm the value shows as `***` in logs.

5. Create a `CODEOWNERS` file that makes `@you` the owner of everything. Open a PR; GitHub should auto-request you as a reviewer.

6. Tag the latest commit as `v1.0` (annotated), push the tag, then create a GitHub release using `gh release create v1.0 --generate-notes`.

7. Enable Dependabot for your repo (Settings → Code security and analysis). Create `.github/dependabot.yml` for weekly npm updates.

8. (Bonus) Set up a workflow that runs every Monday at 9am UTC and posts an issue titled "Weekly review" in your repo.

If you've done all 8, you have a fully automated repo: tests on every push, releases tagged, security updates flowing in, deployable to Pages if applicable. Welcome to modern software development.

**Next up: Chapter 10 — GUI Clients, Tools & Editor Integrations.** The terminal is powerful but not the only way. We'll cover the best GUI Git clients and IDE integrations.

---
---


# Chapter 10 — GUI Clients, Tools & Editor Integrations

> **Goal of this chapter:** Survey the visual tools available for Git. Not everyone loves the terminal; sometimes a GUI is faster. By the end, you'll know which tool to use for what task.

The terminal is the most powerful way to use Git, but for some tasks — resolving complex merge conflicts, visualising branch graphs, scanning diffs across many files — a GUI wins. This chapter is a quick survey; pick one or two that fit your workflow.

---

## 10.1 Why Use a GUI?

| Task | CLI | GUI |
|---|---|---|
| Single commit | Fast | About the same |
| Single file diff | `git diff file` is fine | GUI shows side-by-side, easier to read |
| Multi-file diff across many commits | Painful | GUI excels |
| Resolving merge conflicts | Edit markers manually | GUI 3-way merge is much faster |
| Branch graph visualisation | ASCII art | Beautiful graph |
| Staging individual lines (`-p`) | Tedious | Click-and-drag |
| Beginners learning | Scary | Approachable |

You don't have to pick a side — pros switch between CLI and GUI constantly.

---

## 10.2 GitHub Desktop

**GitHub Desktop** is GitHub's official, free Git client. Available for Windows and macOS.

- Download: <https://desktop.github.com/>
- Source: <https://github.com/desktop/desktop>

### What it does well

- Friendly for absolute beginners. Visualises the "stage → commit → push" loop clearly.
- One-click integration with GitHub for auth, PRs, forks.
- Shows diffs side-by-side with syntax highlighting.
- Branch list, history graph, and "undo last commit" button.

### Limitations

- macOS/Windows only (no native Linux).
- Lacks power features (rebase, cherry-pick are hidden).
- Not customisable.

**Best for:** Beginners transitioning from "I'm scared of Git" to "I use it daily".

---

## 10.3 Sourcetree

**Sourcetree** is Atlassian's free Git client (Windows, macOS). Older and more feature-rich than GitHub Desktop.

- Download: <https://www.sourcetree.com/>

### What it does well

- Full-featured: rebase, cherry-pick, submodules, interactive rebase all supported.
- Excellent visual diff and merge tool.
- Integrates with Bitbucket and Stash out of the box (works fine with GitHub too).
- Supports Git LFS, Git Flow.

### Limitations

- UI feels dated.
- Requires an Atlassian account to use (free).
- No Linux version.

**Best for:** Mid-level users who want GUI access to power features without learning CLI flags.

---

## 10.4 GitKraken

**GitKraken** is a cross-platform (Windows, macOS, Linux) Git client with a beautiful, modern UI.

- Download: <https://www.gitkraken.com/>

### What it does well

- Best-in-class branch graph visualisation.
- Cross-platform (rare for full-featured GUIs).
- Drag-and-drop for merging, rebasing, cherry-picking.
- Built-in merge conflict resolver.
- Integrates with GitHub, GitLab, Bitbucket, Azure DevOps.

### Limitations

- Free version doesn't allow private repos (must pay for Pro).
- Electron-based; can feel heavy on slow machines.

**Best for:** Visual thinkers; teams standardising on a cross-platform GUI.

---

## 10.5 VS Code Built-in Git

VS Code has Git built in. You may not need a separate GUI.

### What it does well

- Source Control panel (Ctrl+Shift+G): see changed files, stage, commit, all from the editor.
- Inline diff: click any modified file to see side-by-side diff.
- Branch picker in the status bar (bottom-left): switch branches with two clicks.
- 3-way merge UI when conflicts occur: "Accept Current", "Accept Incoming", "Accept Both" buttons appear above each conflict.
- Integrated terminal for CLI commands.

### Recommended extensions

- **GitLens** — supercharges Git in VS Code. Shows blame info inline, hover for commit details, commit search, rebase editor.
- **Git Graph** — visualises the branch graph inside VS Code.
- **GitHub Pull Requests** — manage PRs without leaving the editor.
- **Edit csv / Excel Viewer** — useful for data files.

### Setting up VS Code as your default Git editor and merge tool

```bash
git config --global core.editor "code --wait"
git config --global merge.tool code
git config --global mergetool.code.cmd 'code --wait $MERGED'
```

Now `git commit` (without `-m`) opens VS Code; `git mergetool` opens conflicts in VS Code.

---

## 10.6 JetBrains IDEs (IntelliJ, PyCharm, WebStorm, etc.)

JetBrains IDEs have best-in-class Git integration. The git log view, branch tree, diff viewer, and conflict resolver are all excellent.

### What it does well

- **Git tab (Alt+9):** commit, branch, log, all in one tool window.
- **Annotate (blame):** right-click any file → Git → Show History or Annotate.
- **Branch tree:** visual graph with filters.
- **Conflict resolver:** 3-way merge UI with syntax highlighting.
- **Local history:** separate from Git — JetBrains keeps its own history of file changes, even if you didn't commit.

### Limitations

- Heavyweight (lots of RAM).
- Paid (some are free Community editions).
- Per-language: each IDE is for a specific stack.

---

## 10.7 Other Notable Tools

### CLI enhancements

- **`lazygit`** — terminal UI for Git. Brilliant for keyboard-driven workflows.
- **`tig`** — terminal git history browser. ncurses-based, very fast.
- **`gh`** — GitHub CLI (we've covered this).
- **`gitui`** — Rust-based terminal UI, very fast.

### Diff tools

- **Meld** — cross-platform visual diff and merge tool.
- **Beyond Compare** — premium, very polished.
- **KDiff3** — free, handles 3-way merges well.
- **Delta** — `git diff` beautifier for the terminal. Configure once, every `git diff` is gorgeous.

Install delta:

```bash
brew install git-delta      # macOS
cargo install git-delta     # Linux (with Rust)
```

Then add to `~/.gitconfig`:

```ini
[core]
    pager = delta

[interactive]
    diffFilter = delta --color-only

[delta]
    navigate = true
    side-by-side = true
    line-numbers = true
```

### GitHub-specific tools

- **GitHub Mobile** — iOS/Android app. Review PRs, merge, comment from your phone.
- **GitHub Codespaces** — full VS Code in the browser, backed by a cloud VM. Free tier for small use.
- **GitHub Copilot** — AI pair programmer (paid).
- **Octotree** — browser extension: tree-view sidebar for github.com repos.

---

## 10.8 Choosing Your Stack

| Persona | Recommended stack |
|---|---|
| Absolute beginner | GitHub Desktop + VS Code |
| Mid-level developer | VS Code + GitLens + `gh` CLI |
| Power user | Terminal + `lazygit` + `delta` + VS Code only for editing |
| JetBrains user | Use the IDE's built-in Git, supplement with `gh` CLI |
| Visual thinker | GitKraken or Sourcetree + `gh` CLI |
| Mobile reviewer | GitHub Mobile + VS Code |

There's no "right" answer. Try a few and pick what fits.

---

## 10.9 Your Turn

1. Install **GitHub Desktop** and clone one of your repos through it. Make a commit through the GUI. Verify it appears on github.com.

2. Install **GitLens** in VS Code. Open any tracked file. Hover over a line — you should see a popup showing the commit that last touched it.

3. (Optional) Install **`lazygit`** and try its UI. Press `?` for help. Make a commit through it.

4. (Optional) Install **`delta`** and configure it as your pager. Run `git diff` and `git log -p` — the output should look noticeably better.

5. If you use a JetBrains IDE, open your repo in it. Try the **Git → Annotate** feature on a file. Try resolving a synthetic merge conflict using the IDE's 3-way merge UI.

You don't need to use all these tools. Pick the one that fits your workflow and ignore the rest.

**Next up: Chapter 11 — Best Practices and Conventions.** Git is a tool; how you use it determines whether your project's history is a joy or a nightmare to navigate.

---
---


# Chapter 11 — Best Practices and Conventions

> **Goal of this chapter:** Make your repo's history a joy to navigate, not a nightmare. Master atomic commits, conventional commit messages, PR descriptions, repo housekeeping, and licensing.

A good Git history reads like a story. A bad one reads like a stream of consciousness. This chapter is how to make yours good.

---

## 11.1 Atomic Commits and Small Pull Requests

**Atomic commit:** a commit that does exactly one thing. Adds a feature. Fixes a bug. Renames a function. Not all three.

Why atomic matters:
- **Easier to review.** A 5-line PR is reviewed in 30 seconds. A 500-line PR sits for days.
- **Easier to revert.** If commit X introduced a bug, you can `git revert X` without affecting other work.
- **Easier to bisect.** `git bisect` finds the exact commit that introduced a bug. Atomic commits make this trivial.
- **Easier to understand.** Future-you reading `git log` should understand each commit's purpose without reading the diff.

### The rule of thumb

> If you can describe your commit with "and", it should be two commits.

Bad: `Add login page AND fix typo in README AND update dependencies`.
Good: Three commits — `Add login page`, `Fix typo in README`, `Update dependencies`.

### Same for PRs

A PR should do one thing. If you find yourself writing `Part 1: ...; Part 2: ...` in the description, split into two PRs.

---

## 11.2 Commit Message Conventions

The most widely-adopted standard is **Conventional Commits**:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type | When to use |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, semicolons, whitespace (no code change) |
| `refactor` | Code restructuring, no behaviour change |
| `perf` | Performance improvement |
| `test` | Adding or correcting tests |
| `build` | Build system, dependencies |
| `ci` | CI configuration changes |
| `chore` | Maintenance, no production code change |
| `revert` | Reverting a previous commit |

### Examples

```text
feat(auth): add password reset flow

Implements the forgot-password feature end-to-end:
- New route /password/reset
- Email sending via the existing mailer
- Token expiry after 1 hour
- Tests for happy path and expired token

Closes #42
```

```text
fix(login): redirect to dashboard after login

Previously, successful login kept the user on the login page.
The redirect target was being computed before the session was set,
so it always returned to the login form.

Fixes #87
```

```text
docs(readme): document env vars in README

Adds a table of required environment variables to the README,
including default values and where to find them in production.
```

### Rules

1. **Subject line ≤ 50 characters** (so it fits in `git log --oneline`).
2. **Subject line lowercase, no trailing period.**
3. **Subject in imperative mood**: "Add" not "Added" or "Adds".
4. **Blank line after subject.**
5. **Body wrapped at 72 characters** (so it fits in 80-char terminals with indentation).
6. **Body explains *why*, not what.** The diff shows what.
7. **Footer for issue references:** `Closes #42`, `Fixes #87`, `Refs #100`.

### Auto-generating changelogs

With Conventional Commits, tools can auto-generate changelogs:

- **standard-version** (npm): auto-bump version + changelog from commits.
- **semantic-release** (npm): auto-publish to npm on every merge.
- **release-please** (GitHub Action): Google's PR-based release manager.

---

## 11.3 Pull Request Description Template

A good PR description:

```markdown
## What does this PR do?
Implements the password reset flow end-to-end.

## Why?
Users currently cannot recover forgotten passwords (issue #42).

## How did you test this?
- 12 unit tests covering all branches of `resetPassword()`.
- Manual: requested reset for `test@example.com`, verified email arrived, clicked link, set new password, logged in.

## Screenshots
![reset-flow](https://example.com/screenshot.png)

## Checklist
- [x] Tests pass (`npm test`)
- [x] Lint passes (`npm run lint`)
- [x] Documentation updated
- [x] No new console.log statements
- [x] Self-reviewed my own diff
```

### Auto-fill this template

Add `.github/PULL_REQUEST_TEMPLATE.md` to your repo. GitHub uses it as the default PR description.

---

## 11.4 Repository Housekeeping Files

A professional repo has these files at the root:

```
my-project/
├── .github/
│   ├── PULL_REQUEST_TEMPLATE.md
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug-report.md
│   │   └── feature-request.md
│   ├── workflows/
│   │   └── ci.yml
│   ├── CODEOWNERS
│   └── dependabot.yml
├── .gitignore
├── .gitattributes
├── .editorconfig
├── .env.example              ← template; real .env is gitignored
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
└── SECURITY.md
```

### README.md

The face of your repo. Should answer:
- What is this project?
- Why does it exist?
- How do I install it?
- How do I use it?
- How do I contribute?

Use badges (shields.io) for status, version, license, build.

### LICENSE

Pick one. Most common:

| License | Use when |
|---|---|
| MIT | Permissive. Anyone can use, modify, distribute. Most popular for OSS. |
| Apache 2.0 | Permissive + patent grant. Common for bigger projects. |
| GPL v3 | Copyleft. Derivatives must also be GPL. |
| BSD 2-Clause / 3-Clause | Permissive, similar to MIT. |
| Unlicense | Public domain dedication. |
| Proprietary / All Rights Reserved | For private/commercial code. |

Pick MIT unless you have a specific reason. Get the file from <https://choosealicense.com/>.

### CHANGELOG.md

Manual changelog of releases. Format (Keep a Changelog):

```markdown
# Changelog

## [Unreleased]

## [1.2.0] - 2025-10-05
### Added
- Password reset flow.
### Changed
- Login redirects to dashboard.
### Fixed
- Token expiry edge case.

## [1.1.0] - 2025-09-01
### Added
- Dark mode.
```

### CONTRIBUTING.md

How to contribute: setup steps, PR process, code style, testing requirements. New contributors read this first.

### CODE_OF_CONDUCT.md

Adopt the Contributor Covenant: <https://www.contributor-covenant.org/>. Tells contributors how to behave.

### SECURITY.md

How to report security vulnerabilities: email vs. public issue, response time, scope.

### .editorconfig

Standardise editor behaviour across IDEs:

```ini
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false   # Markdown needs trailing two spaces for line breaks

[Makefile]
indent_style = tab
```

Most editors auto-respect `.editorconfig` (with a plugin if needed).

### .env.example

Template for required environment variables. Real `.env` is gitignored:

```bash
# .env.example
DATABASE_URL=postgres://user:pass@localhost:5432/db
API_KEY=your-api-key-here
PORT=3000
```

New developers copy this to `.env` and fill in real values.

---

## 11.5 Choosing a License

If in doubt, choose MIT. Reasons:

- Short (one page).
- Permissive (anyone can use your code).
- Compatible with almost every other license.
- Recognised worldwide.

For commercial projects where you worry about patents, use Apache 2.0.

If you want derivatives to also be open source, use GPL v3.

You can also add a `LICENSE` file via github.com: when creating a repo, pick from the dropdown. Or download from <https://choosealicense.com/licenses/>.

---

## 11.6 The Top 10 Git Mistakes to Avoid

1. **Committing secrets.** Once a secret is in history, it's hard to remove and must be considered compromised. Use `.gitignore` from day one.

2. **Force-pushing to shared branches.** Always use `--force-with-lease`. Never force-push to `main`.

3. **Committing huge files.** Binaries, videos, datasets bloat the repo forever. Use Git LFS for large files.

4. **Not using branches.** Committing directly to `main` for everything makes history chaotic and prevents safe experimentation.

5. **Bad commit messages.** "fix", "update", "asdf", "wip" tell future-you nothing.

6. **Long-lived feature branches.** A branch open for 3 months accumulates conflicts. Merge or rebase often.

7. **Not reading diffs before committing.** `git diff --staged` takes 5 seconds and catches "I didn't mean to commit that".

8. **Squashing everything into one commit per PR.** Loses meaningful history. Better: rebase -i to clean up, then merge with a clean set of commits.

9. **Ignoring merge conflicts.** Marking them "resolved" by deleting both sides loses work. Read, understand, choose.

10. **Not committing often enough.** Hour-long uncommitted sessions risk loss. Commit every 30–60 minutes when work is in a usable state.

---

## 11.7 Team Conventions Checklist

A good team's repo has:

- [ ] `.gitignore` covering secrets, dependencies, build output, OS junk.
- [ ] `.gitattributes` for line endings.
- [ ] `.editorconfig` for consistent indentation.
- [ ] Branch protection on `main` requiring PR + CI.
- [ ] CI workflow running tests + lint on every PR.
- [ ] `CONTRIBUTING.md` explaining the workflow.
- [ ] `CODE_OF_CONDUCT.md` and `SECURITY.md`.
- [ ] PR template and issue templates.
- [ ] Conventional commit messages (enforced by commitlint if strict).
- [ ] Code owners for sensitive paths.
- [ ] Dependabot enabled.
- [ ] Releases tagged with annotated tags.
- [ ] `CHANGELOG.md` updated per release.
- [ ] License file present and correct.

Print this list and audit your repo. Most repos miss 3-4 of these — fix them this week.

---

## 11.8 Git LFS (Large File Storage)

Git is bad at binaries. A 100MB Photoshop file changing every commit bloats the repo. **Git LFS** stores large files out-of-band, keeping the main repo small.

```bash
# Install (macOS)
brew install git-lfs

# Initialise once per user
git lfs install

# Track certain file types
git lfs track "*.psd"
git lfs track "*.zip"
git lfs track "*.mp4"

# Commit the .gitattributes that LFS created
git add .gitattributes
git commit -m "Configure Git LFS for binaries"

# Now add binaries normally
git add design.psd
git commit -m "Add homepage design"
```

GitHub provides 1 GB free LFS storage + 1 GB/month bandwidth for free accounts.

---

## 11.9 Your Turn

1. Audit your `pr-practice` repo against the **Team Conventions Checklist** above. Add the missing files (`.gitignore`, `.gitattributes`, `.editorconfig`, `LICENSE`, `CHANGELOG.md`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`).

2. Create `.github/PULL_REQUEST_TEMPLATE.md` with the structure from section 11.3. Open a PR and verify the template auto-fills.

3. Configure branch protection on `main` requiring 1 approval + CI.

4. Commit using Conventional Commits format for the next 10 commits. Get into the habit.

5. Add a `CODEOWNERS` file making `@you` the owner of all paths. Verify GitHub requests you as a reviewer on the next PR.

6. Enable Dependabot. Wait a day — you'll likely get a PR bumping some dependency.

7. Tag the current commit as `v1.1.0` (annotated), push the tag, create a release. Update `CHANGELOG.md` to match.

By the end of this checklist, your repo is professional-grade. Recruiters, collaborators, and future-you will thank you.

**Next up: Chapter 12 — Guided Real-World Projects.** Five projects that exercise everything you've learned, end to end.

---
---


# Chapter 12 — Guided Real-World Projects

> **Goal of this chapter:** Build five real projects end-to-end using everything you've learned. Each project is increasingly ambitious. By the end, you will have a portfolio of working Git/GitHub demonstrations.

These projects are designed to exercise specific skills. Do them in order. Each builds on the previous.

---

## 12.1 Project 1 — Portfolio From Zero to a Live Website

**Skills exercised:** repo creation, commits, branches, push, GitHub Pages, PR, release.

### The goal

A personal portfolio website, deployed to GitHub Pages, with a release tagged `v1.0`.

### Step-by-step

1. **Create the repo:**

   ```bash
   gh repo create my-portfolio --public --source=. --remote=origin --push
   ```

2. **Create the basic structure:**

   ```bash
   mkdir my-portfolio
   cd my-portfolio
   ```

   Create `index.html`:

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <title>Your Name — Portfolio</title>
     <link rel="stylesheet" href="style.css">
   </head>
   <body>
     <header>
       <h1>Your Name</h1>
       <p>Software developer. Lifelong learner.</p>
     </header>
     <main>
       <section id="projects">
         <h2>Projects</h2>
         <p>Coming soon.</p>
       </section>
       <section id="about">
         <h2>About</h2>
         <p>I'm learning Git & GitHub from zero to hero.</p>
       </section>
     </main>
     <footer>
       <p>&copy; 2025 Your Name</p>
     </footer>
   </body>
   </html>
   ```

   Create `style.css`:

   ```css
   body {
     font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
     max-width: 720px;
     margin: 2rem auto;
     padding: 0 1rem;
     color: #222;
   }
   h1, h2 { color: #0066cc; }
   ```

3. **Initial commit:**

   ```bash
   git add .
   git commit -m "feat: initial portfolio website"
   ```

4. **Create a `gh-pages` workflow** (or use the simple "deploy from main" approach):

   ```bash
   mkdir -p .github/workflows
   ```

   `.github/workflows/deploy.yml`:

   ```yaml
   name: Deploy to Pages

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
       environment: github-pages
       steps:
         - uses: actions/checkout@v4
         - uses: actions/configure-pages@v4
         - uses: actions/upload-pages-artifact@v3
           with:
             path: .
         - uses: actions/deploy-pages@v4
   ```

5. **Commit and push:**

   ```bash
   git add .github/workflows/deploy.yml
   git commit -m "ci: deploy to GitHub Pages on push to main"
   git push
   ```

6. **Configure Pages:** Settings → Pages → Source = GitHub Actions.

7. **Wait ~1 minute.** Visit `https://yourname.github.io/my-portfolio/`. Your site is live.

8. **Branch off for an improvement:**

   ```bash
   git switch -c feature/about-section
   ```

   Edit `index.html` to expand the About section. Add a `CREDITS.md` file. Commit.

9. **Open a PR:** Push the branch, open a PR on github.com, write a description, request a review (from yourself).

10. **Merge the PR** using squash-and-merge. Delete the branch.

11. **Tag a release:**

    ```bash
    git switch main
    git pull
    git tag -a v1.0 -m "First public release of portfolio"
    git push origin v1.0
    gh release create v1.0 --generate-notes --title "v1.0 — Initial release"
    ```

12. **Verify:** Visit the Releases tab on github.com. Your release is there with auto-generated notes.

### What you've demonstrated

End-to-end: repo setup, branching, PR workflow, CI/CD deployment, releases. This is the foundation of every professional web project.

---

## 12.2 Project 2 — The Full Feature Workflow

**Skills exercised:** issue, branch, commits, PR, review feedback, CI, merge.

### The goal

Open an issue for a missing feature, branch, implement, address review feedback, merge with CI passing.

### Step-by-step

1. **Open an issue** on your portfolio repo: "Add a projects gallery with cards".

2. **Branch locally:**

   ```bash
   git switch -c feature/projects-gallery
   ```

3. **Implement the gallery** in `index.html`:

   ```html
   <section id="projects">
     <h2>Projects</h2>
     <div class="grid">
       <article class="card">
         <h3>Project 1</h3>
         <p>A short description.</p>
       </article>
       <article class="card">
         <h3>Project 2</h3>
         <p>Another project.</p>
       </article>
     </div>
   </section>
   ```

   Add CSS:

   ```css
   .grid {
     display: grid;
     grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
     gap: 1rem;
   }
   .card {
     border: 1px solid #ddd;
     padding: 1rem;
     border-radius: 8px;
   }
   ```

4. **Commit (multiple atomic commits):**

   ```bash
   git add index.html
   git commit -m "feat: add projects gallery section"
   git add style.css
   git commit -m "style: add card grid layout for projects"
   ```

5. **Push and open a PR:**

   ```bash
   git push -u origin feature/projects-gallery
   gh pr create --title "Add projects gallery" --body "Closes #1"
   ```

6. **Self-review.** Read every line of the diff. Leave a comment on the CSS suggesting a hover effect.

7. **Address your own feedback:** Add a hover effect, commit, push.

   ```css
   .card:hover {
     box-shadow: 0 4px 8px rgba(0,0,0,0.1);
     transform: translateY(-2px);
     transition: all 0.2s ease;
   }
   ```

   ```bash
   git add style.css
   git commit -m "feat: add hover effect to project cards"
   git push
   ```

8. **Merge the PR** once CI passes. Verify the issue auto-closed.

9. **Pull the merge locally:**

   ```bash
   git switch main
   git pull
   ```

10. **Verify the live site** at your Pages URL.

### What you've demonstrated

The complete loop: issue → branch → multiple commits → PR → review feedback → amend → CI → merge → auto-close. This is what engineers do every day.

---

## 12.3 Project 3 — Merge Conflict Surgery

**Skills exercised:** branching, conflicting changes, conflict resolution, merge commits.

### The goal

Engineer a controlled merge conflict, resolve it cleanly, understand exactly what happened.

### Step-by-step

1. **In your portfolio repo, edit `index.html` line 1 of the About section:**

   ```bash
   git switch -c conflict-practice
   ```

   Change "I'm learning Git & GitHub from zero to hero." to "I build things with Git & GitHub.".

   ```bash
   git add index.html
   git commit -m "docs: update About section wording"
   ```

2. **Switch back to main and edit the same line differently:**

   ```bash
   git switch main
   ```

   Change "I'm learning Git & GitHub from zero to hero." to "I'm a developer who loves clean Git history.".

   ```bash
   git add index.html
   git commit -m "docs: rewrite About section"
   ```

3. **Try to merge `conflict-practice`:**

   ```bash
   git merge conflict-practice
   ```

   Expected: conflict.

4. **Open `index.html`.** You'll see:

   ```html
   <<<<<<< HEAD
   I'm a developer who loves clean Git history.
   =======
   I build things with Git & GitHub.
   >>>>>>> conflict-practice
   ```

5. **Resolve by combining both ideas:**

   ```html
   I'm a developer who loves clean Git history and builds with Git & GitHub.
   ```

6. **Mark as resolved and commit the merge:**

   ```bash
   git add index.html
   git commit
   ```

7. **Inspect the merge commit:**

   ```bash
   git show HEAD
   ```

   Notice the `Merge: <hash1> <hash2>` line showing both parents.

8. **Push:**

   ```bash
   git push
   ```

9. **Delete the merged branch:**

   ```bash
   git branch -d conflict-practice
   ```

### What you've demonstrated

You can resolve real conflicts calmly and correctly. This is one of the most hireable Git skills.

---

## 12.4 Project 4 — Automation with GitHub Actions

**Skills exercised:** writing workflows, matrix builds, secrets, manual triggers.

### The goal

A repo with multiple workflows: CI on push, scheduled job, manual deploy with secrets.

### Step-by-step

1. **Create a new repo `git-actions-lab`:**

   ```bash
   gh repo create git-actions-lab --public --source=. --remote=origin --push
   ```

2. **Add a CI workflow** (`.github/workflows/ci.yml`):

   ```yaml
   name: CI

   on: [push, pull_request]

   jobs:
     test:
       runs-on: ubuntu-latest
       strategy:
         matrix:
           node-version: [18, 20, 22]
       steps:
         - uses: actions/checkout@v4
         - uses: actions/setup-node@v4
           with:
             node-version: ${{ matrix.node-version }}
             cache: 'npm'
         - run: echo "Running tests on Node ${{ matrix.node-version }}"
         - run: echo "TODO: add real tests"
   ```

3. **Add a scheduled workflow** (`.github/workflows/nightly.yml`):

   ```yaml
   name: Nightly

   on:
     schedule:
       - cron: '0 2 * * *'   # every day at 02:00 UTC
     workflow_dispatch:      # also manually

   jobs:
     nightly:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v4
         - name: Create nightly issue
           env:
             GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
           run: |
             gh issue create \
               --title "Nightly check $(date -u +%Y-%m-%d)" \
               --body "Automated nightly check."
   ```

4. **Add a manual deploy workflow** with a secret (`.github/workflows/deploy.yml`):

   ```yaml
   name: Deploy

   on:
     workflow_dispatch:
       inputs:
         environment:
           description: 'Target environment'
           required: true
           type: choice
           options: [staging, production]

   jobs:
     deploy:
       runs-on: ubuntu-latest
       environment: ${{ github.event.inputs.environment }}
       steps:
         - uses: actions/checkout@v4
         - name: Simulate deploy
           env:
             DEPLOY_TOKEN: ${{ secrets.DEPLOY_TOKEN }}
           run: |
             echo "Deploying to ${{ github.event.inputs.environment }}"
             echo "Using token starting with: ${DEPLOY_TOKEN:0:4}..."
   ```

5. **Set a secret:**

   ```bash
   gh secret set DEPLOY_TOKEN --body "fake-token-12345"
   ```

6. **Commit and push everything:**

   ```bash
   git add .
   git commit -m "ci: add CI, nightly, and deploy workflows"
   git push
   ```

7. **Verify:**
   - CI runs on push. Three jobs (Node 18, 20, 22).
   - On github.com → Actions → "Nightly" → "Run workflow" button. Run it manually; an issue should be created.
   - On github.com → Actions → "Deploy" → "Run workflow". Pick "production". In the logs, the secret shows as `***`.

### What you've demonstrated

You can write real CI/CD pipelines. This is the daily work of DevOps engineers.

---

## 12.5 Project 5 — Your First Open-Source Contribution

**Skills exercised:** fork, clone, upstream, branch, push to fork, PR to upstream.

### The goal

Contribute to an existing open-source project. (We'll use a practice repo, but the workflow is identical for real OSS projects.)

### Step-by-step

1. **Find a practice repo.** GitHub maintains <https://github.com/octocat/Spoon-Knife> as a fork-and-PR practice target. Or use any repo marked `good first issue` at <https://github.com/search?q=label%3A%22good+first+issue%22>.

2. **Fork the repo** on github.com (click **Fork** in the top right). Or via CLI:

   ```bash
   gh repo fork octocat/Spoon-Knife --clone
   cd Spoon-Knife
   ```

3. **Add upstream remote:**

   ```bash
   git remote add upstream https://github.com/octocat/Spoon-Knife.git
   git remote -v
   ```

4. **Sync with upstream:**

   ```bash
   git switch main
   git fetch upstream
   git merge upstream/main
   git push origin main
   ```

5. **Branch:**

   ```bash
   git switch -c docs/improve-readme
   ```

6. **Make a small, meaningful improvement:** fix a typo, add a useful line to the README, improve code comments. Don't change functionality.

7. **Commit:**

   ```bash
   git add README.md
   git commit -m "docs: improve README installation step"
   ```

8. **Push to your fork:**

   ```bash
   git push -u origin docs/improve-readme
   ```

9. **Open a PR upstream:**

   ```bash
   gh pr create \
     --repo octocat/Spoon-Knife \
     --base main \
     --head yourname:docs/improve-readme \
     --title "Docs: improve README installation step" \
     --body "Small clarification in the installation section."
   ```

10. **Wait for review.** This is the part that takes the longest. Maintainers are volunteers; weeks can pass.

11. **Address feedback** if requested: push more commits to the same branch.

12. **Celebrate** when it merges.

### What you've demonstrated

You can contribute to open-source projects following the canonical workflow. This is how thousands of people contribute to Linux, React, Python, VS Code, etc.

---

## 12.6 The Mastery Checklist

Tick each box when you can confidently do it without referring to the guide:

- [ ] Explain what Git is to a non-technical friend.
- [ ] Explain the difference between Git and GitHub.
- [ ] Install and configure Git on a fresh machine in under 10 minutes.
- [ ] Create a repo, commit, push, all from memory.
- [ ] Stage individual lines (`git add -p`).
- [ ] Branch, switch, merge.
- [ ] Resolve a merge conflict calmly.
- [ ] Set up a `.gitignore` and `.gitattributes`.
- [ ] Connect a local repo to GitHub via SSH.
- [ ] Open a PR with a good description.
- [ ] Review someone else's PR with inline comments.
- [ ] Use `git reset` (soft, mixed, hard) appropriately.
- [ ] Use `git revert` for pushed commits.
- [ ] Use `git stash` and `git stash pop`.
- [ ] Recover a "deleted" commit via `git reflog`.
- [ ] Rebase a feature branch onto `main`.
- [ ] Use interactive rebase to squash commits.
- [ ] Tag a release and create a GitHub Release.
- [ ] Write a GitHub Actions workflow.
- [ ] Use a secret in a workflow.
- [ ] Set up branch protection.
- [ ] Fork, clone with upstream, sync.
- [ ] Open a PR to a project you don't own.
- [ ] Configure aliases.
- [ ] Read a `git blame` output and find the commit that introduced a line.
- [ ] Use `git bisect` to find a bug-introducing commit.
- [ ] Audit a repo against the Team Conventions Checklist.
- [ ] Explain the Conventional Commits format.
- [ ] Choose an appropriate open-source license.

If you can tick all of these, **you are no longer a beginner at Git**. You are competent. The remaining chapters are reference material.

**Next up: Chapter 13 — Open-Source Contribution Workflow.** A deeper dive into how to find, evaluate, and contribute to open-source projects professionally.

---
---


# Chapter 13 — Open-Source Contribution Workflow

> **Goal of this chapter:** Contribute to open-source projects professionally. Find issues, read `CONTRIBUTING.md`, follow etiquette, get your PR merged.

Thousands of developers contribute to open-source projects every day. The mechanics are Git + GitHub (which you now know); the social side is what this chapter covers.

---

## 13.1 What Counts as Open Source?

**Open source** means the source code is available under a license that allows anyone to use, modify, and distribute it. Different licenses have different rules:

- **MIT/Apache/BSD** — permissive: anyone can use your code, even commercially.
- **GPL** — copyleft: derivatives must also be GPL.
- **Unlicense** — public domain.

If a repo has a `LICENSE` file with an OSI-approved license, it's open source.

Popular open-source projects you may have used: Linux, React, VS Code, Git itself, Node.js, Python, TensorFlow, Kubernetes, Postgres, WordPress.

---

## 13.2 Why Contribute?

- **Build your portfolio.** A PR merged to a popular project is more impressive than any certificate.
- **Learn from experts.** Code review from experienced maintainers is free mentorship.
- **Fix bugs that annoy you.** Found a bug in a library you use? Fix it.
- **Pay it forward.** Open source runs the internet. Contribute back.
- **Meet people.** Many maintainers are friendly and welcoming.
- **Job opportunities.** Recruiters search GitHub for active contributors to projects they care about.

---

## 13.3 Finding a Project to Contribute To

### Labels to search for

Most repos label issues that are good for newcomers:

- `good first issue` — small, well-described, suitable for first-time contributors.
- `help wanted` — maintainers want help.
- `documentation` — docs-only changes, great for non-coders.
- `beginner-friendly` — some repos use this.

Search URLs:

```
https://github.com/search?q=label%3A%22good+first+issue%22+state%3Aopen&type=issues
https://github.com/search?q=label%3A%22help+wanted%22+state%3Aopen&type=issues
```

### Tools for finding projects

- **<https://goodfirstissue.dev/>** — curated list.
- **<https://up-for-grabs.net/>** — projects wanting contributors.
- **<https://www.firsttimersonly.com/>** — advice for first-timers.
- **<https://github.com/trending/>** — trending repos (not always beginner-friendly, but interesting).
- **<https://codetriage.com/>** — get one issue from a project you watch in your inbox daily.

### Picking a project

Prefer projects that:
- Are actively maintained (commits in the last month).
- Have open issues labeled `good first issue`.
- Have a `CONTRIBUTING.md` (signals they want contributors).
- Have a `CODE_OF_CONDUCT.md` (signals respectful community).
- Respond to PRs in reasonable time (check the closed PRs tab).

---

## 13.4 Reading `CONTRIBUTING.md`

Every well-run open-source project has a `CONTRIBUTING.md` at the root. **Read it before opening a PR.** It tells you:

- How to set up the project locally.
- Code style conventions.
- Test requirements (you must add tests for new features).
- Branch / commit / PR conventions.
- How to sign your commits (some projects require DCO or GPG signing).
- Where to ask questions (Discussions tab, Slack, mailing list).

Skipping this is the #1 reason first PRs get rejected.

### Example structure of a `CONTRIBUTING.md`

```markdown
# Contributing

Thanks for your interest! This document explains how to contribute.

## Setup

1. Fork and clone the repo.
2. Run `npm install`.
3. Copy `.env.example` to `.env` and fill in values.
4. Run `npm run dev`.

## Code style

- We use Prettier with the config in `.prettierrc`.
- Run `npm run lint` before committing. CI will fail if lint fails.

## Commit messages

- Follow Conventional Commits: `feat(scope): description`.
- Reference issues: `Closes #123`.

## Tests

- Add tests for any new feature.
- Run `npm test` locally. CI runs the same.

## Pull requests

- One feature per PR.
- Keep PRs under 300 lines if possible.
- Address review feedback within 2 weeks or the PR may be closed.

## Code of Conduct

By participating, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).
```

---

## 13.5 Forking and Cloning (Refresher)

```bash
# Fork on github.com (or use gh)
gh repo fork owner/repo --clone

# Add upstream
git remote add upstream https://github.com/owner/repo.git

# Branch off upstream/main (not your fork's main)
git fetch upstream
git switch -c feature/my-contribution upstream/main
```

The last step is critical: branch from the *original* project's `main`, not your fork's. Your fork's `main` may be out of date.

---

## 13.6 Keeping Your Fork in Sync

Before starting new work, sync:

```bash
git switch main
git fetch upstream
git merge upstream/main
git push origin main
```

Or in one command:

```bash
gh repo sync yourname/repo --source owner/repo
```

Do this weekly if you contribute regularly.

---

## 13.7 Writing the PR

A good OSS PR has:

- **Clear title:** `[Fix] Handle null pointer in user lookup` (some projects prefix with type).
- **Description:** what, why, how tested.
- **Issue reference:** `Fixes #123` (so the issue auto-closes on merge).
- **Linked to issue:** if there's no issue, open one first and discuss the approach before coding.
- **Tests:** added or updated.
- **No unrelated changes:** no formatting "drive-by" fixes in files you didn't mean to touch.
- **Small scope:** one feature per PR.

### Example PR description

```markdown
## What does this PR do?
Fixes a null pointer exception in `UserLookup.findById` when called with a non-existent ID.

## Why?
Currently, `findById(0)` crashes with NPE because the code assumes the user exists. Issue #123 has details.

## How was it tested?
- Added unit test `findById_returnsNull_forNonExistentId`.
- Manually verified with `npm test`.

## Checklist
- [x] Tests pass
- [x] Code follows style guide
- [x] Self-reviewed

Fixes #123
```

---

## 13.8 Code Review Etiquette (Revisited for OSS)

### For contributors

- **Be patient.** Maintainers are volunteers. Days or weeks may pass.
- **Don't ping for updates within a week.** If a month passes, a polite "Any thoughts on this?" is OK.
- **Address feedback gracefully.** Even if you disagree, respond thoughtfully.
- **Push commits, don't force-push** unless asked. Maintainers like to see the evolution.
- **Stay on topic.** Don't sneak in unrelated changes.
- **Close stale PRs.** If you abandon a PR, close it. Don't leave it open.

### For maintainers

- **Be welcoming.** First-time contributors are nervous. A friendly "Thanks for this!" goes a long way.
- **Be specific in feedback.** "This is wrong" → "This is O(n²); a Set would make it O(n)".
- **Don't demand.** Suggest. "Have you considered…".
- **Acknowledge effort.** Even if you reject a PR, thank the contributor for trying.
- **Close inactive PRs politely.** After a month of no response, comment and close.

---

## 13.9 Common First-PR Pitfalls

1. **Not reading `CONTRIBUTING.md`.** Read it twice.
2. **Opening a PR without an issue.** Many projects require an issue first.
3. **Sneaking in unrelated changes.** Reviewers see every file in the diff.
4. **Force-pushing after review.** Maintainers lose the conversation context.
5. **Huge PRs.** 500-line PRs from strangers don't get reviewed.
6. **Arguing with the maintainer's design choices.** If they say "we don't want this", accept it.
7. **Demanding an immediate review.** Maintainers owe you nothing.
8. **Not signing the commit (if DCO required).** Some projects require `Signed-off-by: Name <email>` in the commit message. Add `-s` to `git commit`:
   ```bash
   git commit -s -m "fix: handle null pointer in user lookup"
   ```

---

## 13.10 Where to Go From Here

Once you've merged your first PR:

- **Tackle bigger issues.** Move from `good first issue` to `help wanted`.
- **Become a regular.** Pick one project and contribute regularly. Maintainers will notice.
- **Help others.** Review other people's PRs. Answer issues. Be the welcoming voice.
- **Maintain a project.** Eventually, you'll start your own. Apply everything you've learned about being a good maintainer.

---

## 13.11 Your Turn

1. Go to <https://github.com/search?q=label%3A%22good+first+issue%22+state%3Aopen&type=issues>. Pick an issue in a project you use (or find interesting).

2. Read the project's `CONTRIBUTING.md`. Note any setup steps.

3. Fork and clone locally. Get the project running.

4. Comment on the issue: "I'd like to work on this. Could you confirm the approach is X?" Wait for a reply.

5. Implement, test, commit (with conventional commits if the project uses them).

6. Push and open a PR. Use the PR template from Chapter 11.3.

7. Address any feedback within a day or two.

8. Celebrate when it merges. Add the merged PR URL to your resume.

If you've made it this far in the guide and completed this exercise, **you are a contributor to open source.** That title is permanent.

**Next up: Chapter 14 — The Complete Cheat Sheet.** Bookmark it. Search it when stuck.

---
---


# Chapter 14 — The Complete Cheat Sheet

> **Goal of this chapter:** Be your searchable reference. Bookmark it. When you forget a command, jump here.

This chapter is dense by design. No explanations, just commands and one-liners. Search by category.

---

## 14.1 Command Reference by Category

### Setup and configuration

```bash
git --version                              # check installed version
git config --global user.name "Name"        # set your name
git config --global user.email "email"      # set your email (use GitHub no-reply for privacy)
git config --global init.defaultBranch main # default branch name
git config --global core.editor "code --wait" # default editor
git config --global pull.rebase true        # pull with rebase
git config --global push.default current    # push only current branch
git config --global color.ui auto           # color output
git config --global credential.helper store # store HTTPS credentials
git config --global alias.lg "log --oneline --graph --all --decorate"  # alias
git config --global --list                  # see all settings
git config --global --edit                  # open ~/.gitconfig in your editor
```

### Starting or getting a project

```bash
git init                                   # turn current folder into a Git repo
git clone <url>                            # clone a remote repo
git clone <url> --depth 1                  # shallow clone (only latest commit)
git clone <url> --filter=blob:none         # blobless clone (defer blobs)
git clone <url> -b <branch>                # clone and checkout specific branch
git clone <url> <folder>                   # clone into specific folder
gh repo create <name> --public --source=. --push  # create GitHub repo from current dir
gh repo clone <owner>/<repo>               # clone via gh (auto-auth)
gh repo fork <owner>/<repo> --clone        # fork and clone in one step
```

### The daily loop

```bash
git status                                 # what's modified, staged, etc.
git status -s                              # short status
git add <file>                             # stage one file
git add .                                  # stage everything in current dir
git add -A                                 # stage everything (incl. deletions)
git add -p                                 # stage interactively (per hunk)
git restore --staged <file>                # unstage a file
git restore <file>                         # discard uncommitted changes
git commit -m "message"                    # commit staged changes
git commit -am "message"                   # add tracked files + commit (skips add)
git commit --amend --no-edit               # add changes to last commit
git commit --amend -m "new message"        # change last commit's message
git push                                   # upload commits to remote
git pull                                   # fetch + merge from remote
git fetch                                  # fetch but don't merge
git log --oneline --graph --all --decorate # pretty history
git log -p <file>                          # history with diffs for a file
git log --since="2 weeks ago"              # recent commits
git log --author="Name"                    # commits by author
git log -S "search string"                 # commits that added/removed string
git show <hash>                            # show a specific commit
git show HEAD                              # show latest commit
git show HEAD~3                            # show commit 3 back
git diff                                   # unstaged changes
git diff --staged                          # staged changes
git diff HEAD~1                            # changes since last commit
git diff main feature/x                    # diff between branches
git diff --word-diff                       # word-level diff
```

### Branches

```bash
git branch                                 # list local branches
git branch -a                              # list all (incl. remote)
git branch -vv                             # list with tracking info
git branch <name>                          # create branch
git switch <name>                          # switch to branch
git switch -c <name>                       # create + switch
git checkout -b <name>                     # legacy equivalent of -c
git branch -d <name>                       # delete (safe; refuses if unmerged)
git branch -D <name>                       # force delete
git branch -m <new-name>                   # rename current branch
git branch -m <old> <new>                  # rename any branch
git push origin --delete <branch>          # delete remote branch
git push -u <remote> <branch>              # push new branch + set upstream
git merge <branch>                         # merge <branch> into current
git merge --no-ff <branch>                 # force a merge commit
git merge --abort                          # abort a conflicted merge
git cherry-pick <hash>                     # apply a single commit on current branch
git rebase <branch>                        # replay current branch onto <branch>
git rebase -i HEAD~3                       # interactive rebase last 3 commits
git rebase --abort                         # abort rebase
git rebase --continue                      # continue after resolving conflict
```

### Remotes

```bash
git remote -v                              # list remotes
git remote add <name> <url>                # add remote
git remote remove <name>                   # remove remote
git remote rename <old> <new>              # rename remote
git remote set-url <name> <new-url>        # change remote URL
git remote show <name>                     # details about a remote
git fetch <remote>                         # fetch from named remote
git fetch --all                            # fetch from all remotes
git fetch --tags                           # fetch tags too
git push <remote> <branch>                 # push to named remote/branch
git push -u <remote> <branch>              # push + set upstream
git push --force-with-lease                # safe force-push
git push --tags                            # push all tags
git pull <remote> <branch>                 # fetch + merge
git clone <url>                            # clone a repo
```

### Inspection and archaeology

```bash
git log                                    # full history
git log --oneline                          # one line per commit
git log --oneline --graph --all            # graph view
git log --stat                             # files changed per commit
git log -p                                 # show diffs in log
git log -p <file>                          # history of a file with diffs
git log --follow <file>                    # follow file across renames
git log -S "string"                        # commits adding/removing string
git log --grep="pattern"                   # commits matching message pattern
git log --author="name"                    # commits by author
git log --since="2 weeks ago"              # commits since date
git log --until="yesterday"                # commits until date
git log <file>                              # commits touching a file
git show <hash>                            # full info on a commit
git show HEAD                              # latest commit info
git show HEAD~1                            # parent commit
git show <hash>:<file>                     # file content at a specific commit
git show <branch>:<file>                   # file content at branch tip
git diff                                   # unstaged changes
git diff --staged                          # staged changes
git diff HEAD~1 HEAD                       # diff between two commits
git diff main..feature                     # diff between two branches
git blame <file>                           # who wrote each line
git blame -L 10,20 <file>                  # specific line range
git blame -w <file>                        # ignore whitespace
git grep "pattern"                         # search tracked files
git grep -n "pattern"                      # with line numbers
git shortlog -sne                          # contributors sorted by commit count
git describe --tags                        # nearest tag + commit count
git ls-files                              # list tracked files
git ls-files -s                            # list with hashes (index inspection)
git count-objects -v                       # repo size stats
git fsck                                   # integrity check
```

### Undo and rescue

```bash
git restore --staged <file>                # unstage (keep changes)
git restore <file>                         # discard uncommitted changes
git restore .                              # discard all uncommitted
git reset --soft HEAD~1                    # undo last commit, keep changes staged
git reset HEAD~1                           # undo last commit, keep changes unstaged
git reset --hard HEAD~1                    # undo last commit AND discard changes
git reset --hard <hash>                    # move HEAD to a specific commit (destructive)
git reset --hard origin/main               # match local to remote (destructive)
git revert <hash>                          # add a new commit that undoes <hash>
git revert -m 1 <merge-hash>              # revert a merge commit
git commit --amend --no-edit              # add changes to last commit
git commit --amend -m "new message"       # change last commit message
git stash                                  # shelve uncommitted changes
git stash -u                               # stash including untracked
git stash -a                               # stash including ignored
git stash push -m "wip: feature"          # stash with a message
git stash list                             # list stashes
git stash apply                            # apply most recent stash
git stash apply stash@{1}                  # apply specific stash
git stash pop                              # apply + drop most recent
git stash drop stash@{0}                   # drop one stash
git stash clear                            # drop all stashes
git reflog                                 # show HEAD history
git reflog --all                           # all refs' history
git reset --hard HEAD@{2}                  # restore to 2 operations ago
git branch <name> <hash>                   # recreate a deleted branch
git cherry-pick <hash>                     # apply a commit to current branch
git clean -n                               # dry run: show what would be deleted
git clean -f                               # delete untracked files
git clean -fd                              # delete untracked files + dirs
git clean -fdx                             # also delete ignored files
git push --force-with-lease                # safe force-push
```

### Tags and releases

```bash
git tag <name>                             # lightweight tag
git tag -a <name> -m "message"             # annotated tag (recommended)
git tag -a <name> -m "msg" <hash>          # tag a specific commit
git tag                                    # list all tags
git tag -l "v1.*"                           # filter tags
git show <tag>                              # show tag details
git push origin <tag>                       # push one tag
git push origin --tags                      # push all tags
git tag -d <name>                           # delete tag locally
git push origin --delete <name>            # delete remote tag
gh release create <tag> --notes "..."      # create release
gh release create <tag> --generate-notes   # auto-generate notes
gh release upload <tag> file.zip           # attach binary
gh release download <tag>                  # download release assets
gh release list                             # list releases
```

### Submodules and worktrees

```bash
git submodule add <url> <path>             # add submodule
git submodule update --init --recursive    # init submodules after clone
git submodule update --remote              # update submodules to latest
git submodule deinit -f <path>             # deinit submodule
git rm -f <path>                            # remove submodule
git clone --recurse-submodules <url>       # clone with submodules

git worktree add <path> <branch>           # add worktree
git worktree list                           # list worktrees
git worktree remove <path>                 # remove worktree
```

### Bisect

```bash
git bisect start                           # start
git bisect bad                              # mark current as bad
git bisect good <commit>                   # mark known-good commit
git bisect good                             # mark current as good
git bisect bad                              # mark current as bad
git bisect reset                            # exit
git bisect run <command>                   # automated
```

### GitHub CLI

```bash
gh auth login                              # authenticate
gh auth status                              # check auth
gh repo create <name>                       # create repo
gh repo clone <owner>/<repo>                # clone
gh repo view --web                          # open in browser
gh repo fork <owner>/<repo> --clone         # fork + clone
gh repo sync <owner>/<repo>                 # sync fork

gh pr create --title "..." --body "..."     # open PR
gh pr list                                  # list PRs
gh pr view <num>                            # view PR
gh pr view <num> --web                       # open in browser
gh pr checkout <num>                        # checkout PR branch locally
gh pr diff <num>                            # view diff
gh pr merge <num> --squash --delete-branch  # merge + delete branch
gh pr close <num>                           # close PR
gh pr ready <num>                           # mark draft PR ready

gh issue create --title "..." --body "..."  # open issue
gh issue list                               # list issues
gh issue view <num>                         # view issue
gh issue close <num>                        # close issue
gh issue comment <num> --body "..."         # comment on issue

gh run list                                 # list workflow runs
gh run view <id>                            # view a run
gh run view <id> --log                      # view logs
gh run rerun <id>                           # rerun failed run
gh run watch <id>                           # live-watch a run

gh release create <tag> --notes "..."       # create release
gh release upload <tag> <file>              # attach binary
gh release download <tag>                    # download

gh secret set <name> --body "value"          # set secret
gh secret list                                # list secrets
gh secret delete <name>                      # delete secret

gh gist create <file> --public                # create gist
gh gist list                                  # list gists
```

---

## 14.2 How Do I...? (The Scenario Table)

| I want to... | Command |
|---|---|
| See what changed | `git status` |
| See unstaged diff | `git diff` |
| See staged diff | `git diff --staged` |
| See commit history | `git log --oneline` |
| See who wrote each line of a file | `git blame <file>` |
| Stage all changes | `git add .` |
| Stage only part of a file | `git add -p <file>` |
| Unstage a file | `git restore --staged <file>` |
| Discard local changes | `git restore <file>` |
| Discard all local changes | `git restore .` |
| Discard everything and match HEAD | `git reset --hard HEAD` |
| Discard everything and match remote | `git reset --hard origin/main` |
| Amend last commit | `git commit --amend --no-edit` |
| Change last commit message | `git commit --amend -m "new"` |
| Undo last commit, keep changes | `git reset --soft HEAD~1` |
| Undo last commit, lose changes | `git reset --hard HEAD~1` |
| Undo a pushed commit | `git revert <hash>` then `git push` |
| Save work in progress | `git stash` |
| Restore stash | `git stash pop` |
| Create a branch | `git switch -c <name>` |
| Switch to a branch | `git switch <name>` |
| List branches | `git branch` |
| Delete a branch | `git branch -d <name>` |
| Rename current branch | `git branch -m <new>` |
| Merge a branch | `git merge <branch>` |
| Abort a merge | `git merge --abort` |
| See all branches graph | `git log --oneline --graph --all` |
| Push to remote | `git push` |
| Force push safely | `git push --force-with-lease` |
| Pull from remote | `git pull` |
| Fetch without merging | `git fetch` |
| Add a remote | `git remote add origin <url>` |
| Change remote URL | `git remote set-url origin <new>` |
| See remotes | `git remote -v` |
| Clone a repo | `git clone <url>` |
| Tag a release | `git tag -a v1.0 -m "Release 1.0"` |
| Push tags | `git push --tags` |
| Recover deleted branch | `git reflog` → `git branch <name> <hash>` |
| Recover lost commit | `git reflog` → `git reset --hard <hash>` |
| Squash last 3 commits | `git rebase -i HEAD~3` then `squash` |
| Find which commit broke something | `git bisect start`, `git bisect bad`, `git bisect good <hash>` |
| Search commit messages | `git log --grep="pattern"` |
| Search code in history | `git log -S "string"` |
| Find what changed in a file | `git log -p <file>` |
| Set up an alias | `git config --global alias.lg "log --oneline --graph"` |
| See config | `git config --global --list` |
| Open repo on github.com | `gh repo view --web` |
| Open PR from CLI | `gh pr create` |
| See my CI runs | `gh run list` |

---

## 14.3 The Full Map of Git

```
                              ┌─────────────────────────┐
                              │      GitHub.com         │
                              │   (your remote: origin) │
                              └────────────┬────────────┘
                                           │
                            push/pull/fetch│ (over SSH or HTTPS)
                                           │
        ┌──────────────────────────────────┴───────────────────────────────────┐
        │                          Your Computer                              │
        │                                                                    │
        │   ┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
        │   │ Working Directory│    │  Staging Area    │    │  .git directory  │
        │   │                  │    │   (index)        │    │                  │
        │   │  Your files on   │    │                  │    │  objects/        │
        │   │  disk, edited    │    │                  │    │   blobs, trees,  │
        │   │  by you          │    │                  │    │   commits        │
        │   │                  │    │                  │    │  refs/           │
        │   │                  │    │                  │    │   heads/ (branches)│
        │   │                  │    │                  │    │   tags/          │
        │   │                  │    │                  │    │  HEAD            │
        │   │                  │    │                  │    │  index           │
        │   │                  │    │                  │    │  logs/ (reflog) │
        │   │                  │    │                  │    │  hooks/         │
        │   │                  │    │                  │    │  config         │
        │   │                  │    │                  │    │                  │
        │   │  git diff        │    │ git diff --staged│    │ git log          │
        │   │  git status      │    │ git ls-files -s  │    │ git show         │
        │   │  git restore     │    │ git restore -S   │    │ git cat-file     │
        │   │                  │    │                  │    │                  │
        │   │  ▲      │        │    │  ▲      │        │    │  ▲      │        │
        │   │  │      ▼        │    │  │      ▼        │    │  │      ▼        │
        │   │  │   git restore │    │  │   git commit   │    │  │   git checkout │
        │   │  │   <file>      │    │  │               │    │  │   / git switch  │
        │   │  │      ▲        │    │  │      ▲        │    │  │      ▲        │
        │   │  │      │        │    │  │      │        │    │  │      │        │
        │   │  └──────┴──────  │    │  └──────┴──────  │    │  └──────┴──────  │
        │   │   git add <file> │    │   git commit -m  │    │  (move commits   │
        │   │   ────────────►   │    │   ────────────►  │    │   back to working│
        │   │                   │    │                   │    │   directory)    │
        │   └──────────────────┘    └──────────────────┘    └──────────────────┘
        │                                                                    │
        │              Stash:  git stash (saves working+staging aside)         │
        │              Reflog: git reflog (history of HEAD movements)         │
        │              Hooks:  .git/hooks/ (auto-runs on events)              │
        │                                                                    │
        └────────────────────────────────────────────────────────────────────┘
```

---

## 14.4 Glossary A to Z

| Term | Definition |
|---|---|
| **Annotated tag** | A tag object with metadata (author, date, message). Recommended over lightweight tags. |
| **Atomic commit** | A commit that does exactly one thing. |
| **Author** | The person who originally wrote a commit. May differ from committer (e.g. after rebase). |
| **Bare repo** | A repo with no working directory, just the `.git` contents. Used as a remote. |
| **Bisect** | Binary search through commits to find which one introduced a bug. |
| **Blob** | Git object representing the content of a file. |
| **Branch** | A movable pointer to a commit. Stored in `refs/heads/`. |
| **Cherry-pick** | Apply a single commit from another branch onto the current branch. |
| **Clone** | A local copy of a remote repo, including full history. |
| **Commit** | A saved snapshot in history. Has a tree, parent(s), author, message, hash. |
| **Committer** | The person who applied a commit. May differ from author. |
| **Conflict** | When two branches changed the same lines; Git cannot auto-merge. |
| **Detached HEAD** | When `HEAD` points at a commit directly, not at a branch. |
| **Diff** | A line-by-line display of changes between two states. |
| **Distributed** | Every clone has the full history. No central server required. |
| **Fast-forward** | A merge where the target branch just moves forward (no merge commit). |
| **Fork** | A server-side copy of a repo under your account. GitHub concept. |
| **Garbage collection** | Git's cleanup of unreferenced objects (`git gc`). |
| **HEAD** | Pointer to the current commit (via the current branch). |
| **Hook** | A script that runs automatically before/after a Git event. |
| **Index** | Synonym for staging area. Binary file at `.git/index`. |
| **Lightweight tag** | A tag that's just a ref to a commit, no metadata. |
| **Main** | The conventional default branch name (since 2020). |
| **Master** | The old default branch name. Some repos still use it. |
| **Merge** | Combining two branches' histories. |
| **Merge commit** | A commit with two parents, created by a 3-way merge. |
| **Origin** | The default name for the remote you cloned from. |
| **Packfile** | A compressed bundle of Git objects (`objects/pack/*.pack`). |
| **Pull** | Fetch + merge from remote. |
| **Pull request (PR)** | A proposal to merge a branch. GitHub concept. |
| **Push** | Upload commits to a remote. |
| **Rebase** | Replay commits on top of another branch. Rewrites history. |
| **Ref** | A named pointer: branch, tag, or `HEAD`. |
| **Reflog** | Log of where `HEAD` has been. Safety net. |
| **Release** | A GitHub Pages-style published version of a tag with notes and binaries. |
| **Remote** | Another Git repo yours syncs with. Usually named `origin`. |
| **Repository (repo)** | A folder Git is tracking. Contains the `.git` directory. |
| **SHA / hash** | 40-char fingerprint of a Git object. |
| **Snapshot** | A complete state of all tracked files at one moment. A commit. |
| **Stage** | To mark changes for the next commit (via `git add`). |
| **Stash** | Temporary storage for uncommitted changes. |
| **Submodule** | A Git repo nested inside another. |
| **Tag** | A fixed pointer to a specific commit. Used for releases. |
| **Tree** | Git object representing a directory (file names + blob hashes). |
| **Upstream** | Convention for the original repo's remote (when you forked). |
| **Working directory** | The actual files on disk that you edit. |

---

## 14.5 File Locations Cheat Sheet

| File | Location | Purpose |
|---|---|---|
| Global config | `~/.gitconfig` | User-level Git settings. |
| Repo config | `<repo>/.git/config` | Repo-level settings (overrides global). |
| SSH private key | `~/.ssh/id_ed25519` | Your private SSH key. **Never share.** |
| SSH public key | `~/.ssh/id_ed25519.pub` | Your public SSH key. Share with GitHub. |
| SSH known hosts | `~/.ssh/known_hosts` | Servers you've verified. |
| Repo database | `<repo>/.git/` | All of Git's data. Don't touch manually. |
| Repo objects | `<repo>/.git/objects/` | All blobs, trees, commits. |
| Repo branches | `<repo>/.git/refs/heads/` | One file per local branch. |
| Repo tags | `<repo>/.git/refs/tags/` | One file per tag. |
| Repo HEAD | `<repo>/.git/HEAD` | Pointer to current branch. |
| Repo index | `<repo>/.git/index` | Binary file: the staging area. |
| Repo reflog | `<repo>/.git/logs/HEAD` | History of HEAD movements. |
| Hooks | `<repo>/.git/hooks/` | Sample hook scripts. |
| Workflow files | `<repo>/.github/workflows/` | GitHub Actions workflows. |
| Issue templates | `<repo>/.github/ISSUE_TEMPLATE/` | Templates for new issues. |
| PR template | `<repo>/.github/PULL_REQUEST_TEMPLATE.md` | Default PR description. |
| Code owners | `<repo>/.github/CODEOWNERS` or `<repo>/CODEOWNERS` | Path → owner mappings. |
| Dependabot config | `<repo>/.github/dependabot.yml` | Dependency update config. |

---

## 14.6 File Conventions Cheat Sheet

| File | Purpose |
|---|---|
| `.gitignore` | Files Git should not track. |
| `.gitattributes` | Per-file attributes (line endings, binary/text, etc.). |
| `.editorconfig` | Editor behavior (indent style, charset, etc.). |
| `.env` | Environment variables. **Should be gitignored.** |
| `.env.example` | Template for required env vars (committed). |
| `README.md` | Project description. First thing visitors see. |
| `LICENSE` | Open-source license. |
| `CHANGELOG.md` | Manual changelog. |
| `CONTRIBUTING.md` | How to contribute. |
| `CODE_OF_CONDUCT.md` | Community behavior rules. |
| `SECURITY.md` | How to report vulnerabilities. |
| `Dockerfile` | Container build instructions. |
| `Makefile` | Common dev commands. |
| `package.json` | Node.js project manifest. |
| `pyproject.toml` | Python project manifest. |
| `Cargo.toml` | Rust project manifest. |

Bookmark this chapter. You'll be back.

**Next up: Chapter 15 — Troubleshooting and FAQ.** When things go wrong, jump here.

---
---


# Chapter 15 — Troubleshooting and FAQ

> **Goal of this chapter:** Fix the most common Git errors. Search by error message. Bookmark this page.

When Git refuses to do something, it usually tells you exactly why. This chapter translates the error messages into fixes.

---

## `fatal: not a git repository (or any of the parent directories): .git`

**Cause:** You're running a Git command in a folder that isn't inside a Git repo.

**Fix:**
1. `cd` into the right folder (the one with `.git/` inside).
2. Or run `git init` if you want to make this folder a repo.
3. Or `git clone <url>` to download an existing repo.

To check whether a folder is a repo:

```bash
ls -la | grep .git
# or:
git rev-parse --git-dir
```

---

## `Permission denied (publickey)` when pushing/pulling over SSH

**Cause:** GitHub doesn't recognize your SSH key.

**Fixes:**
1. Verify you have a key:
   ```bash
   ls ~/.ssh/
   ```
   You should see `id_ed25519` and `id_ed25519.pub` (or `id_rsa` / `id_rsa.pub`).

2. If not, generate one (Chapter 1.5).

3. Verify the key is loaded in the agent:
   ```bash
   ssh-add -l
   ```
   Should list your key. If empty:
   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519
   ```

4. Verify GitHub knows your key:
   ```bash
   ssh -T git@github.com
   ```
   Should print `Hi <username>!`.

5. Verify the remote URL uses SSH:
   ```bash
   git remote -v
   ```
   Should show `git@github.com:owner/repo.git`. If it shows `https://`, switch:
   ```bash
   git remote set-url origin git@github.com:owner/repo.git
   ```

---

## `ERROR: Repository not found` / `fatal: unable to access ... : The requested URL returned error: 403`

**Cause:** Either the repo doesn't exist, or you don't have access.

**Fixes:**
1. Verify the URL is correct (typos happen).
2. Verify the repo exists (open in browser).
3. If it's a private repo, verify you've been added as a collaborator.
4. If you're forking, make sure you're pushing to your fork (`yourname/repo`), not the original.
5. If using HTTPS, verify your PAT is correct (re-create it if needed).

---

## `! [rejected] main -> main (fetch first)` / `failed to push some refs`

**Cause:** The remote has commits you don't have locally.

**Fix:**
```bash
git pull
# resolve any conflicts
git push
```

---

## `fatal: refusing to merge unrelated histories`

**Cause:** Git sees two completely independent histories. Usually happens when you `git init` a repo, then `git remote add origin <url>` and `git pull` — but the remote already had commits you don't share a common ancestor with.

**Fix:** If you're sure you want to merge:
```bash
git pull origin main --allow-unrelated-histories
# resolve conflicts if any, then:
git push
```

But better: when starting, clone the empty remote repo instead of `git init` locally.

---

## `fatal: You are not currently on a branch` / "detached HEAD"

**Cause:** You checked out a commit (not a branch), so `HEAD` doesn't point to a branch. New commits won't be on any branch.

**Fix:**

If you haven't made any commits:
```bash
git switch main
```

If you made commits you want to keep:
```bash
git branch save-my-work      # create branch at current commit
git switch main              # safely leave detached HEAD
# later:
git switch save-my-work      # continue work on the saved branch
```

---

## `Your branch is ahead of 'origin/main' by N commits`

**Not an error!** It just means you have N local commits you haven't pushed yet.

**Fix:** Push them:
```bash
git push
```

---

## `warning: LF will be replaced by CRLF` (or the reverse)

**Cause:** Windows uses CRLF line endings; Unix uses LF. Git is normalising line endings. Usually harmless.

**Fix:** Add a `.gitattributes` file (Chapter 8.14):
```text
* text=auto eol=lf
*.bat text eol=crlf
*.png binary
```

Or globally:
```bash
git config --global core.autocrlf input    # macOS/Linux
git config --global core.autocrlf true     # Windows
```

---

## Merge conflict markers got committed (I see `<<<<<<<` in files on GitHub)

**Cause:** You committed a file without resolving the conflict markers.

**Fix:**
1. Open the file, find the `<<<<<<<`, `=======`, `>>>>>>>` markers.
2. Edit the file to the final desired content (removing all markers).
3. `git add <file>` and `git commit` to record the fix.

If the markers are in an old commit (already pushed), use `git revert` to add a fix commit, or `git rebase -i` to fix interactively (if not yet pushed).

---

## `fatal: remote origin already exists`

**Cause:** You tried `git remote add origin <url>` but `origin` already exists.

**Fix:** Use `set-url` instead:
```bash
git remote set-url origin <new-url>
```

Or remove first:
```bash
git remote remove origin
git remote add origin <new-url>
```

---

## `error: failed to push some refs ... hint: Updates were rejected because the tip of your current branch is behind` after history rewriting

**Cause:** You rebased or amended commits that were already pushed. The remote has the old commits; your local has new ones.

**Fix:** Force-push (safely):
```bash
git push --force-with-lease
```

⚠ Only do this on branches that nobody else is using. Never force-push to `main` on a shared project.

---

## `error: Your local changes to the following files would be overwritten by merge/checkout`

**Cause:** You have uncommitted changes that conflict with what Git wants to do.

**Fixes:**

1. **Stash them:**
   ```bash
   git stash
   # do your merge / checkout / pull
   git stash pop
   ```

2. **Commit them:**
   ```bash
   git add . && git commit -m "WIP"
   # do your operation
   ```

3. **Discard them (if you don't want them):**
   ```bash
   git restore .
   # or:
   git checkout -- .
   ```

---

## `Merge branch 'x' of ...` messages everywhere / my history is a braid

**Cause:** You're using `git pull` (which creates merge commits) on a repo where you're the only contributor. Each pull adds a merge commit, even when unnecessary.

**Fix:** Switch to pull with rebase:
```bash
git config --global pull.rebase true
```

Then `git pull` will rebase your local commits on top of the remote, giving a linear history.

To clean up existing braid history:
```bash
git rebase -i origin/main
# pick the first commit, "squash" or "reword" the rest
```

---

## `fatal: bad object <hash>` / `error: object file ... is empty` / repo seems corrupted

**Cause:** Disk corruption, crashed write, or interrupted operation. Rare but happens.

**Fixes:**

1. Run integrity check:
   ```bash
   git fsck --full
   ```
   This will report missing / corrupt objects.

2. Try to recover from a backup remote:
   ```bash
   git fetch --all
   ```

3. If a single object is broken:
   ```bash
   # identify the broken file:
   git fsck --full | grep "missing\|corrupt"
   # delete the broken file, then re-fetch:
   rm .git/objects/<first-2-chars>/<remaining-38-chars>
   git fetch --all
   ```

4. Last resort: re-clone the repo from the remote:
   ```bash
   cd ..
   git clone <url> new-clone
   ```
   You'll lose uncommitted changes in the corrupted repo, but committed-and-pushed work is safe.

---

## `error: lock file exists: .git/index.lock` / `Another git process seems to be running`

**Cause:** A previous Git command crashed or was killed, leaving a `.git/index.lock` file behind.

**Fix:** Verify no Git process is running, then remove the lock:
```bash
ps aux | grep git
# if nothing relevant, remove:
rm .git/index.lock
```

⚠ Only do this if you're sure no Git command is running. Removing an active lock can corrupt the repo.

---

## `Please tell me who you are` before your first commit

**Cause:** You haven't set your name and email.

**Fix:**
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

---

## GitHub asks for a password over HTTPS and rejects it

**Cause:** GitHub stopped accepting account passwords for Git operations in August 2021. You need a Personal Access Token (PAT) instead, or SSH.

**Fix:**

Option 1 — use SSH (recommended):
```bash
git remote set-url origin git@github.com:owner/repo.git
```

Option 2 — use a PAT:
1. Create one at <https://github.com/settings/tokens>.
2. When Git asks for password, paste the PAT (not your account password).
3. Set up credential storage so you only enter it once:
   ```bash
   git config --global credential.helper osxkeychain   # macOS
   git config --global credential.helper manager        # Windows
   git config --global credential.helper store          # Linux (plaintext; less secure)
   ```

---

## `fatal: ambiguous argument 'HEAD'` (on a brand-new repo)

**Cause:** You haven't made any commits yet, so `HEAD` doesn't point anywhere.

**Fix:** Make your first commit:
```bash
git add .
git commit -m "Initial commit"
```

---

## `error: pathspec '<file>' did not match any file(s) known to git`

**Cause:** You tried to `git add` (or operate on) a file that doesn't exist or isn't in the repo.

**Fixes:**
- Verify the file path (typos, case sensitivity).
- For `git checkout -- <file>`: the file must be tracked. If it's new (untracked), use `git restore` instead.
- For `git log <file>`: the file must exist in the current branch.

---

## `fatal: refusing to merge unrelated histories` (during pull)

**Cause:** Local and remote histories have no common ancestor. Common after `git init` + `git remote add` + `git pull` on a non-empty remote.

**Fix:**
```bash
git pull origin main --allow-unrelated-histories
# resolve conflicts
git push
```

Better prevention: clone empty repos instead of init+remote+pull.

---

## `fatal: refusing to delete branch currently checked out`

**Cause:** You can't delete the branch you're on.

**Fix:** Switch to another branch first:
```bash
git switch main
git branch -D <other-branch>
```

---

## `error: cannot lock ref 'refs/heads/feature/...': 'refs/heads/feature' exists`

**Cause:** You have a branch named `feature` and tried to create `feature/something`. Git can't have both a branch and a "folder" with the same name.

**Fix:** Rename the conflicting branch:
```bash
git branch -m feature feature-old
git switch -c feature/something
```

---

## FAQ — quick answers

**Q: How do I undo `git init`?**
A: Delete the `.git` folder: `rm -rf .git`. The rest of your files are untouched.

**Q: How do I undo `git add`?**
A: `git restore --staged <file>` (or `git reset HEAD <file>`).

**Q: How do I change the commit message of the last commit (not pushed)?**
A: `git commit --amend -m "new message"`.

**Q: How do I change the commit message of an old commit?**
A: `git rebase -i HEAD~N`, change `pick` to `reword` for that commit, save.

**Q: How do I push a new branch to remote?**
A: `git push -u origin <branch>` (the `-u` sets up tracking).

**Q: How do I rename a remote branch?**
A: You can't rename a remote branch directly. Push the new name, delete the old:
```bash
git push origin <old>:<new>
git push origin --delete <old>
```

**Q: How do I see which branches are merged into main?**
A: `git branch --merged main`.

**Q: How do I delete all merged branches?**
A: `git branch --merged main | grep -v main | xargs git branch -d`.

**Q: How do I make Git stop asking for my SSH passphrase?**
A: On macOS: add to `~/.ssh/config`:
```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```
On Linux: use `ssh-agent` and add to your shell startup.

**Q: How do I find the commit that introduced a specific line?**
A: `git blame <file>` then look at the commit hash for that line.

**Q: How do I find the commit that broke a feature?**
A: `git bisect` (Chapter 8.8).

**Q: How do I share my Git config across machines?**
A: Commit your `~/.gitconfig` to a dotfiles repo and symlink it. Or use `chezmoi` / `yadm`.

**Q: How do I see what's in the staging area before committing?**
A: `git diff --staged` (or `git diff --cached`).

**Q: How do I make Git case-sensitive for file names?**
A: `git config core.ignorecase false` (per repo).

**Q: How do I switch to a branch that exists only on the remote?**
A: `git fetch && git switch <branch-name>` (modern Git auto-creates a tracking branch).

**Q: How do I see the contents of a file as it was in commit X?**
A: `git show <hash>:<file>`.

**Q: How do I move my repo to GitHub without including sensitive files in history?**
A: Use `git filter-repo` (Chapter 7.12) to scrub history, then push.

**Q: How do I download a single file from GitHub without cloning?**
A: On github.com, open the file → **Raw** button → save. Or `curl https://raw.githubusercontent.com/owner/repo/branch/path/file`.

**Q: How do I find the most recent commit that touched a specific line?**
A: `git blame -L <line>,<line> <file>`.

**Q: Can I undo a force-push?**
A: Often yes, if you know the previous commit hash. `git push --force origin <old-hash>:main`. GitHub staff can sometimes recover via support ticket otherwise.

**Q: How do I see who has access to my repo?**
A: Repo → Settings → Collaborators and teams.

**Q: How do I make a public repo private?**
A: Repo → Settings → Change visibility. Free accounts can have unlimited private repos.

**Q: How do I transfer a repo to another account?**
A: Repo → Settings → Transfer. Both accounts must agree.

**Q: How do I download an entire repo as a ZIP without Git?**
A: github.com → **Code** button → **Download ZIP**. Or `gh repo clone`.

**Q: My PR has conflicts. How do I fix them?**
A: On github.com, click "Resolve conflicts" if it's simple. Otherwise, pull the target branch into your feature branch locally and resolve manually:
```bash
git switch feature/x
git fetch origin
git merge origin/main   # or git rebase origin/main
# resolve conflicts
git push
```

If you've encountered an error not covered here, the official Git FAQ is at <https://git-scm.com/docs/git-faq> and Stack Overflow's `git` tag has answers to virtually every Git question ever asked.

**Next up: Chapter 16 — Resources, Glossary & Next Steps.** Where to go after this guide.

---
---


# Chapter 16 — Resources, Glossary & Next Steps

> **Goal of this chapter:** Give you a curated map of where to go next. Books, courses, tools, communities, and projects to deepen your mastery.

You've finished the guide. Now what? This chapter is your reading list and your path forward.

---

## 16.1 Official Documentation

| Resource | URL |
|---|---|
| Git official site | <https://git-scm.com/> |
| Pro Git book (free, comprehensive) | <https://git-scm.com/book> |
| Git reference manual | <https://git-scm.com/docs> |
| Git FAQ | <https://git-scm.com/docs/git-faq> |
| GitHub Docs | <https://docs.github.com/> |
| GitHub Skills (interactive tutorials) | <https://skills.github.com/> |
| GitHub CLI docs | <https://cli.github.com/manual/> |
| GitHub Actions docs | <https://docs.github.com/actions> |
| GitHub REST API | <https://docs.github.com/rest> |
| GitHub GraphQL API | <https://docs.github.com/graphql> |
| GitHub Pages docs | <https://docs.github.com/pages> |
| GitHub security best practices | <https://docs.github.com/code-security> |

The Pro Git book is the single best resource. Read it cover-to-cover once; refer back forever.

---

## 16.2 Interactive Practice

| Resource | What it is |
|---|---|
| <https://learngitbranching.js.org/> | Visual, interactive Git branching tutorial. Best way to internalise branching/merging. |
| <https://onlywei.github.io/explain-git-with-d3/> | Animated visualisations of Git commands. |
| <https://git.github.io/git-reference/> | Quick command reference. |
| <https://www.atlassian.com/git/tutorials> | Atlassian's Git tutorials (high quality, free). |
| <https://lab.github.com/> | GitHub's own learning lab. |
| <https://www.firsttimersonly.com/> | Resources specifically for first-time open-source contributors. |

Spend 30 minutes on **learngitbranching.js.org** — it's the most effective branching visualisation ever built.

---

## 16.3 Tools Worth Trying

| Tool | What it does | Why you'd use it |
|---|---|---|
| `lazygit` | Terminal UI for Git | Keyboard-driven, very fast |
| `tig` | Terminal history browser | Quick log inspection |
| `gh` | GitHub CLI | Do GitHub stuff from terminal |
| `delta` | Beautiful `git diff` | Best-looking diffs |
| `git-delta` | Same as above (alt name) | Same |
| `pre-commit` | Hook framework | Manage hooks as code |
| `commitlint` | Enforce commit message format | Conventional commits enforcement |
| `semantic-release` | Auto version + publish | Conventional commits → auto release |
| `git-filter-repo` | Rewrite history (remove secrets) | Modern replacement for BFG |
| `git-lfs` | Large File Storage | Track binaries without bloating repo |
| `husky` | Git hooks for JS projects | Easy hook management with npm |
| `lint-staged` | Lint only staged files | Faster pre-commit hooks |
| GitLens (VS Code) | Git superpower for VS Code | Inline blame, hover details, rebase editor |
| Git Graph (VS Code) | Visualise branch graph | Inside VS Code |
| GitHub Desktop | GUI Git client | Beginner-friendly |
| GitKraken | Cross-platform GUI | Beautiful visualisations |
| Sourcetree | Atlassian's GUI client | Power features in GUI |

Try one new tool per week. Most are installable in under 5 minutes.

---

## 16.4 Books

| Book | Author | Notes |
|---|---|---|
| **Pro Git** | Scott Chacon, Ben Straub | Free online. The Bible. |
| **Version Control with Git** | Jon Loeliger, Matthew McCullough | O'Reilly. Deep. |
| **Git for Teams** | Emma Jane Hogbin Westby | Workflow-focused. |
| **GitHub Essentials** | Achilleas Pipinellis | Quick start. |

---

## 16.5 Communities

| Community | Where |
|---|---|
| GitHub Community Discussions | <https://github.community/> |
| Stack Overflow `git` tag | <https://stackoverflow.com/questions/tagged/git> |
| Reddit r/git | <https://reddit.com/r/git> |
| Reddit r/github | <https://reddit.com/r/github> |
| Git mailing list | <https://git.wiki.kernel.org/index.php/GitCommunity> |
| GitHub Discord | Linked from github.com/community |

If you get stuck, search Stack Overflow first — most Git questions have been asked and answered.

---

## 16.6 Where Do You Go From Here?

You've completed the guide. The path forward depends on your goals:

### If you're a student or career-switcher

- Build a portfolio of 3–5 GitHub projects (use the structure from Chapter 11).
- Contribute to one open-source project (Chapter 13).
- Pin your best repos on your GitHub profile.
- Add your GitHub URL to your resume.
- Apply for internships / junior roles — you have the Git skills they want.

### If you're a working developer who never formally learned Git

- Audit your team's repo against the Chapter 11.7 checklist.
- Propose conventions: PR templates, branch protection, CI.
- Mentor juniors on Git (teaching is the best way to solidify knowledge).
- Read *Pro Git* once cover-to-cover.

### If you want to specialise

- **DevOps/Platform Engineering:** Deep-dive GitHub Actions, self-hosted runners, GitHub Enterprise, GitHub Packages, GitHub Container Registry, deployment strategies (blue/green, canary).
- **Security:** GitHub Advanced Security, CodeQL, Dependabot, secret scanning, signed commits (GPG, SSH, X.509), SLSA framework.
- **Open Source Maintainer:** Pick one project you depend on, contribute regularly, eventually become a maintainer. Apply everything in Chapter 13.

### If you want to go deeper on Git internals

- Read the Git source code: <https://github.com/git/git>
- Read the Git book's "Git Internals" chapter (Chapter 10 of Pro Git).
- Watch Linus Torvalds' talk on Git's design: <https://www.youtube.com/watch?v=4XpnKHJAok8>
- Read "Git from the Bottom Up": <https://jwiegley.github.io/git-from-the-bottom-up/>
- Experiment: build a tiny Git clone in your favorite language (a common learning exercise).

---

## 16.7 The Long-Term Mastery Roadmap

| Time | Milestone |
|---|---|
| **Week 1** | Finished this guide. Can init/commit/push/branch/merge confidently. |
| **Month 1** | First real project on GitHub. First PR reviewed and merged. CI configured. |
| **Month 3** | First open-source contribution merged. Comfortable with rebase, stash, reflog. |
| **Month 6** | Mentoring a teammate on Git. Reviewing PRs. |
| **Year 1** | Can explain any Git command's internals. Have architected CI/CD for a project. |
| **Year 2+** | Maintainer of an OSS project, or designing org-wide Git workflows at work. |

Git is one of those tools that pays compound interest. The more you use it, the more you understand; the more you understand, the faster you work; the faster you work, the more time you have to learn even more.

---

## 16.8 Final Thoughts

A few years ago, version control felt intimidating. Now you know:

- What Git is, where it came from, and why it exists.
- How to install and configure it.
- The mental models: snapshots, three areas, branches as pointers, distributed history.
- Everyday commands: `add`, `commit`, `push`, `pull`, `log`, `diff`, `status`.
- Branching and merging, including conflict resolution.
- How to push to GitHub and collaborate via PRs.
- How to undo anything: `reset`, `revert`, `stash`, `reflog`, `restore`.
- Power tools: `rebase`, `cherry-pick`, `bisect`, `blame`, `tag`, `submodule`, `worktree`, hooks.
- How to write CI/CD with GitHub Actions.
- How to use GUI clients and IDE integrations.
- Best practices: atomic commits, conventional messages, repo housekeeping, licensing.
- How to contribute to open source.
- How to recover from any disaster.
- Where to learn more.

You are no longer a Git beginner. You're not even intermediate. You are competent — and competence grows into mastery with use.

The next step is not more reading. The next step is **doing**.

Open a terminal. Create a new repo. Build something. Push it. Open a PR. Get feedback. Merge it. Tag a release.

Then do it again tomorrow. And the day after.

Git is a tool; mastery is a habit. Go build.

---

## License of this guide

This guide is released under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license. You are free to:

- **Share** — copy and redistribute the material in any medium or format.
- **Adapt** — remix, transform, and build upon the material for any purpose, even commercially.

Under the following terms:

- **Attribution** — you must give appropriate credit (link to this repo), indicate if changes were made, and distribute under the same license.

Full license text: <https://creativecommons.org/licenses/by/4.0/>

---

## Contribute to this guide

Found a typo? Want to add a chapter? Open a PR.

```bash
gh repo fork AzizNader1/Learning_Git_GitHub_From_Zero_To_Hero --clone
cd Learning_Git_GitHub_From_Zero_To_Hero
git switch -c docs/improve-section-x
# make changes
git commit -m "docs: improve Section X.Y for clarity"
git push -u origin docs/improve-section-x
gh pr create --title "Docs: improve Section X.Y" --body "What I changed and why."
```

All contributions welcome. Be kind. Follow the Code of Conduct (when added).

---

> **End of guide.** You started at zero. You are now at hero. Go build something worth committing.
>
> *— The Author, 2026*

