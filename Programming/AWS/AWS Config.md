---
creation date: 02-04-2025
modification date: Wednesday 2nd April 2025 22:44:10
---
Rel: [[Programming/AWS/AWS]]
Tags: #aws


- Helps with **auditing and recording compliance** of your AWS resources
- Helps **record configurations and changes over time**
- Possibility of storing the configuration data into **S3** (analyzed by **Athena**)
- **Questions that can be solved by AWS Config:**
    - Is there unrestricted SSH access to my security groups?
    - Do my buckets have any public access?
    - How has my ALB configuration changed over time?
- You can receive **alerts (SNS notifications)** for any changes
- **AWS Config is a per-region service**
- Can be **aggregated across regions and accounts**