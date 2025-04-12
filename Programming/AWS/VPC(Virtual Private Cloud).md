---
creation date: 30-03-2025
modification date: Sunday 30th March 2025 19:08:42
---
It's a private network to deploy your resources.
VPC has subnets:
- private - not accessible from the internet(databases, etc.)
- public - accessible from the internet(EC2 instances, load balancer)
To define access to the internet and between subnets `Route Tables` are used.

- Internet Gateway needs to be created for public subnet to connect to the internet.
- NAT Gateway(AWS managed) & NAT Instances(self-managed) allow your instances in your Private Subnets to access the internet while remaining private.
  Create NAT instance in public to access it from private.
![[NACL vs Security Groups.png]]

### VPC Flow Logs - capture information about IP traffic going into your interfaces:
- VPC Flow logs.
- Subnet Flow logs
- Elastic Network Interface Flow logs

### VPC Endpoints - Allows to connect to AWS services using private network(lower latency)
- VPC Endpoint Gateway - connect to S3 and DynamoDB
- VPC Endpoint Interface - most services

### VPC Private Link - allows to establish connection between your VPC and some 3rd party service(if they're using aws as well).

### Connect on premise service
- Site to Site VPN - using public network
- Direct Connect(DX) - physical private connection to AWS(takes a long time, and a lot of money.)

Transit gateway used to simplify a lot of vpc, vpn, dx connections through hub.

### IP addresses IN AWS
- EC2 instance gets new public IP each start. Private LAN IPs stands the same all the time.
- It's possible to get Elastic IP(public static IP)
- all public IPs on AWS will be charged $0.005 per hour. Free tier 750 hours per month.
- IPv6 is free


Rel: [[Programming/AWS/AWS]]
Tags: #aws
