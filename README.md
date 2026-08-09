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
