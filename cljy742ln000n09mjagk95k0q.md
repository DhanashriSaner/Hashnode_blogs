---
title: "DevOps Automation Toolbox: Linux Shell Scripting Essentials"
seoTitle: ""DevOps Automation Toolbox: Linux Shell Scripting Essentials""
datePublished: Tue Jul 11 2023 11:15:07 GMT+0000 (Coordinated Universal Time)
cuid: cljy742ln000n09mjagk95k0q
slug: devops-automation-toolbox-linux-shell-scripting-essentials
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689067374723/f47d23f0-a89d-4035-a461-56446717ac6e.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689074073426/f3f7fa1b-856c-4226-bad1-a1bee7880aeb.jpeg
tags: devops, linux-for-beginners, shell-script, linux-shell-scripting

---

I'm thrilled to share my latest blog post as a task submission for **Day 4 #90DaysOfDevOps Challenge**.

## **Introduction**:

In the world of DevOps, automation is the key to achieving efficient and reliable software delivery. And when it comes to automation on Linux systems, Linux shell scripting is an indispensable tool in a DevOps engineer's toolbox. Shell scripting allows you to automate repetitive tasks, streamline workflows, and orchestrate complex deployments with ease.

In this blog post, we will explore the essential aspects of Linux shell scripting that every DevOps engineer should be familiar with. We will dive into the fundamental concepts, useful techniques, and practical examples that will empower you to leverage shell scripting for automating various aspects of your DevOps workflow.

## What is Kernel?

The Kernel is a central component of an operating system that manages the operations of computers and hardware. **Linux Kernel** is the heart of **Linux operating systems.** It manages the following resources of the Linux system –

* File management
    
* Process management
    
* I/O management
    
* Memory management
    
* Device management etc.
    

## What is Shell?

In the context of operating systems, a shell is a command-line interface (CLI) or a graphical user interface (GUI) that acts as an intermediary between the user and the operating system. It provides a way for users to interact with the underlying operating system by accepting and executing commands.

A shell interprets user input, whether it is typed commands or clicks in a graphical interface, and translates them into instructions that the operating system can understand. The shell then executes these instructions and returns the results to the user.

The shell serves as a powerful tool for managing and controlling the operating system. It allows users to navigate the file system, run programs, configure system settings, manipulate files and directories, and perform a wide range of tasks. Additionally, the shell often provides features such as scripting capabilities, command history, tab completion, and the ability to redirect input and output.

Common examples of shells in various operating systems include:

* Bash (Bourne Again SHell) in Unix-like systems, including Linux.
    
* Command Prompt (CMD) and PowerShell in Windows.
    
* Zsh (Z Shell), KornShell (ksh), and C Shell (csh) in Unix-like systems.
    

## What is Linux Shell Scripting?

Linux shell scripting refers to the practice of writing scripts or programs using a shell scripting language on a Linux operating system. Shell scripting allows users to automate tasks, execute commands, and perform various operations on a Linux system through a command-line interface.

In Linux, the most commonly used shell is Bash (Bourne Again SHell), which is the default shell for many Linux distributions. However, other shells like Zsh (Z Shell), KornShell (ksh), and C Shell (csh) are also available.

Shell scripts are text files containing a series of commands written in a shell scripting language. These scripts are executed by the shell interpreter, which reads and executes the commands sequentially.

*Here are the tasks for Day4 of* ***#90DaysOfDevOps*** *Challenge:*

## **Tasks**

```plaintext
1) Explain in your own words and examples, what is Shell Scripting for DevOps.
2) What is #!/bin/bash? can we write #!/bin/sh as well?
3) Write a Shell Script which prints I will complete #90DaysOofDevOps challenge
4) Write a Shell Script to take user input, input from arguments and print the variables.
5) Write an Example of If else in Shell Scripting by comparing 2 numbers
```

**1) Explain in your own words and examples, what is Shell Scripting for DevOps.**

Shell scripting for DevOps involves using shell scripts to automate tasks and processes in a DevOps workflow. It allows DevOps engineers to streamline and accelerate various operations, such as build and deployment processes, configuration management, infrastructure provisioning, and continuous integration/continuous deployment (CI/CD) pipelines.

