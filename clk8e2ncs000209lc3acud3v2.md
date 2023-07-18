---
title: "Git Cherry-Pick and Stash: Enhancing Collaboration and Code Refinement"
datePublished: Tue Jul 18 2023 14:27:40 GMT+0000 (Coordinated Universal Time)
cuid: clk8e2ncs000209lc3acud3v2
slug: git-cherry-pick-and-stash-enhancing-collaboration-and-code-refinement
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689668872382/52c931e9-26ff-44f7-8c16-93c7bd0dbd47.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689690449129/16f64994-01c5-4d3c-8f5d-8122c984cbfe.jpeg
tags: git, devops, cherry-pick, 90daysofdevops, trainwithshubham

---

Welcome to Day 11 of the **#90DaysofDevOps** challenge

## Introduction

In the world of software development, effective collaboration and code refinement are vital for maintaining a streamlined workflow and producing high-quality code. Git, the widely-used version control system, offers powerful tools like "cherry-pick" and "stash" that can significantly enhance collaboration and code refinement processes.

In this blog post, we will explore two essential Git features: cherry-pick and stash. We will discuss how these features contribute to collaboration and code refinement, enabling developers to selectively incorporate changes and handle work-in-progress code effectively.

## Git Cherry-Pick

In Git, "cherry-pick" is a command that allows you to select and apply specific commits from one branch to another. It's like picking individual commits from one branch and copying them onto another branch.

With the "cherry-pick" command, Git allows you to integrate selected, individual commits from any branch into your current HEAD branch.

![](https://www.git-tower.com/learn/media/pages/git/faq/cherry-pick/264ebcffd2-1689624102/01-merge-commit.png align="left")

Cherry-pick, on the other hand, allows you to select **individual** commits for integration. Here, only C2 is integrated into the master branch, but not C4.

![](https://www.git-tower.com/learn/media/pages/git/faq/cherry-pick/0da99a2863-1689624102/02-cherry-pick.png align="left")

### Use cases of git cherry-pick

1. **Feature Integration**: When you want to selectively incorporate specific commits from one branch into another, cherry-picking allows you to apply those changes without merging the entire branch. It's useful when you only need specific updates or bug fixes from another branch.
    
2. **Bug Fixes:** If you discover a bug in your codebase and the fix exists in a different branch, cherry-picking the relevant commit can quickly apply the fix to your current branch.
    
3. **Code Review:** During code review, if you identify specific commits that need to be integrated into the main branch or a release branch, cherry-picking enables you to bring those changes into the desired branch.
    
4. **Reverting Changes:** If you need to undo a specific commit or a series of commits, cherry-picking allows you to reverse the changes by selecting and applying the inverse of those commits.
    

### Example of git cherry-pick

Consider the below example.

**Step 1**) Create a new file named "index.txt" with the commit message "Initial commit" inside the master branch.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689678769604/222693f9-e004-4028-8be2-4c24d1d5fc15.png align="center")

**Step 2)** Create three branches:

1. 1.0
    
2. 2.0
    
3. 3.0
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689679256645/4f4ee86d-586d-4e71-b643-0a3695c45f74.png align="center")

**Step 3)** Switched to branch **3.0**, create a new file "feature.txt" and commit the changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689681361589/9f155ebd-f1b8-479a-84f9-ad994e975d21.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689681464487/6622cbd4-7d8e-42f6-bdcf-a4c63e392eb3.png align="center")

Consider there is a bug inside 2.0 and we are trying to resolve it inside 3.0, somehow we fixed it.

**Step 4)** Create a new file "**bugfix.txt**", and write some content in it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689683015451/ca32ba79-c5df-4cc1-aad0-f43e622d3ed7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689683140475/3b97b4c7-ab54-4059-ae7d-786d47887f74.png align="center")

We have fixed the bug in the 3.0 branch.

we need to add this bug fixed inside 2.0 as well but, we don't want to merge the branches.

**Step 4)** Copy the hash-commit of the bugfix.txt file inside the 3.0 branch and use the cherry-pick command inside the 2.0

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689685324275/863979eb-b015-4f69-8f06-8d34bed0e199.png align="center")

Here I copied the commit hash **482cdcd** and use the below command

```plaintext
git cherry-pick <commit-hash>
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689685461765/f6d29dcd-e0a7-45a3-a517-2f0f5d271d9c.png align="center")

## Git Stash

Git **stash** is a command in Git that allows you to temporarily save changes that you have made to your code but are not ready to commit yet.

It enables us to switch branches without committing to the current branch.

The meaning of stash is "store something safely in a hidden place".

### Example of git stash

**Step 1)** Create a new folder **git-stash** and create a new file **index.txt** inside the master branch. Add the changes and commit it.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689686832782/3fe6e863-1e84-41c6-afcd-d1f39b4a442f.png align="center")

**Step 2)** Create a new branch "**stash**" and switched to the stash branch. Create a new file "**feature.txt**" inside the stash branch

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689687061442/7a38f475-01dc-4cb3-a159-a052d5c5ae80.png align="center")

Check the status of a stash branch, and we can see that the file "feature.txt" is in the working area.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689687407321/3f96bb52-4309-46eb-aee0-59f44197c606.png align="center")

**Step 3)** Switch the branch from stash to master, see the status of the branch, and again switched to stash branch.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689688198511/cee86b45-fa46-44b8-8745-2a60abdd4e01.png align="center")

**Step 4)** Now add the work of the stash branch and commit the changes, then switch to master and do certain modifications inside the index.txt, and save the changes.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689688634934/eeee9f32-ded9-4ea5-9002-7f3409511209.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689688601612/015fcc1a-3b51-42d4-a59d-dc1dc43230c9.png align="center")

**Step 5)** Switch to stash, and do some changes in the index.txt file. See the status of the branch, we can notice that the file "index.txt" is modified

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689689068447/acffcb38-bfd7-4e0d-a9e5-91f73c7adbd0.png align="center")

**Step 6)** Try to switch on master.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689689349202/27f7ba33-045c-40cd-b23b-3a7c037e9123.png align="center")

We will get this error. We don't want to commit the changes, so will use a git stash command to temporarily save the changes.

**Step 7)** Use the Git stash command

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689689642565/013913a5-b63a-45ff-9079-cd9c37d5ca08.png align="center")

**Step 8)** Check whether the stash has occurred or not, do the following

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689689769643/dbe6e793-1ccb-438e-bff4-9ba1c0fd0348.png align="center")

Great!! we have successfully stash the file.

## Resolving conflicts in git

Resolving conflicts in Git refers to the process of handling conflicting changes that occur when merging or rebasing branches. Conflicts happen when different branches have made conflicting modifications to the same file or lines of code. Resolving conflicts involves manually reviewing and editing the conflicting files to merge the changes in a way that makes sense. By resolving conflicts, you ensure that the final codebase integrates all desired changes coherently and without errors.

**Thank you** for visiting my blog! I appreciate your time and interest in the content. Stay connected to receive more valuable insights, updates, and helpful information. Feel free to explore other articles and don't hesitate to reach out if you have any questions or need further assistance. Stay tuned for more engaging content in the future. Thank you again and stay connected!