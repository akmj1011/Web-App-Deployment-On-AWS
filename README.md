# Web-App-Deployment-On-AWS
The goal of this Project is to deploy a fully scalable and highly available web  application using Amazon Web Services (AWS). The project focuses on building  a robust infrastructure that can handle traffic efficiently while ensuring reliability  and automatic recovery.

# Deploying a Scalable Web Application on AWS

## Table of Contents

1. [Objective](#objective)
2. [Architecture Diagram](#architecture-diagram)
3. [Step-by-Step Implementation](#step-by-step-implementation)

   * 3.1 [Create AWS Free Tier Account](#create-aws-free-tier-account)
   * 3.2 [Create Key Pair](#create-key-pair)
   * 3.3 [Create Security Group](#create-security-group)
   * 3.4 [Create Launch Template](#create-launch-template)
   * 3.5 [Create Auto Scaling Group](#create-auto-scaling-group)
   * 3.6 [Create Target Group](#create-target-group)
   * 3.7 [Create Application Load Balancer](#create-application-load-balancer)
   * 3.8 [Attach ASG to Load Balancer](#attach-asg-to-load-balancer)
   * 3.9 [Testing the Setup](#testing-the-setup)
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

![Architecture Diagram](/C:/Users/anujk/Desktop/aws/mail.png)

---

## Step-by-Step Implementation

### 3.1 Create AWS Free Tier Account

![AWS Free Tier Account](path/to/aws-free-tier-screenshot.png)
*Screenshot shows the AWS Console after creating and activating the Free Tier account.*

### 3.2 Create Key Pair

![Key Pair](path/to/key-pair-screenshot.png)
*Created an SSH key pair for secure EC2 instance access.*

### 3.3 Create Security Group

![Security Group](path/to/security-group-screenshot.png)
*Configured security group to allow HTTP (port 80) and SSH (port 22).*

### 3.4 Create Launch Template

![Launch Template](path/to/launch-template-screenshot.png)
*Launch template includes AMI, instance type, security group, and user data for Apache installation.*

### 3.5 Create Auto Scaling Group

![Auto Scaling Group](path/to/asg-screenshot.png)
*Set desired, minimum, and maximum instance settings.*

### 3.6 Create Target Group

![Target Group](path/to/target-group-screenshot.png)
*Load balancer routes traffic to this target group.*

### 3.7 Create Application Load Balancer

![Application Load Balancer](path/to/alb-screenshot.png)
*Configured with listener and multiple Availability Zones.*

### 3.8 Attach ASG to Load Balancer

![Attach ASG](path/to/asg-to-alb-screenshot.png)
*Auto Scaling Group attached to target group for automatic instance registration.*

### 3.9 Testing the Setup

* **Test 1: Accessing via ALB**
  ![ALB Test](path/to/alb-test-screenshot.png)
  *Webpage loads successfully from ALB DNS, showing instance ID.*

* **Test 2: Auto-Healing (Instance Replacement)**
  ![Auto-Healing Test](path/to/auto-healing-screenshot.png)
  *Terminated instances are automatically replaced by ASG.*

* **Test 3: Auto Scaling via CPU Load**
  ![CPU Load Test](path/to/cpu-load-test-screenshot.png)
  *CPU stress test run for 300s. Existing instances handled load; no new instances launched.*

---

## Conclusion

Successfully deployed a basic website on AWS displaying a welcome message with instance region and time. Using **Launch Template**, **Auto Scaling Group**, **Target Group**, and **Application Load Balancer**, the webpage runs reliably across multiple instances with automatic traffic distribution and high availability.

---
