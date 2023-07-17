---
title: "Git Commands Decoded: Simplifying Version Control for Developers"
datePublished: Mon Jul 17 2023 16:30:45 GMT+0000 (Coordinated Universal Time)
cuid: clk7312zk000j09mh8unefg1t
slug: git-commands-decoded-simplifying-version-control-for-developers
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689569875864/c52427c6-95ca-4581-ba4f-77a1bcf604b1.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689611394637/d02c543a-fc7d-4ee3-ab89-5281bb53805b.jpeg
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

Welcome to Day 10 of the **#90DaysOfDevOps** challenge.

## Introduction

In this blog, we aim to unravel the complexities of Git commands and provide you with a clear understanding of how they work. Whether you're a beginner exploring version control or an experienced developer looking to enhance your Git workflow, this blog will serve as your go-to resource. We'll break down each command, explain its purpose, and guide you through practical examples, simplifying the process of managing your codebase and collaborating with others. Get ready to unlock the power of Git commands and streamline your development journey. Let's dive in and decode the world of version control with ease!

## **Basic Git Commands**

**git init**: Initializes a new Git repository in the current directory.

```plaintext
git init
```

**git clone \[repository\]**: Creates a local copy of a remote repository.

```plaintext
git clone https://github.com/username/repository.git
```

**git config --global user. name "\[Your Name\]"**: Sets your username globally for all Git repositories.

```plaintext
git config --global user.name "USER_NAME"
```

**git config --global user.email "\[your-email@example.com\]"**: Sets your email globally for all Git repositories.

```plaintext
git config --global user.email "xyz@gmail.com"
```

**git add \[file(s)\]**: Adds file(s) to the staging area.

```plaintext
git add myfile.txt
```

**git commit -m "\[message\]"**: Commits the changes in the staging area with a message.

```plaintext
git commit -m "Added new feature"
```

**git status**: Shows the status of the repository.

```plaintext
git status
```

**git diff**: Displays the differences between the working directory and the staging area.

```plaintext
git diff myfile.txt
```

**git log**: Shows the commit history.

```plaintext
git log
```

**git pull**: Fetches and merges change from a remote repository.

```plaintext
git pull origin master
```

**git push**: Pushes local commits to a remote repository.

```plaintext
git push origin master
```

**git remote**: Lists remote repositories.

```plaintext
git remote -v
```

**git fetch**: Retrieves changes from a remote repository.

```plaintext
git fetch origin
```

**git rm \[file(s)\]**: Removes file(s) from the repository.

```plaintext
git rm myfile.txt
```

**git mv \[oldpath\] \[newpath\]**: Renames or moves a file.

```plaintext
git mv oldfile.txt newfile.txt
```

## Git Branching

Branching in Git is a powerful feature that allows you to create separate lines of development within a repository. It enables collaboration, isolation of work, and the ability to experiment with new features or fixes without impacting the main codebase.

The main branch in Git is typically called "**master**" or "**main**" (depending on the naming convention). When you create a new branch, it starts as an identical copy of the current branch (usually the main branch). From there, you can make changes, add commits, and merge them back into the main branch or other branches as needed.

### Branching Commands

**Creating a New Branch:**

To create a new branch called "feature-login2" without committing on `master`, you can use:

```plaintext
git checkout -b feature-login2
```

**Switching to a Branch:**

To switch to a branch, you can use the `git checkout` a command followed by the name of the branch. For example, let's switch to the "feature-login2" branch:

```plaintext
git checkout feature-login2
```

Now, any changes you make and commits you create will be isolated within the "feature-login" branch.

**Making Changes and Committing:**

Let's say you make some changes to implement a login feature. After making the changes, you can stage and commit them using the standard Git commands:

```plaintext
git add .
git commit -m "file added into new branch"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689579084435/f9e3b2e2-97ed-4657-896b-efd24bbd7622.png align="center")

**Merging Branches:**

Once the changes in the "feature-login" branch are complete and tested, you may want to merge them back into the main branch (e.g., "master" or "main"). To do that, switch to the main branch and use the `git merge` command:

```plaintext
git checkout master
git merge feature-login2
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689579192692/95237d7f-89df-4736-bbd5-479550e98307.png align="center")

