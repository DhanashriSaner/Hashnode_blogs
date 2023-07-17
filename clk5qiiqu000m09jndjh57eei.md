---
title: "Unlocking the Secrets of Git and GitHub: A Developer's Handbook"
datePublished: Sun Jul 16 2023 17:52:37 GMT+0000 (Coordinated Universal Time)
cuid: clk5qiiqu000m09jndjh57eei
slug: unlocking-the-secrets-of-git-and-github-a-developers-handbook
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689520820571/6ba2c648-f559-4f47-b16e-30c9ed11dcd4.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689529945074/309612d2-78ce-45ea-9d85-1af0b5a6f53e.jpeg
tags: github, git, devops, 90daysofdevops, trainwithshubham

---

Welcome to day 9 of the **#90DaysOfDevOps** challenge.

## Introduction

In this blog, we embark on a journey to demystify the powerful tools of Git and GitHub, unveiling their hidden treasures for developers. Whether you're a seasoned professional or just starting your coding adventure, this handbook will equip you with the knowledge and skills to confidently navigate the world of version control. Get ready to unlock the true potential of Git and GitHub as we embark on this exciting quest together!

## What is Git?

Git is a **distributed version control system** that allows developers to track changes in their codebase. It enables multiple people to work on the same project simultaneously, keeping a complete history of all modifications made to the files. With Git, developers can create branches, merge changes, and quickly revert to previous versions if needed. It provides a reliable and efficient way to collaborate, manage code revisions, and ensure the integrity of projects, making it an essential tool for software development teams.

## Difference between the main branch and the master branch

The difference between the "main" branch and the "master" branch lies primarily in their naming convention. Historically, "master" was a commonly used default branch name in Git repositories, which represented the primary development branch. However, in recent years, there has been a movement towards more inclusive language and the recognition that the term "master" may carry racial connotations.

As a result, some communities and organizations have started to transition to alternative default branch names like "main" or "mainline." The purpose of this change is to promote more inclusive and neutral terminology.

In terms of functionality and usage, both the "main" and "master" branches serve the same fundamental purpose: to represent the primary development branch of a Git repository. They act as the starting point for new features and serve as the base branch for merging changes from other branches.

Therefore, the primary difference between "main" and "master" lies in their naming convention and the cultural context surrounding their usage, with "main" being the more inclusive and preferred term in many development communities.

## Steps to create new repository on GitHub

1. Open your web browser and go to the GitHub website [**https://github.com**](https://github.com)
    
2. If you don't have an account, sign up for a new account. If you already have an account, log in.
    
3. Once you're logged in, click on the "**+"** (plus) sign in the top right corner of the GitHub homepage.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689524322202/6a3bd597-df6a-46c4-b855-87a713bd78ab.png align="center")
    
4. In the drop-down menu, select "**New repository**." You can also navigate directly to the "Repositories" tab and click on the green "New" button.
    
5. On the "**Create a new repository**" page, enter a unique name for your repository in the "Repository name" field. Choose a descriptive name that reflects the purpose or content of your project.
    
6. Optionally, provide a brief description of your repository in the "Description" field.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689524560886/0f411d77-d26d-49e8-bf0f-15a06f06e2f3.png align="center")
    
7. **Choose the visibility** of your repository. You can make it public, accessible to everyone, or private, visible only to you and selected collaborators.
    
8. If you want to initialize your repository with a README file, check the "Add a README file" checkbox. This can be helpful to provide initial documentation or instructions for your project.
    
9. Select any additional options you want for your repository, such as adding a .gitignore file or a license.
    
10. Once you have configured the desired settings, click the green "**Create repository**" button.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689524617088/5d134a26-a382-4a53-af6a-db2b84e310b1.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689524708476/629876c0-26d4-4e8e-8061-c2b1b03d2f9a.png align="center")
    
11. Congratulations! Your new repository is now created on GitHub. You will be redirected to the repository's page, where you can find the repository URL, make further changes to the repository settings, and start adding files, branches, and collaborating with others.
    

That's it! You have successfully created a new repository on GitHub.

## What is difference between local & remote repository?

