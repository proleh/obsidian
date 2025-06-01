---
creation date: 30-03-2025
modification date: Sunday 30th March 2025 07:26:04
---
- Provides metrics for each service in AWS.
- Can create Cloudwatch Dashboard of Metrics.
- Can create Alarms to trigger notification for any metric
	- Auto Scaling
	- EC2 instance actions(stop, terminate, reboot)
	- SNS notifications
- etc.
Billing Alarm available only in us-east-1


- CloudWatch Logs
	- Need to install CloudWatch Logs agent to EC2 instance or on premise service to collect logs.
	- Need to configure IAM policy to allow it write logs.

Rel: [[Programming/AWS/AWS]]
Tags: #aws
