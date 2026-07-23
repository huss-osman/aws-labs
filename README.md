<p align="center">
  <img width="450" style="margin-left: 40px;" alt="AWS Banner" src="https://github.com/user-attachments/assets/0b90e1a3-8023-4ee4-95e4-bb7f6d7b143e" />
</p>

# AWS Labs

![Cloud](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazonaws&logoColor=white)
![IaC](https://img.shields.io/badge/IaC-CloudFormation-blue)
![Automation](https://img.shields.io/badge/Automation-Infrastructure%20as%20Code-green)
![Projects](https://img.shields.io/badge/Projects-6-darkgreen)
![Practice](https://img.shields.io/badge/Practice-Hands--on-orange)

This repository documents my AWS labs covering cloud infrastructure, networking, security, scalability, and workflows.

Each assignment focuses on building practical AWS solutions through real-world cloud architectures, deployment workflows, troubleshooting, production-style environments, and industry-standard cloud engineering practices.

The focus of this repository is how AWS services integrate to build secure cloud infrastructure through projects.

---

## Learning Objectives

By working through these demos, I aim to:

- Learn AWS through practical deployments
- Understand Infrastructure as Code using AWS CloudFormation
- Automate cloud infrastructure
- Apply AWS best practices
- Build repeatable cloud environments
- Gain hands-on experience with AWS services

---

## Projects

### **[CloudFormation EC2 Deployment](./cloudformation/01-ec2-instance/)**

Provisioned an Amazon EC2 instance, Security Group, IAM Role, and IAM Instance Profile using an AWS CloudFormation template written in YAML.
Demonstrated Infrastructure as Code through automated stack creation, resource provisioning, and complete infrastructure lifecycle management.
Built through hands-on cloud automation, Infrastructure as Code workflows, YAML development, and AWS deployment practices.

<br>

<p align="center">
  <img width="850" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/0ed4daa0-60c0-40ec-9b35-ed61677f9ef4" />
</p>

<br>

<p align="center">
  <a href="./cloudformation/01-ec2-instance/"><strong>➡️ View Project</strong></a>
</p>

---

### **[VPC & Networking](./vpc/02-vpc-networking.md)**

Designed and deployed a AWS VPC with public and private subnets, Internet and NAT Gateways, route tables, Security Groups, a Bastion Host, and EC2 instances.
Configured secure network segmentation, internet access, SSH connectivity through a Bastion Host, and monitored infrastructure using CloudWatch.
Built through hands-on cloud networking, infrastructure design, routing configuration, access management, and AWS deployment practices.

<br>

<p align="center">
<img width="750" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/4c233bac-f9fc-4731-815e-01ae852d64df" />
</p>

<br>

<p align="center">
  <a href="./vpc/02-vpc-networking.md/"><strong>➡️ View Project</strong></a>
</p>

---

### **[Application Load Balancer](./load-balancer/03-application-load-balancer.md)**

Provisioned an Application Load Balancer with multiple Amazon EC2 instances distributed across Availability Zones using AWS networking services.
Implemented load balancing, target groups, health checks, Security Groups, and scalable traffic distribution across web servers.
Built through hands-on cloud networking, high-availability architecture, infrastructure deployment, and AWS load balancing practices.

<br>

<p align="center">
  <img width="850" alt="Application Load Balancer Architecture" src="https://github.com/user-attachments/assets/025ca542-343f-45ed-8b71-e1146bdfeb90" /> 
</p>

<br>

<p align="center">
  <a href="./load-balancer/03-application-load-balancer.md/"><strong>➡️ View Project</strong></a>
</p>

---

### **[S3 Static Website + CloudFront CDN](./s3/04-s3-static-website-cloudfront.md)**

Provisioned a static website using Amazon S3, CloudFront, Route 53, and ACM to deliver secure content over HTTPS.
Implemented global content delivery, DNS routing, SSL/TLS encryption, caching, and automated website deployment using AWS services.
Built through hands-on cloud hosting, CDN configuration, DNS management, and modern web infrastructure practices.

<br>

<p align="center">
  <img width="850" alt="S3 CloudFront Architecture" src="images/s3-cloudfront-architecture.png" />
</p>

<br>

<p align="center">
  <a href="./s3/03-s3-static-website-cloudfront.md"><strong>➡️ View Project</strong></a>
</p>

---

### **[Serverless REST API](./05-serverless-api-lambda-api-gateway.md)**

Provisioned a serverless REST API using Amazon API Gateway, AWS Lambda, DynamoDB, IAM, and CloudWatch.
Implemented event-driven application workflows, least-privilege IAM permissions, data persistence, monitoring, and API request handling.
Built through hands-on serverless development, cloud automation, Infrastructure as Code concepts, and AWS deployment practices.

<br>

<p align="center">
  <img width="850" alt="Serverless Architecture" src="images/serverless-api-architecture.png" />
</p>

<br>

<p align="center">
  <a href="./serverless/05-serverless-api/"><strong>➡️ View Project</strong></a>
</p>

---

### **[Simple Monitoring with CloudWatch](./monitoring/06-simple-monitoring-cloudwatch/)**

Provisioned an Amazon EC2 instance and configured an Amazon CloudWatch CPU Utilisation alarm to monitor instance performance.
Implemented CloudWatch metrics, alarm thresholds, performance monitoring, and real-time notifications using AWS monitoring services.
Built through hands-on cloud monitoring, infrastructure observability, performance analysis, and AWS operational best practices.

<br>

<p align="center">
  <img width="850" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/d1ec4ba6-4aad-421d-90df-ab4dc6e7f080" /> 
</p>

<br>

<p align="center">
  <a href="./cloudwatch/06-simple-monitoring-cloudwatch.md/"><strong>➡️ View Project</strong></a>
</p>

---

## Resources

- [AWS Documentation](https://docs.aws.amazon.com/)
- [AWS Free Tier](https://aws.amazon.com/free/)
- [AWS Pricing Calculator](https://calculator.aws/#/)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/reference/)
