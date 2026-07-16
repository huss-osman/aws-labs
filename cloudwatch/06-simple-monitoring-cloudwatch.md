# Amazon CloudWatch Monitoring

![Cloud](https://img.shields.io/badge/Cloud-AWS-FF9900?logo=amazonaws&logoColor=white)
![Monitoring](https://img.shields.io/badge/Monitoring-CloudWatch-blue)
![AWS](https://img.shields.io/badge/AWS-EC2-orange)
![Service](https://img.shields.io/badge/Service-CPU%20Alarms-green)
![Observability](https://img.shields.io/badge/Observability-Metrics-red)

<p align="center">
  <img width="1000" alt="Architecture Diagram" src="https://github.com/user-attachments/assets/d1ec4ba6-4aad-421d-90df-ab4dc6e7f080" /> 
</p>

This project demonstrates infrastructure monitoring using Amazon CloudWatch by provisioning an Amazon EC2 instance and configuring a CPU Utilisation alarm. It monitors EC2 performance through CloudWatch metrics, automatically detects high CPU usage, and changes alarm states based on resource activity.

The goal was to understand how AWS monitoring and observability work through practical demonstrations covering CloudWatch metrics, alarms, CPU monitoring, infrastructure visibility, operational monitoring, and cloud resource management.

---

## Objective

The goal of this project was to:

- Learn Amazon CloudWatch
- Monitor EC2 performance
- Configure CPU Utilisation alarms
- Understand CloudWatch metrics
- Generate infrastructure metrics
- Monitor alarm state changes
- Practice cloud observability

---

## How It Works

1. Launch an Amazon EC2 instance.
2. Connect to the instance using SSH.
3. Install the stress package.
4. Create a CloudWatch CPU Utilisation alarm.
5. Generate CPU load using `stress -c 2`.
6. Observe the alarm transition to **ALARM**.
7. Stop the workload.
8. Observe the alarm return to **OK**.
9. Delete the alarm.
10. Terminate the EC2 instance.

---

# Creating the EC2 Instance

Launch a new Amazon EC2 instance that will be monitored using Amazon CloudWatch.

<p align="center">
  <img width="1000" alt="Launch Instance" src="https://github.com/user-attachments/assets/af9e401a-5d6f-4581-8963-dd6805661ca1" />
</p>

> [!NOTE]
> The EC2 instance is named **CloudWatchTest**, making it easier to identify throughout the monitoring demonstration.

<p align="center">
  <img width="1000" alt="Amazon Linux" src="https://github.com/user-attachments/assets/e54d6498-43fc-4a81-9513-d66ca6e91d66" />
</p>

> [!NOTE]
> **Amazon Linux 2023** was selected as the operating system, providing native integration with AWS services.

<p align="center">
  <img width="1000" alt="Instance Type" src="https://github.com/user-attachments/assets/34ae2416-df60-46b4-b6e3-69153e955876" />
</p>

> [!NOTE]
> A **t3.micro** instance type was selected for this demonstration.

<p align="center">
  <img width="1000" alt="Network Settings" src="https://github.com/user-attachments/assets/73314f9f-1dad-4aec-96fb-362e8033835d" />
</p>

> [!NOTE]
> The instance was deployed into the **default VPC** with a **public IPv4 address**. **EC2 Instance Connect** was used, so a key pair was not required.

<p align="center">
  <img width="1000" alt="Detailed Monitoring" src="https://github.com/user-attachments/assets/f93fa5a4-5c0a-46a3-aeb6-2a4c0254e736" />
</p>

> [!IMPORTANT]
> **Detailed CloudWatch Monitoring** was enabled, allowing EC2 metrics to be published at **1-minute intervals** instead of the standard 5-minute intervals.
>
> AWS notes that enabling detailed monitoring may incur additional charges.
>
> Learn more: https://aws.amazon.com/cloudwatch/

<p align="center">
  <img width="1000" alt="Launch Instance" src="https://github.com/user-attachments/assets/b124db81-b561-4d7d-92fe-5fc06e5e10f5" />
</p>

> [!NOTE]
> After reviewing the configuration, the EC2 instance was launched and AWS automatically began provisioning the required resources.

<p align="center">
  <img width="1000" alt="Running Instance" src="https://github.com/user-attachments/assets/154c575d-e8a1-47e5-9b6f-b8ea5ad86327" />
</p>

> [!NOTE]
> ✅ The EC2 instance successfully entered the **Running** state and was ready to publish performance metrics to Amazon CloudWatch.

## Deployment Summary

- **Amazon Linux 2023** was selected as the operating system.
- A **t3.micro** instance type was provisioned.
- The instance was deployed into the **default VPC** with a **public IPv4 address**.
- **EC2 Instance Connect** was used, so a key pair was not required.
- **Detailed CloudWatch Monitoring** was enabled to publish metrics at **1-minute intervals**.
- AWS notes that enabling detailed monitoring may incur **additional CloudWatch charges**.
- The instance successfully entered the **Running** state and was ready for monitoring.
  
---

# Creating the CloudWatch Alarm

Navigate to **Amazon CloudWatch → Alarms** and create a new alarm.

<p align="center">
  <img width="1000" alt="Create Alarm" src="images/aws_cloudwatch_1.png" />
</p>

> [!NOTE]
> A new CloudWatch alarm was created to monitor the EC2 instance CPU utilisation.

---

# Selecting the Metric

Select the metric that the CloudWatch alarm will monitor.

<p align="center">
  <img width="1000" alt="Select Metric" src="images/aws_cloudwatch_2.png" />
</p>

<p align="center">
  <img width="1000" alt="EC2 Metrics" src="images/aws_cloudwatch_3.png" />
</p>

<p align="center">
  <img width="1000" alt="Per Instance Metrics" src="images/aws_cloudwatch_4.png" />
</p>

<p align="center">
  <img width="1000" alt="CPUUtilization Metric" src="images/aws_cloudwatch_5.png" />
</p>

> [!NOTE]
> The **CPUUtilization** metric for the EC2 instance was selected as the metric to monitor.

---

# Configuring the Alarm

Configure the alarm threshold and evaluation condition.

<p align="center">
  <img width="1000" alt="Alarm Configuration" src="images/aws_cloudwatch_6.png" />
</p>

> [!NOTE]
> Configuration included:
>
> - Metric: **CPUUtilization**
> - Threshold Type: **Static**
> - Condition: **Greater than or equal to**
> - Threshold: **15%**

---

# Configuring Alarm Actions

Configure how CloudWatch responds when the alarm changes state.

<p align="center">
  <img width="1000" alt="Alarm Actions" src="images/aws_cloudwatch_7.png" />
</p>

> [!IMPORTANT]
> No Amazon SNS notification topic was configured for this demonstration. The objective was to understand CloudWatch monitoring and alarm state transitions rather than automated notifications.

---

# Naming the Alarm

Provide a descriptive name for the CloudWatch alarm.

<p align="center">
  <img width="1000" alt="Alarm Name" src="images/aws_cloudwatch_8.png" />
</p>

> [!NOTE]
> The alarm was named **cloudwatchtestHIGHCPU** for easy identification.

---

# Alarm Successfully Created

Once created, CloudWatch immediately began evaluating the selected metric.

<p align="center">
  <img width="1000" alt="Alarm Created" src="images/aws_cloudwatch_9.png" />
</p>

The alarm initially displayed:

```text
INSUFFICIENT_DATA
```

> [!NOTE]
> This is the expected initial state after creating a CloudWatch alarm. CloudWatch waits until enough metric data has been collected before evaluating whether the alarm should transition to **OK** or **ALARM**.

---

# Connecting to the EC2 Instance

Connect to the running EC2 instance using **EC2 Instance Connect**.

<p align="center">
  <img width="1000" alt="EC2 Instance Connect" src="images/aws_cloudwatch_10.png" />
</p>

> [!NOTE]
> EC2 Instance Connect provided browser-based shell access without requiring an SSH key pair.

---

# Installing the Stress Package

Install the **stress** package used to generate CPU utilisation.

<p align="center">
  <img width="1000" alt="Install Stress" src="images/aws_cloudwatch_11.png" />
</p>

```bash
sudo yum install stress -y
```

> [!NOTE]
> The **stress** utility generates synthetic CPU workloads for testing monitoring and alarm behaviour.

---

# Reviewing the Stress Utility

Verify the installation by displaying the available command options.

<p align="center">
  <img width="1000" alt="Stress Help" src="images/aws_cloudwatch_12.png" />
</p>

```bash
stress --help
```

---

# Generating CPU Utilisation

Run the stress utility to increase CPU utilisation.

<p align="center">
  <img width="1000" alt="Run Stress" src="images/aws_cloudwatch_13.png" />
</p>

```bash
stress -c 2 -t 3600
```

> [!NOTE]
> Two CPU workers were started to generate sustained CPU utilisation for one hour, allowing CloudWatch to detect the increased load.

---

# EC2 Instance Terminated

The EC2 instance entered the **Shutting-down** state before becoming permanently **Terminated**.

<p align="center">
  <img width="1000" alt="Instance Terminated" src="images/instance-terminated.png" />
</p>

---

# Demonstration

The complete monitoring workflow is shown below.

<!-- Demo video -->

The walkthrough demonstrates:

- Reviewing the EC2 instance
- Reviewing the CloudWatch alarm
- Reviewing CPU utilisation metrics
- Reviewing alarm state changes
- Understanding the monitoring workflow

---

# Cleanup

The cleanup process is shown below.

<!-- Cleanup video -->

The walkthrough demonstrates:

- Deleting the CloudWatch alarm
- Terminating the EC2 instance
- Removing all deployed resources

---

# Why I Built It

I wanted a hands-on understanding of:

- Monitoring AWS infrastructure using CloudWatch
- Creating alarms based on CloudWatch metrics
- Observing infrastructure performance in real time
- Understanding alarm state transitions
- Building operational visibility into cloud environments
- Practising cloud monitoring and observability

---

# Key Takeaways

- Learned Amazon CloudWatch monitoring
- Configured CPU Utilisation alarms
- Generated infrastructure metrics
- Monitored real-time resource performance
- Understood CloudWatch alarm lifecycle
- Improved cloud observability
- Gained hands-on AWS monitoring experience