Git will automatically merge the changes from the "feature-login2" branch into the main branch, incorporating your work into the main codebase.

**Deleting a Branch:**

After merging the changes, you can delete the branch if it's no longer needed. The following command will delete the "feature-login" branch:

```plaintext
git branch -D feature-login
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689579544794/7beb8018-58f8-4b3d-a14e-fa33b780a926.png align="center")

## Git Revert and Reset

In Git, `git revert` and `git reset` are two different commands that serve distinct purposes:

1. **git revert**: The `git revert` command is used to create a new commit that undoes the changes made in a previous commit. It allows you to reverse the effect of a specific commit while preserving the commit history. This is useful when you want to undo changes without discarding any previous commits.
    
2. **git reset**: The `git reset` command allows you to move the current branch pointer to a specific commit. It can be used to undo commits, unstaged changes, or move the branch pointer to a different commit, potentially discarding commits.
    

### Difference Between Git Revert & Reset

|  | **Reset** | **Revert** |
| --- | --- | --- |
| Operation | Rewrites commit history by moving the branch pointer | Creates a new commit to reverse the changes |
| Impact | Potentially dangerous as it discards commits and history | Safer option as it preserves commit history |
| Collaboration | Not recommended for shared branches, as it can cause conflicts for other developers | A safer option for shared branches, as it preserves commit history and allows others to easily understand the changes made |
| Undoing | Can be used to undo commits and return to a previous state | Can be used to undo commits without altering the commit history |
| Usage | `git reset [commit]` | `git revert [commit]` |

## **Task**

```plaintext
- Add a text file called version01.txt inside the Devops/Git/ with “This is first feature of our application” written inside. 
  This should be in a branch coming from `master`, 
 
- swithch to `dev` branch ( Make sure your commit message will reflect as "Added new feature").
 
- version01.txt should reflect at local repo first followed by Remote repo for review. 

- Add new commit in `dev` branch after adding below mentioned content in Devops/Git/version01.txt:
  While writing the file make sure you write these lines
 
 - 1st line>>  This is the bug fix in development branch
 - Commit this with message “ Added feature2 in development branch”
 
 - 2nd line>> This is wrong code
 - Commit this with message “ Added feature3 in development branch
 
 - 3rd line>> This feature will destroy everything from now.
 - Commit with message “ Added feature4 in development branch"

- Restore the file to a previous version where the content should be “This is the bug fix in development branch”
- Merge the dev branch with master
```

### Solution

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689602690056/07a089af-d6cd-4c5b-9fbf-178928f0f7df.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689603147263/436d4c85-4a1b-4510-b230-ebf0f16a6c4b.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689603529076/db9e198d-687b-4e8c-8b70-f471459c97b7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689603679577/78ad2aa4-ff35-4d1a-beef-2468f358e681.png align="center")

**Restore** the file to a previous version where the content should be “**This is the bug fix in the development branch”**

**1)** Using the **reset** command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689604417480/9993492d-acfb-4aaf-a603-f7433ccc84a4.png align="center")

Now the **HEAD** is pointing to commit "Added feature2 in development branch" which consists of the content “**This is the bug fix in the development branch”**

**2)** Using the **revert** command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689605593987/09252287-08ec-4073-8b80-b048cbbbe6e1.png align="center")

**Merge the branches**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689608875651/45c93191-3f87-473e-bdb1-51aeecc38b9a.png align="center")

## Conclusion

In conclusion, understanding and utilizing Git commands can greatly simplify version control for developers. By mastering commands such as `git init`, `git add`, `git commit`, and `git push`, developers can effectively manage their codebase and collaborate with ease. Advanced commands like `git branch`, `git merge`, and `git rebase` provide additional flexibility and control over branch management and commit history. By decoding Git commands, developers can streamline their workflows, enhance productivity, and maintain a well-organized and collaborative development environment.