### Snowball Edge
- Physical data transport solution: move TBs or PBs of data in or out of AWS 
- Alternative to moving data over the network (and paying network fees) 
- Pay per data transfer job 
-  Provide block storage and Amazon S3 -compatible object storage 
- __Snowball Edge Storage Optimized__
	- 80 TB of HDD capacity for block volume and S3 compatible object storage 
- __Snowball Edge Compute Optimized__
	- 42 TB of HDD or 28TB NVMe capacity for block volume and S3 compatible object storage 
	- Use cases: large data cloud migrations, Data centre decommission, disaster recovery

### AWS Snowcone & Snowcone SSD
__Small, portable computing, anywhere, rugged & secure, withstands harsh environments__
- Light (4.5 pounds, 2.1 kg) 
- Device used for edge computing, storage, and data transfer 
- __Snowcone__ – 8 TB of HDD Storage 
- __Snowcone SSD__ – 14 TB of SSD Storage 
- Use Snowcone where Snowball does not fit (space - constrained environment) 
- Must provide your own battery / cables 
- __Can be sent back to AWS offline, or connect it to internet and use AWS DataSync to send data__

### AWS SnowMobile

- Transfer exabytes of data (1 EB = 1,000 PB = 1,000,000 TBs) 
- Each Snowmobile has 100 PB of capacity (use multiple in parallel) 
- High security: temperature controlled, GPS, 24/7 video surveillance 
- Better than Snowball if you transfer more than 10 PB

### Snow Family - Edge Computing
- Snowcone & Snowcone SSD (smaller) 
	- 2 CPUs, 4 GB of memory, wired or wireless access 
	- USB-C power using a cord or the optional battery 
- Snowball Edge – Compute Optimized 
	 - 104 vCPUs, 416 GiB of RAM 
	 - Optional GPU (useful for video processing or machine learning)
	 - 28TB NVMe or 42TB HDD usable storage 
- Snowball Edge – Storage Optimized 
	- Up to 40 vCPUs, 80 GiB of RAM, 80 TB storage
	 - Object storage clustering available 
	 - All: Can run EC2 Instances & AWS Lambda functions (using AWS IoT Greengrass) 
	 - Long-term deployment options: 1 and 3 years discounted pricing