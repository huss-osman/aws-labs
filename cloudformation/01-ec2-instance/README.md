# CloudFormation EC2 Deployment

![Cloud](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazonaws&logoColor=white)
![IaC](https://img.shields.io/badge/IaC-CloudFormation-blue)
![Compute](https://img.shields.io/badge/Compute-EC2-orange?logo=amazonec2&logoColor=white)
![Language](https://img.shields.io/badge/Language-YAML-red)
![Practice](https://img.shields.io/badge/Practice-Hands--on-orange)

<p align="center">
  <img width="1000" alt="CloudFormation EC2 Deployment" src="images/cloudformation-ec2-overview.png">
</p>

---

## Overview

This demonstration provisions an Amazon EC2 instance using an AWS CloudFormation template written in YAML.

Instead of manually creating infrastructure through the AWS Management Console (ClickOps), the infrastructure is defined as code, making deployments repeatable, version-controlled, and easy to recreate.

The stack automatically provisions the required AWS resources and allows the entire deployment to be removed by deleting the CloudFormation stack.

---

## Architecture

<p align="center">
  <img width="1000" alt="Architecture" src="images/architecture.png">
</p>

---

## What this Demonstrates

- Infrastructure as Code (IaC)
- AWS CloudFormation
- YAML Templates
- Amazon EC2
- Security Groups
- Stack Creation
- Stack Deletion
- Repeatable Deployments

---

## Deployment Workflow

```text
CloudFormation YAML
        │
        ▼
CloudFormation Stack
        │
        ▼
Security Group
        │
        ▼
Amazon EC2 Instance
```

---

## Project Structure

```text
01-ec2-instance/
├── README.md
├── ec2instance.yaml
└── images/
    ├── architecture.png
    ├── cloudformation-ec2-overview.png
    ├── yaml-template.png
    ├── create-stack.png
    ├── stack-complete.png
    ├── resources.png
    ├── ec2-running.png
    ├── browser.png
    ├── delete-stack.png
    └── delete-complete.png
```

---

## Deployment

### 1. Create the CloudFormation Stack

Upload the YAML template through the AWS CloudFormation console.

<p align="center">
  <img width="1000" alt="Create Stack" src="images/create-stack.png">
</p>

---

### 2. CloudFormation Creates the Resources

CloudFormation provisions the resources defined in the template.

<p align="center">
  <img width="1000" alt="Stack Complete" src="images/stack-complete.png">
</p>

---

### 3. EC2 Instance Running

Once the stack reaches **CREATE_COMPLETE**, the EC2 instance is available.

<p align="center">
  <img width="1000" alt="EC2 Running" src="images/ec2-running.png">
</p>

---

### 4. Delete the Stack

Deleting the CloudFormation stack automatically removes all resources created by the template.

<p align="center">
  <img width="1000" alt="Delete Stack" src="images/delete-stack.png">
</p>

---

## Key Takeaways

- Infrastructure can be defined using YAML.
- CloudFormation provisions AWS resources automatically.
- Infrastructure becomes repeatable and version controlled.
- Deployments are consistent across environments.
- Entire environments can be created and removed in minutes.
- Infrastructure as Code replaces repetitive manual ClickOps.

---

## References

- https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/
- https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/gettingstarted.html
