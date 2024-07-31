### Version Control Systems (VCS)

Version Control Systems (VCS) are tools that help a software team manage changes to source code over time. For almost all software projects, the source code is like the crown jewels - a precious asset whose value must be protected. VCS are sometimes known as Source Code Management (SCM) tools.

**Types of Version Control Systems:**
1. **Centralized Version Control Systems (CVCS):** In CVCS, there is a single central repository that contains all the versions of the code. Examples include Subversion (SVN) and Perforce.
2. **Distributed Version Control Systems (DVCS):** In DVCS, every contributor has a complete copy of the repository, including its history. Examples include Git and Mercurial.

**Git:**
Git is the most widely used modern version control system in the world today. It is a distributed version control system, originally developed in 2005 by Linus Torvalds, the famous creator of the Linux operating system kernel. Git is a mature, actively maintained open-source tool.

### Git Bash

**Git Bash** is an application that provides Git command-line experience on Windows. It includes a Bash emulation used to run Git from the command line and a set of Unix tools that emulate a Git command line experience.

### Configuring Git

To configure your username and email for Git globally, you can use the following commands:

```bash
$ git config --global user.name "sunilkumark11"
$ git config --global user.email "sunilkumark11@gmail.com"
```

To check your configurations, use:
```bash
$ git config --global --list
```

### Git Workflow

**1. Working Directory:** This is where you create, edit, delete, and organize files.

**2. Staging Area:** A place where you can group changes before committing them.

**3. Local Repository (LR):** Where your project's history is stored.

**File States:**
- **Untracked:** Files that are not tracked by Git.
- **Staged:** Files that are marked to be included in the next commit.
- **Committed:** Files that are safely stored in the local repository.

### Commands

**Initialize a Git repository:**
```bash
$ git init
```

**Check the status of your working directory:**
```bash
$ git status
```

**Add files to the staging area:**
```bash
$ git add f1
$ git add f2 f3
$ git add .
```

**Remove files from the staging area:**
```bash
$ git rm --cached f1
$ git reset f2
```

**Commit changes to the local repository:**
```bash
$ git commit -m "first commit"
```

**View commit history:**
```bash
$ git log
$ git log --oneline
```

### Summary of Notes

1. **Setting username and email:**
   - Commands to set global username and email for Git.
   
2. **Three components according to Git:**
   - **Working Directory:** Where you work on your files.
   - **Staging Area:** Where you prepare your files for the next commit.
   - **Local Repository:** Where your project's history is stored.

3. **Key Commands:**
   - Initialize a Git repository.
   - Move files to the staging area.
   - Remove files from the staging area.
   - Commit files to the local repository.
   - Check the status of files.
   - View commit history.

---

Is there anything specific you need more information about or further explanation?
