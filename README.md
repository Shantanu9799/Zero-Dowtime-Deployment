# ECS Deployment Guide

## 1. AWS ECS Overview
Amazon ECS (Elastic Container Service) is a fully managed container orchestration service provided by AWS. ECS simplifies the process of managing containerized workloads, allowing developers to run and scale Docker containers in production without managing the underlying infrastructure.

---

## 2. Steps to Create ECS using Fargate

### 2.1 Creation of Docker Images and Push to ECR
- Build Docker images for your application.
- Push them to Amazon ECR (Elastic Container Registry) for storage.

### 2.2 Creation of ECS Cluster
- Navigate to the ECS dashboard and click on **Create cluster**.
- Enter the required details and click **Create**.

### 2.3 Creation of Task Definition
- Navigate to the ECS Dashboard.
- From the left panel, choose **Task Definition** and click on **Create new task definition**.
- Configure the task definition with the necessary details.
  - Copy the **Image URI** from the previously created ECR repository.
  - Paste the URI in the **Image URI** section for **Container-1**.
- Click **Create**.

### 2.4 Creation of Service
- Navigate to ECS dashboard, select the newly created cluster (e.g., `ecs-fargate-cluster`).
- At the bottom under **Services**, click **Create**.
- Enter the necessary details for the service.
- Click **Create**. The process will take a few minutes.
- After creation, check the service and tasks.

### 2.5 Final Output
To verify the deployment, open the following URL in your browser:

Example:  
[http://test-lb-108914588.ap-south-1.elb.amazonaws.com:9172/test/](http://test-lb-108914588.ap-south-1.elb.amazonaws.com:9172/test/)


---

## 3. Steps to Delete ECS Cluster

### 3.1 Deregister the Task
- Navigate to the **Task Definition** page.
- Select the task definition, click on **Actions**, and choose **Deregister**.

### 3.2 Delete the Cluster
- Navigate to the **Clusters** page.
- Select your cluster and click on **Delete cluster**.

---

## 4. Steps to Create ECS using EC2

### 4.1 Creation of Docker Images and Push to ECR
- Build Docker images for your application.
- Push them to Amazon ECR (Elastic Container Registry) for storage.

### 4.2 Creation of ECS Cluster
- Navigate to the ECS dashboard and click on **Create cluster**.
- Enter the required details.
- You can create a key-pair for the ECS instances and select it from the dropdown menu.
- Click **Create**.

### 4.3 Creation of Task Definition
- Navigate to the ECS Dashboard.
- From the left panel, choose **Task Definition** and click on **Create new task definition**.
- Configure the task definition with the necessary details.
  - Copy the **Image URI** from the previously created ECR repository.
  - Paste the URI in the **Image URI** section for **Container-1**.
- Click **Create**.

### 4.4 Creation of Service
- Navigate to the ECS dashboard, select the newly created cluster (e.g., `ecs-ec2-cluster`).
- At the bottom under **Services**, click **Create**.
- Enter the necessary details for the service.
- Click **Create**. The process will take a few minutes.
- After creation, check the service and tasks.

### 4.5 Final Output
To verify the deployment, open the following URL in your browser:

Example:  
[http://test-lb-108914588.ap-south-1.elb.amazonaws.com:9172/test/](http://test-lb-108914588.ap-south-1.elb.amazonaws.com:9172/test/)


---

## 5. Notes
- For EC2 instance creation, it's recommended to use instance types like `t2.small` or `t3` instead of `t2.micro` for optimal performance.
- Use **x86(64)** architecture for both the Task Definition and the Cluster.

