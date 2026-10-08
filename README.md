# The Complete Git and GitHub Mastery Guide

## From Absolute Zero to Professional Mastery - Every Line Explained

> This single document is a complete course. It takes you from "I have never heard of version control" to "I can build, branch, collaborate, automate, and ship real applications with Git and GitHub." Every concept is explained word by word, every command is explained line by line, and every command output is decoded so you understand exactly what your computer is doing at all times.

---

## About This Guide

Welcome. If you have arrived here knowing nothing at all about Git or GitHub, you are in exactly the right place, and you should read this guide from the very top to the very bottom in order. If you already know a little, you can skim the early chapters, but be warned: this guide builds like a staircase, where every chapter stands on the one before it, so skipping steps may leave gaps that confuse you later.

This guide was written around three promises:

1. **Zero assumed knowledge.** We start from the absolute beginning: what version control is, why it exists, and where Git and GitHub came from. You do not need to be a programmer to read Parts A through E. You only need a computer and curiosity.
2. **Every line explained.** Every command you are asked to type is followed by an "Anatomy of the command" breakdown that explains each word, each flag, and each symbol. Every command output is followed by a "What just happened" section that decodes every line of the output, including the parts that look like gibberish at first.
3. **From theory to a shipped application.** By the end you will not just "know about" Git and GitHub. You will have used them the way professional teams do: branching, committing, opening pull requests, running automated tests, and deploying a real, working application to a live public URL.

The guide is organized into eight parts, plus two reference appendices:

- **Part A - The Foundations:** What Git and GitHub are, their history, what they give you, why you should use them, and how Git actually works internally.
- **Part B - Getting Set Up:** Installing Git on every operating system, configuring it, and connecting it to GitHub securely.
- **Part C - Git Fundamentals:** The daily core loop of status, add, and commit; commit messages; inspecting history; and ignoring files.
- **Part D - Branching and Merging:** Branches, merges, merge conflicts, rebasing, stashing, and tagging.
- **Part E - GitHub and Collaboration:** Remotes, pushing and pulling, pull requests, forking, and contributing to open source.
- **Part F - Advanced Git:** Undoing anything, cherry-picking, bisect, hooks, aliases, submodules, and a tour inside Git's internals.
- **Part G - Automation with GitHub Actions:** Continuous integration and continuous deployment, with every line of every automation file explained.
- **Part H - Mastery and the Real World:** A full capstone project where we build and ship a real application, team workflows, best practices, a troubleshooting encyclopedia, interview questions, and your roadmap forward.

Read it in order. Type every command yourself. By the end, you will have knowledge that most working professionals use every single day of their careers.

---

## How to Use This Guide

Before you start, learn the visual conventions used in every chapter. They never change, so learning them once will make every code block in this guide instantly readable.

**Convention 1 - Commands you type.** When you see a code block containing lines starting with the dollar sign `$`, the text after the `$` is a command that you type into your terminal:

```bash
$ git status
```

You type `git status` (without the dollar sign and without the space). The `$` is only a symbol representing your terminal's prompt, which is the blinking cursor that waits for your input. In many places this guide will also show commands without the `$` so that comments can be added to the right of them, like this:

```bash
git status    # Ask Git: "What is the current state of my files?"
```

In that style, everything after the `#` symbol is a comment. A comment is text written for humans that the computer ignores. The `#` comment exists purely to teach you what that part of the command means.

**Convention 2 - Output you receive.** Code blocks labeled `text` show what your computer prints back to you. You never type these; Git prints them. After most important outputs, you will find a "What just happened (line by line)" section that translates each output line into plain English.

**Convention 3 - Anatomy of the command.** For every significant new command, you get a word-by-word breakdown. For example, later you will learn that in `git commit -m "message"`, the word `git` is the program, `commit` is the subcommand (the specific action), `-m` is a flag meaning "here is my message inline," and `"message"` is the value passed to that flag. Nothing is left unexplained.

**Convention 4 - Try it yourself.** Boxes like the one below mark hands-on moments. Reading about Git is like reading about swimming: useless until you get in the water.

> **Try it yourself:** Do not just read the commands in this guide. Open a terminal, create a practice folder, and type them. Your fingers learn what your eyes only think they know.

**Convention 5 - Practice files.** In Parts C and D we will work inside a practice repository that you will create and destroy yourself, so nothing can go wrong. Later, Part H builds a real application. You can also re-read any chapter using its Table of Contents link.

A final promise before we begin: Git has a reputation for being confusing, and honestly, parts of it are strange. But almost everything confusing about Git becomes clear once you understand one simple picture: **files move through three areas on your computer, and every command you will ever learn is just moving files between those areas (or between your computer and GitHub).** Chapter 7 will teach you that picture, and it will be your mental map for the entire rest of the guide.

---

## Table of Contents

### Part A - The Foundations

