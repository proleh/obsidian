---
creation date: 23-03-2025
modification date: Sunday 23rd March 2025 06:58:28
---
It's a Managed DNS.

Most common records are:
- [www.google.com](http://www.google.com) => 12.34.56.78 == A record (IPv4)
- [www.google.com](http://www.google.com) => 2001:0db8:85a3:0000:0000:8a2e:0370:7334 == AAAA IPv6
- search.google.com => [www.google.com](http://www.google.com) == CNAME: hostname to hostname
- example.com => AWS resource == Alias (ex: ELB, CloudFront, S3, RDS, etc…)

Diff routing policies:
- Simple: IP -> Domain name.
- Weighted: Distributes traffic by assigned "weight" between insances.
- Latency: Distributes traffic by latency factor.
- Failover: If primary failed, go to recovery.


Rel: [[Programming/AWS/AWS]]
Tags: #aws #GlobalApplicaions, #cdn
