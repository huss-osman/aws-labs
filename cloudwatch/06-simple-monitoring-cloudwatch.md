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

Launch a new Amazon EC2 instance using the default VPC with a public IPv4 address.

<p align="center">
  <img width="1000" alt="EC2 Instance" src="https://github.com/user-attachments/assets/af9e401a-5d6f-4581-8963-dd6805661ca1" /> 
</p>

<p align="center">
  <img width="1000" alt="EC2 Instance" src="https://github.com/user-attachments/assets/e54d6498-43fc-4a81-9513-d66ca6e91d66" /> 
</p>

<p align="center">
  <img width="1000" alt="EC2 Instance" src="https://github.com/user-attachments/assets/34ae2416-df60-46b4-b6e3-69153e955876"" /> 
</p>

Configuration included:

- Amazon Linux 2023
- t3.micro
- Default VPC
- Public IPv4

---

# Connecting to the EC2 Instance

Connect to the EC2 instance using SSH.

<p align="center">
  <img width="1000" alt="SSH Connection" src="images/ssh-connection.png" />
</p>

---

# Installing the Stress Package

Install the **stress** package used to generate CPU utilisation.

<p align="center">
  <img width="1000" alt="Installing Stress" src="images/install-stress.png" />
</p>

```bash
sudo yum install stress -y
```

---

# Creating the CloudWatch Alarm

Create a new CloudWatch alarm based on the EC2 **CPUUtilization** metric.

<p align="center">
  <img width="1000" alt="Create Alarm" src="images/create-alarm.png" />
</p>

---

# Configuring the Alarm

Configure the alarm to trigger whenever CPU utilisation exceeds **15%**.

<p align="center">
  <img width="1000" alt="Alarm Configuration" src="images/alarm-configuration.png" />
</p>

Configuration included:

- Metric: CPUUtilization
- Statistic: Average
- Threshold: Greater than 15%
- Evaluation Period

---

# Alarm Successfully Created

After creation, the alarm entered the monitoring state.

<p align="center">
  <img width="1000" alt="Alarm Created" src="images/alarm-created.png" />
</p>

The alarm initially displayed:

```text
OK
```

or

```text
INSUFFICIENT_DATA
```

while CloudWatch collected metrics.

---

# Generating CPU Utilisation

Generate CPU load using the **stress** utility.

<p align="center">
  <img width="1000" alt="Running Stress" src="images/stress-command.png" />
</p>

```bash
stress -c 2
```

---

# Alarm Triggered

As CPU utilisation exceeded the configured threshold, CloudWatch automatically changed the alarm state.

<p align="center">
  <img width="1000" alt="Alarm State" src="images/alarm-triggered.png" />
</p>

The alarm transitioned to:

```text
ALARM
```

---

# Monitoring CPU Metrics

CloudWatch visualised the increased CPU utilisation using real-time metrics.

<p align="center">
  <img width="1000" alt="CPU Metrics" src="images/cpu-metrics.png" />
</p>

The CPU utilisation graph showed usage increasing above the configured alarm threshold.

---

# Alarm Returns to OK

Stop the workload by pressing:

```text
Ctrl + C
```

Once CPU utilisation decreased, CloudWatch automatically returned the alarm to the **OK** state.

<p align="center">
  <img width="1000" alt="Alarm OK" src="images/alarm-ok.png" />
</p>

---

# Deleting the Alarm

After testing completed, delete the CloudWatch alarm.

<p align="center">
  <img width="1000" alt="Delete Alarm" src="images/delete-alarm.png" />
</p>

---

# Terminating the EC2 Instance

Terminate the EC2 instance used during the demonstration.

<p align="center">
  <img width="1000" alt="Terminate EC2" src="images/terminate-instance.png" />
</p>

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
