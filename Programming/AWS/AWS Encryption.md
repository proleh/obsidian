---
creation date: 02-04-2025
modification date: Wednesday 2nd April 2025 22:22:05
---
Rel: [[Programming/AWS/AWS]]
Tags: #aws

### KMS(Key Management Service)


 
### CloudHSM(Hardware Secutriy Module)
AWS provides the hardware device but the customer is responsible for encryption. The device is temper resistant.

### **Types of KMS Keys**
- **Customer Managed Key:**
    - Create, manage and used by the customer, can enable or disable
    - Possibility of rotation policy (new key generated every year, old key preserved)
    - Possibility to bring-your-own-key
- **AWS Managed Key:**
    - Created, managed and used on the customer's behalf by AWS
    - Used by AWS services (aws/s3, aws/ebs, aws/redshift)
- **AWS Owned Key:**
    - Collection of CMKs that an AWS service owns and manages to use in multiple accounts
    - AWS can use those to protect resources in your account (but you can't view the keys)
        
- **CloudHSM Keys (custom keystore):**
    - Keys generated from your own CloudHSM hardware device
    - Cryptographic operations are performed within the CloudHSM cluster
