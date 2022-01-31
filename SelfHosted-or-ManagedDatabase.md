# AWS RDS vs EC2 Hosted Database

## Situation
Our applications and databases were hosted on-premise.We had to move our application to AWS.
The application used IBM Db2 as a database. AWS RDS does not support IBM Db2.

## Task
We had two options:
1. Move the application to AWS and use the database which are supported by AWS RDS.
2. Move the application to AWS and use the self-hosted database on EC2 with AWS EBS storage.

## Action
Now, we had to decide which option is better. We had to see the trade-off between the two options.
There are various factors that we need to consider.

1. Administration

With RDS it is easy to set up. No need to worry about managing, maintaining, and securing the database.
With EC2, it is a bit complicated. We are in complete control of the os, database and configurations.

2. High availability

RDS has inbuilt support for high availability. It automatically replicates the instance across the region/availability zones.
With EC2, we should configure it to be highly available.

3. Backups

RDS has inbuilt support for backups. It uses cloudwatch to monitor the database and take backups automatically.
With EC2, we should have a separate monitoring and backup system.

4. Performance

RDS can be configured to have certain number of IOPS provisioned. Also cloudwatch can be used to monitor the performance of the database.
With EC2, we should pick the right storage volume to get the IOPS and latency.

5. Security

RDS encrypts the data at REST and also in transit. All readReplicas, automated backups are all encrypted.
With EC2, we need to encrypt at the EBS volume level. We have option to configure at database level as well.

6. Licencing

AWS provides the databases with Licence Included. There is no need to separately buy the licence.
With EC2, we need to buy the database licence separately.

8. Cost

AWS RDS is more expensive as they have to do heavy lifting. Do backups, monitoring, etc.
Installing database server with EC2 is usually cheaper.

## Result
Looking into all the above aspects, most of the setup are one time apart from backups and monitoring.
We had an in house skill for taking backups, monitoring. Also,the cost is low compared to 
managed service like AWS RDS.
So, final decision was, we had to move the application to AWS and use the self-hosted database on EC2 with AWS EBS storage.