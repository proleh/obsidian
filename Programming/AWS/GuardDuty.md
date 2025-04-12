---
creation date: 02-04-2025
modification date: Wednesday 2nd April 2025 22:38:45
---
Rel: [[Programming/AWS/AWS]]
Tags: #aws


- **Intelligent Threat discovery** to protect your AWS Account
- Uses **Machine Learning algorithms**, anomaly detection, 3rd party data
- **One click to enable** (30 days trial), no need to install software
- **Input data includes:**
    - **CloudTrail Events Logs** – unusual API calls, unauthorized deployments
        - _CloudTrail Management Events_ – create VPC subnet, create trail, …
        - _CloudTrail S3 Data Events_ – get object, list objects, delete object, …
    - **VPC Flow Logs** – unusual internal traffic, unusual IP address
    - **DNS Logs** – compromised EC2 instances sending encoded data within DNS queries
    - **Optional Features** – EKS Audit Logs, RDS & Aurora, EBS, Lambda, S3 Data Events…
- Can setup **EventBridge rules** to be notified in case of findings
- EventBridge rules can target **AWS Lambda** or **SNS**
- **Can protect against CryptoCurrency attacks** (has a dedicated “finding” for it)