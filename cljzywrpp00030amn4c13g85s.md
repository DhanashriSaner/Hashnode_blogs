---
title: "Enhancing Security with Linux File Permissions and Access Control Lists"
seoTitle: "Enhancing Security with Linux File Permissions & Access Control List"
datePublished: Wed Jul 12 2023 17:01:02 GMT+0000 (Coordinated Universal Time)
cuid: cljzywrpp00030amn4c13g85s
slug: enhancing-security-with-linux-file-permissions-and-access-control-lists
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689152348403/572a4e55-227c-45cd-9f16-390112ce7251.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689181024474/da580069-0784-4bf0-a65b-9ff173949888.png
tags: linux, security, access-control-list, linux-file-permissions, file-permissions-linux-unix-acls-access-control-lists-security-permissions-chmod-chown-setfacl-getfacl-octal-notation-symbolic-notation-user-permissions-group-permissions-other-permissions-fine-grained-access-control-file-ownership-file-system-security-command-line-operating-systems

---

Welcome to the **Day 6** of the **#90DaysofDevOps** Challenge.

## Introduction:

In today's digital landscape, where data breaches and unauthorized access are constant threats, safeguarding sensitive information is paramount. Linux, known for its robust security features, offers a powerful mechanism for protecting files and directories through file permissions and Access Control Lists (ACLs). Understanding and effectively utilizing these security measures can significantly enhance the overall security posture of your Linux system.

In this blog post, we will delve into the world of Linux file permissions and Access Control Lists, exploring their fundamental concepts, their role in enforcing security, and practical techniques for implementing and managing them. Whether you are a system administrator, a developer, or simply an enthusiast looking to fortify your Linux environment, this guide will provide you with valuable insights and best practices to bolster your system's defenses.

## Linux File Ownership

In Linux, file ownership refers to the association of a file or directory with a specific user and group. Every file and directory is owned by a user and belongs to a group.

1. **User Ownership:**
    
    The user ownership of a file determines which user account has control over the file. The owner of a file can typically modify, delete, or change the permissions of the file. Each user on a Linux system has a unique user ID (UID) that identifies them.
    
2. **Group Ownership:**
    
    The group ownership of a file indicates the group to which the file belongs. A group is a collection of user accounts that can share common permissions for accessing files. Group ownership allows multiple users to access and collaborate on files with shared permissions. Each group on a Linux system has a unique group ID (GID).
    
3. **Other Ownership:**
    
    Other ownership, also known as world ownership, refers to all other users who are neither the user owner nor members of the group that owns the file.
    

Now, the big question arises how does **Linux distinguish** between these three user types so that a user ‘A’ cannot affect a file which contains some other user ‘B’s’ vital information/data? It is like you do not want your colleague, who works on your Linux Computer to view your images. This is where **Permissions** are set in, and they define **user behavior**.

Let us understand the **Permission system** on Linux.

## Linux File Permissions

In Linux, file permissions refer to the access rights or privileges assigned to files and directories. These permissions determine who can perform specific operations on the file, such as reading, writing, and executing.

Here's a breakdown of the three permission types:

1. **Read (r)**: The read permission allows a user to view the contents of a file or list the files within a directory. For directories, it also enables the user to access metadata information like file names and permissions.
    
2. **Write (w)**: The write permission grants a user the ability to modify or delete a file. For directories, it allows creating, deleting, and renaming files within that directory.
    
3. **Execute (x):** The execute permission allows a user to run or execute a file if it is a program or script. For directories, the execute permission enables a user to access the contents of the directory and traverse into it.
    

These permissions are represented by a series of characters when listing files in the terminal. For example, if you run the `ls -l` command, you will see a string of characters like "drwxr-xr-x" at the start of each line. Each character in the string represents a specific permission for the owner, group, and other users, respectively.

