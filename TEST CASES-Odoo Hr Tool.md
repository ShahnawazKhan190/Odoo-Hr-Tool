#                       **TEST CASES \- ODOO HR TOOL**

| Submitted By | Shahnawaz  Khan |
| :---- | :---- |
| Submitted To | Mr. Vipin Tripathi |
| Test Case Version | 1.0 |
| Reviewer  Name | Mr. Vipin Tripathi |

**Goal**: I am working on deploying the Odoo Hr Tool using Podman for  containerization .The Odoo image will be pulled from Docker Hub and run as a container .To ensure high availability reliability, I am implementing a master-slave postgres database setup.

 ghjb


                                                                                                                                            


**Table of Contents**

TC 1: Setup Podman on the System

TC 2: Verify Podman Installation

TC 3: Pull Odoo Image Using Podman

TC 4: Run Odoo Container

TC 5: Verify Odoo Web Access

TC 6: Install Master-Slave Database Setup

TC 7: Verify Master-Slave Database Setup

TC 8: High Availability Failover Test

## Test Environment : 

          \< Description of  testing interfaces or urls available to the tester \>

## Test Case 1: Setup Podman on the System

| Scenario |  | Ensure that Podman is installed on the system. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case ensures that Podman is installed correctly before proceeding with containerization. |  |  |  |
| **Given** |  | The target system meets the required dependencies for Podman. |  |  |  |
| **When** |  | The appropriate installation command is executed (e.g., `sudo apt install podman` for Ubuntu). |  |  |  |
| **Then** |  | Podman is installed successfully without errors.The command `podman --version` confirms the installation. |  |  |  |
| **Test Run** |  | **Date** |  | **Result** |  |
| Testing outputs  (paste your output/snapshots here ) |  |  |  |  |  |

## Test Case 1: Verify Podman Installation

| Scenario |  | Ensure that Podman is installed correctly and functional on the system |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case verifies the successful installation and readiness of Podman for use in deploying containers. |  |  |  |
| **Given** |  | Podman is installed on the target system.The system meets the required dependencies and configurations for Podman. |  |  |  |
| **When** |  | The command `podman --version` is executed in the terminal. |  |  |  |
| **Then** |  | The installed version of Podman is displayed without errors.The output includes the Podman version number and confirms that Podman is operational. |  |  |  |
| **Test Run** |  | **Date** |  | **Result** |  |
| Testing outputs  (paste your output/snapshots here ) |  |  |  |  |  |

Test Case 2: Pull Odoo Image Using Podman

| Scenario |  | Ensure that the Odoo image is successfully pulled from Docker Hub using Podman. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case verifies the ability of Podman to fetch the Odoo image from Docker Hub. |  |  |  |
| **Given** |  | Podman is installed and functional.The system has an active internet connection. |  |  |  |
| **When** |  | The command `podman pull odoo:latest` is executed. |  |  |  |
| **Then** |  | The Odoo image is downloaded successfully.The output confirms that the image is available in Podman storage (`podman images`). |  |  |  |
| **Test Run** |  | **Date** |  | **Result** | Pending/Pass/Fail |
| Testing outputs  (paste your output/snapshots here )  |  |  |  |  |  |

### 

Test Case 3: Run Odoo Container

| Scenario |  | Verify that the Odoo container runs successfully using Podman. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case ensures that the Odoo container starts and runs without issues. |  |  |  |
| **Given** |  | The Odoo image is available locally (`podman images`). |  |  |  |
| **When** |  | The command `podman run -d --name odoo-container -p 8069:8069 odoo` is executed. |  |  |  |
| **Then** |  | The Odoo container starts successfully.The command `podman ps` lists the running Odoo container.  |  |  |  |
| **Test Run** |  | **Date** |  | **Result** | Pending/Pass/Fail |
| Testing outputs  (paste your output/snapshots here )  |  |  |  |  |  |

Test Case 4: Verify Odoo Web Access

| Scenario |  | Ensure that the Odoo web interface is accessible after starting the container. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case ensures that the Odoo application is reachable via a web browser. |  |  |  |
| **Given** |  | The Odoo container is running (`podman ps`). |  |  |  |
| **When** |  | The URL `http://<server-ip>:8069` is accessed in a web browser. |  |  |  |
| **Then** |  | The Odoo login page loads without errors. |  |  |  |
| **Test Run** |  | **Date** |  | **Result** | Pending/Pass/Fail |
| Testing outputs  (paste your output/snapshots here )  |  |  |  |  |  |

## Test Case 5: Install Master-Slave Database Setup

| Scenario |  | Ensure that the PostgreSQL master-slave database setup is installed successfully. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case verifies the successful installation and configuration of a PostgreSQL master-slave database setup. |  |  |  |
| **Given** |  | Podman is installed and functional.The system has an active internet connection. |  |  |  |
| **When** |  | The required PostgreSQL master and slave containers are pulled and configured. |  |  |  |
| **Then** |  | Both the master and slave databases are installed and running.The master database accepts write operations, and the slave is set up to replicate. |  |  |  |
| **Test Run** |  | **Date** |  | **Result** | Pending/Pass/Fail |
| Testing outputs  (paste your output/snapshots here )  |  |  |  |  |  |

Test Case 5: Verify Master-Slave Database Setup

| Scenario |  | Ensure that the PostgreSQL master-slave database is set up correctly and data replication works. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case ensures that changes in the master database reflect in the slave database. |  |  |  |
| **Given** |  | The PostgreSQL master and slave containers are running. |  |  |  |
| **When** |  | A new record is inserted into the master database.The slave database is queried for the new record.  |  |  |  |
| **Then** |  | The record appears in the slave database, confirming replication. |  |  |  |
| **Test Run** |  | **Date** |  | **Result** | Pending/Pass/Fail |
| Testing outputs  (paste your output/snapshots here )  |  |  |  |  |  |

Test Case 6: High Availability Failover Test

| Scenario |  | Ensure that the PostgreSQL master-slave database is set up correctly and data replication works. |  |  |  |
| :---- | ----- | :---- | :---- | :---- | :---- |
| **Remarks:**  |  | This test case ensures that changes in the master database reflect in the slave database. |  |  |  |
| **Given** |  | The PostgreSQL master and slave containers are running. |  |  |  |
| **When** |  | A new record is inserted into the master database.The slave database is queried for the new record. |  |  |  |
| **Then** |  | The record appears in the slave database, confirming replication. |  |  |  |
| **Test Run** |  | **Date** |  | **Result** | Pending/Pass/Fail |
| Testing outputs  (paste your output/snapshots here )  |  |  |  |  |  |