| **Local Repository** | **Remote Repository** |
| --- | --- |
| Resides on your local machine | Hosted on a remote server (e.g., GitHub, GitLab, Bitbucket) |
| Contains the complete history of your project | Serves as a central hub for collaboration and code sharing |
| Allows you to perform Git operations locally | Enables collaboration with other developers |
| Typically located in a directory on your computer | Accessible from anywhere with an internet connection |
| Supports branching, committing, merging, and more | Facilitates code review, issue tracking, and collaboration |
| Does not require an internet connection to work on code | Requires internet connection to sync changes with collaborators |
| Provides flexibility and control over local development | Offers a platform for remote teamwork and project management |

## How to connect local to remote?

To connect your local repository to a remote repository, you can follow these steps:

1. Create a remote repository on the hosting platform (e.g., GitHub).
    
2. In your local repository, open a terminal or command prompt and navigate to the project's directory.
    
3. Add the remote repository URL as a remote to your local repository using the `git remote add` command. For example:
    
    ```plaintext
    git remote add origin <remote_repository_url>
    ```
    
    Here, "origin" is the commonly used name for the default remote repository, but you can choose any meaningful name.
    
4. Verify the remote repository is added by running `git remote -v`. It should display the remote repository URL.
    
5. To push your local commits to the remote repository, use the `git push` command. For example:
    
    ```plaintext
    git push origin <branch_name>
    ```
    
    This will push the commits on the specified branch to the remote repository.
    

By connecting your local repository to a remote repository, you establish a link between the two, enabling collaboration and synchronization between multiple developers working on the same project.

## Set your user name and email address, which will be associated with your commits.

1. Open a terminal or command prompt on your computer.
    
2. Navigate to the root directory of your local Git repository (or any Git repository where you want to set the user name and email).
    
3. Run the following command to set your user name:
    
    ```plaintext
    git config --global user.name "Your Name"
    ```
    
    Replace "Your Name" with your desired user name. The `--global` flag sets this configuration globally for all Git repositories on your machine. If you want to set the user name only for the current repository, omit the `--global` flag.
    
4. Run the following command to set your email address:
    
    ```plaintext
    git config --global user.email "youremail@example.com"
    ```
    
    Replace "**youremail@example.com**" with your actual email address. Again, use the `--global` flag to set it globally or omit it for the current repository only.
    
5. Verify that your user name and email address are set correctly by running the following command:
    
    ```plaintext
    git config --global --get user.name
    git config --global --get user.email
    ```
    
    These commands will display the configured user name and email address, respectively.
    

By setting your user name and email address in Git, your commits will be associated with this information, allowing others to identify the author of the changes.

## Task

```plaintext

1) Create a repository named "Devops" on GitHub
2) Connect your local repository to the repository on GitHub.
3) Create a new file in Devops/Git/Day-02.txt & add some content to it
4) Push your local commits to the repository on GitHub
```

1. **Create a repository named "Devops" on GitHub**
    
2. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689526248070/d121f0f4-48e0-4f27-a814-d92eac3de4ce.png align="center")
    
    **Connect your local repository to the repository on GitHub.**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689528903625/81f7ceb2-ef59-4020-a2ba-55a3597f4367.png align="center")
    
    Verify the remote repository is added by running `git remote -v`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689527087117/f19b08a9-ffee-4a3f-81ab-cf88e1b63e05.png align="center")
    
3. **Create a new file in Devops/Git/Day-02.txt & add some content to it**
    
4. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689529367809/de1c0eb7-a9d4-437b-9593-531b489fbd23.png align="center")
    
    **Push your local commits to the repository on GitHub**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689529449530/8bb36919-a806-4da2-9cc8-ce28e5e75e2a.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689529599875/c1f8128a-184d-41ae-a4ee-fac919f2f917.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689529665640/a14da5b4-2aaa-4f8e-b672-b43e2cc12c1a.png align="center")
    

## Conclusion

Throughout this blog, we have explored the fundamentals of version control, learned advanced techniques for branching and merging, and delved into collaboration workflows on GitHub. By unlocking the secrets of Git and GitHub, developers gain the ability to streamline their code management, enhance collaboration, and maximize productivity. Armed with the knowledge and best practices shared in this handbook, readers are well-equipped to harness the full potential of Git and GitHub and embark on successful software development journeys.