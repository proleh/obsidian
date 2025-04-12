---
creation date: 12-04-2025
modification date: Saturday 12th April 2025 07:32:48
---
Rel: [[Programming/AWS/AWS]] [[Control Tower]]
Tags: #aws
-  Global service
- Allows to manage multiple AWS accounts
- The main account is the master account
- Cost Benefits:  
    • Consolidated Billing across all accounts – single payment method  
    • Pricing benefits from aggregated usage (volume discount for EC2, S3...)  
    • Pooling of Reserved EC2 instances for optimal savings
- API is available to **automate AWS account creation**
-
- **Restrict account privileges using Service Control Policies (SCP)**
	- Whitelist or blacklist IAM actions
	- Applied at the OU or Account level
	- Does not apply to the Master Account
	- SCP is applied to all the Users and Roles of the Account, including Root
	- The SCP does not affect service-linked roles  
	    • Service-linked roles enable other AWS services to integrate with AWS Organizations and can't be restricted by SCPs.
	- SCP must have an explicit Allow (does not allow anything by default)
	- Use cases:  
	    • Restrict access to certain services (for example: can’t use EMR)  
	    • Enforce PCI compliance by explicitly disabling services