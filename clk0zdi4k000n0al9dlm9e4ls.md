---
title: "Unlocking the Potential of Package Management in Linux: A DevOps Perspective"
datePublished: Thu Jul 13 2023 10:01:49 GMT+0000 (Coordinated Universal Time)
cuid: clk0zdi4k000n0al9dlm9e4ls
slug: unlocking-the-potential-of-package-management-in-linux-a-devops-perspective
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1689237284166/a781e219-83b0-4a19-b88c-1199ac23700d.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1689242480309/71caba08-fa26-4c15-b26a-a69b1022a00f.jpeg
tags: learning, package-manager, linux-for-beginners, systemctl, docker-installation

---

## Introduction

Welcome to the Day 7 of the **#90DaysOfDevOps** challenge, where we dive into the world of package management in Linux from a DevOps perspective. In this fast-paced digital era, efficient software deployment is crucial for organizations to stay competitive. And that's where package management comes into play.

## Linux Package Manager

A Linux package manager is a software tool or system used to manage the installation, removal, and maintenance of software packages in a Linux operating system. Linux package managers typically work with pre-compiled software packages that contain executable files, libraries, and configuration files necessary for the proper functioning of applications.

### What is Package?

Package refers to a software bundle that contains all the necessary files and information required for the installation, configuration, and execution of a specific software application or component.

### Functions of Package Managers

1. Package installation
    
2. Dependency management
    
3. Package updates
    
4. Package removal
    
5. Repository management
    
6. Version control
    
7. Conflict resolution
    
8. Package verification and security
    
9. Rollback and recover
    

## Examples of Package Managers in Linux

1. **APT** (Advanced Package Tool): Used in Debian-based distributions such as Debian, Ubuntu, and Linux Mint.
    
2. **YUM** (Yellowdog Updater Modified): Commonly found in Red Hat-based distributions like Red Hat Enterprise Linux (RHEL), CentOS, and Fedora.
    
3. **DNF** (Dandified YUM): The next-generation package manager used in newer versions of Fedora and CentOS.
    
4. **Pacman**: The package manager used in Arch Linux and its derivatives like Manjaro.
    
5. **Zypper**: Found in openSUSE and SUSE Linux Enterprise distributions.
    
6. **Portage**: Used in Gentoo Linux, emphasizing source-based package management.
    
7. **Snap**: A universal package manager that works across various Linux distributions, allowing easy installation of software and its dependencies.
    
8. **Flatpak**: Another universal package manager designed for sandboxed applications, compatible with multiple Linux distributions.
    
9. **AppImage**: A packaging format that allows the software to run on various Linux distributions without installation or specific package managers.
    
10. **RPM** (Red Hat Package Manager): A low-level package management format used by package managers like YUM and DNF, as well as other Linux distributions.
    

## Installation of Docker using APT Package Manager on Ubuntu

![Docker Installation on Ubuntu. Docker installation system requirements | by  Bikram | Medium](https://miro.medium.com/v2/resize:fit:1199/0*cuY5R0hQ9doC8svc.png align="left")

**Step 1)** Update your existing list of packages:

```plaintext
$ sudo apt update
```

**Step 2)** Install the required packages to allow APT to use repositories over HTTPS:

```plaintext
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

**Step 3)** Import the Docker GPG key to ensure package authenticity:

```plaintext
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

**Step 4)** Add the Docker repository to APT sources:

```plaintext
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
```

**Step 5)** Make sure you are about to install from the Docker repo instead of the default Ubuntu repo:

```plaintext
$ apt-cache policy docker-ce
```

**Step 6)** Update the package index again to include the Docker repository:

```plaintext
$ sudo apt update
```

**Step 7)** Finally, install Docker:

```plaintext
$ sudo apt install docker-ce
```

Step 8) After the installation is complete, verify that Docker is running:

```plaintext
$ sudo systemctl status docker
```

**Output**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1689240889345/e7da735a-2f8f-4079-9d92-fcf7cfe4adcd.png align="center")

That's it! You have successfully installed Docker using the APT package manager on Ubuntu. You can now start using Docker to containerize and manage your applications.

## systemctl

systemctl is a command-line utility in Linux systems that is used to control and manage **systemd**, which are the system and service manager. It allows users to start, stop, restart, enable, disable, and check the status of services and units in the systemd ecosystem.

### What is Service in Linux?

A service refers to a background process or daemon that runs continuously to perform specific tasks or provide functionality.

**Command to see all running services on a Linux system**

```plaintext
$ systemctl --type=service --state=running
```

### Common systemctl commands

Displays the version number of the systemctl command.

* Start a service: `sudo systemctl start <service-name>`
    
* Stop a service: `sudo systemctl stop <service-name>`
    
* Restart a service: `sudo systemctl restart <service-name>`
    
* Enable a service to start on boot: `sudo systemctl enable <service-name>`
    
* Disable a service from starting on boot: `sudo systemctl disable <service-name>`
    
* Check the status of a service: `sudo systemctl status <service-name>`
    
* View the logs of a service: `sudo journalctl -u <service-name>`
    

systemctl provides a centralized and standardized way to manage system services and units. It simplifies the administration and control of services in Linux systems, providing a consistent interface across different distributions that use systemd.

## Conclusion

Unlocking the potential of package management in Linux brings immense benefits to DevOps practices. By leveraging package managers, we streamline software deployment, automate dependency management, and ensure system stability. Containerization technologies, such as Docker, complement package management for scalable and consistent deployments. With this knowledge, we can revolutionize DevOps workflows, driving innovation and efficiency in Linux environments. Let's embrace the power of package management and unleash the full potential of Linux for successful DevOps endeavors.