- [Chapter 1: Welcome and How to Use This Guide](#chapter-1-welcome-and-how-to-use-this-guide) - What you will learn and how the guide is structured
- [Chapter 2: What Are Git and GitHub?](#chapter-2-what-are-git-and-github) - The two tools, explained word by word, and how they differ
- [Chapter 3: The History of Git and GitHub](#chapter-3-the-history-of-git-and-github) - Linux, BitKeeper, a ten-day sprint, and a 7.5 billion dollar acquisition
- [Chapter 4: What Git and GitHub Give You](#chapter-4-what-git-and-github-give-you) - Every benefit, mapped to a real situation you will face
- [Chapter 5: Why You Should Use Git and GitHub](#chapter-5-why-you-should-use-git-and-github) - Seven honest reasons, plus the common objections answered
- [Chapter 6: Understanding Version Control](#chapter-6-understanding-version-control) - Local, centralized, and distributed systems compared
- [Chapter 7: How Git Works Under the Hood](#chapter-7-how-git-works-under-the-hood) - Snapshots, the three areas, hashes, and why branches are cheap

### Part B - Getting Set Up

- [Chapter 8: Installing Git on Windows, macOS, and Linux](#chapter-8-installing-git-on-windows-macos-and-linux) - Every step of installation, plus a terminal primer for absolute beginners
- [Chapter 9: First-Time Configuration](#chapter-9-first-time-configuration) - Telling Git who you are, with every setting explained
- [Chapter 10: GitHub Account and SSH Connection](#chapter-10-github-account-and-ssh-connection) - Creating your account and connecting securely with SSH keys

### Part C - Git Fundamentals

- [Chapter 11: Your First Repository](#chapter-11-your-first-repository) - `git init` and `git clone`, and what actually happens
- [Chapter 12: The Core Daily Loop](#chapter-12-the-core-daily-loop) - `git status`, `git add`, `git commit` - the loop you will use forever
- [Chapter 13: Writing Great Commit Messages](#chapter-13-writing-great-commit-messages) - Conventional Commits, atomic commits, and amending
- [Chapter 14: Inspecting History with log, show, and diff](#chapter-14-inspecting-history-with-log-show-and-diff) - Reading history and understanding every diff symbol
- [Chapter 15: The .gitignore File](#chapter-15-the-gitignore-file) - Controlling exactly what Git tracks and ignores

### Part D - Branching and Merging

- [Chapter 16: Branches](#chapter-16-branches) - Creating, switching, renaming, and deleting branches
- [Chapter 17: Merging Branches](#chapter-17-merging-branches) - Fast-forward and three-way merges decoded
- [Chapter 18: Merge Conflicts: The Complete Walkthrough](#chapter-18-merge-conflicts-the-complete-walkthrough) - A real conflict, created, understood, and resolved
- [Chapter 19: Rebasing](#chapter-19-rebasing) - Rewriting history safely, plus interactive rebase
- [Chapter 20: Stashing](#chapter-20-stashing) - Saving unfinished work for later
- [Chapter 21: Tagging](#chapter-21-tagging) - Marking releases with semantic versions

### Part E - GitHub and Collaboration

- [Chapter 22: Remotes: push, pull, and fetch](#chapter-22-remotes-push-pull-and-fetch) - Connecting local work to GitHub, every word explained
- [Chapter 23: The Pull Request Workflow](#chapter-23-the-pull-request-workflow) - The professional way to merge work, end to end
- [Chapter 24: Forking and Open Source Contributions](#chapter-24-forking-and-open-source-contributions) - Contributing to projects you do not own
- [Chapter 25: GitHub Power Features](#chapter-25-github-power-features) - Issues, Projects, Wiki, Gists, Releases, Pages, security, and the GitHub CLI

### Part F - Advanced Git

- [Chapter 26: Undoing Anything in Git](#chapter-26-undoing-anything-in-git) - restore, reset, revert, and the reflog time machine
- [Chapter 27: Precision Tools: cherry-pick, bisect, and grep](#chapter-27-precision-tools-cherry-pick-bisect-and-grep) - Surgical tools for exact jobs
- [Chapter 28: Hooks and Aliases](#chapter-28-hooks-and-aliases) - Automating checks and typing less
- [Chapter 29: Submodules](#chapter-29-submodules) - One repository inside another
- [Chapter 30: Inside the .git Directory](#chapter-30-inside-the-git-directory) - A guided tour that removes all the mystery

### Part G - Automation with GitHub Actions

- [Chapter 31: GitHub Actions from Zero](#chapter-31-github-actions-from-zero) - What CI/CD is, and your first automated workflow
- [Chapter 32: Building a Real CI Pipeline](#chapter-32-building-a-real-ci-pipeline) - A professional test pipeline, line by line
- [Chapter 33: Continuous Deployment](#chapter-33-continuous-deployment) - Automatic deployment to GitHub Pages and real servers

### Part H - Mastery and the Real World

- [Chapter 34: Capstone Project: Build and Ship a Real Application](#chapter-34-capstone-project-build-and-ship-a-real-application) - The full professional workflow, from `git init` to a live URL
- [Chapter 35: Team Workflows](#chapter-35-team-workflows) - GitHub Flow, Git Flow, and trunk-based development
- [Chapter 36: Best Practices and Golden Rules](#chapter-36-best-practices-and-golden-rules) - The habits of people who never lose work
- [Chapter 37: Troubleshooting Encyclopedia](#chapter-37-troubleshooting-encyclopedia) - Every common error, decoded and fixed
- [Chapter 38: Git Interview Questions and Answers](#chapter-38-git-interview-questions-and-answers) - Prove your knowledge to yourself and to employers
- [Chapter 39: Your Roadmap to Mastery](#chapter-39-your-roadmap-to-mastery) - Practice plan, resources, and what comes next

### Appendices

- [Appendix A: Complete Command Reference](#appendix-a-complete-command-reference) - Every command in this guide, grouped by purpose
- [Appendix B: Glossary](#appendix-b-glossary) - Every term, defined in one line

---

## Part A: The Foundations

Everything in this guide rests on the concepts in Part A. Do not skip it, even if you are eager to type commands. The five minutes you spend understanding *why* Git works the way it does will save you hours of confusion later, because most Git confusion is really "I never learned the mental model" confusion.

### Chapter 1: Welcome and How to Use This Guide

#### 1.1 What You Will Be Able to Do at the End

By the last page of this guide, the following sentences will be boringly true about you. Read them now as a preview of your future skill set, and notice that each one currently has a chapter waiting for it:

- You can explain what version control is, and why every software team on Earth uses it.
- You can create a repository, track changes, and read your project's full history like a story.
- You can branch, merge, rebase, and resolve conflicts without fear.
- You can connect a local project to GitHub, push it, and clone it anywhere else.
- You can open, review, and merge pull requests like a professional collaborator.
- You can contribute to open source projects through forking.
- You can write automated pipelines that test and deploy your code on every push.
- You can recover from mistakes that used to make people delete the repository and start over.

That last point deserves emphasis, because it is the quiet reason professionals trust Git so much: **in this guide you will learn that in Git, almost nothing is ever truly lost**, and you will prove it to yourself by digging "deleted" work back out of the reflog in Chapter 26.

#### 1.2 The Philosophy of This Guide

Most Git tutorials fail beginners in one of two ways. The first kind teaches commands only: "type this, then this, then this." The learner obeys, produces the right output, and understands nothing, so the first error message destroys them. The second kind teaches theory only: directed acyclic graphs of commit objects, and the learner can lecture about internals but cannot save a file.

This guide refuses both shortcuts. For every command, you will learn three layers: what it does (the behavior), why it exists (the design reason), and how to read its output (the feedback). Understanding output matters more than beginners expect, because Git talks to you constantly; if you cannot read what it says, you are working blind.

#### 1.3 How to Practice

Create a folder somewhere on your computer named `git-practice`. Every hands-on block in Parts C and D can be executed inside throwaway repositories inside that folder. Break things freely. Delete repositories. Invent conflicts on purpose. The absolute worst outcome of practicing Git is deleting a practice repository, which costs you nothing. The absolute worst outcome of not practicing Git is losing real work later, which can cost you a weekend.

#### 1.4 What You Need

- A computer running Windows, macOS, or Linux (Chapter 8 covers installing Git on all three).
- Internet access, for creating a GitHub account and pushing code.
- No programming knowledge is required until Part G, and even there every line is explained. If you can edit text files, you can follow this guide.

---

### Chapter 2: What Are Git and GitHub?

#### 2.1 The Problem Both Tools Were Built to Solve

Imagine you are writing a document. You write a first version and save it as `report.doc`. The next day you change a paragraph, but you are not sure you will like the change, so you save a copy as `report_v2.doc`. A week later you have this folder:

```text
report.doc
report_v2.doc
report_v2_FINAL.doc
report_v2_FINAL_fixed.doc
report_v2_FINAL_fixed_real_LAST_USE_THIS.doc
```

Every person who has ever worked on a computer knows this folder. It raises questions that the folder cannot answer: What exactly changed between version 2 and version 3? Who made the change that broke everything? Can I get back the paragraph I deleted on Tuesday? Which file did I send to my boss?

Now scale that folder to a software project: thousands of files, ten people editing the same files on the same days, on different computers, in different countries, with a live product that customers are using. The folder-of-copies approach collapses instantly. **Version control software was invented to replace that folder**, and Git is the version control software that won.

#### 2.2 What Version Control Is, Word by Word

The official description of Git is that it is a "distributed version control system." Every one of those four words is a lesson, so take them one at a time.

- **Version:** A version is one complete state of your files at one moment in time. If your project has 10 files and you save all of them together, that combined state is one version. Think of a version as one photograph of your entire project.
- **Control:** Control means management with intent. You decide when a new version is created, you give it a name and a message, and you can order, compare, and restore versions at will. You control the versions; they do not control you.
- **System:** A system means it is a real program with rules, not a habit or a convention. It stores the versions somewhere structured, verifies their integrity, and gives you commands to operate on them.
- **Distributed:** This is the special word that separates Git from older systems, and Chapter 6 is devoted to it. The short version: in Git, every person who works on a project holds a full copy of the entire history on their own machine, not just the latest files.

So, word by word: Git is a **system** for **controlling** the **versions** of your files in a way that is **distributed** among everyone who works on them.

#### 2.3 What Git Is

Git is a program that runs on **your** computer. You install it (Chapter 8), and it lives quietly on your machine like any other program. It has no icon, no window, and no graphical interface of its own; you talk to it by typing commands in a terminal, which is why Chapter 8 includes a terminal primer for people who have never opened one.

When you make a folder a "Git project" (you will do this in Chapter 11 with the `git init` command), Git starts watching that folder and remembering every version you commit to it, storing those versions inside a hidden subfolder named `.git`. From that moment, the folder is called a **repository**: the word literally means a place where things are stored and looked after, like a repository of knowledge. A Git repository is a folder whose complete history Git stores and protects.

The single most important fact about Git for a beginner is this: **Git works locally, on your machine, without the internet.** You can commit, branch, merge, and read your entire history on a plane with no Wi-Fi. GitHub is a separate thing that comes later.

#### 2.4 What GitHub Is

GitHub is a **website** (github.com) that stores copies of Git repositories in the cloud and adds collaboration features on top of them. If Git is the engine in your car, GitHub is a combination of the parking garage, the social club, and the delivery service around it: a place to put a copy of your repository so others can see it, download it, propose changes to it, discuss bugs in it, and build automated pipelines around it.

Two analogies help beginners, and both are true:

1. **Git is like a notebook; GitHub is like a library.** The notebook (Git) holds your writing and all its drafts on your desk. The library (GitHub) lets you publish a copy, let friends check it out, and receive suggested edits pasted in the margins.
2. **Git is like Microsoft Word's track changes; GitHub is like Google Docs' sharing.** Track changes records edits locally; sharing puts the document somewhere others can access and comment on.

#### 2.5 Git vs GitHub, in One Table

| Question | Git | GitHub |
| --- | --- | --- |
| What is it? | A version control program | A hosting and collaboration website |
| Where does it run? | On your computer | In the cloud (as a website) |
| Do you install it? | Yes, you install it once | No, you sign up for an account |
| Does it need internet? | No, fully offline | Yes, it is a website |
| Who makes it? | Originally Linus Torvalds and contributors | Originally four founders; owned by Microsoft since 2018 |
| What does it give you? | Versions, history, branches, merges | Cloud backup, sharing, pull requests, issues, automation, hosting |

Saying "Git" when you mean "GitHub" is like saying "car" when you mean "parking garage." Related, but not the same thing, and people will notice.

#### 2.6 Are There Alternatives?

Yes, and knowing them exists sharpens your understanding. **GitLab** and **Bitbucket** are the main GitHub alternatives (they also host Git repositories and offer collaboration features; GitLab is known for strong built-in CI/CD, Bitbucket for tight integration with Atlassian tools like Jira). As for version control systems themselves, the older centralized ones you will hear about are **SVN (Subversion)** and **CVS**, and Git's sibling is **Mercurial**. You do not need any of these; Git's dominance is nearly total in new projects, which is exactly why this guide teaches it. GitHub, in turn, hosts well over 100 million developers, making it the largest code host on Earth.

#### 2.7 Key Terms Preview

Here are the six words you will see constantly. A full taste now; a feast later.

| Term | Meaning in one line |
| --- | --- |
| Repository (repo) | A folder whose history Git stores |
| Commit | A saved, named snapshot of your files at one moment |
| Branch | A parallel line of work inside one repository |
| Remote | A copy of your repository on another machine, usually GitHub |
| Clone | A downloaded copy of a repository |
| Pull request | A request to merge your branch into someone else's project |

---

### Chapter 3: The History of Git and GitHub

History is not decoration here. Git behaves the way it does because of the crisis it was born from, and once you know the story, several of its strangest features (branches as lightweight pointers, the obsessive speed, the fully offline design) suddenly make perfect sense.

#### 3.1 Before Git: The Old World of Version Control

Software developers have fought the "folder of copies" problem since the 1970s, and version control tools long predate Git. A quick tour of the ancestors, each of which solved part of the problem:

- **RCS (Revision Control System, 1985)** kept old versions of files on your own machine. It was *local*: it could not share anything with anyone else.
- **CVS (Concurrent Versions System, 1990)** added *sharing*: one central server held the project, and every developer connected to it to get files and submit changes. This style is called *centralized* version control.
- **SVN (Subversion, 2000)** modernized the centralized idea and became hugely popular in the 2000s. But centralized systems had two painful weaknesses baked into their design: if the server was down or you were offline, you could not commit anything; and if the server's disk died, the entire project's history could die with it, because clients only held the latest files.

Then came the project that broke all the rules: the Linux kernel.

#### 3.2 The Linux Kernel and the BitKeeper Crisis

In 1991, a Finnish student named **Linus Torvalds** posted a hobby project: a free operating system kernel he called Linux. By the early 2000s, Linux was one of the largest collaborative software projects on the planet, with thousands of developers contributing, and coordinating it was a serious engineering problem.

From 2002, the kernel team used a commercial tool called **BitKeeper** to manage the source. BitKeeper was proprietary software, but its maker, BitMover, allowed free use by open source projects like Linux. It was also, notably, a *distributed* system, and the kernel team came to love working that way.

In April 2005, the arrangement exploded. A developer working on reverse-engineering BitKeeper's protocols angered BitMover, who responded by revoking the free license for the entire kernel community. Suddenly the biggest open source project on Earth had no version control system, and its community was in genuine crisis.

#### 3.3 Ten Days in April 2005

Linus Torvalds decided that the kernel would not depend on anyone else's tool ever again, and that he would simply write a new one himself, designed for exactly how the kernel team worked. He started in early April 2005. Git was functional within days, hosting its own development almost immediately, and by June 2005 it was managing the actual Linux kernel source. A tool written in roughly ten days by one annoyed genius now runs the version control of the modern world.

Linus designed Git around the needs of kernel development, and the design goals explain Git's personality today:

- **Speed:** kernel-sized projects (tens of thousands of files, millions of lines) must be fast, so almost every Git operation is local and near-instant.
- **Simple design:** one clear internal model (snapshots addressed by hashes, which Chapter 7 explains), instead of patchwork features.
- **Strong support for non-linear development:** thousands of developers work in parallel branches that merge constantly, so branching had to be *cheap and instant* (you will learn it costs literally 41 bytes).
- **Fully distributed:** no one can ever revoke the kernel's version control again, because every developer holds the entire history on their own machine.
- **Able to handle large projects efficiently:** years of history and huge trees, stored cleverly.

Even the name is a joke. "Git" is British slang for an unpleasant person. Linus quipped: *"I'm an egotistical bastard, and I name all my projects after myself. First 'Linux', now 'git'."* The joke stuck, the mascot of GitHub became the "Octocat," and today the word means version control.

#### 3.4 Junio Hamano and Git's Maturity

A detail professionals respect: Linus did not stay as Git's maintainer. In July 2005 he handed the project to **Junio C. Hamano**, who has led Git's development ever since, shepherding it through its 1.0 release in December 2005 and two decades of steady improvement. Git's evolution never stopped: the modern commands you will learn in this guide, `git switch` and `git restore` (Chapter 16 and Chapter 26), only arrived in 2019, for example.

#### 3.5 GitHub Is Born (2008)

By 2007, Git was powerful but rough, and there was no friendly place on the internet to put Git repositories. Three developers, **Tom Preston-Werner, Chris Wanstrath, and PJ Hyett** (soon joined by **Scott Chacon**), built a startup around a simple idea: Git hosting with a social layer. **GitHub launched in April 2008** with the mission "build software better, together."

The idea of requesting that a project "pull" your changes existed in distributed version control culture before GitHub, but GitHub turned the **pull request** into a friendly web page with discussion, code review, and one-click merging. That single product decision, more than anything else, is why the pull request became the center of gravity of modern software collaboration, and why Chapter 23 is one of the longest chapters in this guide.

#### 3.6 Microsoft Buys GitHub (2018)

On June 4, 2018, Microsoft announced it was acquiring GitHub for **7.5 billion US dollars**. Many developers feared the worst; the opposite happened. Microsoft kept GitHub independent, increased investment in it, made core features free (including private repositories), and accelerated its evolution. Under Microsoft, GitHub launched **GitHub Actions** in 2019 (the automation platform you will master in Part G), continued growing past **100 million developers** (announced in 2023, still growing since), and pushed AI-assisted development with **GitHub Copilot**.

#### 3.7 The Whole Story on One Timeline

| Year | Event | Why it mattered |
| --- | --- | --- |
| 1991 | Linus Torvalds starts Linux | Creates the project that would need Git |
| 2002 | Linux adopts BitKeeper | Kernel gets distributed version control, temporarily |
| 2005 | BitKeeper license revoked; Linus writes Git in ~10 days | Git is born from a crisis, designed for speed and distribution |
| 2005 | Junio C. Hamano becomes maintainer | Steady leadership that continues today |
| 2008 | GitHub launches | Git gets a home and a social layer |
| 2018 | Microsoft acquires GitHub for $7.5 billion | Massive investment follows; core features become free |
| 2019 | GitHub Actions launches | Automation and CI/CD become built-in |
| 2021 | Copilot reaches general availability | AI pair programming arrives |
| 2023+ | Over 100 million developers | The industry standard, confirmed by numbers |

#### 3.8 Why This History Matters to You

Because the design goals of 2005 are the features you will thank in 2025. When `git log` is instant even in a repository with a million commits, that is the speed goal. When you commit on a plane, that is the distributed goal. When you create your tenth branch in one afternoon without thinking about cost, that is the non-linear-development goal. And when no company can ever take your history hostage, because you have the whole thing on your own laptop, that is the BitKeeper crisis, permanently answered.

### Chapter 4: What Git and GitHub Give You

You now know what Git and GitHub *are*. This chapter is about what they *do for you*, feature by feature, mapped to situations you will actually face. Treat it as the menu before the meal.

#### 4.1 What Git Gives You

**1. A time machine.** Every commit (Chapter 12) is a full snapshot of your project with a message, an author, and a timestamp. You can list them (Chapter 14), compare any two moments, and restore any file, or the entire project, to any point in history. The day you can say "make it like it was on Tuesday," you stop fearing change.

**2. Parallel universes (branches).** A branch (Chapter 16) is a separate line of work inside the same repository. You can build a risky new feature in a branch while your main version stays untouched and working, then merge it in only when it is good (Chapter 17). Before Git, branches were expensive rituals; in Git they cost 41 bytes and are created instantly, which is why professionals create branches as casually as saving a file.

**3. A safety net.** Git checksums every version with a cryptographic hash (Chapter 7). If anything in the history is ever corrupted or tampered with, Git knows. Combined with the reflog (Chapter 26), even "deleted" commits are usually recoverable for around 90 days.

**4. Total speed, fully offline.** History, branching, merging, and searching all happen on your own machine. No network, no server, no waiting.

**5. Blame and archaeology.** `git blame` (Chapter 14) tells you who last changed each line of a file, when, and in which commit, with the commit message explaining *why*. When you wonder "who wrote this and what were they thinking," Git answers with evidence instead of memory.

#### 4.2 What GitHub Gives You

**1. Cloud backup and access anywhere.** A pushed repository lives on GitHub's servers, so your laptop can fall in the ocean and your code survives. You can clone your work onto any machine in minutes (Chapter 22).

**2. Collaboration.** The heart of GitHub is the pull request (Chapter 23): a web page where teammates see your proposed changes, comment line by line, request fixes, approve, and merge. Add Issues for bug tracking, Projects for task boards, and you have the coordination hub of a whole team.

**3. Public proof of your work.** Your GitHub profile is a living portfolio. Recruiters and clients can see real code, real commits over time, and real contributions to real projects. For many self-taught developers, their GitHub profile does more work than their resume.

**4. Free hosting.** GitHub Pages (Chapters 25 and 33) turns a repository into a live public website for free, with an automated pipeline.

**5. Automation.** GitHub Actions (Part G) runs code on every push: tests, builds, deployments. Your project can test itself and deploy itself while you sleep.

**6. Security tooling.** Dependabot warns about vulnerable dependencies, secret scanning warns about leaked passwords, and security advisories help you respond to problems (Chapter 25).

**7. The home of open source.** Millions of public projects, from tiny libraries to the Linux kernel itself, accept contributions from strangers through forks and pull requests (Chapter 24). Learning that workflow makes you a citizen of the largest collaborative effort in software history.

#### 4.3 Map of Fear to Feature

| The day you say... | The feature that saves you |
| --- | --- |
| "It worked yesterday!" | History and `git diff` (Chapter 14) |
| "I want to try something crazy" | Branches (Chapter 16) |
| "We both edited the same file!" | Merge and conflict resolution (Chapters 17-18) |
| "I just destroyed a file" | `git restore` and the reflog (Chapter 26) |
| "My laptop died" | GitHub remote (Chapter 22) |
| "Does this change break anything?" | Automated tests on push (Part G) |
| "Who approved this change?!" | Pull request history and `git blame` |
| "I want a website for my project" | GitHub Pages (Chapter 33) |

---

### Chapter 5: Why You Should Use Git and GitHub

This chapter exists because a beginner who knows *why* tolerates the learning curve, and a beginner who does not, quits in Chapter 12. Here are the seven honest reasons, followed by the objections people raise.

#### 5.1 Reason One: Fearlessness

Without version control, your fear of breaking things makes you timid: you do not refactor, you do not experiment, you do not delete, because a mistake is unrecoverable. With version control, every experiment lives on a branch and every state is a commit away. Professionals are bold *because* they have a safety net, not despite it. Git converts "what if I break it?" into "worst case, I revert in 30 seconds."

#### 5.2 Reason Two: Teamwork Without Destruction

When two people edit the same folder over a shared drive, whoever saves last erases the other's work, silently. Git detects every overlap, and merge conflicts (Chapter 18), the scary thing beginners dread, are actually Git's honest way of saying "two people changed the same lines; a human must decide." That is a feature, not a bug: nothing is silently lost, ever.

#### 5.3 Reason Three: Memory and Documentation

Six months into a project, "why does this code skip validation?" becomes a mystery. Git answers with the commit that introduced the change, its message, its author, and its date. A project's commit history is a diary of decisions, and disciplined messages (Chapter 13) turn that diary into documentation that never goes stale, because it is attached to the exact code it describes.

#### 5.4 Reason Four: It Is the Industry Standard

Virtually every professional development environment uses Git. Job postings list it. Interviewers ask it (Chapter 38 has the questions). Teams assume it. Using anything else makes you the exception that must be argued for. Learning Git is not choosing a tool; it is learning the language the industry speaks.

#### 5.5 Reason Five: Your Public Portfolio

For students and career changers especially: GitHub is where proof lives. A profile with real projects, real commit history, and real contributions to open source outweighs a resume line saying "familiar with tools." Your green contribution squares are a visible record of consistency, and consistency is what employers screen for.

#### 5.6 Reason Six: Backup and Portability

"Pushed to GitHub" means your work exists in at least two places. Combined with how cheap cloning is, your development environment becomes reproducible on any machine on Earth in minutes. Writers, researchers, and data scientists increasingly use Git for exactly this reason, not for code per se.

#### 5.7 Reason Seven: The Gateway to Open Source

Every tool, library, and framework you will ever use is probably on GitHub, and many accept contributions. The fork-and-pull-request workflow (Chapter 24) is the front door of open source, and the first PR you get merged into a project you admire is a genuine career moment.

#### 5.8 Objections, Answered Honestly

**"I work alone, so I don't need it."** You will still make changes you regret, still need yesterday's version, still want your work backed up, and still want a portfolio. Solo developers benefit from four of the seven reasons above, at minimum.

**"I'm not a programmer."** Git tracks *files*, not code. Writers track chapters, designers track assets, researchers track datasets and papers. The commands in this guide never ask you to program.

**"It looks too hard."** The scary parts of Git (rebases, reflogs, plumbing) are the advanced 10%. Parts C and D of this guide cover the 90% used daily, and the hard parts come only after you have a foundation.

---

### Chapter 6: Understanding Version Control

Chapter 2 gave version control a one-paragraph definition. This chapter gives you the full concept, because understanding the three *architectures* of version control systems is what makes "distributed" finally click.

#### 6.1 The Goal, Restated

A version control system has one job: record the states of a set of files over time, so that any state can be retrieved, compared, and restored, and so multiple people can work without destroying each other. Every design below is a different answer to "where do we keep the versions?"

#### 6.2 Local Version Control

The first and simplest design keeps versions on your own machine. The folder-of-copies approach is local version control done by hand, and tools like RCS (1985) did it properly, storing compact deltas of each file version in a local database.

```text
 Your computer
 +--------------------+
 | project files      |<---> local version database
 +--------------------+
```

Its weakness is the word "local": if the disk dies, history dies; and only one person can use it. It solves the "folder of copies" problem and nothing else.

#### 6.3 Centralized Version Control (CVCS)

The 1990s answer was to put the version database on a server: CVS and later SVN. Every developer checks out files from the server and commits changes back to the server.

```text
            +------------------+
            |  CENTRAL SERVER  |   (holds all versions)
            +------------------+
              ^        ^     ^
              |        |     |
            Alice     Bob   Carol   (each holds only
                                     current files)
```

This solved sharing, and teams lived on it for years. But two structural flaws are baked into the design:

1. **Single point of failure:** clients hold only the latest files. If the server dies, the history is gone, and the project is in crisis until the server returns.
2. **No offline work:** to commit, you need the server, so a broken connection means a broken workflow.

#### 6.4 Distributed Version Control (DVCS)

Git's answer: every developer clones the entire repository, complete history included. Each copy is a full peer of the original.

```text
 Alice's laptop          Bob's laptop          Carol's laptop
 +---------------+        +---------------+     +---------------+
 | FULL history  |        | FULL history  |     | FULL history  |
 +---------------+        +---------------+     +---------------+
         ^                      ^                     ^
         +---------- all three synchronize ----------+
                                  |
                          (optional hub, e.g. GitHub)
```

Notice what disappears: there is no single point of failure (any clone can restore the project), and there is no required server (you commit locally always; network only when you choose to share). Notice also that GitHub, despite hosting millions of repositories, is technically *optional* to Git itself; it is the popular hub the arrows point at, not a required master.

#### 6.5 The Comparison on One Table

| | Local (RCS) | Centralized (SVN) | Distributed (Git) |
| --- | --- | --- | --- |
| Where history lives | Your machine | One server | Every clone |
| Needs network | Never | For almost everything | Only to share |
| Server dies | Nothing changes | Project in danger | Nothing changes |
| Branching | Primitive | Slow, expensive | Instant, cheap |
| Typical use today | Historic curiosity | Legacy projects | The industry default |

#### 6.6 Why Distributed Won

Distributed systems turned every weakness of the centralized model into a strength, and then one more feature (cheap branching) transformed how people write software entirely. When you create your first branch in Chapter 16 and notice it takes literally less time than it took to read this sentence, you are feeling the design decision that won the version control war.

---

### Chapter 7: How Git Works Under the Hood

This is the most important conceptual chapter in the guide. Everything after this point is easier once these five ideas are yours, and everything people find confusing about Git traces back to one of them.

#### 7.1 Idea One: Snapshots, Not Diffs

Older systems stored versions as chains of differences: "version 5 is version 4 plus these changes." To reconstruct a file, they replay every diff in order, which is slow for old files.

Git stores each commit as a **snapshot** of your entire project. When you commit, Git takes a "photograph" of every file as it is at that moment and stores the photo. Files that did not change since the previous snapshot are not stored twice; the snapshot simply references the earlier copy (this is how Git stays efficient without sacrificing the snapshot model).

```text
  Commit 1      Commit 2      Commit 3      Commit 4
     o   --------->  o  --------->  o  --------->  o
   [A][B]         [A][B]         [A][B']        [A][B']
                     ^              ^               ^
                  B unchanged     B changed       B unchanged,
                                   (stored once)  reuses commit 3's B
```

For you, this means: viewing, comparing, and restoring any version at any time is instant, because nothing needs to be reconstructed.

#### 7.2 Idea Two: Files Live in Three Areas

This is the picture to burn into your memory. On your computer, your files exist in three places, and every command you will ever learn moves files between them (or between your machine and GitHub):

```text
 +------------------+   git add    +------------------+  git commit  +------------------+
 |  WORKING         | ------------> |  STAGING        | -----------> |  LOCAL           |
 |  DIRECTORY       |               |  AREA           |              |  REPOSITORY      |
 |                  |               |                 |              |                  |
 |  The files you   |  <----------- |  The "next      |  <--------- |  The permanent   |
 |  see and edit    | git restore   |  photo", picked |  git reset / |  album of saved  |
 |                  |  --staged     |  by git add     |  checkout    |  snapshots       |
 +------------------+               +------------------+              +------------------+
                                                                             |          ^
                                                                             | git push | git pull
                                                                             v          |
                                                                      +------------------+
                                                                      |  REMOTE          |
                                                                      |  (e.g. GitHub)   |
                                                                      |  your cloud copy |
                                                                      +------------------+
```

- **The working directory** is the folder you see and edit. It is "real life."
- **The staging area** (also called the *index*) is a waiting room. `git add` places a file in the waiting room, meaning "I want this version included in the next snapshot." Why does the waiting room exist? Because it lets you commit *some* of your changes but not others: you can stage the two files you finished and leave the half-written one out of the photo.
- **The repository** is the permanent history stored inside the hidden `.git` folder. `git commit` photographs the staging area and seals it into history.
- **The remote** is your copy on GitHub. `git push` uploads new commits; `git pull` downloads them.

One sentence to repeat to yourself for the rest of this guide: **edit in the working directory, `git add` to select, `git commit` to save, `git push` to share.**

#### 7.3 Idea Three: Everything Has a Checksum

Git never stores "file number 7." Every version of every file, every directory listing, and every commit gets a unique ID computed from its exact contents, using the SHA-1 hash (a 40-character string like `5f2d4e8c9a1b...`; newer Git can also use SHA-256). You will see these IDs everywhere: in `git log` output, on GitHub commit pages, and in commands like `git show`.

Two magical properties follow:

1. **Same content means same ID.** If you and a stranger on another continent create the same file content, Git gives it the same ID. This is why cloning and merging are so reliable: identical things are recognized as identical anywhere on Earth.
2. **Change one byte and the ID completely changes.** This makes Git's history tamper-evident: corruption or unnoticed modification is automatically detected, because the stored ID would no longer match the content's true ID. This is why a Git repository's history is trustworthy in a way a folder of copies never can be.

#### 7.4 Idea Four: The Four Objects (A Peek Inside)

Deep inside `.git`, Git stores four kinds of objects, and Chapter 30 will let you hold them in your hands:

- A **blob** is the content of one file (just the bytes; even the filename is not stored in it).
- A **tree** is a directory listing: which filenames point to which blobs (and which trees, for subfolders).
- A **commit** is a snapshot reference (a tree) plus metadata: author, date, message, and the ID of the parent commit (which is why history forms a chain).
- An **annotated tag** is a named label attached to one commit (Chapter 21).

A commit, therefore, is a very small object: "this tree, this parent, this person, this message." That is why committing is instant even in huge projects, and it is why two people can hold identical histories with identical IDs.

#### 7.5 Idea Five: A Branch Is Just a Pointer

Here is the secret behind Git's famous cheap branching: a branch is nothing but a tiny file containing the ID (the checksum from Idea Three) of one commit. The file is 41 bytes (40 characters plus a newline). Creating a branch writes one small file; deleting one removes it. There is no copying of code, no heavy ceremony, nothing to be afraid of.

```text
                                     o feature-login   <- a 41-byte file
                                    /                      pointing HERE
   o ---- o ---- o ---- o ---- o                          <- the chain of
                                     ^                        commits
                                     main                   (each points
                                     ^                       to its parent)
                                    HEAD  <- "I am on main" (HEAD points
                                              to the current branch)
```

`HEAD` is Git's "you are here" marker: a special file that names the branch you currently have checked out. When you commit, the branch you are on (the file) is updated to point to the brand-new commit. That is all a branch "is," and when this clicks, `git branch`, `git switch`, fast-forward merges, and detached HEAD (Chapter 21) all stop being mysterious.

#### 7.6 Why This Chapter Was Worth It

When later chapters say "the staging area remembers the version you added, not the version on disk" (Chapter 14's `git diff`), or "rebasing replays commits onto a new parent" (Chapter 19), or "the reflog remembers where HEAD has been" (Chapter 26), they are all just combining the five ideas above. You have just learned the machinery of Git in miniature; the remaining chapters are practice with vocabulary.

## Part B: Getting Set Up

Part B turns your computer into a Git workstation and connects it to GitHub. Nothing here is difficult, but everything here is mandatory, and one skipped step (a wrong email, a missing SSH key) causes confusing errors much later. Follow every step, in order.

### Chapter 8: Installing Git on Windows, macOS, and Linux

#### 8.1 A Terminal Primer for Absolute Beginners

Git is a command-line program, which means you talk to it by typing commands in a **terminal** (also called a **shell** or **command prompt**). If you have never opened one, here is the 60-second orientation:

A terminal is a window where you type a command, press Enter, and the computer responds. The text that appears before your cursor, like `C:\Users\you>` on Windows or `you@MacBook ~ %` on macOS, is called the **prompt**. It means "I am ready for your command." The terminal always "is" somewhere: it has a **current directory** (the folder it is operating in), which you can print with the `pwd` command (print working directory), list with `ls` (macOS/Linux) or `dir` (Windows), and change with `cd` followed by a folder name, as in `cd Documents`. `cd ..` (two dots) means "go up to the parent folder."

How you open the terminal:

- **Windows:** press the Windows key, type `PowerShell`, and open it. (After installing Git, you will also have a friendlier option called **Git Bash**, explained below.)
- **macOS:** press Command + Space, type `Terminal`, and open it.
- **Linux:** it varies by distribution; typically press Ctrl + Alt + T, or search for "Terminal."

That is all the terminal knowledge you need to start. More vocabulary arrives when you need it.

#### 8.2 Installing Git on Windows

1. Open your browser and go to the official download page: `https://git-scm.com/download/win`. The site detects Windows and offers the correct installer automatically. Click it to download.
2. Run the downloaded `.exe` file. Windows may ask "Do you want to allow this app to make changes to your device?" Click **Yes**.
3. The installer walks you through several screens. The important ones, decoded:
   - **License screen:** click Next to accept the GNU General Public License (Git is free and open source).
   - **Select Components:** the defaults (Windows Explorer integration, Git LFS support, file associations) are fine. Click Next.
   - **Choosing the default editor:** the default is Vim, a powerful editor that beginners famously cannot exit. If you use (or will install) Visual Studio Code, choose **Visual Studio Code** here and future commit-message editing will open in a sane editor. You can change this later (Chapter 9).
   - **Adjusting your PATH:** choose **"Git from the command line and also from 3rd-party software."** This is the recommended option; it puts `git` on your PATH (the list of places Windows searches for programs) so the command works everywhere, including PowerShell.
   - **Choosing HTTPS transport backend:** leave the default (OpenSSL library).
   - **Configuring line ending conversions:** choose **"Checkout Windows-style, commit Unix-style line endings"** (the recommended default). Chapter 9 explains what this means and why it prevents a whole category of pointless conflicts.
   - **Terminal emulator:** keep MinTTY as the default. This gives you **Git Bash**, a small Linux-like terminal that ships with Git for Windows. Many tutorials (including this one) use Unix-style commands like `ls` and `cat`; they work perfectly in Git Bash, which is why Git Bash is recommended for following along on Windows.
   - **Credential manager:** keep the default (Git Credential Manager). It remembers your GitHub login so you do not retype it.
4. Finish the installer.
5. Verify the installation. Open a new terminal (PowerShell or Git Bash; it must be a *new* window so it picks up the updated PATH) and type:

```bash
git --version   # Ask which version of Git is installed
```

Expected output looks like:

```text
git version 2.47.1
```

If you see a version number, Git is installed and working. If you see `'git' is not recognized...`, close every terminal window, reopen one, and try again; if it still fails, the PATH option in step 3 was not selected, so rerun the installer and choose the recommended option.

#### 8.3 Installing Git on macOS

On macOS, the easiest route is through Apple's Command Line Tools, which include Git. Open the Terminal and run:

```bash
xcode-select --install    # Ask Apple's developer tools to install themselves (includes Git)
```

A dialog appears offering to install the tools. Click **Install**, accept the license, and wait a few minutes. Then verify:

```bash
git --version             # Confirm Git is now available
```

The alternative (or the way to get the very latest Git version) is Homebrew, macOS's popular package manager. Install Homebrew by pasting the command from `https://brew.sh` into your terminal, then run:

```bash
brew install git          # Download and install the latest Git via Homebrew
```

#### 8.4 Installing Git on Linux

Linux distributions install software through package managers. Use the one matching your distribution:

```bash
sudo apt update && sudo apt install git    # Debian, Ubuntu, Mint: refresh the package list, then install Git
sudo dnf install git                       # Fedora, RHEL
sudo pacman -S git                         # Arch Linux
sudo apk add git                           # Alpine Linux
```

The word `sudo` means "superuser do," i.e., run this with administrator rights; installing system software requires it, and you may be asked for your password. Verify afterward:

```bash
git --version    # Confirm the installation
```

#### 8.5 Updating Git Later

On macOS with Homebrew: `brew upgrade git`. On Linux: `sudo apt upgrade git` (or your equivalent). On Windows: rerun the installer from git-scm.com, or Git for Windows offers an update command inside Git Bash (`git update-git-for-windows`). Git is conservative software; a version one or two years old works fine for everything in this guide.

---

### Chapter 9: First-Time Configuration

#### 9.1 Why Configuration Exists

Every commit you make is stamped with the name and email of its author (this is how `git blame` and GitHub's contribution graphs work). Git refuses to guess your identity, so the very first configuration you must perform is telling it who you are. Configuration lives in plain text files, and Git reads settings from three levels, where the more specific level wins:

| Level | Flag | File it lives in | Typical use |
| --- | --- | --- | --- |
| System | `--system` | one file for every user of the machine | Rarely used |
| Global | `--global` | `~/.gitconfig` in your home folder | Your identity and preferences everywhere |
| Local | `--local` (default) | `.git/config` inside one repository | Settings that apply to one project only |

For the settings in this chapter, global is correct: you are one person with one identity.

#### 9.2 The Essential Settings, Word by Word

Open your terminal and run these three commands, replacing the quoted values with your own real information.

```bash
git config --global user.name "Your Real Name"
```

**Anatomy of the command:**

- `git` - the program
- `config` - the subcommand that reads or writes settings
- `--global` - the flag meaning "write this into my personal global file, so it applies to all my repositories"
- `user.name` - the *key* (the name of the setting); the dot notation means "the `name` key inside the `user` section"
- `"Your Real Name"` - the *value*; the quotes keep a name with spaces as one value

```bash
git config --global user.email "your_email@example.com"
```

Same anatomy; this sets the email stamped into every commit. **Critical detail:** use the *same email you will use for your GitHub account*. GitHub matches commits to your profile (and paints your contribution graph green) by matching this email address to your account. A mismatched email is the number one cause of "my commits don't show on my profile!" confusion.

```bash
git config --global init.defaultBranch main
```

- `init.defaultBranch` - the name Git gives to the first branch in every new repository
- `main` - the modern standard name (GitHub's default since 2020; older tutorials say `master`)

Setting this now means every new repository you create starts on `main`, matching what you will see on GitHub, avoiding the confusing "why does mine say master?" moment.

One more highly recommended setting if you use Visual Studio Code:

```bash
git config --global core.editor "code --wait"
```

- `core.editor` - the editor Git opens when it wants you to write a commit message (Chapter 13)
- `"code --wait"` - launch VS Code (`code`) and pause Git until you close the editor tab (`--wait`), so the message is captured

#### 9.3 Viewing Your Settings

```bash
git config --list              # Print every setting Git currently sees, key = value
git config --list --show-origin # Same, plus the file each setting came from (useful when debugging)
```

Sample output, decoded line by line:

```text
user.name=Your Real Name
user.email=your_email@example.com
init.defaultbranch=main
```

The first line reports your identity's name, the second your identity's email, the third your default branch name. If `user.name` is missing, you forgot step one.

#### 9.4 Line Endings (The Invisible Nuisance)

Operating systems disagree about how to end a line of text: Windows marks line ends with two characters (CRLF), while macOS, Linux, and the software world at large use one (LF). Git can normalize this so mixed endings never create fake "changes" or conflicts. The rule of thumb:

```bash
git config --global core.autocrlf true    # On Windows: convert LF to CRLF when checking out, CRLF to LF when committing
git config --global core.autocrlf input    # On macOS/Linux: keep LF on commit, nothing fancy on checkout
```

If Git ever prints `warning: LF will be replaced by CRLF`, that is this setting doing its job, not an error. Chapter 37 repeats this, because people panic about that warning weekly.

#### 9.5 Getting Help

Git has built-in documentation for every command, two ways:

```bash
git help config    # Open the full manual page for `git config` in your browser or terminal viewer
git config -h      # Print just the quick cheat-sheet of options for `git config` (the -h is short for --help summary)
```

Any command supports both forms; try `git help commit` later. Press `q` to quit the manual viewer.

#### 9.6 Changing Settings Later

Settings are just commands repeated: run the same command with a new value to overwrite. `git config --global --unset user.email` removes a setting entirely, and `git config --global --edit` opens the whole config file in your editor, where settings appear as plain text (the `--edit` flag means "open the file directly").

---

### Chapter 10: GitHub Account and SSH Connection

#### 10.1 Creating Your GitHub Account

1. Go to `https://github.com` and click **Sign up**.
2. Enter your email, create a password, and choose a **username**. Think about the username for one extra minute: it becomes your public profile URL (`github.com/yourname`), appears in your repository URLs, and shows up on every contribution you make. Short, professional, and matching your other professional handles is ideal. Renaming later is possible but touches every URL you have ever shared.
3. Verify your email address when GitHub sends the confirmation. Unverified accounts cannot use key features.
4. Choose the **Free** plan when asked. Free accounts get unlimited public and private repositories, GitHub Pages, and generous Actions minutes; nothing in this guide requires payment.

#### 10.2 The Two Ways to Talk to GitHub

Whenever you push or pull code, GitHub must verify you are really you. Two mechanisms exist:

- **HTTPS + a Personal Access Token (PAT):** you use normal `https://` repository URLs and authenticate with a token (a generated password-like string) instead of your account password (GitHub stopped accepting account passwords for Git operations in 2021). Works everywhere, even behind strict firewalls, but tokens expire and need management.
- **SSH keys:** you generate a cryptographic key pair on your computer, upload the public half to GitHub once, and from then on every push and pull is authenticated automatically, with no passwords and no expirations.

This guide uses SSH, and configures it once, now, so every later chapter "just works."

#### 10.3 What SSH Keys Are, in Plain Words

**SSH** (Secure Shell) is a protocol for securely logging in to remote machines. Its key-based authentication uses a pair of mathematically linked keys:

- The **private key** (for example `~/.ssh/id_ed25519`) stays on your computer, never leaves it, and is never shown to anyone. Think of it as your house key.
- The **public key** (the same filename plus `.pub`) is given freely to servers like GitHub. Think of it as the padlock that only your key fits.

When you connect, GitHub uses the public key to issue a challenge that only someone holding the private key can answer. Your identity is proven without any password traveling anywhere. The practical consequence for you: after one setup, `git push` works forever, from every terminal, with zero prompts.

#### 10.4 Generating Your Key Pair

In your terminal, run:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

**Anatomy of the command:**

- `ssh-keygen` - the key generation program
- `-t ed25519` - the `-t` flag selects the key *type*; `ed25519` is the modern, fast, secure algorithm (if some ancient system demands the older type, use `-t rsa -b 4096`)
- `-C "your_email@example.com"` - `-C` adds a **comment**; the comment travels inside the public key purely so you can recognize which key this is on crowded servers. It does not need to be your email, but the convention is to use it

The program now asks three questions:

1. `Enter file in which to save the key (/home/you/.ssh/id_ed25519):` - press **Enter** to accept the default location. The `~/.ssh` folder is where all SSH tools look.
2. `Enter passphrase (empty for no passphrase):` - a passphrase encrypts your private key so a stolen laptop's keys are useless. For a learning machine, pressing Enter twice (no passphrase) is acceptable and friction-free; security-conscious readers should type one.
3. It then prints a small "randomart" image and the key fingerprints. Nothing to do here; it is just proof of generation.

#### 10.5 Giving GitHub Your Public Key

Your public key is plain text sitting in `~/.ssh/id_ed25519.pub`. Display it:

```bash
cat ~/.ssh/id_ed25519.pub    # Print the public key to the screen (`cat` = concatenate/print a file)
```

You will see one long line beginning with `ssh-ed25519` and ending with your comment email. Select and copy the entire line, then:

1. On GitHub, click your profile photo (top right) and open **Settings**.
2. In the left sidebar, click **SSH and GPG keys**, then **New SSH key**.
3. **Title:** give it a name you will recognize years from now, like "My Ubuntu laptop."
4. **Key type:** leave as the default (Authentication Key).
5. **Key:** paste the copied line. The field should show `ssh-ed25519 ...` as a single line; if it wraps visually that is fine, but there must be no line breaks *inside* the text.
6. Click **Add SSH key**. GitHub may ask you to confirm with your password; this is normal protection for security changes.

Note what you did *not* upload: the private key. GitHub receives only the padlock; you keep the only key.

#### 10.6 Testing the Connection

```bash
ssh -T git@github.com
```

**Anatomy:** `ssh` is the client program; `-T` disables requesting a remote shell session (we only want to test authentication); `git@github.com` means "connect as the user named `git` on the host `github.com`" (GitHub authenticates every Git user as the user `git`, then tells them apart by their key).

The **first** time you connect, SSH has never met GitHub, so it asks:

```text
The authenticity of host 'github.com' can be blocked... continue connecting (yes/no/[fingerprint])?
```

Type `yes` and press Enter. This records GitHub's identity in `~/.ssh/known_hosts` so you are never asked again unless it changes. Then the real result appears:

```text
Hi yourname! You've successfully authenticated, but GitHub does not provide shell access.
```

**Decoded line by line:** `Hi yourname!` means GitHub recognized your key and knows which account it belongs to; `You've successfully authenticated` is the entire point of the test; `but GitHub does not provide shell access` is expected on a normal connection, because GitHub only offers Git operations, not an interactive login, and since you did not ask for a shell, everything is fine. If you saw this line, your computer and GitHub are now permanently, securely linked.

If instead you saw `Permission denied (publickey)`, Chapter 37's troubleshooting entry walks through the three usual causes.

## Part C: Git Fundamentals

Part C is the heart of daily Git use. By the end of Chapter 15 you will be able to create repositories, save versions of your work professionally, read the story of your project's history, and control exactly which files Git tracks. These five chapters cover what professional developers do 90% of the time they use Git.

### Chapter 11: Your First Repository

#### 11.1 What a Repository Is, Exactly

A **repository** (informally, a **repo**) is an ordinary folder that Git has been told to watch. Technically, the moment you run one command inside a folder, Git creates a hidden subfolder named `.git`, and from then on that folder is a repository: Git records the history of everything inside it (that you add) into that hidden folder. The folder with a hidden `.git` inside *is* the repository. Delete the `.git` folder and your project instantly becomes a plain folder again, with all your files intact but no history.

Decide where practice projects live (this guide assumes `~/git-practice`, i.e., a folder named `git-practice` inside your home directory) and let us begin.

#### 11.2 Creating a Repository with git init

Open your terminal and follow along. Every command is annotated.

```bash
mkdir ~/git-practice        # `mkdir` = make directory; creates the practice folder in your home (~)
cd ~/git-practice           # `cd` = change directory; move the terminal INTO the folder we just made
mkdir my-first-repo         # create the folder that will become our first repository
cd my-first-repo            # move into it
git init                    # THE command: tell Git "start watching this folder"
```

**Anatomy of the key command:**

- `git` - the program
- `init` - the subcommand, short for *initialize*: create the hidden `.git` folder and everything a repository needs

Output (recent Git versions):

```text
Initialized empty Git repository in /home/you/git-practice/my-first-repo/.git/
```

**What just happened (line by line):**

- `Initialized` - the setup was completed (note it says *empty*: no commits exist yet; you have a repository with no photographs in the album).
- `empty Git repository` - what was created: a repository containing nothing.
- `in /home/you/.../.git/` - *where* the machinery was created: inside a hidden folder named `.git` at the top of your folder.

Older Git versions may instead print a `hint:` line suggesting `git branch -M main`. That hint appears when your default branch is not `main`; if you configured `init.defaultBranch main` in Chapter 9, you will not see it, and if you do see it, simply run `git branch -M main` (explained below) to rename the branch.

Now prove the hidden folder exists:

```bash
ls            # list visible contents (prints nothing: the folder is empty)
ls -a         # `-a` = all, including hidden files (names starting with a dot)
```

The `ls -a` output shows `.` (this folder), `..` (parent folder), and **`.git`** - the entire "repository" in one hidden package. Optionally explore inside it with `ls .git`; you will meet its contents properly in Chapter 30.

One modern detail worth knowing: if you ever need `git init` to start on `main` without relying on config, use:

```bash
git init -b main    # initialize AND name the first branch "main" directly (the -b flag sets the initial branch name)
```

And if a repository was already created on an old branch name:

```bash
git branch -m main    # rename the current branch to "main" (`-m` = move/rename, like renaming a file)
```

#### 11.3 A Note on Re-Initializing

Running `git init` inside an existing repository is safe. Git notices and re-initializes without touching your history. It is one of the few Git commands you cannot misuse by repeating it.

#### 11.4 Cloning a Repository with git clone

Creating a repository locally is one way to start; downloading an existing one is the other. `git clone` takes a repository that lives somewhere else (usually GitHub) and makes a complete local copy, hidden history included.

```bash
cd ~/git-practice                       # go back to the parent folder where we keep projects
git clone git@github.com:octocat/Hello-World.git    # download a full copy of GitHub's classic demo repo
```

**Anatomy of the URL** (the address you passed to clone), piece by piece:

- `git@github.com` - the server to connect to, as the user `git`, over SSH (Chapter 10; the HTTPS form looks like `https://github.com/octocat/Hello-World.git`)
- `:` - separator between server and path
- `octocat` - the GitHub **account/organization** that owns the repository
- `Hello-World` - the **repository name**
- `.git` - conventional suffix marking this as a Git remote path (GitHub accepts the URL with or without it)

Output:

```text
Cloning into 'Hello-World'...
remote: Enumerating objects: 13, done.
remote: Counting objects: 100% (13/13), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 13 (delta 1), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (13/13), done.
```

**What just happened (line by line):** `Cloning into 'Hello-World'` announces the destination folder Git will create; `Enumerating objects` is the server listing what it has; `Counting... 100%` is the server finishing its inventory; `Compressing objects` is the server packing files for transfer; `Receiving objects: 100%` is your machine receiving and verifying everything. The result: a folder `Hello-World` that is a fully functional repository with complete history, as if you had created it yourself.

Useful variations:

```bash
git clone git@github.com:octocat/Hello-World.git my-copy    # clone into a folder named "my-copy" instead of "Hello-World"
git clone --depth 1 <url>                                    # "shallow" clone: only the latest snapshot, not full history (faster for huge projects)
```

#### 11.5 Deleting a Repository

Since a repository is just a folder plus a `.git` directory, deleting a repository means deleting that folder. For practice repositories, drag to trash or run `rm -rf my-first-repo` with care (`rm -rf` removes a folder and everything inside, recursively, without confirmation - only ever aim it at things you do not want). But wait before deleting this one: the next chapter works inside it.

> **Try it yourself:** create a second throwaway repository, run `ls -a`, delete only its `.git` folder, then run `ls -a` again. Watch the folder "forget" it was a repository. That single experiment teaches what a repository physically is.

---

### Chapter 12: The Core Daily Loop

This is the most important chapter in the guide. The loop you learn here - check status, stage changes, commit - is the loop you will run thousands of times in your career. We go slowly, with every output decoded completely.

#### 12.1 The Loop in One Picture

Recall the three areas from Chapter 7. The daily loop is just files walking through them:

```text
   edit files          git add          git commit
      v                   v                 v
 WORKING DIR  ------->  STAGING AREA  ------->  REPOSITORY
                  git status watches all of it
```

#### 12.2 Making Your First Change

Still inside `my-first-repo`:

```bash
echo "Hello, Git!" > hello.txt    # create a file named hello.txt containing the text "Hello, Git!"
```

**Anatomy:** `echo` prints text; the `>` symbol *redirects* that printed text into a file, creating it if needed (and overwriting if it exists). So this command is "make a file with one line in it," in terminal language. You could equally create the file with any text editor.

#### 12.3 Checking Status: git status

```bash
git status     # ask Git: "what is the current state of my files?"
```

Output:

```text
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.txt

nothing added to commit but untracked files present (use "git add" to track)
```

**What just happened (line by line):**

- `On branch main` - you are on the branch named `main` (Chapter 16 makes branches real; for now, note Git always tells you where you are).
- `No commits yet` - the album is still empty; this repository has never saved a snapshot.
- `Untracked files:` - a heading listing files Git can see but has never been told to care about.
- `(use "git add <file>..." ...)` - a hint telling you the exact command that changes this situation.
- `hello.txt` - the untracked file in question, indented under the heading.
- `nothing added to commit but untracked files present` - a summary: the staging area is empty, so a commit now would save nothing; the only thing happening is that one untracked file.

The word **untracked** is precise Git vocabulary: Git sees the file in your working directory, but it is in neither the staging area nor history. Your job now is to promote it, with `git add`.

#### 12.4 Staging: git add

```bash
git add hello.txt    # put hello.txt into the staging area ("include this file in the next snapshot")
```

**Anatomy:** `git` - the program; `add` - the subcommand that copies the current version of the named file into the staging area; `hello.txt` - the file to stage. Nothing is saved to history yet; the file is merely *selected*.

Check the effect:

```bash
git status
```

Output:

```text
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   hello.txt
```

**What just happened (line by line):** the section heading changed from `Untracked files:` to `Changes to be committed:` - the file has moved from "invisible to history" to "queued for the next snapshot"; the hint line now offers the *opposite* command (how to unstage, which Chapter 26 teaches); `new file: hello.txt` reports that this file is new to the repository, which is exactly how the first appearance of any file looks.

**The many faces of `git add`:**

```bash
git add hello.txt          # stage one specific file
git add hello.txt notes.md # stage two (or more) specific files, space-separated
git add .                  # stage everything in the current directory ("." means "here", and it recurses into subfolders)
git add -A                 # stage all changes anywhere in the repository (adds, modifications, deletions)
git add -u                 # stage all changes to files ALREADY tracked (updates modifications and deletions; ignores new files)
git add *.txt              # stage every file ending in .txt (shell expansion picks the names before Git sees them)
```

For your first months, `git add <file>` and `git add .` are all you need. Awareness of `-A` and `-u` prevents confusion when reading other people's commands.

#### 12.5 Saving: git commit

```bash
git commit -m "Initial commit: add greeting file"
```

**Anatomy of the command, word by word:**

- `git` - the program
- `commit` - the subcommand: photograph the staging area into permanent history (from the English *to commit*: to entrust for safekeeping)
- `-m` - a flag, short for *message*, meaning "the text following in quotes is my commit message" (without `-m`, Git opens your editor to write the message, which Chapter 13 covers)
- `"Initial commit: add greeting file"` - the message itself: a human-readable description of why this snapshot exists

Output:

```text
[main (root-commit) 7c9e4f2] Initial commit: add greeting file
 1 file changed, 1 insertion(+)
 create mode 100644 hello.txt
```

**What just happened (line by line):**

- `[main (root-commit) 7c9e4f2]` - the commit happened on branch `main`; `(root-commit)` marks it as the very first commit in the repository's history (it has no parent - the start of the chain from Chapter 7); `7c9e4f2` is the first seven characters of this commit's unique checksum ID (Chapter 7's Idea Three). Yes, your commit now has a fingerprint; you could run `git show 7c9e4f2` with it.
- `1 file changed, 1 insertion(+)` - the change summary: one file is different compared to the previous snapshot, one line was added.
- `create mode 100644 hello.txt` - a new file entered history. `create mode` means "this snapshot creates this file"; `100644` is the file's permission bits (a regular, readable, writable file - Unix shorthand you may blissfully ignore until Chapter 30).

Congratulations: your repository has history. Run `git status` again and it will now say `nothing to commit, working tree clean`, which is Git's phrase for "everything is saved; you and history agree perfectly."

#### 12.6 The Second Commit: Watching Modification

Edit `hello.txt` (add a second line with your editor, or `echo "Second line" >> hello.txt`, where `>>` *appends* instead of overwriting). Then:

```bash
git status
```

Output:

```text
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   hello.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

**What just happened (line by line):** `Changes not staged for commit:` is a new section - this file is *tracked* (it is in history) but its *current version* is not in the staging area; the two hints give you both exits (stage it, or discard it); `modified: hello.txt` names the state. Notice Git is not alarmed: a modified tracked file is normal everyday life. Stage and commit again:

```bash
git add hello.txt                      # select the new version
git commit -m "Add a second line to the greeting"   # save snapshot number two
```

#### 12.7 The Status Sections at a Glance

`git status` output always sorts your files into up to three sections, and reading them fluently is a genuine professional skill:

| Section heading | Meaning | How to advance it |
| --- | --- | --- |
| `Changes to be committed:` | In staging; will be in next commit | `git commit` |
| `Changes not staged for commit:` | Tracked file, modified on disk | `git add` it |
| `Untracked files:` | New file Git has never been told about | `git add` it |

#### 12.8 The Famous Shortcut

```bash
git commit -am "Update greeting"    # stage-and-commit every TRACKED modified file in one step
```

The `-a` flag (all) auto-stages modifications and deletions of tracked files before committing. It saves typing, with one sharp edge: it silently ignores **new** (untracked) files. Beginners have lost uncommitted new files to this assumption. Use it when you know every changed file belongs in the commit; otherwise stage deliberately.

#### 12.9 Common Misconceptions, Cleared Now

- **Saving in your editor is not committing.** Ctrl+S writes the file to disk (the working directory). Until you `git add` and `git commit`, history knows nothing.
- **Committing is not pushing.** Commits live on your machine. Uploading them to GitHub is `git push`, taught in Chapter 22, and this distinction matters daily.
- **You must re-stage after editing.** Staging records one version of the file. Edit after adding, and the new edits are unstaged again; stage again before committing.

> **Try it yourself:** make three small files, stage only two, commit, and run `git status`. See the third waiting in `Untracked files:`. Then add and commit it as a second commit. You have just exercised the full loop.

---

### Chapter 13: Writing Great Commit Messages

#### 13.1 Why Messages Matter

A commit without a message is a photograph without a caption: someday you will stare at a list of fifty snapshots all saying `update` and understand nothing. Commit messages are letters to your future self and your teammates; six months from now, the message is often the *only* clue to why code changed. Treat every message as the answer to: "if someone saw only the list of changes, what one line would explain *why* I made them?"

#### 13.2 The Format of a Good Message

```text
Add login rate limiting

Users were being locked out by brute-force attempts targeting
the auth endpoint. This commit adds a 5-attempts-per-minute
limit per account, with a clean 429 response.

The limit is stored in Redis so it works across all app servers.
```

The rules this example follows, and why:

- **Subject line under about 50 characters, in the imperative mood:** "Add login rate limiting" reads as an instruction ("this commit will: add rate limiting"), not a diary entry. Compare "added some stuff for login" - vague, past-tense, no information.
- **A blank line between subject and body** when a body exists; tools rely on it.
- **Body wrapped at about 72 characters**, so the text is readable in every terminal and on GitHub.
- **The body explains what and why, never how.** The code diff already shows how. The message answers the questions the diff cannot: what motivated this, what problem existed, what the intended effect is.

#### 13.3 Conventional Commits: Messages That Machines Can Read

Most professional teams adopt **Conventional Commits**, a standard that prefixes the subject with a *type* (and optionally a *scope*):

```text
feat(auth): add password reset flow
fix(cart): stop double-charging on refresh
docs: rewrite installation steps in README
```

**Anatomy:** the *type* declares the kind of change; the optional *scope* in parentheses narrows it to a part of the system; a colon separates prefix and description. The standard types you will use constantly:

| Type | Meaning |
| --- | --- |
| `feat` | A new feature for the user |
| `fix` | A bug fix for the user |
| `docs` | Documentation only |
| `style` | Formatting, whitespace, no logic change |
| `refactor` | Code change that neither fixes a bug nor adds a feature |
| `test` | Adding or changing tests |
| `chore` | Maintenance: tooling, configs, dependencies |
| `perf` | Performance improvement |
| `ci` | Changes to CI/CD configuration |

Why teams accept this discipline: automation reads it. Tools generate changelogs from `feat` commits, release numbers bump from `fix`/`feat` types, and reviewers know what they are about to read before opening the diff. When you reach Chapter 23 and 31, you will see pull requests and pipelines built around exactly this convention.

#### 13.4 Letting the Editor Write the Message

Omitting `-m` opens the editor you configured in Chapter 9:

```bash
git commit          # open the configured editor to write a full multi-line commit message
```

The editor shows commented hints at the bottom (lines starting with `#` are ignored). Write your subject, blank line, body, save, close - the commit completes. This is how you write the rich messages from section 13.2.

#### 13.5 Fixing the Last Commit: git commit --amend

Two amending situations, both safe *only before you have pushed* (Chapter 22; amending a pushed commit rewrites history and confuses everyone else, which Chapter 19 explains in depth):

```bash
git commit --amend -m "better message"     # replace the last commit's message with a corrected one
git add forgotten-file                     # stage the file you forgot...
git commit --amend --no-edit               # ...and fold it into the last commit, keeping the same message
```

**Anatomy:** `--amend` means "modify the most recent commit instead of creating a new one." Conceptually, Git creates a new snapshot containing the staged changes plus the last commit, and points the branch at it; the old commit quietly retires. `--no-edit` says "reuse the existing message."

#### 13.6 Atomic Commits: The Habit of Professionals

An **atomic commit** is one commit for one logical change. "Add search box UI" and "Fix search API pagination bug" are two logical changes; commit them separately, even though you finished both at 2 a.m. The discipline pays forward into almost every advanced technique in this guide: a clean history can be reverted commit-by-commit when something breaks (Chapter 26), cherry-picked onto release branches (Chapter 27), and bisected to find exactly which change broke the build (Chapter 27). Mixed-up histories make all three of those operations painful, so the habit starts now, with your next commit.

### Chapter 14: Inspecting History with log, show, and diff

Saving history is half of Git; reading it back fluently is the other half. This chapter teaches the three inspection commands you will use every single day: `git log` to see *which* snapshots exist, `git show` to examine *one* snapshot, and `git diff` to see *exactly what text changed* between two moments.

#### 14.1 git log: The Story of Your Project

With two or more commits in `my-first-repo`, run:

```bash
git log    # print the repository's commit history, newest first
```

Output:

```text
commit 9a8b7c6d5e4f3a2b1c0d9e8f7a6b5c4d3e2f1a0b (HEAD -> main)
Author: Your Real Name <your_email@example.com>
Date:   Mon Oct 6 10:14:22 2025 +0200

    Add a second line to the greeting

commit 7c9e4f2a1b3c4d5e6f7a8b9c0d1e2f3a4b5c6d7e
Author: Your Real Name <your_email@example.com>
Date:   Mon Oct 6 10:02:47 2025 +0200

    Initial commit: add greeting file
```

**What just happened (line by line), for the first commit entry:**

- `commit 9a8b7c6...` - the commit's full unique checksum ID (Chapter 7). This is the handle by which you can request this snapshot in other commands.
- `(HEAD -> main)` - decoration: `HEAD` (your "you are here" pointer) is on `main`, and this is the commit it points to. On the second entry the decoration is absent - HEAD is not there.
- `Author:` - who made the commit; the name and email come from your Chapter 9 configuration, which is why that chapter insisted you set them.
- `Date:` - when, with timezone.
- A blank line, then the commit message, indented.
- Older entries follow, separated by blank lines, newest first, walking the parent chain (Chapter 7's Idea Four).

**Quitting the viewer:** if history is long, `git log` opens a scrollable pager. Press `q` to quit, the spacebar to page down, and `/something` to search for text. Everyone's first week includes ten minutes stuck in this pager; you have now skipped those.

#### 14.2 The log Flags Worth Memorizing

```bash
git log --oneline      # one line per commit: short ID + message (the 7-char ID is plenty: collision odds are astronomically small)
git log -n 3           # show only the 3 most recent commits (any number works)
git log --stat         # append each commit's changed-file summary and insertion/deletion counts
git log -p             # append each commit's full text diff (patch mode)
git log --graph --all --decorate --oneline   # draw branches, all branches, with names, compact (addictive once you branch)
git log --author="Real Name"   # filter by author
git log --grep="login"         # filter by message content
git log --since="2 weeks ago"  # filter by time
git log -- hello.txt           # show only the commits that touched hello.txt
git log --follow -- hello.txt  # same, but keep following the file across renames
```

Sample `--oneline --graph --all` output for a repo with a branch (Chapter 16 will make this picture real for you):

```text
* 3f2a1b4 (feature-color) Change page to dark theme
| * 9c8d7e6 (HEAD -> main) Fix typo on homepage
|/
* 5e4f3a2 Add homepage
* 7c9e4f2 Initial commit: add greeting file
```

Each `*` is a commit; the vertical lines show which history each commit belongs to; `(HEAD -> main)` marks where you stand; the merge point of the two lines is where `feature-color` diverged from `main`.

#### 14.3 Referring to Commits: HEAD and Its Relatives

Commands accept commit IDs, but also a family of relative names you will use constantly:

```text
HEAD       the commit you are currently standing on
HEAD~1     one commit before HEAD (its parent)
HEAD~2     two commits before HEAD
7c9e4f2    any full or abbreviated commit ID works the same way
main       the tip (latest commit) of branch main
```

So `git show HEAD~1` means "show me the snapshot before this one," a phrase you will type weekly.

#### 14.4 git show: Examine One Snapshot

```bash
git show            # show the newest commit: its message plus its diff
git show HEAD~1     # show the commit before it
git show 7c9e4f2    # show any commit by ID
git show HEAD:hello.txt    # show the CONTENT of hello.txt as it was in that snapshot (note the colon syntax)
```

`git show` is the microscope: one commit, its author, its message, and precisely what changed in it.

#### 14.5 git diff: Reading Change Like a Professional

`git diff` is the command professionals run most, and its output is the classic "wall of confusing symbols" for beginners. After this section it will read like a sentence. The three questions `git diff` answers, each with its own form:

```bash
git diff                 # Q1: "What have I edited on disk that is NOT staged yet?" (working directory vs staging area)
git diff --staged        # Q2: "What is staged that is NOT committed yet?" (staging area vs last commit; --cached is the older synonym)
git diff HEAD            # Q3: "What will differ, on disk or staged, from my last commit?" (everything vs last commit)
git diff 7c9e4f2 9a8b7c6  # compare two commits directly
git diff main feature-color  # compare the tips of two branches
git diff --stat          # skip the text; show a per-file change summary table only
```

Now, the crucial part - reading the output. Modify `hello.txt` (change the second line), and run `git diff`:

```text
diff --git a/hello.txt b/hello.txt
index 3b18e51..d86c691 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1,2 +1,2 @@
 Hello, Git!
-Second line
+Second line, edited for clarity
```

**What just happened (line by line):**

- `diff --git a/hello.txt b/hello.txt` - the header: a diff between two versions of `hello.txt`. The `a/` version is the "old side"; `b/` is the "new side." (Mentally: a = before, b = before-you-know.)
- `index 3b18e51..d86c691 100644` - internal bookkeeping: the checksums (Chapter 7 again) of the old and new blob objects, and the permission mode. You will never need to read this line consciously.
- `--- a/hello.txt` - the minus side is the older version.
- `+++ b/hello.txt` - the plus side is the newer version.
- `@@ -1,2 +1,2 @@` - the *hunk header*, the line everyone squints at. It says: in the old file, starting at line 1, 2 lines are shown; in the new file, starting at line 1, 2 lines are shown. Every `@@` header announces "here is one block of context where changes live."
- ` Hello, Git!` - a *context line* (one leading space): unchanged text printed so you know where you are in the file.
- `-Second line` - a minus line: text as it was in the old version. Red on GitHub and in terminals.
- `+Second line, edited for clarity` - a plus line: the replacement text in the new version. Green on GitHub and in terminals.

That is the entire secret code: **minus lines existed before, plus lines exist after, `@@` counts where.** Every diff you ever read - from Git, GitHub, or code review - is just these five elements repeated.

#### 14.6 git blame: Who Changed This Line

```bash
git blame hello.txt     # print every line of the file, each prefixed with: commit ID, author, date, line number
git blame -L 5,10 app.js    # only lines 5 through 10
```

Sample line of output:

```text
9a8b7c6 (Your Real Name 2025-10-06 10:14:22 +0200 2) Second line, edited for clarity
```

**Decoded:** commit `9a8b7c6` last touched this line; `Your Real Name` on that date and time; it is line `2` of the file; then the line's text. Despite its name, blame is an archaeology tool, not an accusation tool; the commit message behind that ID usually explains *why* (`git show 9a8b7c6`). Teams with healthy cultures say "blame the commit, never the committer."

#### 14.7 git shortlog: Counting Contributions

```bash
git shortlog -sn    # list each author with their commit count, sorted; quick "who is most active here" view
```

A surprisingly honest tool for understanding unfamiliar open source projects in ten seconds.

---

### Chapter 15: The .gitignore File

#### 15.1 The Problem: Not Everything Belongs in History

Real projects produce files that must never be committed: folders of installed dependencies (`node_modules` can hold tens of thousands of files that are rebuilt from a manifest anyway), build output (`dist/`, `*.o` files), secret configuration (`.env` files holding database passwords and API keys - leaking these is a genuine security incident), logs, cache, and operating-system junk (macOS's `.DS_Store`, Windows' `Thumbs.db`). Git happily tracks all of it unless you teach it otherwise, and the teaching tool is a file named, with charming literalness, `.gitignore`.

#### 15.2 Creating the File

Create a plain text file named exactly `.gitignore` (dot included; it is a "hidden" file by convention) at the top of your repository, and commit it like any other file, so teammates inherit the same rules. Its content is a list of *patterns*: one pattern per line, each describing files to ignore.

#### 15.3 The Pattern Language, Rule by Rule

```text
# a comment: lines starting with # are ignored          <- comments explain rules to humans
node_modules/     # any directory named node_modules, at any depth (trailing slash = "must be a directory")
*.log             # * matches any characters, so this is every file ending in .log, anywhere
build/            # every directory named build, at any depth
/build            # only the build directory at the REPO ROOT (leading slash anchors the pattern to the top)
!important.log   # the ! negation: DO track this one file, even though *.log above says ignore it
docs/**/*.pdf     # ** matches any depth of directories: all PDFs anywhere under docs/
temp?             # ? matches exactly ONE character: temp1, tempA, but not temp12
.DS_Store         # macOS junk file, by exact name
.env              # secrets live here: this single rule has prevented a thousand security incidents
```

Rules worth internalizing:

- **Order matters for negation:** a later `!` rule can re-include what an earlier rule excluded (but a directory excluded wholesale cannot have files re-included inside it).
- **Ignored means "untracked-new."** If a file is already tracked (already committed), `.gitignore` does not retroactively erase it. To stop tracking an already-committed file while keeping it on disk:

```bash
git rm --cached settings.local.json    # remove the file from Git's index (history of future snapshots) but keep it in your working directory
git commit -m "chore: stop tracking local settings"
```

`--cached` is the crucial flag: without it, `git rm` deletes the file from disk too.

- **Global ignores** exist for junk you never want in any project (`.DS_Store` for everyone, editor folders): `git config --global core.excludesFile ~/.gitignore_global`, then list those patterns in that file once.

#### 15.4 A Real .gitignore for a Node.js Project

```text
# Dependencies: reinstalled with `npm install`, never committed
node_modules/

# Build output: generated by the build step, rebuilt on demand
build/
dist/

# Secrets and local configuration: MACHINE-specific, DANGEROUS to share
.env
.env.local
*.pem

# Logs and caches
*.log
npm-debug.log*
.cache/

# Operating system junk
.DS_Store        # macOS folder metadata
Thumbs.db        # Windows thumbnail cache

# Editor junk
.vscode/          # per-person editor state (some teams commit chosen shared settings with ! rules)
*.swp             # Vim swap files
.idea/            # JetBrains editor state
```

#### 15.5 Finding Ready-Made Ignore Files

You do not write these from scratch. GitHub maintains a famous repository of templates (search "github gitignore" - it lists hundreds of languages and tools; copy `Node.gitignore` or `Python.gitignore` as a starting point), and the site gitignore.io generates combined files ("generate one for Node + VS Code + macOS" in one click). Also, Chapter 22 will show GitHub offering to add one automatically when you create a repository.

#### 15.6 Checking What Is Ignored

```bash
git status --ignored           # show ignored files too, under an "Ignored files:" section
git check-ignore -v hello.txt  # ask Git which rule (file, line number, pattern) decides a file's fate
```

`git check-ignore -v` output like `.gitignore:2:*.log	build/debug.log` decodes to: "the file `.gitignore`, line 2, pattern `*.log`, is why `build/debug.log` is ignored." Indispensable when a file mysteriously refuses to be tracked.

> **Try it yourself:** create a `.gitignore` with `*.log`, make `a.log` and `important.log` plus a `!important.log` rule after the first, run `git status`, and verify only `a.log` is ignored. Then create a file, commit it, ignore its pattern, and watch Git keep tracking it - then fix it with `git rm --cached`.

## Part D: Branching and Merging

Branching is the feature that made Git famous. In this part you will create parallel lines of work, weave them back together, survive the legendary merge conflict, learn to rewrite history safely with rebase, park unfinished work in a stash, and mark releases with tags. Everything here builds directly on Chapter 7's "a branch is just a pointer" idea.

### Chapter 16: Branches

#### 16.1 What You Already Know

From Chapter 7: a branch is a 41-byte pointer to one commit; `HEAD` is a pointer to the branch you are on; committing advances the branch you are on. If you truly own those three sentences, everything in this chapter is just vocabulary. If you skimmed Chapter 7, this paragraph is your invitation to return.

Practically, a branch is a *label you give to a line of work*. Develop a feature on its own branch, and your `main` version stays untouched and stable the whole time; if the experiment fails, delete the branch and `main` never knew. This is why professionals branch for almost every change, even alone.

#### 16.2 Seeing and Creating Branches

Inside `my-first-repo`:

```bash
git branch            # list local branches (a plain list, with one marker)
```

Output:

```text
* main
```

**What just happened:** there is exactly one branch, `main`, and the `*` (asterisk) marks the branch you are currently on. Remember `HEAD` from Chapter 7: the starred branch is simply where HEAD points.

```bash
git branch feature-greeting    # create a new branch named feature-greeting (pointing at the same commit as main)
```

**Anatomy:** `git branch` + a name = create a pointer with that name. Note what did *not* happen: your files did not change, and you did not *move* to the new branch. Creating a branch and switching to it are separate actions (two commands, or one flag, next).

#### 16.3 Switching Branches

```bash
git switch feature-greeting    # move yourself (HEAD) onto the feature-greeting branch
```

Output:

```text
Switched to branch 'feature-greeting'
```

Your working directory now reflects that branch. Nothing visibly changed, because both branches point at the same commit - but edit a file, commit, and switch back, and the change will *vanish and reappear* as you switch. That vanishing act is not magic: switching branches rewrites your working directory files to match the snapshot of the branch you switch to. (Commit or stash your changes before switching, or Git will either carry uncommitted changes along or refuse to switch to protect you - the refusal message is Chapter 37's "local changes would be overwritten" entry.)

Two forms you must know:

```bash
git switch -c feature-greeting    # create AND switch in one step (the -c flag means "create first, then switch")
git switch -                      # switch to the PREVIOUS branch you were on (hyphen, like `cd -`)
```

**A note on `git checkout`:** older tutorials (and millions of veterans) use `git checkout -b feature-greeting` to create-and-switch. `checkout` is the old multi-purpose command; in 2019 Git split its duties into the safer, clearer `switch` (for branches) and `restore` (for files, Chapter 26). Both work everywhere; this guide teaches the modern pair, so you can read the classics.

#### 16.4 The Full Branch Cycle, Live

Let us run one complete, realistic cycle in the practice repo, with every step annotated.

```bash
git switch main                          # start from main (our stable line)
git switch -c feature-color              # create + switch to a new line of work
echo "color: dark" > theme.txt           # create a new file on this branch
git add theme.txt                        # stage it
git commit -m "feat: add dark theme file"    # commit it (now feature-color is 1 commit ahead of main)
git log --oneline                        # verify: your new commit is on top; (HEAD -> feature-color)
git switch main                           # go back to main...
ls                                        # ...and see theme.txt is GONE (it exists only on the other branch)
git switch feature-color                 # come back...
ls                                        # ...and theme.txt is back. Same folder, two realities.
git branch -v                            # list branches with each one's latest commit ID and message
```

Sample `git branch -v` output:

```text
  feature-color 3f2a1b4 feat: add dark theme file
* main          9a8b7c6 Add a second line to the greeting
```

**Decoded:** each line is a branch, its tip commit's short ID, and that commit's message; the `*` says you are currently on `main` - which is *behind* `feature-color` by one commit. The two branches are two labels on the same timeline, one pointing one commit later.

#### 16.5 Renaming and Deleting Branches

```bash
git branch -m feature-color feature-dark-theme    # rename a branch (-m, like renaming a file)
git branch -m main-work                            # with ONE name: rename the branch you are ON
git branch -d feature-dark-theme                   # delete the branch (-d = delete, but only if its work is merged)
git branch -D experiment-gone-wrong               # delete FORCEFULLY, even if unmerged (-D = uppercase = override safety)
```

The `-d` vs `-D` distinction is Git protecting you: `-d` refuses to delete a branch whose commits are not reachable from another branch (i.e., deleting would lose work); `-D` says "I am certain, delete anyway." If you ever `-D` by mistake, the reflog (Chapter 26) can usually recover it - remember that Git almost never truly loses committed work.

Branch names should be lowercase, hyphenated, and descriptive of intent: `feature/login-form`, `fix/cart-total`, or the compact `feat/login-form` you will see in the wild. Vague names like `stuff`, `test2`, and `john-branch` are how merge lists become archaeology puzzles.

#### 16.6 Why "Branches Are Cheap" Matters

Some older systems took seconds (or minutes) to copy the whole project per branch; Git takes microseconds to write one pointer. The cultural consequence: professionals branch *constantly and casually* - one branch per feature, per bugfix, per experiment, per typo. Do not ration branches; you have an unlimited supply. The only rule is: `main` stays healthy, work happens on branches (formalized in Chapter 23 as GitHub Flow).

---

### Chapter 17: Merging Branches

#### 17.1 What Merging Means

Two branches have grown apart; **merging** combines their work into one. You merge *into* the branch you are standing on: sit on `main`, run `git merge feature-dark-theme`, and Git weaves the feature's commits into main's line. The golden setup sentence: **"To merge X into Y, first switch to Y, then merge X."**

#### 17.2 The Simple Case: Fast-Forward

The simplest merge happens when your current branch has *not moved* since the other branch was created. Restore the practice setup (`feature-color` exists, one commit ahead of `main`), then:

```bash
git switch main                    # stand on the branch we merge INTO
git merge feature-color             # pull feature-color's work into main
```

Output:

```text
Updating 9a8b7c6..3f2a1b4
Fast-forward
 theme.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 theme.txt
```

**What just happened (line by line):** `Updating 9a8b7c6..3f2a1b4` names the two endpoints of the operation (old tip of main, tip of feature); `Fast-forward` is the interesting word: main had no new commits of its own, so Git did not need to *combine* anything - it simply slid the `main` pointer forward to the feature's commit. A diagram of what happened:

```text
 BEFORE merge                                AFTER merge

 o---o---o  feature-color                    o---o---o  feature-color
         \                                           \
          o  main (behind)                            o  main (MOVED FORWARD to here)
```

- `theme.txt | 1 +` - the change summary: one file, one added line.
- `create mode 100644 theme.txt` - the file entered main's history, same wording as Chapter 12.

#### 17.3 The Interesting Case: Three-Way Merge

When *both* branches have new commits (the common real case), there is no simple "slide forward"; Git must combine two divergent timelines, and it creates a new commit that has **two parents**.

Set it up: commit a change on `main` (e.g., `echo "note" > notes.md`, add, commit), and commit another change on `feature-color` (e.g., add a second line to `theme.txt`, add, commit). Now:

```bash
git switch main                # merge INTO main
git merge feature-color        # combine the divergent histories
```

Git opens your editor with a pre-filled message:

```text
Merge branch 'feature-color'
```

Keep that message (save and close). Output:

```text
Merge made by the 'ort' strategy.
 theme.txt | 1 +
 1 file changed, 1 insertion(+)
```

**What just happened (line by line):** the editor opened because a *merge commit* was being created and Git insisted it have a message; the default message simply names what was merged into what - that is the convention. `Merge made by the 'ort' strategy` says Git used its standard recursive three-way merge algorithm (the name of the internal strategy is trivia; "ort" is just its codename). The summary lines list what the merge brought in. The history now looks like this:

```text
 o---o---M   main    (M = merge commit, TWO parents)
  \      \
   o---o--/  feature-color
```

The merge commit `M` points back to *both* the previous tip of `main` and the tip of `feature-color`, so history records not only the changes but the *shape* of the collaboration.

#### 17.4 Forcing the Merge Commit: --no-ff

Some teams dislike invisible fast-forwards (they erase the evidence that a feature branch existed) and configure the habit:

```bash
git merge --no-ff feature-color    # "--no-ff" = "no fast-forward": ALWAYS create a merge commit, even when a slide would do
```

The resulting history shows explicit `Merge branch 'feature-color'` nodes for every feature - a readable changelog-shaped history at the cost of more commits. Teams choose per taste; now you can read both.

#### 17.5 After the Merge: Cleanup

```bash
git branch -d feature-color    # the merged branch is now redundant; -d works because its work is reachable from main
```

Deleting a *merged* branch deletes only the label, never the commits: they are now part of main's history. The branch pointer itself was just a sticky note, exactly as Chapter 7 promised.

#### 17.6 Two Everyday Merge Verbs

```bash
git merge --abort    # mid-merge panic button: restore everything to the pre-merge state (invaluable during conflicts)
git merge main        # run from a FEATURE branch: brings main's latest work into your feature (keeping it current)
```

The second form is the courtesy merge you will do dozens of times: keeping your feature branch up to date with main so the final merge is small and boring. Boring merges are the goal; Chapter 18 handles the day a merge refuses to be boring.

---

### Chapter 18: Merge Conflicts: The Complete Walkthrough

#### 18.1 What a Conflict Actually Is

A conflict is Git saying, with total honesty: *"You changed line X of file F in branch A, and someone (or you, on another branch) changed line X of file F in branch B. I can combine histories, but I cannot combine intents. A human must decide the text."* Conflicts are not errors, corruption, or punishment - they are the price of Git never silently choosing for you. Learn this chapter calmly once, and conflicts lose their terror permanently.

#### 18.2 Building a Real Conflict, Step by Step

We will manufacture a small conflict in the practice repo and resolve it completely.

```bash
git switch main                                  # start on main
echo "Welcome to my site" > page.txt             # create page.txt with one greeting line
git add page.txt                                # stage it
git commit -m "feat: add welcome page"           # commit on main
git switch -c feature-headline                  # new branch from here
echo "Welcome to my AWESOME site" > page.txt     # on the branch, change THE SAME LINE
git add page.txt                                 # stage
git commit -m "feat: punchier headline"          # commit on the feature branch
git switch main                                  # back to main...
echo "Welcome to my humble site" > page.txt      # ...and change THE SAME LINE, differently
git add page.txt                                 # stage
git commit -m "feat: humble headline"            # commit on main
```

Now main and feature-headline have each changed the one line of `page.txt` to different text. The histories diverged with two incompatible intents for the same line. Merge:

```bash
git merge feature-headline       # attempt the weave
```

Output:

```text
Auto-merging page.txt
CONFLICT (content): Merge conflict in page.txt
Automatic merge failed; fix conflicts and then commit the result.
```

**What just happened (line by line):**

- `Auto-merging page.txt` - Git tried to combine the file automatically (it can and does merge most changes silently).
- `CONFLICT (content): Merge conflict in page.txt` - the specific spot where automatic combination is impossible: content conflict, in this file.
- `Automatic merge failed; fix conflicts and then commit the result.` - your instruction manual for the next minutes, in one sentence: fix, then commit. Git has not crashed; it has paused, waiting for you.

#### 18.3 Reading the Battlefield: status and the File

```bash
git status
```

The relevant part of the output:

```text
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   page.txt
```

**Decoded:** `You have unmerged paths` - the merge is paused mid-flight; the two hints are the two exits (finish it, or abort it); `both modified: page.txt` is the conflict category: *both* branches modified this file. Other categories exist (`deleted by them`, `added by us`, and friends) but they are rarer and the resolution process is identical: inspect, decide, `git add`.

Now the famous part. Open `page.txt` in your editor:

```text
<<<<<<< HEAD
Welcome to my humble site
=======
Welcome to my AWESOME site
>>>>>>> feature-headline
```

**The conflict markers, line by line - memorize these five roles:**

- `<<<<<<< HEAD` - begins the section, and names the *first* side: HEAD, i.e., the branch you are standing on (main). The lines below it are *your current branch's version*.
- `Welcome to my humble site` - main's version of the contested lines.
- `=======` - the dividing line between the two contenders (seven equals signs, exactly).
- `Welcome to my AWESOME site` - the *incoming* branch's version (the branch being merged in).
- `>>>>>>> feature-headline` - ends the section, naming the second side: the branch being merged.

Neither line, and no marker, is allowed to survive into the final file. You resolve a conflict by *editing the file into the version that should exist in the future*.

#### 18.4 Resolving: Your Four Choices

Edit `page.txt`. You have four legitimate resolutions, and picking among them is a *human* decision, not a Git one:

1. **Keep yours:** delete the markers, the other side, keep `Welcome to my humble site`.
2. **Keep theirs:** delete markers and your side, keep `Welcome to my AWESOME site`.
3. **Combine into something new:** the classic team answer - delete the markers and write a third, best line, e.g., `Welcome to my awesome and humble site`.
4. **Keep nothing:** delete both lines entirely (sometimes the right call).

Suppose you choose the combined third option; the final file is:

```text
Welcome to my awesome and humble site
```

No markers, no sides - just the version that should exist going forward. Save the file.

#### 18.5 Completing the Merge

```bash
git add page.txt        # tell Git: "page.txt is now resolved as staged" (add marks a conflict RESOLVED)
git status              # verify: no more "Unmerged paths"; instead "All conflicts fixed but you are still merging"
git commit              # complete the merge; the editor opens with the default message "Merge branch 'feature-headline'" - keep it, save, close
```

Output:

```text
[main 6d7e8f9] Merge branch 'feature-headline'
```

The merge commit is created, the branch timelines are woven, and `git log --oneline --graph` will show you the diamond shape of a resolved divergence. Then the usual cleanup:

```bash
git branch -d feature-headline    # the feature branch's work is merged; remove the sticky note
```

#### 18.6 The Panic Button

At any point before you `git add` the resolved files:

```bash
git merge --abort    # cancel the entire merge and restore the repository to its pre-merge state, exactly
```

`--abort` is not defeat; professionals use it to escape a messy situation, re-read the code, and try the merge again with fresh eyes. There is also `git checkout --ours page.txt` ("resolve this file by taking *my current branch's* whole version") and `--theirs` (take the *incoming* version wholesale) - powerful for whole-file decisions, hazardous for subtle ones, and confusingly named under pressure, so many people prefer editing by hand, as above, or configuring a merge tool (`git config merge.tool kdiff3` style setups; VS Code's built-in three-pane conflict UI is excellent and free).

#### 18.7 Preventing Conflicts (Culture, Not Commands)

Four habits prevent most conflicts before they happen: **merge or rebase from main often** (small overlaps never accumulate); **keep branches short-lived** (a branch merged within days has almost no room to diverge); **talk before editing the same region** (the vast majority of conflicts are two teammates who did not know); and **agree on formatting** (many "conflicts" are just tabs-vs-spaces and line-ending noise; shared formatting tools and the Chapter 9 line-ending settings eliminate them). None of these are commands. All of them are more valuable than any command in this chapter.

### Chapter 19: Rebasing

#### 19.1 The Problem Rebasing Solves

Your feature branch is three days old. Meanwhile, teammates kept committing to `main`. Your history now looks like a fork that keeps drifting away from the road. You *could* merge main into your branch (Chapter 17.6), but that creates extra merge commits, and after several rounds, history looks like a plate of spaghetti. **Rebase** is the alternative: it makes your branch *appear* to have been created *now*, on top of the latest main, with a clean straight line.

#### 19.2 What Rebase Literally Does

`git rebase main` (run from your feature branch) does the following, conceptually: it finds the commits that exist on your branch but not on main (your "own" commits), temporarily *lifts them off*, moves your branch's starting point to the tip of main, and *replays your commits one by one* on top of it, as if you had written them just now.

```text
 BEFORE rebase                          AFTER rebase

           o---o---o  feature                  o'---o'---o'  feature
          /              \                    /
 o---o---o---o---o  main    becomes    o---o---o---o---o  main
              ^                                     ^
     (feature "hung" from          (feature now "hangs" from the
      an OLD point of main)         NEWEST point of main; o' are
                                    COPIES of o with new IDs)
```

The technical subtlety hidden in that apostrophe: the replayed commits are *new commits with new checksums* (Chapter 7's Idea Three: any change to content changes the ID). The work is identical; the objects are new. This subtlety is the entire reason the Golden Rule below exists.

#### 19.3 Doing It

```bash
git switch feature-color      # stand on the branch you want to re-base
git fetch origin               # make sure you know the latest main (Chapter 22)
git rebase main                # replay this branch's commits on top of main's tip
```

Typical output:

```text
Successfully rebased and updated refs/heads/feature-color.
```

Now your branch contains both main's latest work and your own, in one straight line. When you eventually merge the branch into main, the merge is a boring fast-forward (Chapter 17.2), which is the entire aesthetic goal of rebase.

#### 19.4 Rebase Conflicts

Because rebase replays your commits *one at a time*, a conflict during rebase is smaller and more local than a merge conflict: you resolve it for *one commit*, then continue. The flow:

```bash
git rebase main                       # a conflict stops the replay
# ...edit the conflicted file(s), exactly as in Chapter 18...
git add the-fixed-file.txt            # mark resolution
git rebase --continue                 # proceed to replaying the NEXT commit
git rebase --skip                      # (rarely) skip a commit that turned out empty
git rebase --abort                     # bail out entirely: restore everything to the pre-rebase state, exactly
```

`--abort` here is as reliable as in merges: no half-rebased state survives.

#### 19.5 Merge vs Rebase: The Honest Comparison

| | `git merge main` into your branch | `git rebase main` onto your branch |
| --- | --- | --- |
| History shape | True, with merge commits | Linear, as if written in order |
| Commit IDs | All preserved | Your own commits get NEW IDs |
| Risk during operation | One conflict session | Conflicts possibly once per replayed commit |
| Rewrite of history? | No | Yes (of your branch only, ideally) |
| Best for | Sharing work immediately; public branches | Cleaning your private branch before a pull request |

Both commands exist; mature developers use both, on purpose: rebase to tidy a private branch, merge to integrate public work.

#### 19.6 The Golden Rule of Rebasing

**Never rebase a branch that other people already have copies of.** If a branch exists only on your laptop, rebasing it changes nothing for anyone else, and you should tidy it freely. But if teammates have the branch or it has been pushed and pulled by others, rebasing rewrites commit IDs: your collaborators still hold the old IDs, so their history and yours become parallel universes, producing the "I have changes you don't have forever" class of merge nightmares. The rule in one breath: **rebase your private work; merge shared work.**

#### 19.7 Interactive Rebase: Rewriting Your Own History Before Showing It

The power-user form of rebase lets you edit your *own* recent commits before opening a pull request:

```bash
git rebase -i HEAD~4    # "-i" = interactive; operate on my last 4 commits
```

Your editor opens Git's to-do list:

```text
pick 1a2b3c4 feat: add login form
pick 5d6e7f8 fix typo
pick 9a0b1c2 docs: update README
pick 3e4f5a6 feat: add logout button
```

**Decoded, and the verbs you can write:** lines run oldest (top) to newest (bottom). Replace `pick` with a verb to change that commit's fate, save, and close:

| Verb | Effect |
| --- | --- |
| `pick` | keep the commit as-is |
| `reword` | keep the change, edit its commit message |
| `edit` | pause here so you can modify the commit's content |
| `squash` | melt this commit INTO the one above it, combining messages |
| `fixup` | melt into the one above, discarding this message (the "oops typo" absorber) |
| `drop` | delete the commit entirely |

The classic use: you have four commits of which two are cleanup noise. Change the second to `fixup` (absorbing the typo fix into the login form), maybe `reword` another, save - and your pull request now shows *two clean commits instead of four messy ones*. This is the professional's "present your work, not your process" move. Golden Rule applies with full force: interactive rebase only on commits nobody else has seen.

#### 19.8 One Config That Tidies Everything

```bash
git config --global pull.rebase true    # make `git pull` rebase your local commits on top of fetched ones instead of creating a merge commit
```

With this, day-start syncs produce straight histories automatically. (Reversible with `git config --global pull.rebase false`.) Some prefer `pull.rebase` left alone and to choose per situation with `git pull --rebase`; both camps are healthy.

---

### Chapter 20: Stashing

#### 20.1 The Scenario

You are halfway through a feature - files open, changes half-made, nothing committable (committing half-work would violate the atomic-commit principle from Chapter 13) - when an urgent bug lands on your desk, and the fix belongs on `main`, not your feature branch. You need a clean working directory *now*. This is exactly what `git stash` was invented for: **stash = put your unfinished changes in a drawer, clean the desk, come back later.**

#### 20.2 Saving the Drawer: git stash

On your feature branch with uncommitted changes:

```bash
git stash         # save current uncommitted changes (tracked files) and clean the working directory
```

Output:

```text
Saved working directory and index state WIP on feature-color: 3f2a1b4 feat: add dark theme file
```

**What just happened (line by line):** `Saved working directory and index state` - both your unstaged edits *and* things you had staged are preserved; `WIP on feature-color:` - it was saved on this branch (WIP = Work In Progress); `3f2a1b4 feat: ...` - the commit you were on when stashing. Your working directory is now *clean*: `git status` will report `nothing to commit, working tree clean`, and you can switch branches freely to fix the urgent bug.

The useful variants:

```bash
git stash -u                          # also stash UNTRACKED new files (the -u flag = --include-untracked; the brand-new file you had just created)
git stash push -m "half-finished color logic"   # save with a label you will recognize tomorrow (push is the explicit modern spelling)
```

#### 20.3 The Drawer Is a Stack

Stashes stack; each gets an index:

```bash
git stash list     # show all stashes
```

Output:

```text
stash@{0}: On feature-color: half-finished color logic
stash@{1}: WIP on main: 9a8b7c6 Add a second line to the greeting
```

**Decoded:** `stash@{0}` (read: "stash at position zero") is the *most recent* one; `stash@{1}` the one under it - a stack, newest on top, exactly like `HEAD~1` counts backward. The `On feature-color:` part records which branch you stashed on; the description is your `-m` label.

#### 20.4 Getting Work Back: pop vs apply

```bash
git stash pop      # apply the newest stash (stash@{0}) AND remove it from the stack
git stash apply    # apply the newest stash but KEEP it in the stack (safe: re-applyable)
git stash apply stash@{1}    # apply a specific older stash by index
git stash pop stash@{0}      # pop a specific stash
```

The pop-vs-apply choice is about confidence: `pop` assumes the apply will work perfectly and the stash will never be needed again; `apply` keeps the drawer contents until you explicitly `git stash drop stash@{0}` (removes one) or `git stash clear` (empties the drawer, unrecoverably). When a pop lands on code that changed since the stash, you can get conflicts (marked exactly like Chapter 18's); resolve them, `git add`, and the stash is applied.

#### 20.5 The Full Realistic Session

```bash
# (on feature-color, mid-work, urgent bug arrives)
git stash push -m "half-finished color logic"    # clear the desk
git switch main                                   # go where the bugfix belongs
git switch -c fix/login-crash                     # fix on a branch, even urgent fixes
# ...fix, add, commit, push, merge the fix (Chapters 16-17 or 23)...
git switch feature-color                          # return to the feature
git stash list                                    # confirm the stash is waiting
git stash pop                                     # resume exactly where you were
```

That is the whole skill: five commands, one clean save-and-return. Stashes are not forever, though: they survive branch switches but live only in your local repository, are easy to forget, and do not travel on push. The rule of thumb professionals follow: **stash is for hours, branches are for days, commits are for anything longer.**

---

### Chapter 21: Tagging

#### 21.1 What a Tag Is

A tag is a *permanent, named pointer* to one commit - most often the commit of a release. Where branches move (they advance with every commit), tags stand still forever. "v1.0.0" is not a place that moves; it is a monument at a specific spot in history. Teams use tags to mark the exact commit that became each shipped version, and GitHub turns tags into Releases (Chapter 25).

#### 21.2 Lightweight vs Annotated Tags

```bash
git tag v1.0.0                              # LIGHTWEIGHT: just a pointer, a private bookmark
git tag -a v1.0.0 -m "First stable release"  # ANNOTATED: a full Git object with tagger, date, and message
```

**Anatomy of the annotated form:** `git tag` - the tagging command; `-a` - *annotate*, meaning "create a real tag object" (not just a pointer); `v1.0.0` - the tag's name; `-m "..."` - the tag's message, same flag-grammar as commit messages. The annotated tag stores *who* tagged, *when*, *why* - and can be cryptographically signed. The universal recommendation is exactly this: **use lightweight tags for temporary local notes; always use annotated tags for anything you will share.**

#### 21.3 Working with Tags

```bash
git tag                       # list all tags (alphabetically, so v1.10 sorts before v1.2 - a classic surprise)
git tag -l "v1.*"             # list only tags matching the pattern (l = list)
git show v1.0.0               # inspect: shows the tag object (tagger, message) AND the commit it points to
git tag -a v1.1.0 9a8b7c6 -m "Maintenance release"   # tag a PAST commit by ID, not the current one
git tag -d v1.0.0             # delete a LOCAL tag (-d = delete)
```

#### 21.4 The Push Surprise: Tags Do Not Travel Alone

`git push` (Chapter 22) sends commits and branches, **but not tags** - you push tags explicitly:

```bash
git push origin v1.0.0        # push one specific tag
git push origin --tags         # push every local tag at once
git push origin --delete v1.0.0    # delete a tag from the REMOTE (GitHub)
```

Why the design? Tags are announcements ("this is a release"), not work in progress, so Git makes you announce deliberately.

#### 21.5 Versioning Like an Adult: Semantic Versioning

Tag names usually follow **SemVer** (semver.org), a three-number promise: `MAJOR.MINOR.PATCH`, bumped by exactly one part per release:

- **PATCH** (1.0.**0** to 1.0.**1**): bug fixes only; nothing new, nothing broken.
- **MINOR** (1.**0**.1 to 1.**1**.0): new features, backward compatible; existing users can upgrade safely.
- **MAJOR** (**1**.1.0 to **2**.0.0): breaking changes; users may need to change their own code.

So "we went from 2.4.1 to 3.0.0" is a complete sentence in SemVer: *something broke on purpose*.

#### 21.6 Visiting a Tag: Detached HEAD, Demystified

```bash
git switch --detach v1.0.0    # check out the exact snapshot of the tag (see the code AS RELEASED)
```

You are now in **detached HEAD** state: HEAD (Chapter 7) is no longer riding on a branch pointer; it is pinned directly to one commit. That is all "detached" means: *not attached to a branch*. It is completely safe for looking around (`git log`, running the old version, `git diff v1.0.0 main` to see everything since the release). One rule: do not commit here - commits made with no branch pointing at them are hard to find afterward (reflog rescues them, Chapter 26, but why suffer). To leave, switch back to a branch:

```bash
git switch main     # re-attach HEAD to a branch; the monument stays where it was
```

> **Try it yourself:** tag your current practice repo `v1.0.0`, make another commit, then `git diff v1.0.0 main` - a complete "what changed since the release" report in one command. That diff is the backbone of writing release notes.

## Part E: GitHub and Collaboration

Everything so far has lived on your machine. Part E connects your work to GitHub: uploading repositories, downloading updates, collaborating through pull requests, contributing to other people's projects, and a tour of GitHub's power features. After Part E, you are, without exaggeration, using Git the way professional teams do.

### Chapter 22: Remotes: push, pull, and fetch

#### 22.1 What a Remote Is

A **remote** is a named shortcut to a copy of your repository that lives somewhere else - usually a repository on GitHub. Your local repository and the remote each hold a *complete* repository (Chapter 6: distributed); they synchronize by exchanging commits. The conventional name for your main remote is `origin`, but that is only a convention, like naming your dog Dog: the name means nothing special to Git, and you will later meet a second common name, `upstream`, in Chapter 24.

```text
   your laptop                        GitHub
 +---------------+    git push      +---------------+
 | local repo    | --------------> | origin repo   |
 | (your edits)  | <-------------- | (shared copy) |
 +---------------+    git pull      +---------------+
                        /\
                 your teammates' laptops
                 push and pull the same way
```

#### 22.2 Creating Your Repository on GitHub

This section assumes you created the practice repo below in earlier chapters; the identical steps apply to any project you will ever upload.

1. On github.com, click the **+** icon (top right) and choose **New repository**.
2. Fill in the fields, each decoded:
   - **Repository name:** `my-first-repo` (will appear in your URL; lowercase-hyphenated is the convention).
   - **Description:** optional one-liner shown under the name.
   - **Public / Private:** Public means anyone can *view* the code (only you and invited collaborators can *change* it); Private means only you. You can flip this later in Settings.
   - **Add a README file:** **leave it unchecked** for this walkthrough. If GitHub creates a README now, the remote will contain a commit your local copy does not have, and your first push will be rejected with the "unrelated histories" error (Chapter 37 has the full story). For the same reason, skip the **.gitignore** and **license** dropdowns for now - we want an empty remote.
3. Click **Create repository**. GitHub shows a page of suggested commands - which is exactly what the next section teaches, properly.

#### 22.3 Connecting: git remote add

Back in your terminal, inside `my-first-repo`:

```bash
git remote add origin git@github.com:yourname/my-first-repo.git
```

**Anatomy of the command, word by word:**

- `git` - the program
- `remote` - the subcommand for managing remotes (add, rename, remove, show)
- `add` - register a new one
- `origin` - the *name* we are giving this remote (purely a local label; a bookmark name)
- `git@github.com:yourname/my-first-repo.git` - the *address* of the remote: SSH form (Chapter 10); the HTTPS form is `https://github.com/yourname/my-first-repo.git`

Verify the connection:

```bash
git remote -v    # -v = verbose: list remotes with their addresses
```

Output:

```text
origin  git@github.com:yourname/my-first-repo.git (fetch)
origin  git@github.com:yourname/my-first-repo.git (push)
```

**Decoded:** your repository now knows one remote named `origin` at that address, usable for both fetching (downloading) and pushing (uploading). Related housekeeping: `git remote rename origin github` renames it; `git remote remove origin` forgets it (nothing on GitHub is affected); `git remote set-url origin <new-url>` changes the address - this is how you switch an old HTTPS remote to SSH.

#### 22.4 The First Push

```bash
git push -u origin main    # upload your commits to GitHub, and remember the connection
```

**Anatomy of the command, word by word:**

- `git push` - upload local commits to a remote
- `-u` - short for `--set-upstream`: "and link my local `main` to the remote's `main` for the future" (once set, plain `git push` knows where to go - this is why you type this long form once per branch, ever)
- `origin` - the remote to push to (by bookmark name)
- `main` - the local branch to push

Output:

```text
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Compressing objects: 100% (6/6), done.
Writing objects: 100% (10/10), 1.05 KiB | 1.05 MiB/s, done.
Total 10 (delta 2), reused 0 (delta 0), pack-reused 0
To github.com:yourname/my-first-repo.git
 * [new branch]      main -> main
branch 'main' set up to track remote branch 'main' from 'origin'.
```

**What just happened (line by line):** `Enumerating/Counting/Compressing/Writing objects` - Git packaging and uploading the repository's internal objects (Chapter 7's blobs and trees); `To github.com:...` - the destination; `* [new branch] main -> main` - a branch was created on the remote, arrow-style: local `main` went *to* remote `main`; `branch 'main' set up to track...` - the `-u` link was recorded. Refresh the GitHub page: your commits, files, and history are now on the internet.

Two quiet concepts in that output deserve names. **Remote-tracking branches** are your local copies of the remote's branch positions, named `origin/main` (read: "what main looked like on origin, as of my last contact"). After the push, `origin/main` equals your `main`. And **tracking** is the `-u` relationship that lets `git status` report "Your branch is up to date with 'origin/main'" and plain `git push`/`git pull` work with no arguments.

#### 22.5 The Download Side: fetch and pull

The two commands that bring remote work down, and the difference professionals care about:

```bash
git fetch origin       # download everything new from origin, update origin/* markers... and CHANGE NOTHING ELSE
git pull               # download (fetch) and then MERGE the downloaded commits into your current branch
```

`git fetch` is the *look before you leap* command: it updates your `origin/main` marker and downloads the objects, but leaves your working files and your branches untouched. You can then inspect (`git log main..origin/main` lists "what they have that I don't"), compare, or merge when you choose. `git pull` is the *leap* itself: fetch plus immediate merge (or rebase, if you configured `pull.rebase` in Chapter 19) into whatever branch you are on. Both are correct; fetching first is how you keep calm with many teammates.

Sample `git pull` output when a teammate pushed work:

```text
remote: Enumerating objects: 5, done.
...
From github.com:yourname/my-first-repo
   9a8b7c6..5e4f3a2  main       -> origin/main
Updating 9a8b7c6..5e4f3a2
Fast-forward
 notes.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 notes.md
```

**Decoded:** the `From github.com:...` block is the fetch half (note `main -> origin/main`: your marker of the remote's position moved); `Updating 9a8b7c6..5e4f3a2 / Fast-forward` is the merge half - Chapter 17.2's simplest merge, because you had no local work they lacked. If you *did* have local commits, this half would be a three-way merge (or a rebase), and could even conflict (Chapter 18).

#### 22.6 The Daily Sync Rhythm

The push-pull rhythm of a working day, distilled: **`git pull` when you sit down** (start from everyone's latest), **work in commits** (Chapters 12-13), **`git push` when a unit is done** (share and back up). If push is ever rejected with `! [rejected] ... (fetch first)`, it means the remote has commits you lack: pull first (resolving anything that arises), then push again. Chapter 37 covers that moment in full, because it happens to everyone on day one.

#### 22.7 Authentication, Revisited

Your Chapter 10 SSH setup is what makes the pushes above just work. Two facts for completeness: HTTPS-URL repositories authenticate with a **Personal Access Token** (Settings -> Developer settings -> Personal access tokens; it functions as a password, so treat it like one and give it the narrowest permissions), and credential managers (Git Credential Manager on Windows, the `osxkeychain` helper on macOS) can remember HTTPS tokens so both styles become invisible after first use.

> **Try it yourself:** clone your own repository into a second folder (`git clone git@github.com:yourname/my-first-repo.git roundtrip-test`), make a commit there, push, then return to your original folder, `git fetch`, and run `git log main..origin/main` - you are watching your two copies synchronize, which is the entire distributed model in four commands.

---

### Chapter 23: The Pull Request Workflow

#### 23.1 What a Pull Request Is

A **pull request** (PR) is a web page on GitHub that says: *"Here is a branch of work; here is the branch it should be merged into; please review it, discuss it, test it, and merge it."* It is not a Git command - it is a GitHub feature layered on Git, and it is the center of modern collaboration: every change to a professional codebase, at thousands of companies, arrives as a pull request. The name decodes literally: you are *requesting* that the maintainers *pull* your changes into their project.

#### 23.2 GitHub Flow: The Workflow You Already Almost Know

The PR workflow sits on everything from Parts C and D, adding exactly two new moves (push a branch; click buttons on GitHub):

```text
 1. main is always healthy and deployable
 2. git switch -c feature/xyz-name    <- new branch for one unit of work
 3. commit early, commit well          <- Chapters 12-13
 4. git push -u origin feature/xyz-name   <- NEW: publish the branch
 5. Open a pull request on GitHub       <- NEW: propose, review, discuss
 6. Squash-merge when approved          <- the work joins main, one clean commit
```

Rule 1 is why the workflow works: because `main` is never broken, any emergency is small. Everything else exists to protect rule 1.

#### 23.3 A Complete Pull Request, Start to Finish

In `my-first-repo`:

```bash
git switch main          # always branch from the latest main
git pull                 # sync: start from what everyone else sees
git switch -c feature/footer       # branch for the unit of work
echo "Made with Git" > footer.txt   # the "feature": one new file
git add footer.txt                 # stage
git commit -m "feat: add footer note"   # commit (Conventional, atomic, from Chapter 13)
git push -u origin feature/footer  # publish the branch to GitHub (the -u dance, once per branch)
```

GitHub now shows a yellow banner on your repository page: **"feature/footer had recent pushes - Compare & pull request"**. Click it (or open the Pull requests tab and click New pull request). The PR creation page has anatomy worth decoding line by line:

- **base: main <- compare: feature/footer** - the direction of the merge, displayed left to right: the *base* is where work is going; *compare* is the branch carrying the work. Read the whole page as the sentence "merge compare into base."
- **Title:** becomes the merge commit message - use the same discipline as Chapter 13: `feat: add footer note`.
- **Description:** the room to explain *what and why* (not how - the diff shows how). A good template:

```markdown
## What
Adds a footer note to the repository.

## Why
The repository should show it is maintained with Git, for the tutorial readers.

## How I tested
Ran the site locally; footer appears on every page.

Closes #3
```

The last line is a magic spell: `Closes #3` links the PR to Issue #3 (Chapter 25), and merging the PR *automatically closes the issue*. The recognized keywords are close/closes/closed, fix/fixes/fixed, and resolve/resolves/resolved, always followed by the issue number.

- **Reviewers** (sidebar): people whose approval you want before merge; they are notified.
- **Assignees:** who is doing the work (usually you; for solo PRs, unused).
- **Labels, milestone, projects:** taxonomy for teams; optional.
- **Draft pull request** (dropdown on the create button): opens the PR marked as work-in-progress, blocking accidental merges until you click "Ready for review."

Click **Create pull request**.

#### 23.4 The Review

Your reviewer opens the PR and sees: the description, the *Files changed* tab (every diff, rendered in the red/green language of Chapter 14.5, line-commentable), and the *Checks* tab (Part G: your automated tests will report here). The reviewer can leave line comments (each starting a thread), reply to threads, and finally submit a review with one of three verdicts: **Comment** (observations, no verdict), **Approve** (green light), or **Request changes** (red light with required fixes). The author pushes additional commits to the same branch - the PR updates automatically, because a PR tracks a *branch*, not a snapshot - and the cycle continues until an approval.

Review etiquette, learned once: small PRs get good reviews (beyond ~400 changed lines, review quality collapses); review comments critique the *code*, never the *person* ("this loop might be slow with large lists" not "you wrote this badly"); and respond to every comment, even if only with "done" or a thoughtful disagreement - silence is how code review culture dies.

#### 23.5 Merging: The Three Strategies

The green **Merge pull request** button is a dropdown with three strategies, and now you can understand all three from Part D alone:

| Button | What it creates | History looks like |
| --- | --- | --- |
| **Merge** | A true merge commit (two parents, Chapter 17.3) | preserved graph, explicit merge nodes |
| **Squash and merge** | ALL the PR's commits melted into ONE new commit on main | one clean commit per PR - most teams' default |
| **Rebase and merge** | The PR's commits replayed onto main, keeping their count | linear, no merge commit, new commit IDs (Chapter 19) |

For feature work, **squash and merge** is the modern default: whatever mess the exploration produced, `main` sees exactly one well-named commit (`feat: add footer note (#4)`) - GitHub appends the PR number automatically. Use plain **merge** when the individual commits are meaningful (a sequence worth preserving), and **rebase and merge** when you curated the commits yourself with Chapter 19.7.

#### 23.6 After the Merge: The Ritual Nobody Teaches You

After merging, the ritual that closes the loop:

```bash
git switch main               # return to main
git pull                      # download the merged work (note: your local main now has the squash commit)
git branch -d feature/footer  # delete the local branch (its work is now IN main, so -d succeeds)
```

On GitHub, the merge page offers **Delete branch** - say yes (branches are disposable; the PR page preserves the history forever, even after branch deletion). Your `origin/feature/footer` marker disappears after the deletion synchronizes. The workflow is complete: main grew one unit of reviewed work, and nothing dirty touched it at any point.

> **Try it yourself:** run the full loop twice - two tiny features, two PRs (you can approve and merge your own PRs in your own repositories; teams configure how many approvals are required). The second time, notice how mechanical it has already become. That muscle memory is the deliverable of this chapter.

### Chapter 24: Forking and Open Source Contributions

#### 24.1 Fork, Clone, Branch: Three Words That Finally Stop Blurring

- A **clone** is a local copy of a repository (Chapter 11).
- A **branch** is a parallel line inside one repository (Chapter 16).
- A **fork** is *your personal server-side copy of someone else's GitHub repository*, made by clicking one button on GitHub.

The situation a fork solves: you cannot push to `octocat/Spoon-Knife` (it is not yours), but you want to change it. Clicking **Fork** gives you `yourname/Spoon-Knife` - a full copy under your account that you *can* push to. From that fork, you open a pull request *back* to the original. The photocopier analogy holds: fork = photocopy the whole book into your own library; branch = a bookmark within one copy; the PR = a letter to the original author saying "here are pages to replace."

#### 24.2 The Complete Open Source Workflow

Every open source contribution on Earth follows these steps. Practice them now on GitHub's official practice repository, `octocat/Spoon-Knife`, which exists purely for this rehearsal.

**Step 1 - Fork.** Visit `github.com/octocat/Spoon-Knife` and click **Fork** (top right). Seconds later you are looking at `github.com/yourname/Spoon-Knife`. You now "own" a copy you cannot break and cannot harm.

**Step 2 - Clone your fork** (not the original!):

```bash
cd ~/git-practice                                   # where you keep projects
git clone git@github.com:yourname/Spoon-Knife.git   # clone YOUR fork (you can push here)
cd Spoon-Knife                                       # enter the project
```

**Step 3 - Connect the original as a second remote named upstream:**

```bash
git remote add upstream git@github.com:octocat/Spoon-Knife.git   # register the ORIGINAL under the name "upstream"
git remote -v                                                       # verify your two remotes
```

Output:

```text
origin    git@github.com:yourname/Spoon-Knife.git (fetch)
origin    git@github.com:yourname/Spoon-Knife.git (push)
upstream  git@github.com:octocat/Spoon-Knife.git (fetch)
upstream  git@github.com:octocat/Spoon-Knife.git (push)
```

**Decoded:** `origin` is your fork (where you push); `upstream` is the original (where you fetch updates from, and where you will send a PR). The names are pure convention, but *universal* convention - every tutorial, teammate, and blog post uses exactly these two names for exactly these two roles.

**Step 4 - Branch, work, commit** (everything you already know):

```bash
git switch -c docs/fix-readme-typo     # a small, well-named branch
# ...edit README.md, fixing the typo you found...
git add README.md                      # stage
git commit -m "docs: fix typo in README installation section"   # a perfect little commit
```

**Step 5 - Push to your fork:**

```bash
git push -u origin docs/fix-readme-typo    # -u dance, once per branch, to YOUR fork
```

**Step 6 - Open the pull request against the ORIGINAL.** Visit `github.com/yourname/Spoon-Knife`; GitHub's banner offers **"Compare & pull request"**. Verify the direction carefully - GitHub pre-fills it, but read it as a sentence - this time it is inverted from Chapter 23: **base repository: octocat/Spoon-Knife (base branch: main) <- head repository: yourname/Spoon-Knife (compare: docs/fix-readme-typo)**: you are requesting that *octocat's* project *pull* from *your* fork. Write the description (what, why, tested how), and click **Create pull request**. Maintainers of that project will review it. On a practice repo nothing further happens; on real projects, the discussion cycle of Chapter 23.4 plays out.

#### 24.3 Keeping Your Fork Current

Weeks later, the original project has moved; your fork is stale. Two ways to update, same result:

```bash
git fetch upstream                  # download the original's latest state
git switch main                      # update your local main...
git merge upstream/main               # ...by merging the original's main into it
git push origin main                 # push the refreshed main to your fork
```

Or on GitHub itself: your fork's page now has a **Sync fork** button that does the same thing server-side. Either way, always branch *from a fresh main*, so your PRs carry only your change and none of your staleness.

#### 24.4 Etiquette That Gets Your PRs Merged

Open source culture has unwritten rules, and they are learnable: **read the project's README and CONTRIBUTING.md first** (many projects specify branch naming, commit style, or test requirements; ignoring these is the fastest route to a closed PR); **claim an issue before fixing it** ("I'll take this" on the issue thread prevents two strangers duplicating each other); **small PRs win** (one fix per PR, always); **match the project's code style and add tests** if tests exist; **be patient and responsive** (maintainers are volunteers; reply to review comments with fixes, pushed to the same branch). For your first contribution ever, search repos by the label **"good first issue"** (maintainers flag intentionally-easy entry points) or contribute to **documentation** - it is real, valued work with a famously low barrier and famously high merge rate.

---

### Chapter 25: GitHub Power Features

This chapter is a guided tour of the rest of GitHub - each feature gets exactly what a working practitioner needs: what it is, when to reach for it, and the two or three clicks that operate it.

#### 25.1 Issues: The To-Do List of Everything

An **issue** is a tracked conversation about one problem or task. Click the **Issues** tab, then **New issue**, and you get a title, a description (Markdown: headings, lists, code fences - it is a README in miniature), and a sidebar for: **labels** (`bug`, `enhancement`, `good first issue`, `wontfix`... taxonomy and filtering), **assignees** (who owns it), **milestones** (due-date groupings like `v1.1.0`), and **projects** (Kanban boards, next section). Issues do three magic tricks: commits mentioning `#12` show up in the issue's timeline; `git commit -m "fix: handle empty input (#12)"` cross-links the commit; and merging a PR whose description says `Closes #12` auto-closes the issue (Chapter 23.3's magic spell). Teams also create **issue templates** (a `.github/ISSUE_TEMPLATE/` folder in the repo) so every bug report arrives with structured questions. Habits: search existing issues before filing ("is it already known?"), one issue = one topic, and include reproduction steps.

#### 25.2 Projects: The Kanban Board

**Projects** turn issues and PRs into a board: columns like `To do / In progress / Review / Done`, with cards you drag between them, each card backed by an issue or PR (or a raw note). Projects can be enabled to auto-move: an issue moves to Done when its PR merges. This is lightweight project management living inside your repository, which is why tiny teams run entire products with GitHub alone and no other tooling.

#### 25.3 Wiki and Documentation

Every repository has a **Wiki** tab: a multi-page documentation site (again Markdown, with page history - it is itself a mini Git repository you can clone). Uses vary: the README holds the "front page" (what, install, quickstart) while long-form docs, tutorials, and design decisions live in the wiki. Many projects instead keep docs in a `docs/` folder for versioned review via PRs - same goal, different flavor.

#### 25.4 Gists: The Snippet Drawer

A **gist** (gist.github.com) is a mini-repository for a single text snippet: a script, a config file, a SQL query. Secret gists (the default) are unlisted-but-shareable by URL; public gists are forkable like repositories. Every gist is a full Git repo: clone it, version it, embed it. Use it when the answer to "where do I put this one file?" is not "a whole repository."

#### 25.5 Releases: Shipping Officially

A **Release** (Releases sidebar section, or from the tags page) is a tag (Chapter 21) dressed for the public: title (`v1.2.0`), curated release notes (a generated diff link plus your prose describing what changed), and **binary attachments** (installers, archives) - the download page of serious projects. **Draft releases** let you prepare notes while the tag does not exist yet; publishing the release creates the tag. GitHub also auto-generates release notes from Conventional Commits (Chapter 13.3) with the "Generate release notes" button - the robots reading your discipline paying dividends.

#### 25.6 GitHub Pages: Free Hosting

**GitHub Pages** serves a repository as a live website at `https://yourname.github.io/repo/` - free, no server, no billing, with automatic HTTPS. The instant way: Settings -> Pages -> set Source to your `main` branch - GitHub publishes the repository's HTML files. The professional way (build step, custom domains, full control) is the Actions-based deployment you will build in Chapter 33. There is also the special personal-site form: a repository named exactly `yourname.github.io` publishes to `https://yourname.github.io` itself - the classic free portfolio homepage.

#### 25.7 Actions: The Preview

**GitHub Actions** (Part G) runs software for you on GitHub's computers when events happen: push, PR, schedule, manual trigger. If you have seen small badges in READMEs like `build | passing`, you have seen Actions output. Everything from "run my tests on every push" to "deploy my site on merge" - three full chapters start at Chapter 31.

#### 25.8 Security Features

Four names worth knowing: **Dependabot** scans dependencies (your `package.json`, `requirements.txt`...) against vulnerability databases and opens PRs proposing safe upgrades (Settings -> Security); **secret scanning** alerts when it detects leaked API keys even in old commits; **CodeQL** analyzes code itself for vulnerability patterns (free for public repos); and **security advisories** give you a private channel to fix and announce a vulnerability responsibly. For a beginner the actionable habit is simpler: never commit secrets (Chapter 15), and turn on Dependabot in Settings.

#### 25.9 Insights

The **Insights** tab is a free analytics suite for the repo: **Contributors** (commit graphs per person), **Traffic** (views and clones over time - the internet discovering your project), **Commits/Code frequency** (when the project is alive), and **Pulse** (a weekly digest of activity). The Traffic page in particular is quietly addictive once your project is public.

#### 25.10 The GitHub CLI: GitHub in Your Terminal

The **`gh``** tool (cli.github.com) puts GitHub in the terminal, eliminating the biggest friction of PR life - browser round-trips. Install it, then:

```bash
gh auth login                      # connect it to your account (guided; choose SSH and your Chapter 10 key)
gh repo create my-new-repo --public --source=. --push    # create a GitHub repo FROM the current folder and push, one command
gh pr create --fill                 # open a PR from the current branch, auto-filling title/description from commits
gh pr status                        # show PRs for this branch: yours, needing your review
gh pr checkout 12                   # download and check out a collaborator's PR branch locally, for testing
gh issue list --label "good first issue"   # browse work from the terminal
```

Each flag above is decodable with skills you own: `--source=.` means "the repository is the current directory," `--push` means "push immediately after creating," `--fill` means "fill the PR form from my commit messages." The single most-loved feature is `gh pr checkout` - reviewing a PR locally, in your editor, is a different experience from reviewing in a browser.

#### 25.11 Copilot, Briefly

**GitHub Copilot** is GitHub's AI pair programmer: it suggests code and entire functions in your editor, and increasingly answers questions about your repository. It is a paid product with a limited free tier. Whatever your stance on AI assistance, its existence does not change this guide's truth: Copilot writes lines; *you* are still the one who must understand repositories, branches, commits, and pull requests - the machinery this guide teaches, and the machinery your team will judge you by.

## Part F: Advanced Git

Part F is the part people ask for in job interviews and in emergencies. You will learn to undo *anything* (including "deleted" work), to perform surgical operations on single commits, to automate quality checks with hooks, to type 60% less with aliases, to combine repositories with submodules, and finally to open the `.git` folder and understand every file inside it.

### Chapter 26: Undoing Anything in Git

#### 26.1 The Truth First

Git's reputation for mercilessness is unearned, and the reason is architectural: a commit is an object in a database, not a file in a folder. Deleting a file from your working directory does not delete its committed snapshot; even "undoing" a commit usually just moves a pointer, leaving the commit object recoverable by the **reflog** (section 26.7) for around 90 days. The honest failure modes are only two: never-committed work (truly gone with `--hard` or `git clean`), and pushed-and-rewritten history (a social problem, not a technical one). Everything else is recoverable. Now, systematically, from the smallest undo to the largest.

#### 26.2 Level One: Discard Uncommitted Changes in One File

You edited a file, the edit is wrong, and you want the file back the way it was at the last commit/staging:

```bash
git restore page.txt    # discard working-directory changes to this file, restoring the staged version
```

The modern command is `git restore` (2019); the old spelling you will see everywhere is `git checkout -- page.txt` (identical effect). The double dash means "what follows is a file path, not a branch name" - necessary because old `checkout` handled both. This is a destructive command (uncommitted edits are gone), so run it only when you mean it.

#### 26.3 Level Two: Unstage a File

You ran `git add` on something prematurely; the file is staged but uncommitted:

```bash
git restore --staged page.txt    # remove the file from the STAGING area, leaving the file and its edits untouched
```

Read it carefully: `git restore` restores; `--staged` says what to restore *from where to where* - it restores the staging entry to match HEAD. File on disk: unchanged. Old spelling: `git reset HEAD page.txt` (same effect, and yes, that is the first appearance of `reset`, which grows teeth in a moment).

#### 26.4 Level Three: Fix the Last Commit

Covered in Chapter 13.5 and repeated here because it is *the* undo you will use weekly:

```bash
git commit --amend --no-edit    # fold currently staged changes into the last commit, keeping its message
git commit --amend -m "new message"    # same, but replace the message
```

Amend is safe while the commit is local-only. If you already pushed the commit, amend + force-push is the history-rewriting territory of Chapter 19.6 - prefer section 26.6's revert for anything pushed.

#### 26.5 Level Four: Undo Commits Locally with reset

`git reset` moves the current branch's pointer backward, and its three modes answer the question "and what happens to the changes that were in the undone commits?" Watch the same reset through three lenses:

```bash
git reset --soft HEAD~1    # move branch back 1 commit; changes stay STAGED (safest: nothing leaves the machine)
git reset --mixed HEAD~1   # move branch back; changes stay on DISK, UNSTAGED (this is the DEFAULT mode)
git reset --hard HEAD~1    # move branch back; changes are REMOVED from disk too (dangerous, total)
```

**Anatomy:** `HEAD~1` means "the parent of HEAD" (Chapter 14.3's notation); `--soft/--mixed/--hard` select *how much* of the working state is reset along with the pointer. The picture that makes it stick:

```text
                          where HEAD ends up:   staging area:      working directory:
 --soft   HEAD~1                    staged as-is        untouched
 --mixed (default)                  empty                     changes present, unstaged
 --hard                             empty                     pristine (edits DELETED)
```

**The canonical uses:** `--soft` to recommit properly ("the last three commits should have been one"); `--mixed` to uncommit and reselect what goes in ("committed too early, let me restage carefully"); `--hard` to genuinely erase local work ("this experiment never happened") - and note that `--hard` also restores staged files, making it the true nuke. Even after `--hard`, the commits themselves linger in the database for reflog rescue (26.7) - which is why Git veterans say "reset --hard is recoverable if it was ever committed."

#### 26.6 Level Five: Undo Pushed Commits with revert

**`git reset` on a shared branch is forbidden** (Chapter 19.6's Golden Rule: moving the public pointer backward makes teammates' history diverge from yours). The shared-safe undo is:

```bash
git revert 9a8b7c6    # create a NEW commit that is the exact inverse of commit 9a8b7c6
```

Output:

```text
[main 4e5f6a7] Revert "feat: add footer note"
 1 file changed, 1 deletion(-)
 delete mode 100644 footer.txt
```

**Decoded:** Git did not erase history; it authored a new commit that performs the opposite changes (deleted the file the old commit added). The timeline grows forward - the old commit remains visible, the revert sits next to it - which is why teammates pulling your branch just receive a normal new commit. The diff of "old + revert" is nothing. This is the undo you use on anything already pushed to a shared branch: honest, forward-only, conflict-safe.

One special case: reverting a *merge commit* requires telling Git which parent was "main": `git revert -m 1 <merge-commit-id>`. The `-m 1` selects parent 1 ("mainline," the branch you merged INTO) as the side to restore.

#### 26.7 The Time Machine: git reflog

The reflog ("reference log") is Git's private diary of everywhere HEAD has pointed, kept for you locally. Almost every "I destroyed my work" story ends here:

```bash
git reflog    # show the history of HEAD movements
```

Output:

```text
9a8b7c6 (HEAD -> main) HEAD@{0}: commit: feat: add footer note
5e4f3a2 HEAD@{1}: commit: fix typo
3f2a1b4 HEAD@{2}: commit: feat: add dark theme file
7c9e4f2 HEAD@{3}: reset: moving to HEAD~1     <-- a reset happened here, "losing" 3f2a1b4
```

**Decoded, line by line:** each line is one past position of HEAD; `HEAD@{0}` is *now*; `HEAD@{1}` is "where HEAD was one move ago" (counting backward, exactly like `stash@{0}` in Chapter 20); the text after the colon is what caused the move - a commit, a reset, a checkout, a merge. The demonstration writes itself: even after `git reset --hard HEAD~1`, line `HEAD@{2}` still names the "lost" commit `3f2a1b4`, so:

```bash
git reset --hard 3f2a1b4         # travel back: branch pointer and files restored to that snapshot
git branch rescue 3f2a1b4         # gentler alternative: rescue the commit onto a new branch, current branch untouched
```

**The limits, honestly stated:** the reflog is local (your teammates' reflogs are their own), it covers *committed* states (never-committed edits are truly gone), and entries expire (default: 90 days) before the garbage collector truly deletes unreachable objects. Ninety days is a lot of safety net; "commit early, commit often" (Chapter 13.6) is still the policy that keeps you inside it.

#### 26.8 Cleaning Untracked Files

```bash
git clean -n       # DRY RUN: list what WOULD be deleted, delete nothing (always run this first)
git clean -f       # delete untracked files (not ignored ones)
git clean -fd       # delete untracked files AND untracked directories
git clean -fdx      # nuclear: untracked AND ignored (node_modules gone too) - read it twice before running
```

Untracked means invisible to the reflog: `git clean -f` is the one command in this chapter with no time machine behind it. The `-n` dry-run habit exists for exactly this reason.

#### 26.9 The Decision Table

Print this table mentally; it is the chapter compressed:

| You want to... | Command | Safety |
| --- | --- | --- |
| Discard edits in one file | `git restore <file>` | Destructive to uncommitted edits |
| Unstage a file | `git restore --staged <file>` | Fully safe |
| Fix last commit (message/files) | `git commit --amend` | Safe if not pushed |
| Redo the last N commits as staged | `git reset --soft HEAD~N` | Safe if not pushed |
| Erase local commits entirely | `git reset --hard HEAD~N` | Local only; reflog can rescue |
| Undo a PUSHED commit | `git revert <id>` | The shared-safe undo |
| Recover "lost" commits | `git reflog` then reset/branch | Usually works within 90 days |
| Delete untracked junk | `git clean -n` then `-f` | No reflog: be sure |

---

### Chapter 27: Precision Tools: cherry-pick, bisect, and grep

#### 27.1 git cherry-pick: Copying One Commit

`git merge` brings over *everything* from a branch; `git cherry-pick` brings *one specific commit* - replaying it as a new commit on your current branch. The everyday scenarios: you need a bugfix that lives on a feature branch but is not merged yet; a hotfix made on `main` needs to also land on your `v1.0` release branch; or a teammate's commit solves your exact problem and you need it now without their other work.

```bash
git switch release-v1            # stand on the branch that NEEDS the fix
git log main --oneline           # find the commit's ID (e.g. 5e4f3a2)
git cherry-pick 5e4f3a2          # replay that one commit here
```

Output:

```text
[release-v1 8f9a0b1] fix: handle empty input
 1 file changed, 3 insertions(+)
```

**Decoded:** a *new* commit `8f9a0b1` was created on `release-v1` with the *same changes and message* as `5e4f3a2` - new ID because new parent (Chapter 7, Idea Three). Add `-x` (`git cherry-pick -x 5e4f3a2`) to append "(cherry picked from commit 5e4f3a2...)" to the message - the honest bookkeeping flag you want on shared branches, because in six months "why are there two copies of this fix?" should be answerable. Conflicts during a pick resolve exactly like Chapter 18, then `git cherry-pick --continue`. Ranges work too: `git cherry-pick A..B` picks everything after A up to B. And the caution label: cherry-picking *instead of merging* regularly creates parallel histories of duplicate changes (the "same patch, two IDs" problem); it is a scalpel for exceptions, not a lifestyle.

#### 27.2 git bisect: The Bug Hunt Binary Search

The situation: the app worked last Tuesday; today it is broken; there are 60 commits in between; the culprit is one of them, and you would rather not check out 60 versions manually. `git bisect` finds it in about six steps, by *binary search*: it checks out the midpoint of the suspects, you answer "does this version work?", it halves the remaining suspects, repeat. Sixty commits, six questions; 1,000 commits, ten.

A complete annotated session:

```bash
git bisect start         # begin the hunt
git bisect bad           # verdict: CURRENT version (HEAD) is broken - the known end of the bad range
git bisect good v1.2.0    # verdict: tag v1.2.0 (Chapter 21) was the last KNOWN-GOOD version
```

Output:

```text
Bisecting: 30 revisions left to test after this (roughly 5 steps)
[f1e2d3c...] feat: add login rate limiting
```

**Decoded:** Git checked out the middle commit of the suspect range (`f1e2d3c`), tells you 30 commits remain and about 5 rounds will finish. Now *you* run the program, reproduce, and judge this exact version:

```bash
git bisect good     # if this checkout WORKS: culprit is in the newer half
git bisect bad      # if this checkout is BROKEN: culprit is in the older half (including this one)
```

After each verdict, Git checks out the next midpoint automatically. When the range collapses:

```text
5e4f3a2 is the first bad commit
commit 5e4f3a2
Author: ...
    fix: change validation order
```

**Decoded:** `first bad commit` - the commit that introduced the bug, with its message: your suspect, with a confession note attached. The final command:

```bash
git bisect reset      # return to the branch you started on; hunt over
```

The automation upgrade, when you have a test that fails on the bug: `git bisect run npm test` - Git runs the command at each step itself, treats exit code 0 as good and non-zero as bad, and delivers the culprit without you touching anything. This combination - a fast test plus bisect - is why disciplined commit hygiene (Chapter 13.6) is not pedantry: atomic commits make bisect surgical, and bisect is the closest thing debugging has to a time machine.

#### 27.3 git grep: Search, but With Repository Awareness

The system `grep` searches a folder; `git grep` searches *what Git knows about*: your tracked files, in seconds, at any point in history:

```bash
git grep "rateLimit"            # find the string in all tracked files of the current checkout
git grep -n "rateLimit"         # -n: prefix each hit with its line number
git grep -i "ratelimit"         # -i: case-insensitive (matches rateLimit, RateLimit, RATELIMIT...)
git grep -c "TODO"              # -c: per-file COUNT of matches (a satisfying to-do census)
git grep -l "rateLimit"         # -l: just the filenames containing matches
git grep "rateLimit" v1.0.0     # search the code AS OF TAG v1.0.0 - "when did this first exist?"
git grep --cached "rateLimit"   # search what is STAGED (before committing it)
```

The differences from plain grep that matter: `git grep` respects `.gitignore` (no node_modules noise), searches any snapshot of history, and is fast on huge repositories (it walks Git's own index). "Search the code as of v1.0.0" is also a soft introduction to archaeological thinking: the repository contains every version your project ever had.

#### 27.4 Which Tool When

| The situation | The precision tool |
| --- | --- |
| One commit from elsewhere, needed here | `git cherry-pick` |
| "Something between then and now broke this" | `git bisect` |
| "Where in the codebase is X?" | `git grep` |
| "What did this file look like at v1.0?" | `git show v1.0.0:path` (Chapter 14) |

### Chapter 28: Hooks and Aliases

#### 28.1 What Hooks Are

A **hook** is a script Git runs automatically at a specific moment in a Git operation: before a commit completes, before a push leaves, after a checkout, and so on. Hooks turn Git's checkpoints into a quality-control system: your code can *refuse to be committed* if it contains a forbidden string, *refuse to be pushed* if tests fail, or *remind you of conventions* as messages are written. Hooks are plain scripts (shell by default; any executable works), and they live in a special folder inside the repository: `.git/hooks/`.

Look inside any repository: `ls .git/hooks` shows a collection of `*.sample` files - inactive templates Git ships for documentation. A hook *activates* when you remove the `.sample` extension and make the file executable. The contract every hook obeys: **exit code 0 means "proceed"; any non-zero exit code means "stop the operation and show my output."** That single rule is the entire hook API.

#### 28.2 A Complete pre-commit Hook, Line by Line

The `pre-commit` hook runs between you typing `git commit` and the commit being created - the perfect enforcement point. Create the file `.git/hooks/pre-commit` with this content, where every line is annotated:

```bash
#!/bin/sh                                        # line 1: "shebang" - run this file with /bin/sh, the shell

# Block commits that contain debug leftovers
if git diff --cached | grep -q "console.log"; then    # line 3: `git diff --cached` = the staged changes (what is about to be committed); `|` pipes that text into `grep -q "console.log"` which searches silently (-q = quiet) and exits 0 if found
  echo "ERROR: console.log found in staged changes."  # line 4: print the reason for rejection to the user
  echo "Remove debug prints, or use 'git commit --no-verify' if you truly must."   # line 5: how to proceed
  exit 1                                          # line 6: NON-ZERO exit = stop this commit, right now
fi                                                # line 7: end of the if-block

exit 0                                            # line 8: reached only if nothing was found: exit 0 = allow the commit
```

Activate it (two steps, both required):

```bash
chmod +x .git/hooks/pre-commit    # chmod changes file permissions; +x adds "executable" - without it Git ignores the file
```

Now `git commit` with a staged `console.log` prints both error lines and produces no commit. `git commit --no-verify` (the documented escape hatch, also `-n`) skips hooks when you truly must - and the escape hatch existing is what makes strict hooks tolerable to a team.

#### 28.3 The Other Hooks You Will Actually Use

| Hook | Runs when | Classic use |
| --- | --- | --- |
| `pre-commit` | before a commit is created | block debug leftovers, lint, format check |
| `commit-msg` | after the message is written, before commit finalizes | enforce Conventional Commits |
| `pre-push` | before a push leaves your machine | run the test suite locally |
| `prepare-commit-msg` | before the editor opens | inject a message template (e.g., the issue number) |
| `post-merge` | after a merge completes | rebuild dependencies, update generated files |

A `commit-msg` example worth understanding, because message discipline is Chapter 13's theme - create `.git/hooks/commit-msg`:

```bash
#!/bin/sh                                    # shell, as always
MSG_FILE="$1"                                 # line: hooks receive arguments; $1 to commit-msg is the FILE containing the message
if ! grep -qE "^(feat|fix|docs|chore|refactor|test|perf|ci)(\(.+\))?: .+" "$MSG_FILE"; then   # line: grep -E = extended regex; the pattern demands a line STARTING (^) with a known type, optional (...) scope, a colon+space, then text
  echo "ERROR: message must follow Conventional Commits, e.g. 'feat: add login'"    # the rejection reason
  exit 1                                      # stop the commit
fi
exit 0                                        # message is valid: proceed
```

#### 28.4 The Catch, and the Industry Answer

Here is the hook trap that surprises everyone: **`.git/hooks` is not version-controlled and does not travel with clones.** Your carefully built pre-commit hook protects only *your* copy of the repository; a fresh teammate clone has no hooks at all (and GitHub cannot run local hooks - see Part G for that). The industry's answer is hook *manager* packages that install hooks through the version-controlled dependency system every project already has: **husky** + **lint-staged** for JavaScript projects, **pre-commit** for Python, **lefthook** cross-language. Same hook scripts, but a one-command setup in `package.json` (Chapter 34's capstone will show the pattern). For personal use and learning, plain `.git/hooks` scripts remain perfect.

#### 28.5 Aliases: Typing 60% Less

An **alias** is a personal shorthand you teach Git via the same `git config` you learned in Chapter 9: `git config --global alias.<name> "<expansion>"`. Afterward `git <name>` runs the expansion. A curated set, each annotated:

```bash
git config --global alias.st "status -sb"                 # `git st` = short-format status with branch info (-s short, -b show branch)
git config --global alias.cm "commit -m"                  # `git cm "msg"` = the commit you type fifty times a day
git config --global alias.unstage "restore --staged"      # `git unstage file` = self-documenting, no flag to misremember
git config --global alias.last "log -1 HEAD"               # `git last` = show the most recent commit in full
git config --global alias.amend "commit --amend --no-edit" # `git amend` = the Chapter 13.5 shortcut, named honestly
git config --global alias.lg "log --graph --oneline --all --decorate"   # `git lg` = THE pretty history graph (Chapter 14.2)
git config --global alias.undo "reset --soft HEAD~1"      # `git undo` = uncommit, keep changes staged (Chapter 26.5, soft mode)
```

Aliasing any flag you can decode is legitimate; the discipline is naming aliases after their *meaning* (`unstage`, `undo`, `last`), not their letters. Aliases with shell power start with `!`: `git config --global alias.cdls '!cd "$1" && ls'` style (rarely needed; know the `!` convention when you meet it). Remove one with `git config --global --unset alias.st`, or view them all with `git config --global --get-regexp alias`. Fair warning: `git lg` is habit-forming - it is the graph from Chapter 14, one keystroke away, and it is how professionals actually *watch* repositories evolve.

---

### Chapter 29: Submodules

#### 29.1 The Problem

Sometimes project A needs to include project B, and both are independent Git repositories with their own histories - you want to embed B inside A without merging them into one repository. Classic cases: a shared component library used by several apps, a vendored external tool, or a documentation theme. Git's feature for this is the **submodule**: a repository embedded inside another repository, pinned to one exact commit.

#### 29.2 Adding a Submodule

```bash
git submodule add git@github.com:yourname/shared-lib.git lib/shared    # embed shared-lib's repository at the path lib/shared
```

**Anatomy:** `git submodule` - the subcommand family; `add` - register a new embedded repository; the URL - where to clone it from; `lib/shared` - the path inside *this* repository where it will live (optional; defaults to the repo name).

Two changes appear, both of which must be committed:

1. `.gitmodules` - a new tracked file recording the mapping. Its content, decoded:

```text
[submodule "lib/shared"]              # the section: one embedded repository
    path = lib/shared                 # where it lives inside THIS repository
    url = git@github.com:yourname/shared-lib.git    # where a fresh clone should fetch it from
```

2. A staged entry `lib/shared` that is not a normal file but a **gitlink**: the recording of "this path points at that repository, pinned to this exact commit." Commit both, and push. Note what the parent repository does *not* contain: the submodule's files or history - only the *pointer* (this is why submodules stay lightweight, and also the root of their confusion, next section).

#### 29.3 Cloning a Repository That Has Submodules

A plain clone fetches the parent but leaves the submodule paths *empty* - the classic "why is this folder empty" surprise. Two equivalent fixes:

```bash
git clone --recurse-submodules git@github.com:yourname/project-a.git    # clone AND fetch submodules, one command
# or, inside an existing clone:
git submodule update --init --recursive    # initialize (register paths from .gitmodules) and fetch each pinned commit; --recursive handles submodules-inside-submodules
```

#### 29.4 Living With Submodules

Enter `lib/shared` and it behaves as the full repository it is: its own branches, commits, history (you can even check its `.git`). Two behaviors define daily life:

**Working inside it:** changes committed inside the submodule affect only the submodule. The parent still pins the *old* commit until you re-pin:

```bash
cd lib/shared && git switch main && git pull    # bring the submodule up to date (inside the submodule)
cd ../.. && git add lib/shared && git commit -m "chore: bump shared-lib submodule"    # re-pin it in the PARENT: normal add/commit of the path records the new pinned commit
```

**The detour warning:** `cd lib/shared; git status` will often say `HEAD detached at <hash>` (Chapter 21.6). This is normal: the parent pinned a *commit*, not a branch, so the submodule checks out that commit directly. Detached-and-inspecting is safe; if you want to *develop* in the submodule, first `git switch main` (or a work branch) inside it.

#### 29.5 When NOT to Use Submodules

Honest consensus: submodules are Git's most-hated feature, and the feeling is earned - empty folders after cloning, detached HEADs, teammates forgetting `--init`, updates that need two repositories' worth of ceremony. Reach for alternatives first: **package managers** (npm, pip, Maven, Cargo) when the dependency can be a versioned package - which is *most* of the time; **one big repository** (a "monorepo") when the parts always evolve together and share tooling; **`git subtree`** when you want the vendor's files *merged into* your tree with their history preserved. Submodules earn their keep in a narrow zone: independent histories, exact-commit pinning, sparse inclusion. If you find yourself in that zone, you now know the machinery.

---

### Chapter 30: Inside the .git Directory

The entire guide has whispered it; this chapter says it plainly and proves it with your own eyes: **everything Git knows about your repository lives in one hidden folder.** Demystifying it is the difference between operating Git from memory and *understanding* it - and understanding it is what Chapter 26's undo wizardry, Chapter 19's rebase warnings, and every future error message are actually about.

#### 30.1 The Tour

Run `ls .git` inside `my-first-repo` and meet the residents, each with one job:

```text
HEAD         config       hooks/       info/        objects/     refs/
description  index        logs/
```

| Item | What it is |
| --- | --- |
| `HEAD` | one line: where "here" is (usually: which branch) |
| `config` | this repository's local settings (the `--local` level of Chapter 9) |
| `description` | unused placeholder for server software |
| `hooks/` | Chapter 28's hook scripts live here |
| `index` | the staging area, as an actual binary file - "the index" is a literal file |
| `info/` | rarely used extras (global excludes patterns) |
| `objects/` | THE database: every blob, tree, and commit this repository has ever committed |
| `refs/` | pointers: `refs/heads/*` are branches, `refs/tags/*` are tags |
| `logs/` | the reflog from Chapter 26.7, stored as append-only files |
| (occasional) `MERGE_HEAD`, `ORIG_HEAD`, `COMMIT_EDITMSG` | scratch state during operations: the merge in progress, the pre-rebase position, the last editor message |

#### 30.2 HEAD, Opened

```bash
cat .git/HEAD    # print the file (cat = concatenate/print, Chapter 10)
```

Output:

```text
ref: refs/heads/main
```

One line, decoded: HEAD is a *symbolic reference* - instead of naming a commit directly, it names another pointer: "the branch file at `refs/heads/main`." That indirection is what "being on a branch" means. Switch branches (`git switch`), `cat` it again, and the line changes. Check out a tag or commit directly and the file *stops being symbolic* - it holds a raw commit hash. That state is Chapter 21.6's "detached HEAD," now with its mechanical explanation: `cat .git/HEAD` says so, and so does `git status`.

#### 30.3 Branches, Opened

```bash
ls .git/refs/heads/     # list the branch files
cat .git/refs/heads/main    # print the content of the branch named main
```

Output:

```text
9a8b7c6d5e4f3a2b1c0d9e8f7a6b5c4d3e2f1a0b
```

That is the *entire content* of a branch: one commit ID, 41 bytes. Chapter 7's "branch is just a pointer" was literal, and here is the pointer on disk. Now prove the causality chain: `git branch experiment` and `ls .git/refs/heads/` again - a new file `experiment` appeared; `git branch -d experiment` and it is gone. `git commit` runs, and the `main` file's content changes to the new commit's ID. Tada: all of branching was file writes all along.

#### 30.4 The Database, Opened

```bash
ls .git/objects/        # see the two-character directories...
ls .git/objects/9a/     # ...inside one live the objects whose ID starts with 9a
```

Loose objects are stored one file per object, filed under the first two characters of their ID (efficiency: millions of files across 256 directories instead of one giant directory). Now meet your own commits as objects, with plumbing commands (Git's low-level vocabulary; the everyday commands you know are "porcelain"):

```bash
git cat-file -p HEAD     # -p = pretty-print the object HEAD points at
```

Output:

```text
tree 5d6e7f8...
parent 7c9e4f2...
author Your Real Name <your_email@example.com> 1760000000 +0200
committer Your Real Name <your_email@example.com> 1760000000 +0200

Add a second line to the greeting
```

**Decoded, line by line - this is Chapter 7.4 as a real object in your hands:** `tree 5d6e7f8...` - the snapshot this commit points to (the directory listing); `parent 7c9e4f2...` - the previous commit (absent on the very first commit: your root-commit from Chapter 12 had no parent line); `author`/`committer` - who and when, from your Chapter 9 identity, with a Unix timestamp; then the message, verbatim. Follow the tree: `git cat-file -p 5d6e7f8` prints the directory listing (filenames pointing to blob IDs and subtrees); follow a blob: `git cat-file -p <blob-id>` prints the file content itself. The chain commit -> tree -> blob from Idea Four is not a diagram anymore; it is three commands you just ran. (One more plumbing gem: `git hash-object hello.txt` prints what the ID of its current content *would be* - the identity mathematics of Idea Three, executed live.)

#### 30.5 Why This Tour Matters

Three payoffs, compounding forever. First, **fear reduction**: corruption and mystery shrink when the wizard is exposed as a filing cabinet (HEAD is a file; branches are files; history is a database of compressed objects). Second, **error literacy**: "refusing to update ref with old packed ref," "unable to create index.lock," "bad object" - future error messages describe *these specific things*, and Chapter 37 will read them to you fluently. Third, **confidence with danger**: now you know what `reset` moves (the branch file's content), what rebase creates (new objects; the old ones linger in `objects/` until garbage collection), and why the reflog (the `logs/` directory!) can find "lost" commits: they were never deleted from the database, only unreferenced. Git has been honest the whole time; now you have read its diary.

## Part G: Automation with GitHub Actions

Everything so far has been *you* operating Git. Part G teaches you to make *computers* operate it: running tests when you push, building on every pull request, and deploying your project automatically when main changes. This is CI/CD - the automation layer of modern software - and GitHub Actions is the tool that makes it three YAML files and zero servers.

### Chapter 31: GitHub Actions from Zero

#### 31.1 What CI/CD Means, Word by Word

- **CI - Continuous Integration:** every push (and every PR) triggers an automatic *integration check*: your code is fetched onto a fresh machine, where it is built and tested from scratch. The word "continuous" means *on every change*, not "eventually." The point: the bug you just introduced is reported in minutes, on a clean machine, not in three weeks on a teammate's laptop.
- **CD - Continuous Delivery:** after the checks pass, a *release artifact* (a build ready to ship) is produced automatically.
- **CD - Continuous Deployment:** the artifact is *deployed to real users* automatically - merge to main, and the site updates itself.

The problem this stack solves is the oldest one in teamwork: "works on my machine" (the bug class that appears only on machines that differ from yours), and its cousin "we tested it manually once and prayed." CI replaces prayer with a machine that re-verifies everything, identically, every time.

#### 31.2 What GitHub Actions Is

GitHub Actions is GitHub's built-in automation platform: when repository *events* happen (push, PR, schedule...), GitHub *rents you a computer* (a fresh virtual machine, called a **runner**), and on it executes the steps described in a file you committed to the repository. For public repositories this is free; private repositories include a monthly allowance of free minutes (GitHub bills usage beyond that - a meter you will not approach at this guide's scale).

#### 31.3 YAML in Three Minutes

Workflows are written in **YAML** (a human-readable configuration format, pronounced "YAM-el"), so here is the entire grammar you need, annotated:

```yaml
name: My workflow          # a key "name" with the value "My workflow"  (key: value, colon + space)
                            # a comment: everything after the # is ignored

jobs:                      # a key whose value is a LIST of things (plural key = list follows)
  - first-item             # list items start with "- " (hyphen + space), each on its own line
  - second-item            # each hyphen is a new list item

setup:                     # keys can have nested values by INDENTATION (2 spaces, never tabs)
  key-inside: value        # a key nested one level under "setup"
```

The one rule with no exceptions: **indentation carries meaning**, so mis-aligned spaces are the number-one workflow error. If a file ever fails mysteriously, check your indentation first.

#### 31.4 Where Workflows Live

Workflows live in the directory `.github/workflows/` at your repository root, one file per workflow, named anything ending `.yml`. Being ordinary repository files, they are versioned, reviewed via PRs, and upgraded with the code they serve. This is Actions' quiet genius: your automation is code, in your repository, exactly like everything else in this guide.

#### 31.5 Your First Workflow, Then Every Line of It

Create `.github/workflows/hello.yml` in `my-first-repo` with exactly this content:

```yaml
name: My first workflow

on: push

jobs:
  say-hello:
    runs-on: ubuntu-latest
    steps:
      - name: Greet the world
        run: echo "Hello from a GitHub runner!"
```

Commit and push it:

```bash
git add .github/workflows/hello.yml
git commit -m "ci: add first workflow"
git push
```

Then, on github.com, open your repository and click the **Actions** tab. Watch your workflow appear, click it, click the job `say-hello`, click the step `Greet the world`, and watch a machine you do not own print your greeting. Now the anatomy, line by line - this small file contains every structural concept in the entire platform:

- `name: My first workflow` - the display name in the Actions tab (cosmetic).
- `on: push` - **when to run**: on every push, of any branch. The `on:` key accepts events, branches filters, schedules...
- `jobs:` - the container of **jobs**. A workflow has one or more jobs, which *by default run in parallel*.
- `say-hello:` - a **job ID** you invent (no spaces; hyphens fine). Displayed as the job's name.
- `runs-on: ubuntu-latest` - **which machine to rent**: GitHub's newest Ubuntu runner (also `windows-latest`, `macos-latest`). This single line is the "server" you are not buying.
- `steps:` - the ordered list of the job's **steps**, executed top to bottom.
- `- name: Greet the world` - a new list item; a human label for the step (shown as a collapsible section in the UI).
- `run: echo "Hello!"` - the actual command to execute in the runner's shell. Steps come in exactly two kinds: `run:` (run this shell command) or `uses:` (run this pre-packaged *Action*, next section).

#### 31.6 The `uses:` Keyword: Pre-Packaged Power

`uses:` loads a published, reusable step. The one you will type most in your life:

```yaml
      - uses: actions/checkout@v4    # fetch YOUR repository's code onto the runner
```

**Decoded:** `actions/checkout` is the action's name (`actions` = GitHub's official account, `checkout` = the action that clones your repo onto the runner); `@v4` pins the major version to use. The deep reason it exists: your runner is a *stranger's blank machine* - it does not contain your code until checkout fetches it. That blankness is CI's superpower (a fresh machine on every run is what makes results trustworthy) and checkout is the bridge across it.

#### 31.7 The Vocabulary, Assembled

| Word | Meaning |
| --- | --- |
| Workflow | one `.yml` file: a trigger plus jobs |
| Event | what fires a workflow (`on:`): push, pull_request, schedule, manual |
| Runner | the fresh virtual machine a job runs on |
| Job | one parallelizable unit of work on one runner |
| Step | one item in a job's list: `run` a command or `uses` an action |
| Action | a pre-packaged reusable step (`uses: owner/action@version`) |

#### 31.8 The Badge (Proof of Health, Publicly)

At the top of the repository's Actions tab, each workflow offers a **status badge** - a live image URL that reads passing/failing. Embedding it in a README (the professional handshake you have seen a thousand times):

```markdown
![CI](https://github.com/yourname/my-first-repo/actions/workflows/hello.yml/badge.svg)
```

**Decoded:** `![CI](URL)` is Markdown's image syntax (alt text `CI`, then the image URL); the URL points at your repository's badge endpoint, which GitHub renders as a green "passing" or red "failing" badge, live. Every serious open source project wears these at the top of its README; by Part H you will too.

#### 31.9 The Events You Will Actually Trigger On

```yaml
on: push                                  # every push, any branch
on: [push, pull_request]                  # a LIST: pushes AND pull requests (PRs get their own run)
on:
  push:
    branches: [main]                      # only pushes TO main
on:
  pull_request:
    branches: [main]                      # only PRs TARGETING main
on: workflow_dispatch                      # a manual "Run workflow" button appears in the Actions tab
on:
  schedule:
    - cron: "0 3 * * 1"                    # weekly: minute hour day-of-month month day-of-week (this: Mondays 03:00 UTC)
```

The push-plus-pull_request combo is the CI standard: your feature branch gets tested as you work, and the PR gets its own authoritative record of the exact code being proposed for merge.

---

### Chapter 32: Building a Real CI Pipeline

#### 32.1 The Goal

A real pipeline for a JavaScript project: on every push and PR, install dependencies, run the linter, run the tests, and verify a production build succeeds - on a clean machine, on two Node.js versions, uploading the build as an artifact. Every line below is one you have either already met or will meet now, decoded.

Create `.github/workflows/ci.yml`:

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [20, 22]

    steps:
      - name: Check out the code
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ matrix.node-version }}
          cache: npm

      - name: Install dependencies
        run: npm ci

      - name: Lint
        run: npm run lint

      - name: Run tests
        run: npm test

      - name: Build
        run: npm run build

  package:
    needs: test
    runs-on: ubuntu-latest
    steps:
      - name: Check out the code
        uses: actions/checkout@v4

      - name: Build production bundle
        run: npm ci && npm run build

      - name: Upload build artifact
        uses: actions/upload-artifact@v4
        with:
          name: site-build
          path: dist/
```

#### 32.2 Every New Line, Decoded

- `on: push: branches: [main]` with `pull_request:` bare - run on pushes *to main only*, plus *every* PR regardless of target-branch (the standard CI posture: feature branches get checked via their PRs, main gets checked on every direct push).
- `strategy: matrix: node-version: [20, 22]` - a **matrix**: the `test` job runs once *per value*, i.e., twice - once on Node 20, once on Node 22. Version drift is its own bug class ("works on Node 22, dies on 20"); the matrix catches it per-push.
- `uses: actions/setup-node@v4` - installs Node.js on the runner (the runner ships with many tools, but pinning versions is CI hygiene: your laptop, the runner, and production should all agree).
- `with:` - the *inputs* block for an action; every action accepts its own set of inputs.
- `node-version: ${{ matrix.node-version }}` - the `{{ }}` is Actions' expression syntax (variable substitution); `matrix.node-version` reads the current matrix cell's value. Each of the two parallel jobs inserts its own number here.
- `cache: npm` - save `~/.npm`'s download cache between runs. Repeat runs skip dependency downloads; the cache is stored keyed to your lockfile.
- `npm ci` - "clean install": installs *exactly* what `package-lock.json` records, deleting `node_modules` first, and *failing* if lockfile and manifest disagree. In CI it is the correct command where `npm install` ("install something reasonable") is the wrong one - CI is about reproducibility, not convenience.
- `run: npm run lint` / `npm test` / `npm run build` - the project's own scripts (from `package.json`'s `scripts` block); CI just runs what the project defines. The lesson generalizes: a good pipeline is thin - it runs the commands the project already owns.
- `needs: test` - **job dependency**: `package` waits for `test` to succeed on *all* matrix cells before starting. Without `needs:`, jobs run in parallel; with it, you draw the DAG.
- `uses: actions/upload-artifact@v4` with `name:` and `path: dist/` - after the build, upload the `dist/` folder as a downloadable **artifact**: a zip attached to the run's page in the Actions tab, retained for a default of 90 days. Artifacts are how CI output gets into hands (including yours, debugging at 2 a.m.).

#### 32.3 Where Results Live

Every run appears in the **Actions** tab: a list entry per event, colored green (success), red (failure), or yellow (running), each expandable to its jobs, each to its steps, each to its raw logs. On **pull requests**, the run's verdict appears *inside the PR* under the Checks tab - which is the professional tie-in: repository Settings -> Branches -> Branch protection for `main` can require "status checks" to pass before merging is even possible. That is the closed loop: tests fail, PR cannot merge, main stays green - forever (Chapter 23.2's rule 1, now enforced by machinery instead of discipline).

One debugging reflex for your first failures: read the failing step's log from the top - the first `error` in the wall of text is the real one; the lines below it are aftershocks. And remember the YAML reflex from 31.3: malformed indentation fails before your code even runs.

---

### Chapter 33: Continuous Deployment

#### 33.1 The Idea

CI verifies your code; **CD ships it**: merge to main, and the site is rebuilt and re-published with no human hands. This chapter deploys to **GitHub Pages** (free static hosting, Chapter 25.6) with the modern Actions-based flow, then sketches deploying to a real server.

#### 33.2 The Pages Deployment Workflow

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: pages
  cancel-in-progress: true

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Check out the code
        uses: actions/checkout@v4

      - name: Configure Pages
        uses: actions/configure-pages@v4

      - name: Upload site content
        uses: actions/upload-pages-artifact@v3
        with:
          path: .

      - name: Deploy
        id: deployment
        uses: actions/deploy-pages@v4
```

#### 33.3 Every Line, Decoded

- `on: push: branches: [main]` + `workflow_dispatch:` - deploy when main changes, plus a manual button for re-deploys on demand. Deploying only from main is deliberate: main is the only branch people trust (Chapter 23), and deployment is the maximum-trust action.
- `permissions:` - **least-privilege, per-workflow tokens**. By default a workflow's token is broad; this block shrinks it to exactly what deploying needs: `contents: read` (read the code), `pages: write` (publish to Pages), `id-token: write` (prove this workflow's identity to the Pages service - the modern OIDC authentication, no stored passwords at all).
- `concurrency: group: pages` + `cancel-in-progress: true` - serialize deploys: a second deploy while one runs is queued (or the older one cancelled). Deploys racing each other produces last-write-wins chaos; this makes them orderly.
- `environment:` - GitHub's environments feature: this job targets the protected `github-pages` environment, and `url:` publishes the final link into the run's UI. (On serious projects, environments gate deploys: `production` can require manual approvals.)
- `actions/configure-pages@v4` - prepare the Pages service for this repository.
- `actions/upload-pages-artifact@v3` with `path: .` - bundle the site (here: the repository *is* the site, so the path is the whole folder; a built project would say `path: dist/`, combining with Chapter 32's build).
- `id: deployment` + `actions/deploy-pages@v4` - the final act: publish. The `id:` gives the step a name other lines can reference - which `url: ${{ steps.deployment.outputs.page_url }}` above does exactly: read the URL this step outputs, and display it.

#### 33.4 Turning It On

Settings -> Pages -> under Build and deployment, set **Source: GitHub Actions**. (The legacy "deploy from branch" mode is the Chapter 25.6 click-path; Actions source is the modern, controllable one.) Push to main once more, watch the Actions tab, and open the URL the run prints: `https://yourname.github.io/my-first-repo/` - your repository, live on the internet, re-published by machinery on every push to main.

#### 33.5 Deploying to a Real Server Instead

For a virtual private server or any machine with SSH access, the same skeleton with different final steps: connect with SSH and run the deploy commands there.

```yaml
      - name: Deploy over SSH
        uses: appleboy/ssh-action@v1        # a popular community action that runs commands on your server via SSH
        with:
          host: ${{ secrets.SERVER_HOST }}    # the server's address, stored as a secret
          username: ${{ secrets.SERVER_USER }}
          key: ${{ secrets.SERVER_SSH_KEY }}   # the private key, stored as a secret
          script: |                           # the pipe makes a MULTI-LINE value: the commands to run ON the server
            cd /var/www/app
            git pull
            npm ci --omit=dev
            systemctl restart app
```

The single new concept is **secrets**: repository Settings -> Secrets and variables -> Actions -> New repository secret. A secret is a named value GitHub encrypts and exposes *only* to workflows as `${{ secrets.NAME }}` - never printed in logs, never visible after saving. The deployment keys to your server have no business in a repository file (Chapter 15's `.gitignore` protects files from *accidents*; secrets protect values from *existing in the repo at all*). Between this pattern and the OIDC token of 33.3 lies the entire modern philosophy: **credentials belong in secret stores, never in repositories.**

#### 33.6 The CD Pyramid You Just Climbed

Level 1: publish on merge to main (this chapter). Level 2: environments with approvals for production. Level 3: deploy on *tags* only (`on: push: tags: ["v*"]`), so releases - Chapter 21's semantic monuments - trigger shipping. All three are the same skeleton you now own, with different triggers and destinations.

## Part H: Mastery and the Real World

Part H is where everything you have learned becomes one continuous professional performance: a real application, planned in issues, built in branches, merged through pull requests, tested by automation, tagged as a release, and deployed to a live URL. Then the surrounding skills: team workflows, best practices, troubleshooting, interview answers, and your roadmap.

### Chapter 34: Capstone Project: Build and Ship a Real Application

#### 34.1 Meet TaskFlow

You will build **TaskFlow**, a real, working to-do application: vanilla HTML, CSS, and JavaScript (no frameworks, no dependencies, nothing to install), persisted in the browser's localStorage, deployed live on GitHub Pages. The application is deliberately simple so the *workflow* is the star: every professional Git habit from Parts C through G gets exercised exactly once, in order. Here is the full journey on one page:

```text
 1. git init the project                          (Chapter 11)
 2. Build a minimal skeleton, commit atomically    (Chapters 12-13)
 3. Push it to a brand-new GitHub repository       (Chapter 22)
 4. Plan features as Issues                         (Chapter 25)
 5. Build each feature: branch -> commit -> PR     (Chapters 16, 23)
 6. Tag v1.0.0 and publish a GitHub Release        (Chapters 21, 25)
 7. Add a CI workflow that tests it                 (Chapters 31-32)
 8. Deploy it live with an Actions workflow         (Chapters 25, 33)
```

#### 34.2 Step 1 - Create the Project

```bash
mkdir ~/git-practice/taskflow    # create the project folder
cd ~/git-practice/taskflow       # enter it
git init -b main                 # initialize the repository, first branch named main (Chapter 11)
```

Now create the skeleton. Create `index.html` with this content - every line annotated:

```html
<!DOCTYPE html>                        <!-- line 1: "this document is HTML5" - the standard opening declaration -->
<html lang="en">                       <!-- the root element; lang helps screen readers and search engines -->
  <head>                               <!-- metadata: everything ABOUT the page, not visible in it -->
    <meta charset="UTF-8" />           <!-- character encoding: enables any language's characters -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" /> <!-- make it behave on phones -->
    <title>TaskFlow</title>            <!-- the text in the browser tab -->
    <link rel="stylesheet" href="style.css" /> <!-- attach the stylesheet (Chapter 15's ignored-by-nothing file) -->
    <script src="app.js" defer></script> <!-- attach the JavaScript; "defer" = run after HTML is fully parsed -->
  </head>
  <body>                               <!-- the visible page -->
    <main class="container">           <!-- a semantic wrapper; the class hooks CSS -->
      <h1>TaskFlow</h1>                <!-- the heading -->
      <p class="subtitle">A to-do app, versioned with Git.</p>
      <!-- the input row: a text field and a button, ready for the add-task feature -->
      <form id="task-form">
        <input id="task-input" type="text" placeholder="What needs doing?" required />
        <button type="submit">Add</button>
      </form>
      <!-- the task list: currently empty; JavaScript will fill it -->
      <ul id="task-list"></ul>
      <p id="task-count"></p>          <!-- the counter line, filled by JavaScript later -->
    </main>
  </body>
</html>
```

Create `style.css`:

```css
body {                                      /* the whole page */
  font-family: system-ui, sans-serif;       /* the OS's native font: clean, zero bytes downloaded */
  background: #f4f5f7;                     /* soft gray backdrop */
  color: #1f2430;                          /* dark text: good contrast */
  margin: 0;                               /* remove browser default margins */
}
.container { max-width: 520px; margin: 3rem auto; padding: 0 1rem; } /* centered column, 3rem above, safe on phones */
h1 { margin-bottom: 0.25rem; }
.subtitle { margin-top: 0; color: #6b7280; }
#task-form { display: flex; gap: 0.5rem; margin: 1rem 0; } /* input and button side by side, small gap */
#task-input { flex: 1; padding: 0.5rem; }  /* the input grows to fill the row */
#task-list { list-style: none; padding: 0; } /* remove default bullet styling */
#task-list li {                             /* each task row */
  display: flex; align-items: center; gap: 0.5rem;  /* checkbox, text, delete button in a row */
  background: #ffffff; padding: 0.6rem 0.8rem; margin-bottom: 0.5rem;
  border-radius: 6px; border: 1px solid #e5e7eb;
}
#task-list li.done span { text-decoration: line-through; color: #9ca3af; } /* completed tasks: crossed out */
#task-list li button { margin-left: auto; background: none; border: none; cursor: pointer; color: #ef4444; }
```

Create an empty placeholder `app.js` (a single comment line):

```js
// TaskFlow application logic arrives with the first feature branch.
```

Create `.gitignore` (Chapter 15's habit, from day one):

```text
.DS_Store        # macOS junk (Chapter 15's tour)
Thumbs.db        # Windows junk
.vscode/         # per-person editor state
```

#### 34.3 Step 2 - The Atomic First Commits

Practice Chapter 13.6 deliberately: three logical units, three commits.

```bash
git add index.html style.css
git commit -m "feat: add page skeleton and styling"
git add app.js
git commit -m "chore: add app.js placeholder"
git add .gitignore
git commit -m "chore: add gitignore"
```

And the badge that starts life immediately (Chapter 31.8): create `README.md` containing a title, a one-line description, and nothing else yet - we will grow it:

```bash
git add README.md
git commit -m "docs: add readme"
```

#### 34.4 Step 3 - Publish to GitHub

Create the repository on GitHub exactly as Chapter 22.2 taught (name `taskflow`, Public, no auto-files), then:

```bash
git remote add origin git@github.com:yourname/taskflow.git   # register the remote (Chapter 22.3)
git push -u origin main                                       # first push; -u dance once, forever (Chapter 22.4)
```

(Or the one-command version, Chapter 25.10: `gh repo create taskflow --public --source=. --push`.)

#### 34.5 Step 4 - Plan the Work as Issues

Click Issues -> New issue, and file four - each a small, well-scoped unit (Chapter 25.1's rules):

- Issue #1: "Add task creation" - submitting the form adds a task to the list.
- Issue #2: "Mark tasks complete" - checkbox strikes through the task.
- Issue #3: "Delete tasks" - per-task delete button.
- Issue #4: "Persist tasks and show a live counter" - localStorage + remaining count.

#### 34.6 Step 5 - Feature Cycle One: Add Task Creation (The Full Professional Loop, Once, Slowly)

```bash
git switch main && git pull      # ALWAYS start from the latest main (Chapter 23.3's liturgy)
git switch -c feat/add-tasks     # branch named for the issue (Chapter 16 naming conventions)
```

Now write the real `app.js` - every line annotated:

```js
// TaskFlow application logic.

const form = document.querySelector("#task-form");        // find the <form> element by its id; const = never reassigned
const input = document.querySelector("#task-input");        // the text field
const list = document.querySelector("#task-list");         // the <ul> that displays tasks
const count = document.querySelector("#task-count");       // the counter line

let tasks = [];                                           // the in-memory task list; "let" because its CONTENT changes
                                                           // (tasks will persist to localStorage in issue #4)

function render() {                                        // redraw the list from the data: the single source of truth
  list.innerHTML = "";                                     // clear the current display...
  for (const task of tasks) {                              // ...then rebuild it from the array...
    const li = document.createElement("li");               // one <li> per task
    const box = document.createElement("input");             // its checkbox...
    box.type = "checkbox";                                 // ...is literally an input of type checkbox
    box.checked = task.done;                              // reflect the data
    const span = document.createElement("span");             // the task text...
    span.textContent = task.text;                          // ...safely as TEXT (never innerHTML: user input!)
    const del = document.createElement("button");           // the delete button
    del.textContent = "x";                                 // a plain glyph; issues #2 and #3 wire these up
    li.append(box, span, del);                              // assemble the row
    list.append(li);                                       // add it to the list
  }
  const left = tasks.filter((t) => !t.done).length;         // count NOT-done items (filter keeps where condition true)
  count.textContent = left + " of " + tasks.length + " remaining";   // the live counter (issue #4's visible half)
}

form.addEventListener("submit", (event) => {               // when the form is submitted...
  event.preventDefault();                                  // ...stop the browser's default full-page reload
  const text = input.value.trim();                         // read and trim the input
  if (!text) return;                                       // ignore empty submissions (belt: the input is also "required")
  tasks.push({ text: text, done: false });                 // add a task OBJECT {text, done} to the data
  input.value = "";                                        // clear the field for the next entry
  render();                                                // redraw
});
```

Commit and publish the branch (Chapter 23.3, verbatim):

```bash
git add app.js
git commit -m "feat: add task creation (closes #1)"    # the (closes #1) spell: merging auto-closes Issue #1
git push -u origin feat/add-tasks
```

Open the pull request on GitHub (base `main` <- compare `feat/add-tasks`), with a description that follows the Chapter 23.3 template: **What** (submitting the form appends a task), **Why** (core feature, Issue #1), **How I tested** ("added three tasks locally; they appear; counter updates"). Self-review the Files-changed tab (yes, reviewing your own PR is a real habit), then **Squash and merge** (Chapter 23.5's modern default). Then the ritual (Chapter 23.6):

```bash
git switch main
git pull
git branch -d feat/add-tasks
```

Watch the PR page: Issue #1 auto-closed itself. That single sentence - *merged, and the issue closed itself* - is the professional loop closing with zero human bookkeeping.

#### 34.7 Feature Cycles Two and Three (The Same Loop, Faster)

**feat/complete-tasks** and **feat/delete-tasks** (Issues #2 and #3) follow the identical loop, so only the new code is shown. Both changes live inside `render()` - replace the middle of the loop with:

```js
    box.checked = task.done;                              // (unchanged) reflect the data...
    box.addEventListener("change", () => {                // WHEN the checkbox is toggled...
      task.done = box.checked;                            // ...update the DATA, not the pixels...
      render();                                           // ...and let render() repaint from data
    });                                                   // (data-first rendering: the habit scales forever)
```

Commit: `feat: toggle task completion (closes #2)`. And for deleting, after `del.textContent = "x";`:

```js
    del.addEventListener("click", () => {                 // WHEN the delete button is clicked...
      tasks = tasks.filter((t) => t !== task);             // ...drop THIS task from the array (identity check: "t" is not "this one")
      render();                                           // ...repaint
    });
```

Commit: `feat: delete tasks (closes #3)`. Each on its own branch, its own PR, its own squash-merge. Note the accumulating evidence of good habits: main grows by one clean commit per feature, issues close themselves, and each PR was small enough to genuinely review.

#### 34.8 Feature Cycle Four: Persistence (Issue #4)

Persistence belongs to *every* mutation: save after add, toggle, and delete; load at startup. On branch `feat/persist`:

```js
let tasks = JSON.parse(localStorage.getItem("taskflow-tasks") || "[]");  // ON STARTUP: read the saved string; JSON.parse revives the array; "|| '[]'" = first-visit fallback: empty list, never a crash
```

And one helper called after every mutation:

```js
function save() {                                          // one job: serialize and persist the data
  localStorage.setItem("taskflow-tasks", JSON.stringify(tasks));  // localStorage stores STRINGS; JSON.stringify turns the array into one
}
```

Add `save();` after each `tasks.push(...)`, `task.done = ...`, and `tasks = tasks.filter(...)` line, commit as `feat: persist tasks and show live counter (closes #4)`, PR, merge. Close your browser entirely, reopen: your tasks survived. The application is feature-complete.

#### 34.9 Step 6 - Tag and Release v1.0.0

```bash
git switch main && git pull    # stand on the finished product
git tag -a v1.0.0 -m "TaskFlow 1.0.0: create, complete, delete, persist"   # the annotated monument (Chapter 21.2)
git push origin v1.0.0         # tags travel only when explicitly pushed (Chapter 21.4)
```

On GitHub: Releases -> Draft a new release -> **Choose a tag** -> select `v1.0.0` -> auto-generate notes (Chapter 25.5) -> Publish. Your repository now has a public releases page.

#### 34.10 Step 7 - CI: The Application Tests Itself

Vanilla JavaScript with zero dependencies still deserves CI, and `node:test` (built into Node since version 18) makes it genuinely possible with zero installs. Create `tests/app.test.js` - every line annotated:

```js
const test = require("node:test");              // node:test = the built-in test framework (require = CommonJS import)
const assert = require("node:assert");           // node:assert = the built-in assertion library
const fs = require("node:fs");                   // node:fs = file system access (reading our own files)

test("index.html exists and is an HTML5 document", () => {        // a named test: the smallest unit of proof
  const html = fs.readFileSync("index.html", "utf8");            // read the file as text (utf8 = correct decoding)
  assert.ok(html.includes("<!DOCTYPE html>"));                    // assert.ok FAILS THE TEST if the value is falsy
  assert.ok(html.includes("task-form"));                          // the form the app depends on must exist
});

test("app.js contains the three core features by name", () => {
  const js = fs.readFileSync("app.js", "utf8");
  assert.ok(js.includes("render"));           // structure: rendering from data
  assert.ok(js.includes("preventDefault"));   // behavior: form handling without page reload
  assert.ok(js.includes("localStorage"));     // feature #4: persistence
});

test("style.css styles the task list", () => {
  const css = fs.readFileSync("style.css", "utf8");
  assert.ok(css.includes("#task-list"));     // the stylesheet targets the list
});
```

And `.github/workflows/ci.yml`, which you can now read fluently (Chapter 31-32):

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:                # every push to main, and every PR

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4          # fetch the code onto the blank runner
      - uses: actions/setup-node@v4        # install Node
        with:
          node-version: 20
      - run: node --test                    # Node's built-in test RUNNER: finds tests/*.test.js and runs them
      - run: node --check app.js            # bonus: full syntax validation of app.js (exits non-zero on any parse error)
```

Commit (`ci: add test workflow`), push to main, and watch the Actions tab run it green. Add the badge (Chapter 31.8) to `README.md`, commit, push - watch the badge appear, green, live.

#### 34.11 Step 8 - Deploy: The Live URL

Add `.github/workflows/deploy.yml` - it is *literally* Chapter 33.2's file (upload path `.`, since the site is plain static files). Settings -> Pages -> Source: GitHub Actions. Push, watch the run, then visit:

```text
https://yourname.github.io/taskflow/
```

Your application is live on the internet, and every future merge to main redeploys it automatically.

#### 34.12 Step 9 - Finish the README

Grow the README into the Chapter 36.4 shape: title + badge, one-paragraph description, a screenshot, live demo link, and how to run it locally (clone, open `index.html`). Final commits, final push - and this time, deliberately, on a branch with a PR, because it is muscle memory now, not ceremony.

#### 34.13 What You Just Practiced

| Skill | Where | Where it was taught |
| --- | --- | --- |
| init, atomic commits, conventional messages | Steps 1-2 | Chapters 11-13 |
| remotes, first push | Step 3 | Chapter 22 |
| issues as planning | Step 4 | Chapter 25 |
| branch -> commit -> PR -> squash-merge -> cleanup | Steps 5-8 | Chapters 16, 23 |
| closing issues via PR | Steps 5-8 | Chapter 23.3 |
| annotated tags, GitHub Releases | Step 6 | Chapters 21, 25 |
| CI with tests on every push/PR | Step 7 | Chapters 31-32 |
| automated deployment | Step 8 | Chapter 33 |

One final exercise that doubles as an exam: **clone your own project on another machine** (`git clone git@github.com:yourname/taskflow.git`), and continue its development there - a new feature, through the full loop. If that works (it will), you have not just read this guide; you have *deployed* its skills across machines, which is the definition of having them.

### Chapter 35: Team Workflows

You know every move; a **workflow** is the *choreography* a team agrees on: which branches exist, who merges what, and how code reaches production. There are three dominant choreographies in the industry, and choosing among them - or at least understanding the one your team uses - is a mark of seniority.

#### 35.1 GitHub Flow: The One You Already Know

You have been doing GitHub Flow since Chapter 23: `main` is always deployable; all work happens on short-lived branches; PRs review and merge it; deploys follow merges. That is the entire specification - six lines, no special branches, no ceremony.

```text
   main:  ---o---o---o---o---o---o--->      (every o = a reviewed, tested, deployable state)
                 \     / \        /
       branches:  o---o   o---o---o         (short-lived feature/fix branches, PR'd, squash-merged, deleted)
```

**Where it shines:** web applications and services, deployed continuously, small-to-huge teams (it is GitHub's own internal workflow, hence the name). **Where it strains:** software with formal versioned releases (mobile apps, installed software) needs more scaffolding - which is what Git Flow provides.

#### 35.2 Git Flow: The Full Cathedral

Git Flow (a 2010 convention by Vincent Driessen) formalizes releases with dedicated long-lived branches:

| Branch | Purpose | Lives |
| --- | --- | --- |
| `main` (or `master`) | production only: every commit is a shipped release, tagged | forever |
| `develop` | the integration line: where features accumulate toward the next release | forever |
| `feature/*` | one unit of work, branched *from develop*, merged *into develop* | days |
| `release/*` | stabilization of the upcoming version ("v1.2.0-rc1": no new features, bugfixes only), merged to both `develop` and `main` | days |
| `hotfix/*` | urgent production fix, branched from `main`, merged into both `main` and `develop` | hours-days |

```text
 main:    ---o(v1.0)------o(v1.1)------------->    (tags on every release commit)
              \            / \         /
 develop:     o--o--o--o--o---o--o--o-->         (integration; version merges back down)
               \    /          \    /
 features:      o--o            o--o              (branched from, merged back to develop)
```

**Where it shines:** versioned, scheduled releases; multiple supported versions alive simultaneously. **Where it strains:** continuous web deployment (the `develop` detour adds latency to every change - and note the modern successor tooling is the `git-flow` command suite, while most web teams have simply moved on to the alternatives below).

#### 35.3 Trunk-Based Development

The high-velocity philosophy: everyone merges to `main` ("the trunk") *very* frequently - multiple times a day; branches live hours, not days. The enabler of such boldness: **feature flags** (runtime switches hiding unfinished code paths in production, so an incomplete feature ships dark and is enabled when ready) plus relentless CI on every push (Chapter 32 made you fluent in that half already).

**Where it shines:** large organizations optimizing for integration speed (Google and Meta famously run variants of it). **What it demands:** the strongest automated test culture of the three - trunk-based with weak tests is just chaos with a name.

#### 35.4 Choosing

| Your situation | Reach for |
| --- | --- |
| Web app/service, deploy often, small-or-medium team | **GitHub Flow** (the default answer; also this guide's) |
| Versioned releases, app stores, multiple supported versions | **Git Flow** |
| Large org, mature test culture, integration speed is god | **Trunk-based** |

For learning teams, GitHub Flow's simplicity wins: it exercises 100% of the skills from this guide and hides none of its mistakes behind ceremony.

#### 35.5 Hardening GitHub Flow: Protected Branches and CODEOWNERS

Two GitHub settings convert workflow *conventions* into workflow *guarantees*. Repository Settings -> Branches -> Add branch protection rule for `main`:

- **Require a pull request before merging** - direct pushes to main are rejected; the PR is not optional bureaucracy, it is technically impossible to skip.
- **Require approvals** (1 or 2) - a second human must have approved.
- **Require status checks to pass** - the Chapter 32 CI run must be green; a red build blocks the merge button itself.
- **Require linear history** - rejects merge commits, enforcing the squash-and-merge aesthetic.

And `CODEOWNERS` - a file at repository root (`.github/CODEOWNERS`) mapping paths to the people whose *review is automatically requested*:

```text
# .github/CODEOWNERS
*                        @yourname                     # default: the repo owner reviews everything
/docs/                   @tech-writers-team            # documentation changes need the writers' review
/src/payments/            @payments-team @alice        # the payments code needs its owning team AND alice
.github/workflows/        @devops-team                 # CI/CD changes get DevOps eyes automatically
```

**Decoded, line by line:** the format is `<path pattern> <owners>`; `*` matches everything (the fallback rule); owners prefixed with `@` are GitHub accounts or teams; more specific (later) rules refine more general (earlier) ones. The effect: PRs that touch payments automatically add `@payments-team` as required reviewers. Code ownership that enforces itself is one of the cheapest quality systems a scaling team can install - and you can already read its whole configuration language, because it is four lines of pattern-matching you have seen twice before (`.gitignore` in Chapter 15, `.gitmodules` in Chapter 29).

---

### Chapter 36: Best Practices and Golden Rules

#### 36.1 Daily Discipline

**Pull before you start; push before you stop.** Begin every session with `git pull` (begin from everyone's latest), end every session with `git push` (never leave finished work marooned on one machine; the laptop that falls in the ocean takes unpushed commits with it - Chapter 22 made this a two-word habit).

**Commit small, commit often, commit honestly.** Small atomic commits (Chapter 13.6) are not bureaucracy; they are what makes revert (Chapter 26.6), cherry-pick (Chapter 27.1), and bisect (Chapter 27.2) surgical instead of catastrophic. The professional test of a commit: "could I explain this one in a single subject line?" If not, split it.

**Never sleep on uncommitted work.** The one loss Git cannot undo is the never-committed (Chapter 26.1's honest failure mode). A commit takes four seconds; make it.

**Branch for anything that takes more than minutes.** Branches are free (Chapter 16.6); `main`'s cleanliness is expensive. The reflex "about to try something? `git switch -c` first" is the single highest-leverage habit in this entire guide.

#### 36.2 The Unforgivable Sins

**Never commit secrets.** API keys, tokens, `.env` files, private keys: a pushed secret is compromised *even if you delete the commit later* - clones, forks, and scrapers move fast. The protocol: ignore `.env` from commit zero (Chapter 15), use GitHub secrets for CI values (Chapter 33.5), and if a secret *did* escape: rotate/revoke it *first* (assume it is captured), then clean history (filter-repo) as a courtesy. **Never rewrite shared history.** Chapter 19.6's Golden Rule, restated as culture: rebase your private branches freely; merge or revert everything public. **Never force-push to main.** It is the rewrite-sin at maximum volume; branch protection (Chapter 35.5) exists to make it impossible.

#### 36.3 Collaboration Craft

**Small pull requests.** Review quality collapses somewhere around 400 changed lines; split rather than apologize. **Review the code, never the coder** (Chapter 23.4's phrasing discipline), and when *receiving* review, remember that a requested change is collaboration, not verdict. **Update your branch, don't force-push it, during review** - new commits show reviewers exactly what changed since their last look; a rewritten history invalidates their work. **Link issues and PRs** (`Closes #N`, Chapter 23.3) so the project's paper trail writes itself. And **write the README your future contributor deserves**: what it is, a screenshot or live link, install and run instructions, how to contribute - Chapter 34.12 built exactly this shape, once, slowly; reproducing it is now minutes.

#### 36.4 The Ten Golden Rules

1. **`main` is sacred.** Every commit on it is reviewed, tested, and deployable; all work arrives via PR. (Chapters 23, 35)
2. **Commit early, commit often, commit atomically, message honestly.** (Chapter 13)
3. **Pull before you push.** The rejected push is a race you can always win politely. (Chapters 22, 37)
4. **Branch for experiments; delete branches without ceremony.** (Chapter 16)
5. **Stage deliberately (`git add <file>`); let `git status` narrate.** The unread status output is where mistakes hide. (Chapter 12)
6. **`.gitignore` from day one; secrets never in repositories, ever.** (Chapters 15, 36.2)
7. **Revert on shared branches; reset only on your own.** (Chapter 26)
8. **Rebase private work to keep history honest; merge shared work to keep history true.** (Chapter 19)
9. **When lost: `git status`, then `git reflog`, then breathe.** Almost nothing is truly lost. (Chapters 26, 30)
10. **Automate what you repeat: aliases for typing, hooks for checks, Actions for pipelines.** (Chapters 28, 31-33)

Tape rule ten to your monitor if you keep only one: every chapter of Part G began as someone repeating rule ten's manual version until it hurt. Now - the encyclopedia of when things hurt anyway, and their cures.

### Chapter 37: Troubleshooting Encyclopedia

Errors are not failure; they are Git talking to you. Every entry below follows the same shape: the exact message, what it *actually* means, the fix with annotated commands, and the prevention. Read this chapter twice: once now, once the first time something below happens to you and your memory whispers "this was in the encyclopedia."

#### 37.1 `fatal: not a git repository (or any of the parent directories): .git`

**Meaning:** you ran a Git command in a folder that is not inside any repository - Git walked upward through parent folders looking for a `.git` directory (Chapter 11) and found none. **Fix:** `pwd` to see where you actually are, `cd` to your project folder, and retry; or `git init` if the project genuinely needs to be born. **Prevention:** the prompt habit - check that your shell is where you think it is; or a glance at `git status`, which cannot lie to you about repository-ness.

#### 37.2 `Please tell me who you are` (fatal: unable to auto-detect email address)

**Meaning:** your first-ever commit on a machine, before Chapter 9's identity configuration. Git refuses to author anonymous history. **Fix:**

```bash
git config --global user.name "Your Real Name"     # the identity, installed once (Chapter 9.2)
git config --global user.email "your_email@example.com"
```

**Prevention:** Chapter 9 exists precisely for this moment.

#### 37.3 `nothing to commit, working tree clean`

**Meaning:** not an error at all - your staging area and history agree perfectly (Chapter 12.5's phrase). Common in two confusing disguises: you forgot to `git add` your new edits, or you already committed and forgot. **Fix:** if you expected changes to be waiting, run `git add .` then `git status` again; and `git log -1` to see whether you in fact already committed it. **Prevention:** `git status` *before* `git commit`, always - it narrates reality.

#### 37.4 `! [rejected] main -> main (fetch first)` (hint: Updates were rejected...)

**Meaning:** the remote has commits you do not have - someone (or you, on another machine, Chapter 34.13) pushed first. Git refuses your push because accepting it would orphan their work. This is not corruption; it is Git protecting your teammate. **Fix:**

```bash
git pull                     # fetch + merge their work into yours (or rebase, if pull.rebase is set)
# (resolve any conflicts exactly as Chapter 18 taught)
git push                     # now your work sits atop theirs; push succeeds
```

**Prevention:** rule 3 - pull before you push, and push before you stop.

#### 37.5 `fatal: refusing to merge unrelated histories`

**Meaning:** two histories with *no common ancestor*: classically, you created a GitHub repository *with* a README/license (Chapter 22.2's warning about that checkbox), then connected a local repository with its own separate first commit. Git is asking: "am I really looking at two beginnings of one project?" **Fix**, when you are sure it is one project:

```bash
git pull origin main --allow-unrelated-histories    # the explicit override: "yes, merge the two beginnings"
# (resolve conflicts if both sides created the same file, e.g., README.md)
git push
```

**Prevention:** when connecting an existing local repo, create the GitHub side *empty* (no README, no license) - Chapter 22.2's checklist.

#### 37.6 `Permission denied (publickey)` / `fatal: Could not read from remote repository`

**Meaning:** the SSH handshake from Chapter 10.6 failed: your key is missing, not loaded, or not the one GitHub has. **Fix, in order of likelihood:**

```bash
ls ~/.ssh/id_ed25519*                  # 1. Does the key exist at all? If nothing prints: rerun ssh-keygen (Chapter 10.4)
ssh -T git@github.com                   # 2. Test the connection (success prints "Hi yourname!" - Chapter 10.6)
cat ~/.ssh/id_ed25519.pub               # 3. If the test fails: is THIS key's public half on GitHub? (Settings -> SSH keys)
git remote -v                          # 4. Is the remote even SSH-form? An https:// URL uses PAT auth, not SSH keys
```

**Prevention:** one deliberate Chapter 10 setup session, once per machine.

#### 37.7 `fatal: Authentication failed` (HTTPS / PAT)

**Meaning:** HTTPS remotes authenticate with a Personal Access Token (Chapter 22.7), and yours is missing, mistyped, or expired. **Fix:** create a fresh token (github.com -> Settings -> Developer settings -> Personal access tokens -> fine-grained, scoped to your repositories) and let your credential manager store it on first use; or sidestep tokens entirely by switching the remote to SSH: `git remote set-url origin git@github.com:yourname/repo.git`. **Prevention:** SSH keys (Chapter 10) - they never expire silently.

#### 37.8 `You are in 'detached HEAD' state`

**Meaning:** HEAD is pinned to a commit instead of riding a branch - you checked out a tag or commit ID (Chapter 21.6), or poked around an old hash. Not dangerous for *looking*; dangerous for *committing* (a commit made here belongs to no branch and is hard to find again). **Fix:** `git switch main` (or your branch) to reattach. If you already committed in detached state and want the work: `git branch rescue <that-commit-id>` before switching, or find it later via `git reflog` (Chapter 26.7). **Prevention:** visiting history with `git switch --detach` *while knowing it is a visit*, and `git log`/`git show` (read-only tools) instead of checkout when you only want to look.

#### 37.9 `error: Your local changes to the following files would be overwritten by merge/checkout`

**Meaning:** you have uncommitted edits in a file that the incoming operation wants to rewrite; Git refuses to steamroll your work. **Fix, choose your truth:**

```bash
git stash                       # option A: the edits are precious - drawer them (Chapter 20), operate, pop later
git restore <file>              # option B: the edits are garbage - discard them (Chapter 26.2), then retry
git commit -am "wip"            # option C: commit them first, as a real save point
```

**Prevention:** clean-or-stashed working directory before switching and merging - the three-way decision above *is* the professional reflex.

#### 37.10 `error: Another git process seems to be running... (index.lock exists)`

**Meaning:** a previous Git operation died mid-flight (crash, closed terminal) and left its lock file - Git's "do not disturb" sign for the staging area (Chapter 30's `index` plus its `index.lock` sibling). **Fix:**

```bash
ps aux | grep git               # 1. Confirm NO git process is genuinely running (if one is: wait or close it)
rm -f .git/index.lock           # 2. Remove the stale lock (safe ONLY when no git process is running)
```

**Prevention:** little to do - it is a crash artifact, not a habit flaw. The file's existence and meaning are yours to read now, courtesy of Chapter 30.

#### 37.11 A merge is stuck half-done

**Meaning:** you started a merge (or rebase, or cherry-pick), conflicts appeared (Chapter 18), and you wandered off / got confused. `git status` will say `You have unmerged paths` (or `interactive rebase in progress`). **Fix:** the two exits are always the same pair: finish (edit, `git add`, `git commit` or `git rebase --continue`) or abort (`git merge --abort` / `git rebase --abort` / `git cherry-pick --abort` - all restore the pre-operation state exactly). Search files for leftover markers if `status` still complains: `grep -rn "<<<<<<<" .` finds any marker Git is waiting on you to remove.

#### 37.12 `warning: LF will be replaced by CRLF` (or the reverse)

**Meaning:** not an error - Chapter 9.4's line-ending normalization doing its job out loud. Windows's two-character line endings (CRLF) versus the universal single LF: your `core.autocrlf` setting is harmonizing them, and warning you about it, verbosely, forever. **Fix:** nothing; or silence it by adding a `.gitattributes` file with one line, `* text=auto`, which makes the rule explicit and portable (the same normalization, declared in the repository instead of per-machine config). **Prevention:** the Chapter 9.4 settings at setup time; formatting tools (Prettier et al.) end the deeper tabs-vs-spaces noise.

#### 37.13 The 100 MB wall: `remote: error: File ... exceeds GitHub's file storage limit`

**Meaning:** GitHub rejects files over 100 MB and warns on those over 50 MB - repositories are for source, not for videos, datasets, and installers. **Fix for the future:** the file belongs in `.gitignore` (Chapter 15), in cloud storage, or in **Git LFS** (Large File Storage - an official extension that tracks huge files as small pointers and stores the bytes elsewhere). **Fix for the crime already committed:** if it *only* exists in recent local commits, unwind with `git reset --soft HEAD~N` and commit properly without it; if it has been pushed, history rewriting with `git filter-repo` is the standard tool - a genuinely advanced operation; and if the file was a *secret* rather than merely *large*, reread Chapter 36.2's protocol: rotate first, clean second.

#### 37.14 `error: src refspec main does not match any`

**Meaning:** you tried to push a branch name that does not exist locally - almost always pushing from a repository with zero commits, or before your first commit on `main`. **Fix:** commit something first (`git status` narrates what is pending), then push; if your local branch is genuinely named differently (`master` from an old default), rename it (`git branch -m main`, Chapter 11.2) or push the name that exists. **Prevention:** the Chapter 9 `init.defaultBranch main` setting makes the mismatch never happen on your machines.

#### 37.15 The Meta-Errors: YAML and Indentation (Actions)

From Chapter 31: workflows failing with `invalid yaml` or `while parsing a block mapping` are *indentation* errors, not code errors - two spaces, never tabs, alignment carries meaning. And a workflow file that lives anywhere except exactly `.github/workflows/*.yml` simply never runs (silently: the file is committed, GitHub ignores it). The debugging order for Actions failures: 1) did the workflow even trigger? (Actions tab) 2) which step red? (the first `error` in its log is the real one) 3) does it pass locally on a fresh clone? - the runner is a stranger's blank machine (Chapter 31.6), and "works on my machine" is precisely what CI exists to catch.

---

### Chapter 38: Git Interview Questions and Answers

Fifteen questions that cover what interviews actually ask. Answer in your own words first; then read the model answer.

**1. What is the difference between Git and GitHub?**
Git is a distributed version control program that runs locally on your machine, storing history in the hidden `.git` folder of a repository. GitHub is a website that hosts copies of Git repositories in the cloud and layers collaboration features on top - pull requests, issues, Actions automation, Pages hosting. They integrate (you push and pull between them) but they are separate products by separate origins.

**2. What is the difference between `git fetch` and `git pull`?**
`git fetch` downloads everything new from the remote and updates your remote-tracking markers (`origin/main`) while changing nothing else - you can inspect before integrating. `git pull` is `git fetch` immediately followed by a merge (or rebase, per configuration) into your current branch. Fetch is look-then-decide; pull is fetch-and-leap.

**3. What is the staging area and why does it exist?**
The staging area (index) is the list of changes that the next commit will contain. It exists so commits can be composed deliberately: you can stage two finished files and leave the half-written one out, letting each commit be one logical, reviewable, revertible unit of change instead of "everything on my disk right now."

**4. What is the difference between `git merge` and `git rebase`?**
Both integrate one branch's work into another. Merge creates a new commit with two parents, preserving the true history of parallel work. Rebase replays your commits one by one onto the target's tip, producing a linear history as if the work happened sequentially - but rewriting commit IDs. The professional rule: rebase your private, unshared branches; merge (or revert) anything already shared.

**5. What is the difference between `git reset` and `git revert`?**
Reset moves the current branch pointer backward to an earlier commit - history is rewritten from the branch's point of view (with `--soft/--mixed/--hard` controlling what survives on disk). Revert creates a *new* commit that performs the inverse of a given commit, so history only grows forward. Reset is for local, unshared history; revert is the shared-safe undo.

**6. What is HEAD?**
HEAD is Git's "you are here" pointer: normally a file (`.git/HEAD`) naming the branch you are on, which in turn names that branch's tip commit. Committing advances the current branch, which moves HEAD's referent. When HEAD holds a raw commit hash instead of a branch name, you are in "detached HEAD" state - safe for inspecting, unwise for committing.

**7. What is a fast-forward merge?**
A merge where the current branch has no new commits since the other branch diverged, so Git can simply slide the current branch pointer forward to the other branch's tip - no merge commit needed. `--no-ff` forces a merge commit anyway, recording explicitly that a feature branch existed.

**8. How do you undo a commit that has already been pushed to a shared branch?**
With `git revert <commit>`: it creates a new, inverse commit, which you push normally. Never `reset` or rewrite history on shared branches - teammates' histories would diverge from yours, producing duplicated and conflicting work.

**9. What is the reflog?**
The reference log: Git's local, append-only diary of everywhere HEAD and branch pointers have been. Because commits are objects in a database (and "deletion" usually just un-references them), the reflog typically lets you find and restore "lost" commits for around 90 days - the safety net behind `git reset --hard` mistakes.

**10. How does `git bisect` work?**
Binary search over history to find the commit that introduced a bug: you mark the current version bad and a known-good version good; Git checks out the midpoint, you judge it, and the suspect range halves each round - about six steps for 60 commits. `git bisect run <command>` automates the judging using a test's exit code.

**11. What is a detached HEAD state and how do you get out of it?**
HEAD pointing directly at a commit instead of riding a branch - caused by checking out a tag or commit hash. Exit with `git switch <branch>`. If you committed while detached and want that work, `git branch rescue <hash>` first (or find it via the reflog).

**12. What is the difference between an annotated and a lightweight tag?**
A lightweight tag is just a pointer file - a private bookmark. An annotated tag is a full Git object carrying tagger, date, message, and optional cryptographic signature, and it is what you publish for releases.

**13. How do you resolve a merge conflict?**
Git marks the file with `<<<<<<<` (your branch's side), `=======` (divider), and `>>>>>>>` (incoming branch's side). I edit the file into the version that should exist going forward - choosing one side, the other, or a combination - then `git add` the file to mark it resolved and `git commit` to complete the merge. `git merge --abort` cancels everything if needed.

**14. What is the staging command you would use to commit only *some* of the changes inside a single file?**
`git add -p <file>` (patch mode): it walks through the file's changed regions ("hunks") one by one, asking y/n per hunk, building a staging selection finer than whole files. (Chapter 12 mentioned it as a teaser; it is a fair interview follow-up.)

**15. What is the `.git` directory?**
The entire repository's machinery in one hidden folder: `HEAD` (the you-are-here pointer), `config` (local settings), `index` (the staging area, literally a file), `objects/` (the content-addressed database of every blob, tree, and commit), `refs/` (branches are small pointer files inside it), `logs/` (the reflog), and `hooks/`. Deleting it converts the project back into a plain folder with no history.

---

### Chapter 39: Your Roadmap to Mastery

#### 39.1 The Four-Week Practice Ladder

Reading this guide made you *literate*; the following month makes you *fluent*. Each week assumes about 30-60 minutes of deliberate practice, and each builds on the last exactly as the chapters did.

- **Week 1 - The loop, until it is boring.** Create a fresh repository every day and run the full Chapter 12 cycle: edit, status, add, commit, log, diff. On day 3, add branching (Chapter 16); on day 5, deliberately create and resolve a conflict (Chapter 18). Boring is the goal: fluency is boredom, installed.
- **Week 2 - Live on GitHub.** Push every practice repository (Chapter 22). Convert each of the five TaskFlow-adjacent mini-projects into a proper repo: README with badge, issues filed *before* working, each change through a PR you self-review, squash-merged. Tag each one `v1.0.0` with a Release (Chapter 34.9's shape).
- **Week 3 - Collaborate with yourself, then others.** Clone your own repos on a second machine (or a second folder) and practice pull-merge-push sync (Chapter 37.4's dance). Then go public: find an open source project you actually use, find its `good first issue` label (Chapter 24.4), and contribute one documentation fix through the full fork-and-PR workflow. The first merged PR is a career moment; documentation is the honest, high-merge-rate place to earn it.
- **Week 4 - Automate.** Add CI to one repository (Chapter 32's shape, adapted: real tests if the project has them, syntax checks if not), then a Pages deployment (Chapter 33). Break your own CI deliberately (introduce a failing test) and read the failure log - debugging the red X is half the skill of owning the green one.

#### 39.2 Project Ideas That Compound

The portfolio that grows from this ladder: a personal homepage at `yourname.github.io` (Chapter 25.6, deployed via your own Chapter 33 workflow); TaskFlow extended into *your* idea of a tool (recurrence? due dates? multiple lists? - each feature a branch and a PR); a `dotfiles` repository (your editor and shell configuration, versioned - a beloved developer tradition that doubles as configuration-as-code practice); and one contribution each to two open source projects (documentation counts, always).

#### 39.3 The Resources Worth Your Time

- **Pro Git** (git-scm.com/book) - the official, complete, free book by Scott Chacon and Ben Straub; Chapters 1-3 and 7 overlap beautifully with this guide's territory, and its reference chapters outlast any tutorial.
- **The official Git documentation and tutorials** (git-scm.com/doc) - `git help <command>` in your terminal is the same content, offline.
- **GitHub Skills** (skills.github.com) - GitHub's free interactive course platform; "Introduction to GitHub" and "Communicate using Markdown" are the natural next credits after this guide.
- **Learn Git Branching** (learngitbranching.js.org) - the famous interactive visual trainer for branching, merging, and rebasing; the sandbox where Chapter 7's pointer diagrams come alive.
- **Oh Shit, Git!?!** (ohshitgit.com) - the friendly emergency manual for exactly the Chapter 37 moments, with the profanity level the URL promises.
- **The GitHub docs** (docs.github.com) - authoritative for every platform feature: Actions, Pages, security, and the API.

#### 39.4 The Closing Perspective

You began this guide with the folder named `final_v2_FINAL_fixed_real_LAST.doc`, and you now know why that folder is extinct in professional software. You know the three areas and why every command is a transfer between them. You can branch, merge, resolve, rebase, revert, and rescue. You have shipped a real application through issues, pull requests, automated tests, and automated deployment, and you possess the encyclopedia for the days things go wrong anyway - because they will, to everyone, forever, and that is fine.

Git rewards depth for decades: every advanced topic you will ever meet - worktrees, filter-repo, `log -S`, replace refs, signed commits - is a composition of the ideas in this guide, built on the three areas, the checksummed objects, and the pointers. You did not just learn commands; you learned the machine underneath them.

The last assignment is the first one, again, for real: open a terminal, `git init` something that matters to you, and begin.

## Appendices

### Appendix A: Complete Command Reference

Every command taught in this guide, grouped by purpose. The chapter where each concept was taught appears in parentheses.

**Setup and configuration (Chapter 8-9, 10)**

| Command | Meaning |
| --- | --- |
| `git --version` | show the installed Git version |
| `git config --global user.name "Name"` | set the name stamped on your commits |
| `git config --global user.email "email"` | set the email stamped on your commits (match GitHub) |
| `git config --global init.defaultBranch main` | name new repositories' first branch `main` |
| `git config --global core.editor "code --wait"` | choose the editor for commit messages |
| `git config --global core.autocrlf true` / `input` | normalize line endings (Windows / macOS-Linux) |
| `git config --list [--show-origin]` | print all settings, optionally with source files |
| `git config --global --unset <key>` | remove a setting |
| `ssh-keygen -t ed25519 -C "email"` | generate an SSH key pair |
| `ssh -T git@github.com` | test the GitHub SSH connection |

**Starting repositories (Chapter 11)**

| Command | Meaning |
| --- | --- |
| `git init [-b main]` | make the current folder a repository |
| `git clone <url> [folder]` | download a full copy of a remote repository |
| `git clone --depth 1 <url>` | shallow clone: latest snapshot only |
| `git branch -m main` | rename the current branch to `main` |

**The daily loop (Chapters 12-14)**

| Command | Meaning |
| --- | --- |
| `git status [-sb]` | show the state of the three areas |
| `git add <file>` / `git add .` / `git add -A` / `git add -u` | stage files (specific / here / all / all-tracked) |
| `git add -p` | stage selected hunks interactively |
| `git commit -m "message"` | commit the staged snapshot, with message |
| `git commit -am "message"` | stage tracked changes and commit in one step |
| `git commit --amend [--no-edit]` | fix the most recent commit |
| `git log [--oneline -n --stat -p --graph --all]` | view history (compact / limited / with stats / with diffs / drawn) |
| `git log --grep="word"` / `--author="Name"` | filter history by message or author |
| `git show [revision]` | inspect one commit |
| `git diff` / `--staged` / `HEAD` | compare: disk-vs-staging / staging-vs-HEAD / disk-vs-HEAD |
| `git diff A B` / `--stat` | compare two commits or branches / summary only |
| `git blame [-L a,b] <file>` | who changed each line, when, in which commit |
| `git shortlog -sn` | commit counts per author |

**Ignoring files (Chapter 15)**

| Command | Meaning |
| --- | --- |
| `git status --ignored` | include ignored files in status |
| `git check-ignore -v <path>` | show which ignore rule matches a path |
| `git rm --cached <file>` | stop tracking a file, keep it on disk |

**Branching and merging (Chapters 16-18)**

| Command | Meaning |
| --- | --- |
| `git branch [-v]` | list branches (with tips) |
| `git branch <name>` | create a branch |
| `git branch -d / -D <name>` | delete a branch (safely / forcefully) |
| `git branch -m <new-name>` | rename the current branch |
| `git switch <branch>` | change branches |
| `git switch -c <name>` | create and switch in one step |
| `git switch -` | return to the previous branch |
| `git switch --detach <tag-or-commit>` | visit a commit or tag (detached HEAD) |
| `git merge <branch>` | merge that branch into the current one |
| `git merge --no-ff <branch>` | merge, always creating a merge commit |
| `git merge --abort` | cancel a conflicted merge |

**Rewriting and parking (Chapters 19-20)**

| Command | Meaning |
| --- | --- |
| `git rebase <branch>` | replay current branch's commits onto that branch |
| `git rebase -i HEAD~n` | interactively edit your last n commits |
| `git rebase --continue / --abort` | proceed past / cancel a rebase |
| `git stash [push -m "msg"]` | shelve uncommitted work |
| `git stash -u` | stash including untracked files |
| `git stash list` | show the stash stack |
| `git stash pop / apply [stash@{n}]` | restore (and remove / keep) a stash |
| `git stash drop / clear` | delete one / all stashes |

**Tags (Chapter 21)**

| Command | Meaning |
| --- | --- |
| `git tag` / `git tag -l "v1.*"` | list tags (all / matching pattern) |
| `git tag -a v1.0.0 -m "msg"` | create an annotated tag |
| `git tag -a v1.0.0 <commit>` | tag a past commit |
| `git show v1.0.0` | inspect a tag and its commit |
| `git tag -d v1.0.0` | delete a local tag |
| `git push origin v1.0.0` / `--tags` | push one / all tags |
| `git push origin --delete v1.0.0` | delete a remote tag |

**Remotes and collaboration (Chapters 22-24)**

| Command | Meaning |
| --- | --- |
| `git remote add <name> <url>` | register a remote (origin / upstream) |
| `git remote -v` | list remotes with addresses |
| `git remote set-url <name> <url>` | change a remote's address |
| `git remote rename / remove` | rename / forget a remote |
| `git push [-u origin main]` | upload commits (-u links the branch) |
| `git fetch [origin]` | download remote updates, change nothing local |
| `git pull [--rebase]` | fetch and merge (or rebase) into current branch |
| `git log main..origin/main` | commits the remote has that you don't |

**Undoing and recovering (Chapters 26-27)**

| Command | Meaning |
| --- | --- |
| `git restore <file>` | discard uncommitted changes to a file |
| `git restore --staged <file>` | unstage a file |
| `git reset --soft / --mixed / --hard HEAD~n` | undo n commits (keep staged / keep unstaged / erase) |
| `git revert <commit>` | undo a shared commit with an inverse commit |
| `git revert -m 1 <merge-commit>` | revert a merge commit |
| `git reflog` | the HEAD movement diary |
| `git clean -n` / `-f` / `-fd` | dry-run / delete untracked files |
| `git cherry-pick [-x] <commit>` | copy one commit onto the current branch |
| `git bisect start/bad/good/reset` | binary-search history for a bug |
| `git bisect run <command>` | automated bisect via a test command |
| `git grep [-n -i -c -l] "pattern" [revision]` | search tracked files (line numbers / insensitive / count / files / in history) |

**Hooks, aliases, internals (Chapters 28-30)**

| Command | Meaning |
| --- | --- |
| `chmod +x .git/hooks/<hook>` | activate a hook script |
| `git commit --no-verify` | skip hooks for one commit |
| `git config --global alias.<name> "<cmd>"` | create a shorthand |
| `git config --global --get-regexp alias` | list your aliases |
| `git submodule add <url> [path]` | embed a repository |
| `git submodule update --init --recursive` | populate submodules after cloning |
| `git clone --recurse-submodules <url>` | clone including submodules |
| `git cat-file -p <object>` | pretty-print any internal object |
| `git hash-object <file>` | show the checksum ID content would have |
| `git ls-files` | list the files in the index |

### Appendix B: Glossary

| Term | One-line meaning |
| --- | --- |
| Repository (repo) | a folder whose complete history Git stores in its `.git` directory |
| Working directory | the folder you actually see and edit ("real life") |
| Staging area / index | the waiting room of selected changes that the next commit will contain |
| Commit | a permanent, checksummed snapshot with message, author, and parent |
| SHA / hash | the 40-character checksum ID of any Git object |
| HEAD | the pointer marking where you are (usually: the current branch) |
| Branch | a movable pointer to one commit; a line of work |
| Checkout | old multi-purpose command for switching/creating branches and restoring files |
| `git switch` / `git restore` | the modern (2019) split of checkout's duties: branches / files |
| Merge | combining two branches' work into one history |
| Merge commit | a commit with two parents, recording a merge |
| Fast-forward | a merge where the branch pointer can simply slide forward |
| Conflict | two histories changed the same lines; a human decides the result |
| Rebase | replaying commits onto a new parent, producing linear history |
| Golden Rule | never rebase or rewrite history that others already have |
| Stash | a drawer for uncommitted work, restored later |
| Tag | a permanent named pointer, usually marking a release |
| Annotated tag | a full tag object with tagger, date, message |
| SemVer | MAJOR.MINOR.PATCH version numbering with meaning |
| Remote | a named shortcut to a copy of the repo elsewhere (GitHub) |
| origin / upstream | conventional remote names: yours / the original project |
| Remote-tracking branch | your local snapshot of a remote branch's position (`origin/main`) |
| Clone / fork | local copy of a repository / your server-side copy on GitHub |
| Pull request (PR) | the web page requesting that your branch be reviewed and merged |
| Squash merge | melting all of a PR's commits into one on merge |
| Issue | a tracked discussion for one bug or task |
| Release | a tag plus notes plus artifacts, published on GitHub |
| CI / CD | automatic test-and-build on every change / automatic delivery and deployment |
| Workflow / job / step / runner / action | GitHub Actions vocabulary: file / unit / item / machine / reusable step |
| Reflog | the local diary of HEAD movements; the recovery time machine |
| Detached HEAD | HEAD pinned to a commit instead of riding a branch |
| Conventional Commits | `feat:`/`fix:`/... typed commit messages machines can parse |
| Atomic commit | one commit = one logical change |
| `.gitignore` / `.gitattributes` | files Git should not track / per-path behavior rules |
| `.gitmodules` | the file recording a repository's submodules |
| Git LFS | the extension for versioning huge files via pointers |
| Plumbing / porcelain | Git's low-level commands / its friendly everyday commands |
| Blob / tree / commit object | file content / directory listing / snapshot-plus-metadata in the database |
| Monorepo | one repository containing many related projects |
| Trunk-based development | merging to main multiple times daily behind feature flags |
| Personal Access Token | a password-like credential for HTTPS Git operations |
| Secret | an encrypted value GitHub exposes only to workflows |

