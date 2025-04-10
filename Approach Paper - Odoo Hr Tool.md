# **Approach Paper \- ODOO HR TOOL**

**Table of Contents :**

**[1\. Objective:	1](#1.-objective:)**

[**2\. Proposed Solutions:	1**](#2.-proposed-solutions:)

[**3\. Approach 1: Details	2**](#heading=h.rqm7ideo133a)

[3.1. Architecture Diagram	2](#3.1.-architecture-diagram)

[3.2.  Description	3](#3.2.-description)

[3.3. Pre-requisites	3](#3.3.-pre-requisites)

[3.3.1. Hardware Requirements	3](#3.3.1.-hardware-requirements)

[3.3.2.Software Requirements	3](#3.3.2.software-requirements)

[3.3.3.Networking Requirements	4](#3.3.3.networking-requirements)

[**4\. Approach 2: Details	4**](#4.-approach-2:-details)

[4.1. Architecture Diagram	4](#4.1.-architecture-diagram)

[4.2. Description	4](#4.2.-description)

[4.3. Pre-requisites	5](#4.3.-pre-requisites)

[4.3.1.  Hardware Requirements	5](#4.3.1.-hardware-requirements)

[4.3.2.  Software Requirements	5](#4.3.2.-software-requirements)

[4.4.3. Networking Requirements	5](#4.4.3.-networking-requirements)

##    **1\. Objective:** {#1.-objective:}

The objective of this project is to deploy the Odoo HR Tool using Podman for containerization. The deployment will ensure high availability and reliability by implementing a master-slave SQL database setup. This approach aims to provide a scalable, resilient, and efficient solution for HR management using Odoo.

##    **2\. Proposed Solutions:** {#2.-proposed-solutions:}

## 

##     **Approach 1:**Deploying Odoo with a Single Podman Container      and a Separate Database Cluster.            

In this setup, Odoo runs inside a single Podman container, while the database is configured in a master-slave setup to ensure high availability. Podman 

handles containerization, offering a secure and rootless environment for better security and efficiency.

### 

**Approach 2:** Deploying Odoo and Database with Podman     Compose.

In this method, both Odoo and its database are deployed using Podman Compose, which helps manage multiple services easily. The database is set up with a master-slave replication model to ensure data redundancy and high availability. This approach makes scaling and managing services more efficient.

## 

**Chosen Approach: Approach 1**

**Reason:** Approach 1 is chosen due to its simplicity, security benefits of Podman, and ease of deployment in a controlled environment. Additionally, managing a single Odoo container with an independent high-availability database cluster aligns well with business continuity and minimal operational overhead.

  **3\.** **Approach 1: Details**

###    **3.1. Architecture Diagram** {#3.1.-architecture-diagram}

![][image1]

 

### **3.2.  Description** {#3.2.-description}

This approach involves deploying Odoo as a standalone Podman container while maintaining a separate SQL database setup in a master-slave configuration. This ensures database redundancy and failover capability. The rootless nature of Podman enhances security and eliminates the need for privileged access.

**Pros:**

* Simplified deployment process.

* Better security with Podman’s rootless mode.

* High availability through a master-slave database setup.

* Easier to manage and troubleshoot.

**Cons:**

* Scaling Odoo might require additional Podman configurations.

* Single-container Odoo may need resource adjustments for performance optimization.

### **3.3. Pre-requisites** {#3.3.-pre-requisites}

#### **3.3.1. Hardware Requirements** {#3.3.1.-hardware-requirements}

* Minimum 4 CPU cores

* 8GB RAM

* 100GB Storage

#### **3.3.2.Software Requirements** {#3.3.2.software-requirements}

* Operating System: Ubuntu 22.04 / RHEL 9

* Podman Version: 4.x

* PostgreSQL Version: 14 (for master-slave setup)

* Odoo Version: 16 (Docker Hub Image)

#### **3.3.3.Networking Requirements** {#3.3.3.networking-requirements}

* Internal network for database replication

* Internet access for pulling container images

## 

##    **4\. Approach 2: Details** {#4.-approach-2:-details}

###  **4.1. Architecture Diagram** {#4.1.-architecture-diagram}

![][image2]

### **4.2. Description** {#4.2.-description}

This approach uses Podman Compose to deploy Odoo alongside its database services in a multi-container setup. This provides better orchestration and scalability by defining services in a configuration file. The master-slave database setup ensures redundancy and fault tolerance.

**Pros:**

* Automated management of multiple services.

* Easier scaling of Odoo and database containers.

* Improved separation of concerns between Odoo and the database.

**Cons:**

* Increased complexity in configuration.

* Requires additional network configuration for inter-container communication.

### **4.3. Pre-requisites** {#4.3.-pre-requisites}

#### **4.3.1.  Hardware Requirements** {#4.3.1.-hardware-requirements}

* Minimum 4 CPU cores

* 8GB RAM

* 120GB Storage

#### **4.3.2.  Software Requirements** {#4.3.2.-software-requirements}

* Operating System: Ubuntu 22.04 / RHEL 9

* Pod-man Version: 4.x

* Podman Compose

* PostgreSQL Version: 14 (for master-slave setup)

* Odoo Version: 16 (Docker Hub Image)

#### **4.4.3. Networking Requirements** {#4.4.3.-networking-requirements}

* Internal container networking for Podman Compose

* Internet access for pulling container images

