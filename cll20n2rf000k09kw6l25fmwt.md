---
title: "Two-tier Web Application Deployment using Docker Compose"
datePublished: Tue Aug 08 2023 08:04:44 GMT+0000 (Coordinated Universal Time)
cuid: cll20n2rf000k09kw6l25fmwt
slug: two-tier-web-application-deployment-using-docker-compose
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1691479045831/476c2ae7-0858-4ffc-9537-634cf25976ec.png
tags: docker, devops, docker-compose, two-tire-application

---

## Introduction

Welcome to our blog! The demand for efficient and seamless web application deployment is ever-growing in today's digital age. The world of two-tier web architecture is a powerful approach. But that's not all – we're taking it a step further by introducing you to the magic of Docker Compose, a game-changing tool that simplifies the deployment process, enhances scalability, and streamlines management. In this blog, we'll unravel the concepts behind the two-tier architecture and guide you through deploying your very own two-tier web application using Docker Compose.

## What is Two-tier Architecture?

![Two-Tier Architecture - Coding Ninjas](https://files.codingninjas.in/article_images/two-tier-architecture-0-1648535544.webp align="left")

Two-tier architecture, also known as two-layer architecture, is a software architecture design in which an application is divided into two distinct layers or tiers:

1. **Presentation Layer (Client Tier):**
    
    * This is the user interface or the front-end layer of the application that interacts directly with users.
        
    * It is responsible for presenting data and user interfaces to the users, typically through a graphical user interface (GUI).
        
    * User interactions, such as input validation and user interface logic, are managed in this layer.
        
    * The presentation layer communicates with the data layer to retrieve or store data.
        
2. **Data/Storage Layer (Server Tier):**
    
    * This is the back-end layer that handles data storage, retrieval, and manipulation.
        
    * It is responsible for managing data storage, databases, and data-related operations.
        
    * Business logic and application functionality that involve data processing are typically handled in this layer.
        
    * The data layer communicates with the presentation layer to provide the requested data or to store data submitted by users.
        

## What is Docker Compose?

Docker Compose is **a tool that was developed to help define and share multi-container applications**. With Compose, we can create a YAML file to define the services and with a single command, can spin everything up or tear it all down.

### docker-compose.yml

A `docker-compose.yml` file, often referred to as a Compose file, is a configuration file used by Docker Compose to define and manage multi-container applications. This YAML-formatted file contains all the necessary instructions and settings to specify the services, networks, and volumes that make up your application.

**Example**

```plaintext
version: '3'
services:
  
  backend:
    build:
      context: .
    ports:
      - "5000:5000"
    environment:
      MYSQL_HOST: mysql
      MYSQL_USER: root
      MYSQL_PASSWORD: test@123
      MYSQL_DB: two_tier
    depends_on:
      - mysql

  mysql:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: test@123
      MYSQL_DATABASE: two_tier
      MYSQL_USER: devops
      MYSQL_PASSWORD: devops
    volumes:
      - mysql-data:/var/lib/mysql  # Mount the volume for MySQL data storage

volumes:
  mysql-data:
```

## Project

### **Step 1: Clone the Repository**

Open your terminal and execute the following commands:

```plaintext
https://github.com/DhanashriSaner/two-tier-flask-app.git
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691410691364/b0b95ecf-950c-4474-92c9-1df7121f0cdb.png align="center")

### **Step 2: Install Docker Compose**

```plaintext
sudo apt install docker-compose -y
```

### **Step 3: Start the Application with Docker Compose**

```plaintext
docker-compose up -d
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691410849367/ec41bfe5-96d4-410d-aacb-a439cd6e97e2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691410893538/a3238e6f-2944-4cdb-914b-f7bd449b722d.png align="center")

### **Step 4: Verify Containers**

To make sure everything is up and running, execute the following command:

```plaintext
docker ps
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691410991846/80a040f9-3ad5-422e-a577-e3df4b85e19d.png align="center")

### **Step 5: Create a MySQL Data Volume**

Now, let's create a data volume to store the MySQL data.

```plaintext
sudo mkdir /var/lib/mysql/
```

### **Step 6: Access MySQL Database**

Now the MySQL database is running in the container. We have to find the container name using the `docker ps` command. Then, use the following command to access the MySQL shell:

```plaintext
docker exec -it <CONTAINER_ID> bash
```

```plaintext
mysql -u root -p
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691411245896/9c8fa59b-ce68-4e16-9c43-ee4da27367c1.png align="center")

### **Step 7: Create the database and table**

Now You'll have to enter the MySQL root password to log in and execute the following queries.

```plaintext
use two_tier;

show databases;

create table messages (message varchar(300));
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691411389482/8f76a741-3cdc-47b9-9627-235e36425190.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691411463305/baec194c-cd82-4e5b-aece-177e10679a89.png align="left")

### **Step 8: Access the Application**

To check your Flask application progress, open a web browser and enter the following URL:

```plaintext
http://PUBLIC_IP_OF_SERVER:5000
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1691411958493/ff6ab1f9-4e55-4d87-89d6-aafdf706b702.png align="center")

### **Step 9: Cleaning up**

To stop and remove the Docker containers, press `Ctrl+C` in the terminal where the containers are running, or use the following command:

```plaintext
docker-compose down
```

With this newfound knowledge, you're ready to embark on your own deployment adventures, crafting digital landscapes that seamlessly integrate presentation and data layers. Remember, the road to mastery may have its twists and turns, but armed with Docker Compose, you've got the compass to navigate the complex terrain of modern application deployment.

So go ahead, start composing your container symphony, and watch your web applications. Happy deploying!