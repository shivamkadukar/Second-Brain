- Managed NFS (network file system) that can be mounted on many EC2 
- EFS works with EC2 instances in multi-AZ 
- Highly available, scalable, expensive (3x gp2), pay per use
![[aws efs.png|500]]

• Use cases: content management, web serving, data sharing, Wordpress • Uses NFSv4.1 protocol • Uses security group to control access to EFS • __Compatible with Linux based AMI (not Windows)__ • Encryption at rest using KMS • POSIX file system (~Linux) that has a standard file API • File system scales automatically, pay-per-use, no capacity planning!
### EFS - Performance & Storage Classes
- EFS Scale 
	- 1000s of concurrent NFS clients, 10 GB+ /s throughput 
	- Grow to Petabyte-scale network file system, automatically 
- Performance Mode (set at EFS creation time) 
	- __General Purpose (default__) – latency-sensitive use cases (web server, CMS, etc…) 
	- __Max I/O__ – higher latency, throughput, highly parallel (big data, media processing) 
- Throughput Mode 
	- __Bursting__ – 1 TB = 50MiB/s + burst of up to 100MiB/s 
	- __Provisioned__ – set your throughput regardless of storage size, ex: 1 GiB/s for 1 TB storage 
	- __Elastic__ – automatically scales throughput up or down based on your workloads 
		- Up to 3GiB/s for reads and 1GiB/s for writes 
		- Used for unpredictable workloads

__Storage Classes__
• Storage Tiers (lifecycle management feature – move file after N days) • Standard: for frequently accessed files • Infrequent access (EFS-IA): cost to retrieve files, lower price to store. Enable EFS -IA with a Lifecycle Policy • Availability and durability • Standard: Multi-AZ, great for prod • One Zone: One AZ, great for dev, backup enabled by default, compatible with IA (EFS One Zone -IA) • Over 90% in cost savings
![[efs storgage classes.png|400]]