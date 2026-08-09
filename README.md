# ☁️ AWS CloudWatch & SNS — Automated EC2 Monitoring

> **Real-Time CPU Monitoring & Automated Email Alerting using AWS**

![AWS](https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws)
![EC2](https://img.shields.io/badge/Amazon-EC2-blue?style=for-the-badge&logo=amazonec2)
![CloudWatch](https://img.shields.io/badge/Amazon-CloudWatch-purple?style=for-the-badge&logo=amazonaws)
![SNS](https://img.shields.io/badge/Amazon-SNS-red?style=for-the-badge&logo=amazonaws)
![Linux](https://img.shields.io/badge/Linux-Server-black?style=for-the-badge&logo=linux)

---

## 🚀 Project Overview

This project demonstrates a real-time AWS monitoring and automated alerting solution using:

- Amazon EC2
- Amazon CloudWatch
- CloudWatch Alarms
- Amazon SNS
- Linux
- CPU Stress Testing

The EC2 instance is continuously monitored by CloudWatch. When CPU utilization crosses the configured threshold, a CloudWatch Alarm is triggered and Amazon SNS automatically sends an email notification to the administrator.

---

## 🎯 Problem Statement

High CPU utilization can reduce application performance.

Manual server monitoring is time-consuming, delayed alerts can affect response time, and downtime can impact users and business operations.

This project provides an automated monitoring and notification solution.

---

## 💡 Solution

The monitoring workflow is:

```text
EC2 Instance
     ↓
CPU Monitoring
     ↓
CloudWatch
     ↓
CloudWatch Alarm
     ↓
SNS Topic
     ↓
Email Notification
     ↓
Administrator Action

```
---

## 📊 Project Presentation

[📥 Download/View Project PPT](https://github.com/darshanpatil8799/CloudWatch-SNS/edit/main/CloudWatch-SNS)

---

## 📖 Implementation Steps

1️⃣ Create an Amazon EC2 Instance

2️⃣ Configure Amazon CloudWatch Monitoring

3️⃣ Create a CloudWatch Alarm

4️⃣ Set CPU Utilization Threshold to 40%

5️⃣ Create an Amazon SNS Topic

6️⃣ Configure Email Subscription

7️⃣ Confirm SNS Email Subscription

8️⃣ Generate CPU Load Using Stress Testing

9️⃣ Trigger the CloudWatch Alarm

🔟 Receive Automated Email Notification

---

## 🎯 Learning Outcomes

- Amazon EC2 Monitoring
- Amazon CloudWatch
- CloudWatch Alarms
- CPU Utilization Monitoring
- Amazon SNS
- Email Notifications
- CPU Stress Testing
- AWS Monitoring & Observability
- Automated Alerting

---

## 🌟 Future Enhancements

- Monitor Memory & Disk Utilization
- Create CloudWatch Dashboards
- Configure SMS Notifications
- Integrate Slack/Teams Alerts
- Implement AWS Lambda Automated Remediation
- Configure Auto Scaling
- Integrate Monitoring with CI/CD
