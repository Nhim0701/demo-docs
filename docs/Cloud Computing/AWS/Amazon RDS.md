RDS  : Relational Database Service
A _DB engine_ is the specific relational database software that runs on your DB instance. Amazon RDS currently supports the following engines:
- MariaDB
- Microsoft SQL Server
- MySQL
- Oracle
- PostgreSQL
Each DB engine has its own supported features, and each version of a DB engine can include specific features. Support for Amazon RDS features varies across AWS Regions and specific versions of each DB engine. To check feature support in different engine versions and Regions, see [Supported features in Amazon RDS by AWS Region and DB engine](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.RDSFeaturesRegionsDBEngines.grids.html).

Additionally, each DB engine has a set of parameters in a DB parameter group that control the behavior of the databases that it manages.

**Can't SSH into your instances**

When RDS detects you are running out of free database storage, it scales automatically

Read Replicas
.Up to 15 read replicas
.Same region you don't pay Network cost

Amazon Aurora
• Aurora is a proprietary technology from AWS (not open sourced) 
• Postgres and MySQL are both supported as Aurora DB (that means your drivers will work as if Aurora was a Postgres or MySQL database) 
• Aurora is “AWS cloud optimized” and claims 5x performance improvement over MySQL on RDS, over 3x the performance of Postgres on RDS
• Aurora storage automatically grows in increments of 10GB, up to 128 TB.
• Aurora can have up to 15 replicas and the replication process is faster than MySQL (sub 10 ms replica lag) 
• Failover in Aurora is instantaneous. It’s HA (High Availability) native.
• Aurora costs more than RDS (20% more) – but is more efficient


