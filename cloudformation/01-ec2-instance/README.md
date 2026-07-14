# CloudFormation EC2 Deployment

![Cloud](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazonaws&logoColor=white)
![IaC](https://img.shields.io/badge/IaC-CloudFormation-blue)
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Language](https://img.shields.io/badge/Language-YAML-red)
![Automation](https://img.shields.io/badge/Automation-Infrastructure%20as%20Code-green)


<p align="center">
<img width="850" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/0ed4daa0-60c0-40ec-9b35-ed61677f9ef4" /> 
</p>


This project demonstrates Infrastructure as Code (IaC) by provisioning an Amazon EC2 instance using an AWS CloudFormation template written in YAML. It deploys an EC2 instance, Security Group, IAM Role, and IAM Instance Profile automatically through a CloudFormation stack, eliminating manual infrastructure provisioning.

The goal was to understand how cloud infrastructure is deployed through code, covering concepts such as Infrastructure as Code, CloudFormation stacks, YAML templates, automated resource provisioning, and repeatable cloud deployments in AWS.

---

## Objective

The goal of this project was to:

- Learn Infrastructure as Code (IaC)
- Build a CloudFormation template using YAML
- Provision an EC2 instance automatically
- Create a Security Group through CloudFormation
- Understand CloudFormation stacks
- Deploy infrastructure without ClickOps
- Practice automated cloud provisioning

---

## How It Works

1. The YAML template is uploaded to AWS CloudFormation.
2. CloudFormation creates a new stack.
3. AWS provisions the Security Group.
4. AWS launches the EC2 instance.
5. The infrastructure becomes available.
6. Deleting the stack removes every provisioned resource.

---

# Reviewing the CloudFormation Template

The infrastructure is fully defined inside a YAML template.

Download the template here:

➡️ **[ec2-instance.yaml](./ec2-instance.yaml)**

<p align="center">
<img width="1000" alt="YAML Template" src="https://github.com/user-attachments/assets/ff0d7951-504b-497b-a2c5-7f267c881183" /> 
</p> 

---

# Defining the Parameters

The template begins by defining configurable parameters that can be supplied during deployment.

<p align="center">
<img width="1000" alt="Parameters" src="https://github.com/user-attachments/assets/df981119-5d6e-4c7b-a5ba-2bfae9f37159" />
</p>

---

# Defining the EC2 Instance

CloudFormation provisions the EC2 instance using the resource definition contained within the template.

<p align="center">
<img width="700" alt="EC2 Resource" src="https://github.com/user-attachments/assets/170cb751-c48a-41e4-bfba-619925383935" /> 

</p>

---

# Defining the Security Group

The Security Group is created automatically as part of the stack deployment.

<p align="center">
<img width="750" alt="Security Group Resource" src="https://github.com/user-attachments/assets/4da61fe6-3658-42b0-941a-245b75062349" />
</p>


# Stack Successfully Created

Once validation completed, CloudFormation provisioned every resource defined in the template.

<p align="center">
<img width="1000" alt="Stack Complete" src="https://github.com/user-attachments/assets/2400a20c-26c3-4408-9c70-c35a8342863e" /> 
</p>

The deployment reached:

```text
CREATE_COMPLETE
```

---

# Provisioned Resources

CloudFormation provisioned the AWS resources defined in the YAML template, automatically deploying each component.

<p align="center">
<img width="1000" alt="Resources" src="https://github.com/user-attachments/assets/3b25b1f2-6122-4ee7-bdfd-98fcd366fc86" /> 
</p>

The following resources were provisioned successfully:

- Amazon EC2 Instance
- Security Group
- IAM Role
- IAM Instance Profile

Each resource reached the **CREATE_COMPLETE** state, confirming that the CloudFormation stack deployed the infrastructure successfully without requiring manual configuration through the AWS Management Console.

---

# EC2 Instance Running

After the stack completed, the EC2 instance became available.

<p align="center">
<img width="1000" alt="EC2 Running" src="https://github.com/user-attachments/assets/1d17a0fa-0e74-42a5-a33b-b68386f3353e" />

</p>

Configuration included:

- Amazon Linux 2023
- t3.micro
- Public IPv4
- Security Group

---

# Demonstration

The complete deployment process is shown below.

https://github.com/user-attachments/assets/bf139c56-9bdd-49e2-b305-372a73ddcf4c

The walkthrough demonstrates:

- Reviewing the YAML template
- Creating the CloudFormation stack
- Provisioning AWS resources
- Reviewing the EC2 instance
- Understanding the deployment workflow

---

# Deleting the Stack

Once testing was complete, the CloudFormation stack was deleted.

https://github.com/user-attachments/assets/734e6b52-20cc-41e6-9a01-30ddf91e65a8

CloudFormation first removed the stack's logical resources before deleting the corresponding physical AWS resources, automatically cleaning up the deployed infrastructure.

---

# Resource Deletion

During the deletion process, CloudFormation terminated the EC2 instance and removed the remaining resources defined in the stack.

<p align="center">
<img width="1000" alt="EC2 Instance Shutting Down" src="https://github.com/user-attachments/assets/3d696f34-2cb7-4269-b38f-2ffe94f278aa" /> 
</p>

The EC2 instance entered the **Shutting-down** state before being permanently **Terminated**, completing the stack deletion lifecycle.

---

# Why I Built It

I wanted a hands-on understanding of:

- How Infrastructure as Code (IaC) simplifies cloud deployments
- Building reusable cloud infrastructure using AWS CloudFormation
- Defining AWS resources through YAML templates
- Automating infrastructure provisioning instead of using ClickOps
- Understanding the CloudFormation stack lifecycle from creation to deletion
- Building repeatable, version-controlled cloud deployments

---

# Key Takeaways

- Learned Infrastructure as Code using AWS CloudFormation
- Built reusable cloud infrastructure using YAML
- Automated EC2 provisioning
- Understood CloudFormation stack lifecycle
- Reduced manual ClickOps
- Built repeatable cloud deployments
- Learned how AWS provisions infrastructure from code
