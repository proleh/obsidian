---
creation date: 12-04-2025
modification date: Saturday 12th April 2025 08:03:05
---
Rel: [[Programming/AWS/AWS]]
Tags: #aws

### AWS has 4 pricing models:
- **Pay as you go**: pay for what you use, remain agile, responsive, meet scale demands
- **Save when you reserve**: minimize risks, predictably manage budgets, comply with long-term requirements  
    • Reservations are available for EC2 Reserved Instances, DynamoDB Reserved Capacity, ElastiCache Reserved Nodes, RDS Reserved Instance, Redshift Reserved Nodes
- **Pay less by using more**: volume-based discounts
- **Pay less as AWS grows**

### Free services & free tier in AWS
- IAM
- VPC
- Consolidated Billing
- Elastic Beanstalk
- CloudFormation
- Auto Scaling Groups
- Free Tier: [https://aws.amazon.com/free/](https://aws.amazon.com/free/)  
    • EC2 t2.micro instance for a year  
    • S3, EBS, ELB, AWS Data transfer
⚠️ **You do pay for the resources created**

### **Compute Pricing – EC2**
- **On-demand instances**:  
    • Minimum of 60s  
    • Pay per second (Linux/Windows) or per hour (other)
    
- **Reserved instances**:  
    • Up to 75% discount compared to On-demand on hourly rate  
    • 1- or 3-years commitment  
    • All upfront, partial upfront, no upfront
    
- **Spot instances**:  
    • Up to 90% discount compared to On-demand on hourly rate  
    • Bid for unused capacity
    
- **Dedicated Host**:  
    • On-demand  
    • Reservation for 1 year or 3 years commitment
    
- **Savings plans** as an alternative to save on sustained usage

### **Compute Pricing – Lambda & ECS**
- **Lambda**:  
    • Pay per call  
    • Pay per duration
    
- **ECS**:  
    • EC2 Launch Type Model: No additional fees, you pay for AWS resources stored and created in your application
    
- **Fargate**:  
    • Fargate Launch Type Model: Pay for vCPU and memory resources allocated to your applications in your containers

### **Storage Pricing – S3**
- **Storage class**: S3 Standard, S3 Infrequent Access, S3 One-Zone IA, S3 Intelligent Tiering, S3 Glacier and S3 Glacier Deep Archive
- Number and size of objects: Price can be tiered (based on volume)
- Number and type of requests
- Data transfer OUT of the S3 region
- S3 Transfer Acceleration
- Lifecycle transitions
- Similar service: EFS (pay per use, has infrequent access & lifecycle rules)

### **Storage Pricing – EBS**
- Volume type (based on performance)
- Storage volume in GB per month **provisioned**
- **IOPS**:  
    • General Purpose SSD: Included  
    • Provisioned IOPS SSD: Provisioned amount in IOPS  
    • Magnetic: Number of requests
- **Snapshots**:  
    • Added data cost per GB per month
- **Data transfer**:  
    • Outbound data transfer are tiered for volume discounts  
    • Inbound is free
    
### **Database Pricing – RDS**
- Per hour billing
- **Database characteristics**:  
    • Engine  
    • Size  
    • Memory class
- **Purchase type**:  
    • On-demand  
    • Reserved instances (1 or 3 years) with optional up-front
- **Backup Storage**: There is no additional charge for backup storage up to 100% of your total database storage for a region.
- Additional storage (per GB per month)
- Number of input and output requests per month
- **Deployment type** (storage and I/O are variable):  
    • Single AZ  
    • Multiple AZs
- **Data transfer**:  
    • Outbound data transfer are tiered for volume discounts  
    • Inbound is free

### **Content Delivery – CloudFront**

- Pricing is different across different geographic regions
- Aggregated for each edge location, then applied to your bill
- Data Transfer Out (volume discount)
- Number of HTTP/HTTPS requests

### **Savings Plan**
- Commit a certain $ amount per hour for 1 or 3 years
- Easiest way to setup long-term commitments on AWS

**EC2 Savings Plan**  
• Up to 72% discount compared to On-Demand  
• **Commit to usage of individual instance families in a region** (e.g., m5)  
• Regardless of AZ, size (m5.xl to m5.4xl), OS (Linux/Windows)  
• All upfront, partial upfront, no upfront

**Compute Savings Plan**  
• Up to 66% discount compared to On-Demand  
• Regardless of **Family, Region**, size, OS, tenancy, **compute option**  
• Compute Options: EC2, Fargate, Lambda

**Machine Learning Savings Plan**: SageMaker
- Setup from the AWS Cost Explorer console