####Availability Zones
Availability zones are split across regions, where each region can have mutliple availabilty zones that enable business continuity

####Edge Locations
Used for Cloudfront. This distributes static content to end users at low latency. 
Also protects against DDoS attacks.

####IaaS, PaaS, or SaaS
IaaS: Infrastructure as a service.
-Basic building blocks in IT
-Manage a Linux service, managed my EC2

PaaS: cloud managed hardware and os

SaaS: Complete product. I.e. Office 365, or Salesforce.

Serverless: Build/run apps/code without compute.
Use lambda, S3, DynamoDB (NoSQL Database), AZ SNS (Simple Notification Service).

####S3 Lab
Segement data into buckets. 
Glacier: Long term archive of data, less accessible. Used for archiving. Cheap to store and archive, expensive to retrieve.
EBS: Block Storage, attach to servers to EC2 instances. (Attach a hard drive)
EFS: Network Attached Storage for EC2. Multiple servers access data stores, i.e. Nas/SoftNas
Storage Gateway: Hybrid On-Prem + cloud service.
Snowball: Migrate a large amount of data from On Prem to AWS Cloud.

###Storage Example
VPC: Virtual private cloud.
We want servers to have access to other data, but not be attached by something/someone outside.
Thus we abstract everything in a Virtual Private Cloud.

S3 Comes in when we have a bucket, drop things into bucket. Lifecycle rule on the bucket to glacier vault, for long term archiving.
    -Lowest cost storage on aws
    -Located in cloud, NOT inside of the VPC.
    -We need to create a VPC Endpoint to connect to S3.

####Hybrid Storage 
Corp Datacenter has a crapton of data. Easier to do a Snowball. (hi-cap storage device, shove it in there, ship it back.)

Or:
Storage gateway, which directly connects on-prem to cloud.
Frequently accessed content gets put into a bucket.

###Database Service 
RDS: Relational Database Service
- MySQL, MariaDB, AZ Aurora,
- DynamoDB (NoSQL Service)
- RedShift (Database Warehouse based on PostgresSQL)
- Elasticache (In memory caches)
- Database Migration Service (Migrate from/to databases)
- Neptune (Graph Database Service)

####Example:
-We have a on site oracle database
-In VPC, we create an Oracle for Aurora, migrate with DMS.
-That oracle database load can be reduced by putting Elasticache node in front of requests for frequently used data.
 