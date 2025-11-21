# Deploying a Scalable Web Application on AWS

The goal of this Project is to deploy a fully scalable and highly available web  application using Amazon Web Services (AWS). The project focuses on building  a robust infrastructure that can handle traffic efficiently while ensuring reliability  and automatic recovery.

## Table of Contents

1. [Objective](#objective)
2. [Architecture Diagram](#architecture-diagram)
3. [Step-by-Step Implementation](#step-by-step-implementation)

   * [3.1 Create Key Pair](#31-create-key-pair)
   * [3.2 Create Security Group](#32-create-security-group)
   * [3.3 Create Launch Template](#33-create-launch-template)
   * [3.4 Create Auto Scaling Group](#34-create-auto-scaling-group)
   * [3.5 Create Target Group](#35-create-target-group)
   * [3.6 Create Application Load Balancer](#36-create-application-load-balancer)
   * [3.7 Attach ASG to Load Balancer](#37-attach-asg-to-load-balancer)
   * [3.8 Testing the Setup](#38-testing-the-setup)
4. [Conclusion](#conclusion)

---

## Objective

The goal of this project is to deploy a fully scalable and highly available web application using Amazon Web Services (AWS). The project focuses on building a robust infrastructure that can handle traffic efficiently while ensuring reliability and automatic recovery.

**Key Objectives:**

* **Scalable Deployment:** Automatically increase or decrease EC2 instances based on demand.
* **High Availability:** Distribute instances across multiple Availability Zones.
* **Launch Template:** Standardize EC2 configurations (AMI, instance type, security groups, key pairs).
* **Auto Scaling Group (ASG):** Manage instance scaling automatically based on CPU utilization or traffic patterns.
* **Application Load Balancer (ALB):** Evenly distribute incoming traffic across EC2 instances.
* **Target Group:** Route traffic to the appropriate instances.
* **Auto-Healing:** Automatically replace unhealthy instances to maintain uptime.

This project demonstrates practical skills in AWS cloud architecture, automation, and resource management.

---

## Architecture Diagram

<img width="2414" height="967" alt="AWS Project Architecture 3" src="https://github.com/user-attachments/assets/29cd5707-8904-4e43-8ae7-b870b6d2da63" />

---

## Step-by-Step Implementation

### 3.1 Create Key Pair

<img width="1918" height="1078" alt="Key Pair" src="https://github.com/user-attachments/assets/c3f77621-2f79-4551-a812-90b297a4d05a" />

---

*Created an SSH key pair for secure EC2 instance access.*

### 3.2 Create Security Group

<img width="1918" height="1077" alt="Security Group" src="https://github.com/user-attachments/assets/158fdb7b-30f2-42f2-8f8c-1f7000757f61" />


*Configured security group to allow HTTP (port 80) and SSH (port 22).*

### 3.3 Create Launch Template

<img width="1918" height="1078" alt="Template 1" src="https://github.com/user-attachments/assets/7ceed709-5258-4eab-aa97-83dde21abc56" />

<img width="1918" height="1078" alt="Template 2" src="https://github.com/user-attachments/assets/70cb46c8-894a-4217-a357-f9953be9da76" />


*Launch template includes AMI, instance type, security group, and user data for Apache installation.*

### 3.4 Create Auto Scaling Group

<img width="1918" height="1078" alt="Auto Scaling 1" src="https://github.com/user-attachments/assets/b9af5c7d-464d-4650-9885-46e7f382546e" />

<img width="1918" height="1078" alt="Auto Scaling 2" src="https://github.com/user-attachments/assets/c6d7ef17-e18d-432a-9da8-a03e55a07a69" />


*Set desired, minimum, and maximum instance settings.*

### 3.5 Create Target Group

<img width="1918" height="1078" alt="Target Group 1" src="https://github.com/user-attachments/assets/cd0a33e2-2d13-4260-be13-d838cef2a24d" />


*Load balancer routes traffic to this target group.*

### 3.6 Create Application Load Balancer

<img width="1918" height="1078" alt="Load Balancer" src="https://github.com/user-attachments/assets/3f4e085b-114c-4ed8-b29e-70609c1d6400" />


*Configured with listener and multiple Availability Zones.*

### 3.7 Attach ASG to Load Balancer

<img width="1918" height="1078" alt="Auto Scaling 3 attached load balancer" src="https://github.com/user-attachments/assets/e14ed42d-d217-4e22-94ec-d324c247cf60" />


*Auto Scaling Group attached to target group for automatic instance registration.*

### 3.8 Testing the Setup

* **Test 1: Accessing via ALB**

  <img width="1918" height="1078" alt="Main Output " src="https://github.com/user-attachments/assets/5bb2a6e8-39a1-4bbd-8ac5-80e893c59220" />
  
  
  *Webpage loads successfully from ALB DNS, showing instance ID.*

* **Test 2: Auto-Healing (Instance Replacement)**

  <img width="1918" height="1078" alt="testing of auto sync" src="https://github.com/user-attachments/assets/617a69c2-13bf-4747-b16d-ee0d42096d3f" />

  <img width="1918" height="1078" alt="automatically started new instances" src="https://github.com/user-attachments/assets/50adac00-2334-4472-82f5-12d64cff6c6b" />
  
  
  *Terminated instances are automatically replaced by ASG.*

* **Test 3: Auto Scaling via CPU Load**

  <img width="1918" height="1078" alt="Main Cmd Output1" src="https://github.com/user-attachments/assets/7d7f54f8-a035-41ef-823b-a9215ea1fa8e" />
  
  
  *CPU stress test run for 300s. Existing instances handled load; no new instances launched.*

---

## Conclusion

<img width="1918" height="1078" alt="Main Output Cmd" src="https://github.com/user-attachments/assets/798be7a6-d1da-4148-8288-d1874b75f3c0" />


Successfully deployed a basic website on AWS displaying a welcome message with instance region and time. Using **Launch Template**, **Auto Scaling Group**, **Target Group**, and **Application Load Balancer**, the webpage runs reliably across multiple instances with automatic traffic distribution and high availability.

---
