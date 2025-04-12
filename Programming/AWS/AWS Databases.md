Tags: #aws #db

[[Programming/AWS/AWS]]
DB can be self-hosted on EC2 instance or by using RDS.
**Advantage over using RDS versus deploying DB on EC2**

## Summary

**Databases & Analytics Summary in AWS**

- **Relational Databases – OLTP**: RDS & Aurora (SQL)
- Differences between **Multi-AZ, Read Replicas, Multi-Region**
- **In-memory Database**: ElastiCache
- **Key/Value Database**: DynamoDB (serverless) & DAX (cache for DynamoDB)
- **Warehouse – OLAP**: Redshift (SQL)
- **Hadoop Cluster**: EMR
- **Athena**: query data on Amazon S3 (serverless & SQL)
- **QuickSight**: dashboards on your data (serverless)
- **DocumentDB**: “Aurora for MongoDB” (JSON – NoSQL database)
- **Amazon QLDB**: Financial Transactions Ledger (immutable journal, cryptographically verifiable)
- **Amazon Managed Blockchain**: managed Hyperledger Fabric & Ethereum blockchains
- **Glue**: Managed ETL (Extract Transform Load) and Data Catalog service
- **Database Migration**: DMS
- **Neptune**: graph database
- **Timestream**: time-series database



## Details

### RDS is a managed service:
    - Automated provisioning, OS patching
    - Continuous backups and restore to specific timestamp (Point in Time Restore)
    - Monitoring dashboards
    - Read replicas for improved read performance
    - Multi AZ setup for DR (Disaster Recovery)
    - Maintenance windows for upgrades
    - Scaling capability (vertical and horizontal)
- BUT you cannot ssh to the db instance.
- ### Amazon Aurora:
	- Proprietary technology.
	- PostgreSQL and MySQL are supported.
	- It's AWS cloud optimized and claims 5x performance over MySQL RDS and 3x over PostgreSQL.
	- Auto grow up to 128TB by 10gb.
	- Costs more than RDS(+20%).
- Aurora Serverless
	- Pay per second, can be cost effective.
	- Good for infrequent, intermittent or unpredictable workloads.
- RDS can be
	- Read Replica - faster reads.
	- Multiple AZ - disaster recovery
	- Multiple regions - region disaster recovery.


### Elasticache
Same way as RDS ElastiCache is to get managed Redis or Memcache.

### DynamoDB
- NoSQL distributed serverless DB, blazingly fast, has Standard and Infrequent Access Table Classes.
- It's a key\value DB with PK(PartionKey and SortKey) and Attributes(Schema defined per item)
- ![[DynamoDB structure.png]]
- DynamoDB Accelerator (DAX) - in-memory cache for only DynameDB(like Redis)
- There is also DynamoDB Global Table which are available in multiple regions for read\write with extra low-latency.

### Redshift
- Based on PosgreSQL, but it's not OLTP(online transaction processing) but OLAP(online analytical processing), used for analytics.
- Data loaded every hour not very second.
- Columnar storage of data instead of row based.
- MPP(Massively Parallel Query Execution)
- Pay as you go.
- Has an SQL interface
- Easy integration with BI tools as AWS QuickSIght or Tableu.


### EMR(Elastic MapReduce)
- EMR creates Hadoop clusters(Big DATA) to analyze vast amount of data.
- Clusters can be of hundreds of EC2 instances.
- Use Cases: data processing, machine learning, web indexing...

### Athena
- Serverless query service to perform analytics over Amazon S3 objects.
- Use SQL query to get files
- Supports CSV, JSON, ORC, Avro
- Price is $5.00 per 1TB pf scanned data.
- Use Case: BI, analytics, reporting, VPC Flow logs, ELB Logs, CloudTrails, etc.

### Amazon Quicksight
- Serverless machine learning BI service for creating interactive dashboards.
- Pricing per sessiong.
- Use Cases: BI, visualizations, ad-hoc analysis, business insights.
- Integrated with Aurora, RDS, Athena, Redshift, S3 etc.

### DocumentDB
- DocumentDB is AWS implementation of MongoDB, as Aurora for PostgresSQL\MySQL.
- Fully managed, highly available with replication across 3 AZ.
- Storage automatically grows in increments of 10GB.

### Amazon Neptune
- Fully managed Graph database
- 3 AZ with up tp 15 read replicas
- Can store up to billions of relations and query with milliseconds latency


### Amazon Timestream
- Time Series database
- 1000s time faster than relational db and 1\10th cost

### QLDB
- Quantum Ledger Database
- A ledger is a book recording financial transactions
- It's immutable system like blockchain
- There is no decentralizations component.

### Managed Blockchain

### AWS Glue
- Managed **extract, transform and load** (ETL) service
- Used to prepare and transform data for analytics(get data from S3 + RDS and load to Redshift)
- The AWS ***Glue Data Catalog*** is a central repository to store structural and operational metadata for all your data assets. For a given data set, you can store its table definition, physical location, add business relevant attributes, as well as track how this data has changed over time.


### DMS(data migration service)
- migrate db from source to the target
- supports homongeneous migrations: ex Orcale to Oracle
- supports heterogeneous migrations: ex Microsoft SQL to Aurora