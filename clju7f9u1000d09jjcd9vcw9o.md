---
title: "Linux Command Line Essentials: Boosting Your Productivity and Efficiency"
seoTitle: "Linux Command Line Essentials"
datePublished: Sat Jul 08 2023 16:12:45 GMT+0000 (Coordinated Universal Time)
cuid: clju7f9u1000d09jjcd9vcw9o
slug: linux-command-line-essentials-boosting-your-productivity-and-efficiency
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1688823316967/9aff46eb-a354-4153-9c3a-abbac9ce52a4.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1688832648479/48b13b4f-967f-468d-93e3-19e21a1ece85.jpeg
tags: ubuntu, linux, devops, linux-for-beginners

---

I'm excited to share my first blog post as a task submission for **Day 3 #90DaysOfDevOps Challenge**. Join me on this exciting journey of unlocking the potential of Linux!

In this blog, we delve into the Linux command line essentials that will supercharge your productivity and efficiency. Discover the power and flexibility of the command line interface as we explore fundamental commands, practical tips, and advanced techniques. Whether you're a Linux newcomer or an experienced user, this guide will equip you with the necessary skills to navigate, manipulate, and automate tasks using the command line.

### **Linux Architecture**

![LINUX Arch](https://github.com/DhanashriSaner/Linux_basics/assets/88526990/15cf1244-facf-43e1-9706-dde2f62f7394 align="center")

1. **Kernel:** Kernel is the core of the Linux-based operating system. It virtualizes the common hardware resources of the computer to provide each process with its virtual resources. Different types of the kernel are:
    
    * Monolithic Kernel
        
    * Hybrid kernel
        
    * Exo kernel
        
    * Nano kernel
        
    * Microkernel
        
2. **System Library:** It is the special types of functions that are used to implement the functionality of the operating system.
    
3. **Shell:** It is an interface to the kernel which hides the complexity of the kernel’s functions from the users. It takes commands from the user and executes the kernel’s functions.
    
4. **Hardware Layer:** This layer consists of all peripheral devices like RAM/ HDD/ CPU etc.
    
5. **System Utility:** It provides the functionalities of an operating system to the user.
    

### Day 3 Task: Basic Linux Commands

#### Task: What is the Linux command to

```plaintext
1. To view what's written in a file.
2. To change the access permissions of files.
3. To check which commands you have run till now.
4. To remove a directory/ Folder.
5. To create a fruits.txt file and to view the content.
6. Add content in fruits.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.
7. To Show only top three fruits from the file.
8. To Show only bottom three fruits from the file.
9. To create another file Colors.txt and to view the content.
10. Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.
11. To find the difference between fruits.txt and Colors.txt file.
```

### **Solution**

1. **To view what's written in a file.**
    
    * `cat filename`
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688826063905/25f9fcb3-9f41-4cc7-9e4f-698cf0d506de.png align="center")
    
    **To change the access permissions of files.**
    
    * `chmod 777 filename`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688827171215/5c3615d4-3cdb-4b98-a9fa-bda51520354d.png align="center")
        
    
    **To check which commands you have run till now.**
    
    * `history`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688827562801/ca6746e2-e09c-4c06-a504-9198de390432.png align="center")
        
    
    **To remove a directory/ Folder.**
    
    * `rm -rf foldername/`
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688827494554/8cf728cb-feaf-43a3-9fd7-371b185eb642.png align="center")
    
    **To create a fruits.txt file and to view the content.**
    
    * `vim fruits.txt`
        
    * `cat fruits.txt`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688827877996/c58e5a46-f074-4455-a92b-5bb2d4150d7c.png align="center")
        
    
    **Add content in fruits.txt (One in each line) - Apple, Mango, Banana, Cherry, Kiwi, Orange, Guava.**
    
    * `echo -e "Apple\nMango\nBanana\nCherry\nKiwi\nOrange\nGuava" > fruits.txt`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688831677661/f9a9e3b7-ec55-48ba-a0f9-0a1be993720f.png align="center")
        
    
    **To show only the top three fruits from the file.**
    
    * `head -3 devops.txt`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688829086406/5756a4f6-6449-4ca2-904b-956e4622534e.png align="center")
        
    
    **To show only the bottom three fruits from the file.**
    
    * `tail -3 devops.txt`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688829233322/0ec6a23e-a788-4862-afa0-543c5dd0296d.png align="center")
        
    
    **To create another file Colors.txt and to view the content.**
    
    * `nano filename.txt && cat filename.txt`
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688829601684/3964ba7e-00b4-4bc6-b4bf-882e9e299aee.png align="center")
    
    **Add content in Colors.txt (One in each line) - Red, Pink, White, Black, Blue, Orange, Purple, Grey.**
    
    * `echo -e "Red\nPink\nWhite\nBlack\nBlue\nOrange\nPurple\nGrey" > Colors.txt`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688830066929/7f3e91db-374a-4bcf-b110-bc5b079d10b0.png align="center")
        
    
    **To find the difference between fruits.txt and Colors.txt file**
    
    * `diff fruits.txt Colors.txt`
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1688831855496/86d6e470-c292-4299-82fb-bc88d2731964.png align="center")