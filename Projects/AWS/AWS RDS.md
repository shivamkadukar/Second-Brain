• RDS stands for Relational Database Service • It’s a managed DB service for DB use SQL as a query language. • It allows you to create databases in the cloud that are managed by AWS • Postgres • MySQL • MariaDB • Oracle • Microsoft SQL Server • Aurora (AWS Proprietary database)

__Advantage over using DB on EC2__
• RDS is a managed service: • Automated provisioning, OS patching • Continuous backups and restore to specific timestamp (Point in Time Restore)! • Monitoring dashboards • Read replicas for improved read performance • Multi AZ setup for DR (Disaster Recovery) • Maintenance windows for upgrades • Scaling capability (vertical and horizontal) • Storage backed by EBS (gp2 or io1) 
• BUT you can’t SSH into your instances

### RDS - Storage Auto Scaling

- Helps you increase storage on your RDS DB instance dynamically 
- When RDS detects you are running out of free database storage, it scales automatically 
- Avoid manually scaling your database storage 
- You have to set __Maximum Storage Threshold__ (maximum limit for DB storage) • Automatically modify storage if: • Free storage is less than 10% of allocated storage • Low-storage lasts at least 5 minutes • 6 hours have passed since last modification 
- __Useful for applications with unpredictable workloads__
- Supports all RDS database engines (MariaDB, MySQL, PostgreSQL, SQL Server, Oracle)

### RDS - Read Replicas for read scalability
• Up to 15 Read Replicas • Within AZ, Cross AZ or Cross Region • Replication is ASYNC, so reads are eventually consistent • Replicas can be promoted to their own DB • Applications must update the connection string to leverage read replicas
• Read replicas are used for SELECT (=read) only kind of statements (not INSERT, UPDATE, DELETE)
![[rds read replica.png|400]]
__Read Replicas - Network Cost__
• In AWS there’s a network cost when data goes from one AZ to another • For RDS Read Replicas within the same region, you don’t pay that fee

### RDS Multi AZ (Disaster Recovery)
• SYNC replication • One DNS name – automatic app failover to standby • Increase availability • Failover in case of loss of AZ, loss of network, instance or storage failure • No manual intervention in apps • Not used for scaling 
• Note:The Read Replicas be setup as Multi AZ for Disaster Recovery (DR)

![[rds disaster recovery.png|350]]
__RDS - From Single AZ to Multi AZ__

- Zero downtime operation (no need to stop the DB) 
- Just click on “modify” for the database 
- The following happens internally:
	- A snapshot is taken 
	- A new DB is restored from the snapshot in a new AZ 
	- Synchronization is established between the two databases
### RDS - Custom

- __Managed Oracle and Microsoft SQL Server Database with OS and database customization__ 
- RDS: Automates setup, operation, and scaling of database in AWS 
- Custom: access to the underlying database and OS so you can 
	- Configure settings 
	- Install patches 
	- Enable native features 
	- __Access the underlying EC2 Instance using SSH or SSM Session Manager__
- __De-activate Automation Mode__ to perform your customization, better to take a DB snapshot before •
- RDS vs. RDS Custom 
	- RDS: entire database and the OS to be managed by AWS 
	- RDS Custom: full admin access to the underlying OS and the database