
# Git and GitHub – Beginner Notes

## 1. What is Git?

Git is a version control system used to track changes in files and manage source code.

**Uses of Git:**
- Tracks changes in code.
- Helps developers work together.
- Allows us to restore previous versions.
- Helps manage different versions of a project.

## 2. What is GitHub?

GitHub is an online platform used to store and manage Git repositories.

- Git is a version control tool.
- GitHub is a platform that hosts Git repositories.

## 3. Clone an Existing Repository

Cloning means downloading an existing repository from GitHub to our local computer.

**Command:**
```bash
git clone repository-url
```

Example:
```bash
git clone https://github.com/Pratikshapaygude81/Python-training.git
```

Navigate into the repository:
```bash
cd Python-training
```

Open the repository in VS Code:
```bash
code .
```

## 4. Basic Repository Commands

Check repository status:
```bash
git status
```

Display local branches:
```bash
git branch
```

Display remote repository details:
```bash
git remote -v
```

Display the last five commits:
```bash
git log --oneline -5
```

## 5. What is a Branch?

A branch is a separate line of development that allows developers to work on different tasks without directly modifying the main branch.

Example:
- main
- git_practice
- feature-login

### Create a new branch
```bash
git branch branch_name
```

### Switch to an existing branch
```bash
git switch branch_name
```

### Create and switch to a new branch
```bash
git switch -c branch_name
```

Example:
```bash
git switch -c git_practice
```

### Verify the current branch
```bash
git branch
```

The `*` symbol indicates the currently active branch.

## 6. Creating a New File

We can create a new file using VS Code Explorer.

Steps:
1. Open the repository in VS Code.
2. Select the required folder.
3. Right-click and select New File.
4. Enter the filename.
5. Add content and save the file.

Example filename: `git_notes.md`

## 7. Understanding Git Status

```bash
git status
```

Git displays the current state of the repository.

### Untracked Files

A newly created file that Git is not tracking yet is called an untracked file.

Example:
```text
Untracked files:
    git_notes.md
```

## 8. Adding Files to Git

The `git add` command moves changes to the staging area.

### Add a specific file
```bash
git add filename
```

Example:
```bash
git add 01_basic_python/git_notes.md
```

### Add all changed and new files
```bash
git add .
```

### Check staged changes
```bash
git status
```

## 9. What is Staging?

Staging means selecting the changes that we want to include in our next commit.

Git has three important areas:

1. Working Directory – Where we create or modify files.
2. Staging Area – Where we prepare changes for a commit.
3. Repository – Where committed changes are stored.

## 10. What is a Commit?

A commit is a record of staged changes in the local repository.

**Command:**
```bash
git commit -m "Commit message"
```

Example:
```bash
git commit -m "Add Git practice notes"
```

A good commit message should briefly describe the changes.

## 11. What is Push?

Push means uploading local commits to a remote repository such as GitHub.

**Command:**
```bash
git push -u origin branch_name
```

Example:
```bash
git push -u origin git_practice
```

After setting the upstream branch, we can generally use:
```bash
git push
```

## 12. What is Pull?

Pull means fetching changes from the remote repository and integrating them into the current local branch.

**Command:**
```bash
git pull
```

To specify the remote and branch:
```bash
git pull origin main
```

## 13. What is Fetch?

Fetch downloads new commits and remote branch information without integrating those changes into the current branch.

**Command:**
```bash
git fetch
```

Difference:
- `git fetch` downloads remote updates.
- `git pull` downloads and integrates remote updates.

## 14. What is a Pull Request (PR)?

A Pull Request is a request to review and merge changes from one branch into another branch.

Example:
- Source branch: git_practice
- Target branch: main

### Steps to create a Pull Request

1. Create a new branch.
2. Make changes to files.
3. Stage the changes using `git add`.
4. Commit the changes using `git commit`.
5. Push the branch to GitHub.
6. Open the repository on GitHub.
7. Select Compare & pull request or New pull request.
8. Select the source and target branches.
9. Review the changes.
10. Click Create pull request.

The reviewer can review the code, request changes, approve the PR, and merge it.

**Important:** Follow the target branch specified by your trainer or team.

## 15. Difference Between Git Add, Commit and Push

| Command | Purpose |
|---|---|
| git add | Stages changes |
| git commit | Records staged changes locally |
| git push | Uploads commits to GitHub |

## 16. Complete Git Workflow

```text
Clone Repository
       |
       v
Open in VS Code
       |
       v
Create New Branch
       |
       v
Create or Modify Files
       |
       v
Git Add
       |
       v
Git Commit
       |
       v
Git Push
       |
       v
Create Pull Request
       |
       v
Code Review
       |
       v
Merge
```

## 17. Important Git Commands – Quick Revision

| Command | Purpose |
|---|---|
| git clone URL | Clone a repository |
| cd folder-name | Navigate into a folder |
| code . | Open folder in VS Code |
| git status | Check repository status |
| git branch | List local branches |
| git branch name | Create a branch |
| git switch name | Switch branches |
| git switch -c name | Create and switch branches |
| git add filename | Stage a specific file |
| git add . | Stage all changes |
| git commit -m "message" | Commit changes |
| git push | Push commits |
| git pull | Fetch and integrate changes |
| git fetch | Download remote updates |
| git remote -v | Display remote URLs |
| git log --oneline -5 | Display recent commits |

## 18. Practice Checklist

- [ ] Clone an existing repository.
- [ ] Open the repository in VS Code.
- [ ] Check repository status.
- [ ] Create a new branch.
- [ ] Switch between branches.
- [ ] Create a new file.
- [ ] Add the file to Git.
- [ ] Check staged changes.
- [ ] Commit the changes.
- [ ] Push the branch to GitHub.
- [ ] Create a Pull Request.
- [ ] Understand code review and merging.
