<div align="center">

# 📊 AWS EC2 CPU Utilization Monitoring & Email Alerts

### Monitor server health with Amazon CloudWatch and get notified through Amazon SNS

**Hands-on AWS Project | By Darshan Patil**

![AWS](https://img.shields.io/badge/Cloud-AWS-orange?logo=amazonaws&logoColor=white)
![EC2](https://img.shields.io/badge/Compute-Amazon%20EC2-FF9900?logo=amazonec2&logoColor=white)
![CloudWatch](https://img.shields.io/badge/Monitoring-Amazon%20CloudWatch-BC3A2B?logo=amazoncloudwatch&logoColor=white)
![SNS](https://img.shields.io/badge/Notifications-Amazon%20SNS-7AA116?logo=amazonsimple&logoColor=white)
![Status](https://img.shields.io/badge/Project-Hands--On-blue)

</div>

---

## 📌 Project Overview

This project demonstrates how to monitor CPU utilization on an Amazon EC2 instance using **Amazon CloudWatch** and send an email notification through **Amazon Simple Notification Service (SNS)** when CPU usage crosses a configured threshold.

Think of CloudWatch as a security guard monitoring a server. When CPU utilization becomes too high, a CloudWatch alarm triggers an SNS notification so the administrator can respond quickly.

## 🎯 Problem Statement

High CPU usage can reduce application performance, manual monitoring takes time, delayed alerts can slow incident response, and server downtime can affect users and business operations.

## 💡 Solution

1. Deploy a server using Amazon EC2.
2. Monitor CPU utilization with Amazon CloudWatch.
3. Configure a CloudWatch alarm with a predefined CPU threshold.
4. Connect the alarm to an Amazon SNS topic.
5. Subscribe an email address to the topic and confirm the subscription.
6. Generate CPU load for testing and verify that the alert email arrives.

## 🧰 AWS Services Used

| Service | Role in this project |
|---|---|
| **Amazon EC2** | Runs the server |
| **Amazon CloudWatch** | Monitors CPU utilization and evaluates the alarm threshold |
| **Amazon SNS** | Sends an email notification when the alarm publishes a message |

## 🏗️ Architecture

```text
                  🖥️ Amazon EC2 Instance
                           |
                           | CPU Utilization Metrics
                           v
                 📊 Amazon CloudWatch
                           |
                    CPU threshold crossed
                           |
                           v
                    🚨 CloudWatch Alarm
                           |
                           v
                     📣 Amazon SNS Topic
                           |
                           v
                    📧 Email Notification
                           |
                           v
                    👨‍💻 Administrator
```

## ⚙️ Implementation Steps

### 1. Launch an EC2 instance
- Sign in to the AWS Management Console.
- Choose the required AWS Region and open **EC2**.
- Launch an instance with a suitable Amazon Machine Image and instance type.
- Configure networking and secure access based on your requirements.
- Wait for the instance to reach the running state and pass status checks.

### 2. Configure a CloudWatch alarm
- From the EC2 instance options, open **Monitor and troubleshoot → Manage CloudWatch alarms** (console labels may vary).
- Create or configure an alarm for the **CPUUtilization** metric.
- Set the threshold to **40%**, as used in this project guide.
- Choose an evaluation period and datapoints that suit your test.
- Configure the alarm action to publish a notification to an SNS topic.

### 3. Create an SNS email subscription
- Open **Amazon SNS → Topics**.
- Select the SNS topic associated with the alarm, or create one if needed.
- Choose **Create subscription**.
- Set **Protocol** to `Email` and enter your email address as the endpoint.
- Create the subscription.
- Open the confirmation email from AWS and confirm the subscription.

### 4. Generate CPU load for testing
Connect to the EC2 instance using your configured, secure access method. On a compatible Amazon Linux system, install the stress-testing tool if it is available in the configured repositories:

```bash
sudo yum update -y
sudo yum install stress -y
```

Generate a CPU load for a short, controlled test:

```bash
stress --cpu9
```

The exact package manager and package availability can vary by Amazon Linux version. Use a test workload appropriate for your instance size and stop it after validation.

### 5. Verify the notification
- Open the CPU utilization graph in CloudWatch.
- Observe whether CPU utilization crosses the configured threshold.
- Check the alarm state and allow for the configured evaluation period.
- Confirm that an email notification arrives at the subscribed address.

> **Note:** CloudWatch alarms evaluate metrics over configured periods, so email delivery is not necessarily instantaneous. A notification is sent only when the alarm action and SNS subscription are configured correctly and the alarm transitions into a state that triggers the action.

## 🧪 Validation Checklist

- [ ] EC2 instance is running.
- [ ] CloudWatch shows CPU utilization metrics.
- [ ] Alarm threshold is configured (40% for this project).
- [ ] SNS email subscription is confirmed.
- [ ] Test workload raises CPU utilization as expected.
- [ ] Alarm changes state and the email notification is received.

## 🔐 Security & Cost Awareness

- Use IAM roles and least-privilege permissions where possible.
- Secure remote access; avoid opening administration ports to the entire internet.
- Never commit passwords, private keys, or AWS credentials to GitHub.
- EC2 compute, CloudWatch features, SNS notifications, and related resources may incur charges depending on your account, Region, usage, and current AWS pricing.
- Stop or terminate test resources when they are no longer needed, and review alarm/topic resources before finishing.

## 💡 Key Learnings

- Understanding EC2 CPU utilization metrics.
- Creating and configuring CloudWatch alarms.
- Integrating CloudWatch with SNS.
- Confirming an SNS email subscription.
- Testing an alert workflow by generating controlled CPU load.
- Improving awareness of monitoring, incident response, and server reliability.

```text
.
├── README.md
└── screenshots/
    ├── ec2-instance.png
    ├── cloudwatch-alarm.png
    ├── cpu-utilization-graph.png
    ├── sns-email-subscription.png
    └── email-alert.png
```
```

## 🚀 Future Enhancements

- Create CloudWatch dashboards for multiple instances.
- Add alarms for memory and disk metrics using an appropriate monitoring agent.
- Route notifications to additional operational channels.
- Explore automated recovery or scaling actions where suitable.
- Document incident response steps for high CPU utilization.

## 👨‍💻 Author

**Darshan Patil**  
Cloud & DevOps Learner

- GitHub: [Darshan Patil](https://github.com/darshanpatil8799/darshanpatil8799)
- LinkedIn: [Darshan Patil](www.linkedin.com/in/darshan-devops)
---

<div align="center">

### ☁️ Monitor. Alert. Respond. Improve.

**Building practical AWS Cloud and DevOps skills, one project at a time.**

</div>