Example: Let's consider a common scenario in a DevOps workflow where a web application needs to be built, tested, and deployed to a production server. Shell scripting can help automate this process. Here's an example:

1. Build Script:
    
    * The shell script can retrieve the latest source code from a version control system.
        
    * It can compile the code, resolve dependencies, and package the application.
        
    * It can perform unit tests and generate reports.
        
2. Deployment Script:
    
    * The shell script can connect to the production server via SSH.
        
    * It can stop the existing web server.
        
    * It can copy the newly built application package to the server.
        
    * It can configure the server settings and dependencies.
        
    * It can start the web server and verify the deployment.
        
3. Integration Script:
    
    * The shell script can be integrated into a CI/CD pipeline.
        
    * It can trigger the build script whenever there is a new commit to the version control system.
        
    * It can run automated tests and code quality checks.
        
    * It can deploy the application to a staging environment for further testing.
        
    * It can deploy to the production environment upon successful testing.
        

In this example, shell scripting simplifies the DevOps process by automating the build, deployment, and integration tasks. By using shell scripts, DevOps engineers can save time, ensure consistency, and reduce the chances of human error. Shell scripting empowers DevOps teams to achieve faster and more reliable software delivery, enabling them to focus on higher-level tasks and improvements.

**2) What is #!/bin/bash? can we write #!/bin/sh as well?**

The shebang line, also known as the hashbang or the interpreter directive, is a special line that appears at the beginning of a script file. It specifies the interpreter or shell that should be used to execute the script.

The shebang line typically starts with "#!" followed by the path to the interpreter binary. For example, "#!/bin/bash" specifies that the script should be executed using the Bash shell located at "/bin/bash".

Now, regarding "#!/bin/sh", it specifies that the script should be executed using the default system shell, which can vary depending on the Linux distribution or Unix-like operating system being used. In many systems, "/bin/sh" is a symbolic link or a small POSIX-compliant shell that may or may not be the same as Bash.

The key distinction between "#!/bin/bash" and "#!/bin/sh" lies in their behavior and features. Bash is an enhanced version of the Bourne shell (sh) with additional features and capabilities. It supports more advanced functionality, such as arrays, associative arrays, extended pattern matching, and more.

By using "#!/bin/sh", you are indicating that your script should work with a minimal feature set that is common to all POSIX-compliant shells. This ensures portability across different systems and avoids relying on Bash-specific features that may not be available in other shells.

In summary, while both "#!/bin/bash" and "#!/bin/sh" can be used as shebang lines, the former explicitly specifies the use of the Bash shell, while the latter allows for more portability by using the default system shell, which may or may not be Bash.

**3) Write a Shell Script that prints I will complete #90DaysOofDevOps challenge**

```plaintext
    #!/bin/bash
    echo "I will complete #90DaysOfDevOps challenge"
```

**4) Write a Shell Script to take user input, input from arguments and print the variables**

![image](https://user-images.githubusercontent.com/88526990/251676284-94d7ff7b-3869-4a6e-8ad7-8e48a388404c.png align="left")

**Output**

![image](https://user-images.githubusercontent.com/88526990/251676509-e73702de-5994-49f3-b9a0-c94decf2b712.png align="left")

**5) Write an Example of If else in Shell Scripting by comparing 2 numbers**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689073521245/69c969cd-af68-4304-8eae-5266a9b20ff6.png align="center")

**Output**

For checking equality

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689073593452/7ccf90ab-8b95-48f9-9bdd-4973a92fa9e8.png align="center")

If the first number is big

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689073632402/efccdc1c-cd0f-4338-bde9-d902d2f0a082.png align="center")

If the second number is big

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689073684469/f29ab2da-068e-4af9-af2a-d8feca722f26.png align="center")

## Conclusion

Linux shell scripting is a vital tool in the DevOps automation toolbox. With its power to automate tasks, streamline workflows, and enhance productivity, shell scripting empowers DevOps engineers to achieve efficient and reliable software delivery.

Unlock the full potential of Linux shell scripting, unleash the power of automation, and elevate your DevOps practices to new heights. Happy scripting and best of luck on your DevOps journey!