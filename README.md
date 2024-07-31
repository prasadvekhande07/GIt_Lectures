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

### Branching in Git

**Branching** is a powerful feature provided in Git, allowing developers to create separate branches for different functionalities or tasks. This helps keep the development process organized and uncluttered. Developers can work on features or bug fixes in isolation without affecting the main codebase. Once the changes are tested and validated, they can be merged back into the main branch, usually the "master" or "main" branch.

#### Default Branch
The default branch in Git is called **"master"** (or "main" in newer Git versions).

#### Example Scenario
Let's say a developer is working on different parts of a website: Home Page, Services, and Contact Us pages. They can create separate branches for each functionality to keep the changes organized.

### Git Commands for Branching

**Initialize a Git Repository:**
```bash
$ git init
```
This command initializes a new Git repository. The default branch will be **master**.

**Create a New Branch:**
```bash
$ git branch branchname
```
For example, to create a branch named **test**:
```bash
$ git branch test
```

### Workflow Example

1. **Home Page:**
   - Files: `f1`, `f2`, `f3`
   
2. **Services Page:**
   - Files: `f4`, `f5`
   
3. **Contact Us Page:**
   - Files: `f6`, `f7`, `f8`

Each functionality can be developed in separate branches:

- `home-page`
- `services`
- `contact-us`

### Commands

1. **Initialize the Repository:**
   ```bash
   $ git init
   ```
   This sets up a new Git repository with the default branch **master**.

2. **Check the Branches:**
   ```bash
   $ git branch
   ```
   This command lists all branches in the repository.

3. **Create New Branches:**
   ```bash
   $ git branch home-page
   $ git branch services
   $ git branch contact-us
   ```

4. **Switch to a Branch:**
   ```bash
   $ git checkout home-page
   ```
   This switches to the `home-page` branch.

5. **Merge a Branch to Master:**
   ```bash
   $ git checkout master
   $ git merge home-page
   ```
   This merges the changes from the `home-page` branch into the `master` branch.

By following this branching strategy, developers can work on different parts of a project simultaneously without interfering with each other’s work. Once each feature is complete, it can be merged into the master branch, ensuring a smooth and organized development process.

### Git Rebase

**Git Rebase** is a powerful tool that allows you to move or combine a sequence of commits to a new base commit. It is often used to keep a clean project history by creating linear, easy-to-follow commit histories.

**Fast-Forward Merge:**
In a fast-forward merge, the commits from a feature branch are applied directly to the `master` branch as if they were committed there initially. This is useful when you want the feature branch changes to appear as the latest working version on the `master`.

### Commands and Usage

**Rebase a Branch:**
```bash
$ git rebase branchname
```
This command rebases the current branch onto the `branchname`.

**Interactive Rebase:**
Interactive rebase allows you to rearrange, edit, or squash commits.

**Rearrange Commit Order:**
```bash
$ git rebase -i HEAD~4
```
This command initiates an interactive rebase for the last 4 commits. In the interactive mode, you can change the order of the commits, edit commit messages, or even combine commits.

**Squash Commits:**
Squashing combines multiple commits into one. This is useful for cleaning up your commit history.

1. Initiate interactive rebase:
    ```bash
    $ git rebase -i HEAD~4
    ```
2. Replace `pick` with `squash` for the commits you want to combine.

Example:
```
pick 1234567 First commit
squash 89abcd2 Second commit
squash ef34567 Third commit
squash 456789a Fourth commit
```

After saving and closing the editor, Git will combine the specified commits into one.

**Cherry-Pick Commits:**
Cherry-picking allows you to apply specific commits from one branch onto another branch. This is useful when you need to apply specific fixes or features without merging the entire branch.

**Cherry-Pick Commits:**
```bash
$ git cherry-pick 8e2f540 a502215
```
In this example, the commits with IDs `8e2f540` and `a502215` are applied to the current branch.

### Summary

1. **Git Rebase:** Used for moving or combining commits to a new base commit. It can help maintain a clean, linear project history.
2. **Fast-Forward Merge:** Makes the feature branch changes appear as the latest version on the `master`.
3. **Interactive Rebase:** Allows rearranging, editing, or squashing commits.
4. **Squash Commits:** Combines multiple commits into one for a cleaner history.
5. **Cherry-Pick:** Applies specific commits from one branch to another without merging the entire branch.

By understanding and using these commands, you can manage your Git commit history effectively, keeping it clean and easy to understand.

### Git Amend

The `git commit --amend` command allows you to modify the most recent commit. This is useful if you forgot to include some changes or need to update the commit message.

**Usage:**
```bash
$ git commit --amend -m "Updated commit message"
```
This command will replace the last commit with a new one that includes the changes from the previous commit plus any new changes you’ve staged.

### Example Scenario

1. Make some changes and commit:
    ```bash
    $ git add .
    $ git commit -m "Initial commit"
    ```
2. Realize you forgot to include a file or need to change the commit message:
    ```bash
    $ git add forgotten-file.txt
    $ git commit --amend -m "Updated commit with forgotten file"
    ```

This will update the last commit to include `forgotten-file.txt` and use the new commit message.

### Resetting to a Previous Commit

The `git reset` command is used to reset your current HEAD to a specified state. The `--hard` option discards all changes in the working directory and index, setting them to the specified commit.

**Usage:**
```bash
$ git reset --hard <commit-hash>
```
For example:
```bash
$ git reset --hard c9187df
```
This command will reset your current branch to the state of the commit with hash `c9187df`, discarding any changes that were made after that commit.

### Commands Summary

1. **Amend Last Commit:**
    ```bash
    $ git commit --amend -m "New commit message"
    ```
    - This updates the most recent commit with a new message or additional changes.

2. **Reset to a Previous Commit:**
    ```bash
    $ git reset --hard <commit-hash>
    ```
    - This resets your working directory and index to the state of the specified commit, discarding all changes made after that commit.

### Practical Workflow

1. **Amending a Commit:**
    - Stage your changes:
      ```bash
      $ git add modified-file.txt
      ```
    - Amend the last commit:
      ```bash
      $ git commit --amend -m "Updated commit with additional changes"
      ```

2. **Resetting to a Previous Version:**
    - Find the commit hash you want to reset to:
      ```bash
      $ git log
      ```
    - Reset to that commit:
      ```bash
      $ git reset --hard c9187df
      ```

By using these commands, you can easily update your most recent commit or revert your working directory to a previous state, allowing for flexible and efficient version control.
