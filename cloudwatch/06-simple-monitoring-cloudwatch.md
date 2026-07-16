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
  <img width="1000" alt="Create Alarm" src="https://github.com/user-attachments/assets/e90b04c3-57b5-42c0-80ef-9004ae61d139" /> 
</p>

> [!NOTE]
> A new CloudWatch alarm was created to monitor the EC2 instance CPU utilisation.

---

# Selecting the Metric

Select the metric that the CloudWatch alarm will monitor.

<p align="center">
  <img width="1000" alt="EC2 Metrics" src="https://github.com/user-attachments/assets/a3e5fc77-42fa-471d-86f7-e08af3935c56" /> 
</p>

<p align="center">
  <img width="1000" alt="Per Instance Metrics" src="https://github.com/user-attachments/assets/acc17310-286d-4e03-b932-18db91241e57" />
</p>

<p align="center">
  <img width="1000" alt="CPUUtilization Metric" src="https://github.com/user-attachments/assets/14294230-332b-4660-a8d0-811d73b7e780" /> 
</p>

> [!NOTE]
> The **CPUUtilization** metric for the EC2 instance was selected as the metric to monitor.

---

# Configuring the Alarm

Configure the alarm threshold and evaluation condition.

<p align="center">
  <img width="1000" alt="Alarm Configuration" src="https://github.com/user-attachments/assets/b262c0d6-55a9-4fb4-9ae8-f670b99356f4" />
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
  <img width="1000" alt="Alarm Actions" src="https://github.com/user-attachments/assets/0722096d-48ea-499b-bb47-75c804e899b1" /> 
</p>

> [!IMPORTANT]
> No Amazon SNS notification topic was configured for this demonstration. The objective was to understand CloudWatch monitoring and alarm state transitions rather than automated notifications.

---

# Naming the Alarm

Provide a descriptive name for the CloudWatch alarm.

<p align="center">
  <img width="1000" alt="Alarm Name" src="https://github.com/user-attachments/assets/5fcf39a2-8f67-49d0-a064-e1578ad13ad0" /> 
</p>

> [!NOTE]
> The alarm was named **cloudwatchtestHIGHCPU** for easy identification.

---

# Alarm Successfully Created

Once created, CloudWatch immediately began evaluating the selected metric.

<p align="center">
  <img width="1000" alt="Alarm Created" src="https://github.com/user-attachments/assets/7542a49d-366f-4ac0-95c3-2e283d943de8" /> 
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
  <img width="1000" alt="EC2 Instance Connect" src="https://github.com/user-attachments/assets/2fc23244-21ef-4a14-a08b-b898f17b473f" /> 
</p>

> [!NOTE]
> EC2 Instance Connect provided browser-based shell access without requiring an SSH key pair.

---

# Installing the Stress Package

Install the **stress** package used to generate CPU utilisation.

<p align="center">
  <img width="1000" alt="Install Stress" src="https://github.com/user-attachments/assets/054468b6-7237-47e0-bfa8-04661173c4a8" /> 
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
  <img width="1000" alt="Stress Help" src="https://github.com/user-attachments/assets/ba142e44-bceb-4d70-9129-0990d24d9545" /> 
</p>

```bash
stress --help
```

---

# Generating CPU Utilisation

Run the stress utility to increase CPU utilisation.

<p align="center">
  <img width="1000" alt="Run Stress" src="https://github.com/user-attachments/assets/629f7ca5-c34a-41e9-a41b-2b87339d01c3" /> 
</p>

```bash
stress -c 2 -t 3600
```

> [!NOTE]
> Two CPU workers were started to generate sustained CPU utilisation for one hour, allowing CloudWatch to detect the increased load.

---

# Monitoring the Alarm State

CloudWatch continued collecting CPU metrics while the alarm remained in the **OK** state.

<p align="center">
  <img width="1000" alt="Alarm OK" src="https://github.com/user-attachments/assets/6db5b253-5c6e-4416-a157-b77d416ffe05" /> 
</p>

> [!NOTE]
> Initially, CPU utilisation remained below the configured **15%** threshold, so the alarm stayed in the **OK** state while CloudWatch continued evaluating incoming metrics.

---

# Alarm Triggered

As the stress workload increased CPU utilisation, CloudWatch detected that the configured threshold had been exceeded.

<p align="center">
  <img width="1000" alt="Alarm Triggered" src="https://github.com/user-attachments/assets/976c866c-0916-4886-b3ce-14ad14c4a7b0" /> 
</p>

> [!IMPORTANT]
> Once CPU utilisation exceeded **15%**, CloudWatch automatically transitioned the alarm from **OK** to **ALARM**. The CPU graph also showed the utilisation spike crossing the configured threshold.

---

# Stopping the Workload

After verifying the alarm had triggered, the stress process was stopped.

<p align="center">
  <img width="1000" alt="Stopping Stress" src="https://github.com/user-attachments/assets/a830d71b-e0c3-430b-9edb-4e29b67d323a" /> 
</p>

```bash
Ctrl + Z
```

> [!NOTE]
> Stopping the stress process allowed CPU utilisation to gradually decrease back to normal operating levels.

---

# Alarm Returned to OK

As CPU utilisation dropped below the configured threshold, CloudWatch automatically updated the alarm state.

<p align="center">
  <img width="1000" alt="Alarm Returned OK" src="https://github.com/user-attachments/assets/5044d857-9dcd-4c7f-9d6c-3228cb322d64" />
</p>

> [!NOTE]
> Once sufficient metric data confirmed CPU utilisation had returned below **15%**, the alarm automatically transitioned back to the **OK** state.

---

# Deleting the Alarm

After completing the monitoring demonstration, the CloudWatch alarm was removed.

<p align="center">
  <img width="1000" alt="Delete Alarm" src="https://github.com/user-attachments/assets/1c07bdc7-f45f-498b-986f-a347a1adfb33" /> 
</p>

> [!NOTE]
> Deleting the alarm stops CloudWatch from continuing to evaluate the selected metric, although the EC2 instance continues publishing metrics while it remains running.

---

# Terminating the EC2 Instance

With testing complete, the EC2 instance was terminated.

<p align="center">
  <img width="1000" alt="Terminate EC2" src="https://github.com/user-attachments/assets/44893b43-f65b-4620-a468-4750394b03b5" /> 
</p>

> [!NOTE]
> The EC2 instance was terminated to prevent unnecessary AWS charges after the demonstration had finished.

---

# EC2 Instance Terminated

AWS completed the instance termination process.

<p align="center">
  <img width="1000" alt="Instance Terminated" src="https://github.com/user-attachments/assets/a47f6883-31d0-4fc0-9f28-7f8aa9d460ce" />
</p>

> [!NOTE]
> The instance successfully entered the **Terminated** state and was no longer consuming compute resources.

---

# Removing the Security Group

The custom Security Group created for the demonstration was also removed.

<p align="center">
  <img width="1000" alt="Delete Security Group" src="https://github.com/user-attachments/assets/23c227c7-a430-4ac9-9777-221c0c34f364" />
</p>

> [!NOTE]
> After the EC2 instance was terminated, the custom **cloudwatchSG** Security Group was deleted to complete the infrastructure cleanup and avoid leaving unused AWS resources.

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
