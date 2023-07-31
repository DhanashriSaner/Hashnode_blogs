---
title: "Mastering the Command Line: Your Ultimate Linux and Git Cheat Sheet"
datePublished: Mon Jul 31 2023 04:52:17 GMT+0000 (Coordinated Universal Time)
cuid: clkqe8s8y000s09jy3bfr1y26
slug: mastering-the-command-line-your-ultimate-linux-and-git-cheat-sheet
tags: linux, git, cheatsheet, 90daysofdevops, trainwithshubham

---

## Introduction

Welcome to **day 12** of the **#90daysofdevops** challenge, where we'll equip you with the ultimate cheat sheet for mastering the command line in Linux and Git. Whether you're a beginner or an experienced user, this concise guide will empower you to navigate these powerful tools quickly and efficiently. Say goodbye to endless searches for commands and hello to a streamlined, expert-level experience in the world of Linux and version control with Git. Let's dive in and unlock the true potential of your command line skills!

## Linux Command Line Cheatsheet

### Navigation

* `pwd` Print working directory.
    
* `ls` List files and directories.
    
* `cd` Change directory.
    
* `cd ..` Go up one level in the directory structure.
    
* `cd ~` Go to the home directory.
    

### File Operations

* `touch filename`: Create an empty file.
    
* `mkdir dirname`: Create a new directory.
    
* `cp source destination`: Copy files/directories.
    
* `mv source destination`: Move/rename files/directories.
    
* `rm filename`: Remove/delete a file.
    
* `rmdir dirname`: Remove/delete an empty directory.
    
* `rm -r dirname`: Remove/delete a directory and its contents.
    

### File Viewing and Editing

* `cat filename`: Display the contents of a file.
    
* `more filename`: View a file page by page.
    
* `vim filename`: Edit a file using the Vim text editor (advanced).
    

### File Permissions

```plaintext
        PERMISSION      EXAMPLE

         U   G   W
        rwx rwx rwx     chmod 777 filename
        rwx rwx r-x     chmod 775 filename
        rwx r-x r-x     chmod 755 filename
        rw- rw- r--     chmod 664 filename
        rw- r-- r--     chmod 644 filename

# NOTE: Use 777 sparingly!

        LEGEND
        U = User
        G = Group
        W = World

        r = Read
        w = write
        x = execute
        - = no access
```

* `chmod permissions filename`: Change file permissions.
    
* `chown owner:group filename`: Change file ownership.
    
* `chgrp group filename`: Change group ownership.
    

### Searching

1. Basic Usage:
    
    * `grep pattern file`: Search for "pattern" in "file."
        
    * `grep -r pattern directory`: Recursively search for "pattern" in "directory."
        
2. Case Insensitive Search:
    
    * `grep -i pattern file`: Perform a case-insensitive search.
        
3. Display Line Numbers:
    
    * `grep -n pattern file`: Show line numbers in the output.
        
4. Display Matching Count:
    
    * `grep -c pattern file`: Show the count of matches.
        
5. Invert Match (Exclude Lines):
    
    * `grep -v pattern file`: Display lines that do not match the pattern.
        
6. Whole Word Search:
    
    * `grep -w pattern file`: Search for whole word occurrences only.
        
7. Regular Expression Search:
    
    * `grep -E "regex" file`: Use extended regular expressions (ERE).
        
    * `grep -P "regex" file`: Use Perl-compatible regular expressions (PCRE).
        
8. Combine Multiple Patterns (OR):
    
    * `grep -e pattern1 -e pattern2 file`: Match either "pattern1" or "pattern2."
        
9. Show Context Around Matches:
    
    * `grep -A num pattern file`: Display "num" lines after each match.
        
    * `grep -B num pattern file`: Display "num" lines before each match.
        
    * `grep -C num pattern file`: Display "num" lines before and after each match.
        
10. Count Matches per File:
    
    * `grep -c pattern files...`: Show the count of matches for each file.
        
11. Using grep with Pipes:
    
    * `command | grep pattern`: Search for "pattern" in the output of "command."
        

### Process Management

* `ps`: List currently running processes.
    
* `ps aux`: Detailed list of all processes.
    
* `kill PID`: Terminate a process with a specific process ID.
    

### Networking

* `ping host`: Check connectivity to a host.
    
* `ifconfig`: Display network interface configuration.
    
* `ssh user@host`: Securely log into a remote host (requires SSH).
    

## Git Cheatsheet

### **Setting Up**

* `git init`: Initialize a new Git repository in the current directory.
    
* `git clone <repository_url>`: Clone a remote repository to your local machine.
    

### **Adding and Committing**

* `git status` Check the status of your working directory and staged changes.
    
* `git add <file>` Add changes in `<file>` to the staging area.
    
* `git add .` Add all changes to the staging area.
    
* `git commit -m "commit message"` Commit staged changes with a descriptive message.
    

### **Branches**

* `git branch`: List all branches in the repository.
    
* `git branch <branch_name>`: Create a new branch named `<branch_name>`.
    
* `git checkout <branch_name>`: Switch to an existing branch.
    
* `git checkout -b <new_branch>`: Create and switch to a new branch.
    

### **Merging**

* First, switch to the branch you want to merge changes into (e.g., `git checkout main`).
    
* `git merge <branch_name>`: Merge changes from `<branch_name>` into the current branch.
    

### **Pulling and Pushing**

* `git pull`: Pull changes from the remote repository into your current branch.
    
* `git push <remote_name> <branch_name>`: Push local commits to the remote repository.
    

### **Viewing History**

* `git log`: View the commit history.
    
* `git log --oneline`: Show condensed commit history (one line per commit).
    

### **Discarding Changes**

* `git restore <file>`: Discard changes in `<file>` and restore it to the last committed state.
    
* `git reset --hard HEAD`: Discard all changes in the working directory and staging area.
    
* `git revert <commit_hash>`: Create a new commit that undoes changes introduced by the specified `<commit_hash>`.
    
* `git clean -df`: Remove all untracked files and directories from the working directory. (-d: directories, -f: force)
    

### **Remote Repositories**

* `git remote`: List remote repositories.
    
* `git remote add <name> <repository_url>`: Add a new remote repository.
    
* `git remote -v`: Show the URLs of remote repositories.
    
* `git remote remove <name>`: Remove a remote repository.
    

### **Updating Local Repository**

* `git fetch`: Fetch changes from the remote repository without merging.
    
* `git pull`: Fetch and automatically merge changes from the remote repository.
    

### **Ignoring Files**

* Create a file named `.gitignore` and list the files or patterns you want to ignore.
    

**Thank You** for visiting my blog.  
Happy coding and command-line mastery! Keep exploring, keep learning, and stay tuned for more tech insights on our blog. Until next time, happy scripting!