![Linux File Permissions Explained: A Practical Approach](https://linuxopsys.com/wp-content/uploads/2021/12/linux-permissions-2021-12-1004.png align="left")

Let's see file permissions in Linux with an example:

**Command to see the file persmissions:**

```plaintext
$ ls -l
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689168554909/fa308b42-7ffe-4bdb-8376-ca933659948c.png align="center")

Here, the first ‘**–**‘ implies that we have selected a file

![File Permissions in Linux/Unix](https://www.guru99.com/images/its_a_file.png align="left")

Else, if it were a directory, **d** would have been shown.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689168834296/a6232fc2-af23-4027-b047-b865819dc298.png align="left")

Where characters represent the following:

**r** = read permission  
**w** = write permission  
**x** = execute permission  
**–** = no permission

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689169045785/35a83a08-9268-4d43-9216-1b7c33a12ce4.png align="left")

Here, the first part of the code is **‘rw-‘**. This suggests that the **owner** can:

* Read the file
    
* Write or edit the file
    
* She cannot execute the file since the execute bit is set to ‘-‘.
    

The second part is **‘rw-‘.** It is for the **user group** and **group members** can:

* Read the file
    
* Write or edit the file
    
* They cannot execute the file since the execute bit is set to ‘-‘.
    

The third part is for the world which means any user. It says **‘r- -‘.** This means the user can only:

* Read the file
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689169679445/edcf089c-2acd-40ec-92ad-1db352e6e577.png align="left")
    

## **Changing file/directory permissions in Linux Using ‘chmod’ command**

We can use the ‘**chmod’** command which stands for ‘change mode’. Using the command, we can set permissions (read, write, execute) on a file/directory for the owner, group and the world.

**Syntax**

```plaintext
chmod permissions filename
```

There are 2 ways to use the command –

1. **Symbolic mode**
    
    The symbolic representation uses a combination of characters to represent the permission bits. In this, we have to make a combination of **letters** and **operators** to set or tell what to do with permissions.
    
    The following operators can be used with the symbolic mode-
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689184829582/31cad4a0-ef0f-4759-aea1-7b9ab382753a.png align="center")
    
    The following letters can be used in symbolic mode-
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689184871579/e304cbc4-f996-4630-b391-1f4ca86f837d.png align="center")
    
    The various owners are represented as-
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689184894369/909595f5-c209-4fad-8de3-40c672ea2856.png align="center")
    
    Let's see an example:
    
    Current file permissions are:
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689172449400/57e7d09f-c0db-4a75-b704-431db7e52c4d.png align="center")
    
    Setting Permissions to the '**Others'** user
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689172617308/5db12a70-a85f-4650-b574-30e44b48546b.png align="center")
    
    Adding '**execute**' permission to the user **group**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689172934898/230bd729-5bbd-45d8-a915-2ad35383150f.png align="center")
    
    Removing **'read'** permission for **'user'**
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689173190503/c699ea2e-77d3-4fb2-aafc-b56786a9c6f8.png align="center")
    
2. **Octal \\ Numeric mode**
    
    Octal mode representation is another method used in Linux to represent file permissions. It is a concise numerical representation that uses octal (base-8) digits to represent the permission bits for the user, group, and other categories. Each permission type (read, write, execute) is assigned a numeric value, and these values are combined to represent the overall permission set.
    
    The table below gives numbers for all permission types.
    
    ![The table below gives numbers for all for permissions types.](https://vk9-sec.com/wp-content/uploads/2020/03/resultado-de-imagen-de-chmod-permissions.png align="left")
    
    Let’s see the **chmod** permissions command in action.
    
    Checking current file permissions for the file
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689172449400/57e7d09f-c0db-4a75-b704-431db7e52c4d.png align="center")
    
    **chmod 764** and again checking file permissions
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689174223246/993db4bd-0d51-462a-bc80-b580f10a58fc.png align="center")
    
    In the above-given terminal window, we have changed the permissions of the file ‘new\_file.txt' to ‘764’.
    
    ‘764’ absolute code says the following:
    
    * **Owner** can read, write and execute
        
    * **Usergroup** can read and write
        
    * **Others** can only read
        
        ![File Permissions in Linux/Unix](https://www.guru99.com/images/FilePermissions(1).png align="center")
        

This is how you can change user permissions in Linux on file.

## Access Control Lists(ACL) in Linux

**Access Control Lists** (ACLs) are an extension to traditional Linux file permissions that provide more fine-grained control over access rights for files and directories. While standard file permissions (user, group, and other) offer a limited set of permissions, ACLs allow for additional access rules to be defined for specific users or groups.

### Uses of Access Control Lists

1. **Fine-grained access control**: ACLs provide a more granular level of control over file and directory permissions, allowing you to define specific access rights for individual users or groups.
    
2. **Access for non-owner users**: ACLs enable granting or restricting access to files and directories for users or groups who are not the owner or part of the owning group.
    
3. **Collaboration and shared resources**: ACLs facilitate secure collaboration by allowing selected users or groups to have tailored access permissions to specific files or directories.
    
4. **Complex permission scenarios**: ACLs are useful in scenarios where standard file permissions alone are not sufficient, such as granting read access to one group of users while restricting write access to another group.
    
5. **Compliance with security policies:** ACLs help meet security requirements by enabling precise control over access to sensitive files, ensuring that only authorized individuals or groups can perform certain actions.
    
6. **Multi-user environments:** In environments with multiple users, ACLs allow administrators to set specific access permissions for each user, reducing the risk of unauthorized modifications or data breaches.
    
7. **File servers and shared file systems**: ACLs play a crucial role in file servers and shared file systems, ensuring that different users or groups have appropriate access rights to shared resources.
    
8. **Dynamic modification**: ACLs can be modified dynamically, allowing for the addition or removal of specific access rules without changing the existing permissions, providing flexibility in access management.
    
9. **Inheritance**: ACLs can be inherited by subdirectories and files within a directory, making it easier to maintain consistent access control throughout a directory tree.
    
10. **Compliance with regulatory standards**: ACLs assist in meeting regulatory requirements regarding access control and data privacy, as they offer more flexibility in defining and enforcing access policies.
    

### What are **setfacl** and **getfacl in ACL?**

In Linux, `setfacl` and `getfacl` are commands used to manage and manipulate Access Control Lists (ACLs).

1. **setfacl**
    
    The `setfacl` command is used to set or modify the ACL of files and directories. It allows you to define or modify specific access rules for individual users or groups, granting or revoking permissions beyond the traditional file permissions.
    
    The `setfacl` command has various options and syntax variations to specify the desired ACL rules. For example, you can use the `-m` option to modify existing ACLs, the `-x` option to remove specific ACL entries, or the `-R` option to apply ACL changes recursively to subdirectories.
    
    Usage examples:
    
    * `setfacl -m u:user1:rw file.txt`: Grants read and write permissions to `user1` on `file.txt`.
        
    * `setfacl -x u:user2 file.txt`: Removes the ACL entry for `user2` on `file.txt`.
        
2. **getfacl**
    
    The `getfacl` command is used to retrieve and display the ACL information of files and directories. It allows you to view the existing ACL entries and their corresponding permissions for users and groups.
    
    Running `getfacl` without any options on a file or directory will display the ACL information in a human-readable format, including the owner, group, and other ACL entries, as well as their associated permissions.
    
    Usage examples:
    
    * `getfacl file.txt`: Displays the ACL entries and permissions for `file.txt`.
        
    * `getfacl -R directory/`: Displays the ACL information for the `directory/` and all its subdirectories recursively.
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689179490684/f44cc746-4182-4c49-bf05-33e68ca94ad8.png align="center")
        

## Conclusion

Linux file permissions and Access Control Lists (ACLs) offer powerful tools for enhancing security in your Linux environment. By leveraging these mechanisms, you can enforce fine-grained access control, protect sensitive files, facilitate secure collaboration, and ensure compliance with security policies.

Remember, security is an ongoing process, and regular review and maintenance of file permissions and ACLs are crucial to adapt to evolving threats. Stay proactive, stay vigilant, and enjoy the enhanced security benefits that Linux file permissions and ACLs bring to your system.

Thank you for joining us on this journey to enhance security with Linux file permissions and Access Control Lists. Secure your files, protect your system, and embrace the power of robust access control.