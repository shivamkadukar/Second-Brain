• EC2 is one of the most popular of AWS’ offering • EC2 = Elastic Compute Cloud = Infrastructure as a Service • It mainly consists in the capability of : • Renting virtual machines (EC2) • Storing data on virtual drives (EBS) • Distributing load across machines (ELB) • Scaling the services using an auto-scaling group (ASG) • Knowing EC2 is fundamental to understand how the Cloud works

### EC2 sizing & configuration options
- Operating System (OS): Linux, Windows or Mac OS 
- How much compute power & cores (CPU) 
- How much random-access memory (RAM) 
- How much storage space: 
	- Network-attached (EBS & EFS) •
	- hardware (EC2 Instance Store) 
- Network card: speed of the card, Public IP address 
- Firewall rules: __security group__ 
- Bootstrap script (configure at first launch): EC2 User Data

__EC2 User Data Script__
It is possible to bootstrap our instances using an EC2 User data script. • bootstrapping means launching commands when a machine starts • That script is only run once at the instance first start • EC2 user data is used to automate boot tasks such as: • Installing updates • Installing software • Downloading common files from the internet • Anything you can think of • The EC2 User Data Script runs with the root user

### EC2 Instance Types

- You can use different types of EC2 instances that are optimised for different use cases (https://aws.amazon.com/ec2/instance-types/) 
- AWS has the following naming convention: m5.2xlarge 
	- m: instance class 
	- 5: generation (AWS improves them over time) 
	- 2xlarge: size within the instance class
__General Purpose__
• Great for a diversity of workloads such as web servers or code repositories • Balance between: • Compute • Memory • Networking

__Compute Optimized__
Great for compute-intensive tasks that require high performance processors: • Batch processing workloads • Media transcoding • High performance web servers • High performance computing (HPC) • Scientific modeling & machine learning • Dedicated gaming servers

__Memory Optimized__
Fast performance for workloads that process large data sets in memory • Use cases: • High performance, relational/non-relational databases • Distributed web scale cache stores • In-memory databases optimized for BI (business intelligence) • Applications performing real-time processing of big unstructured data

__Storage Optimized__
Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage • Use cases: • High frequency online transaction processing (OLTP) systems • Relational & NoSQL databases • Cache for in-memory databases (for example, Redis) • Data warehousing applications • Distributed file systems

__EC2 Instance Connect__
Connect to your EC2 instance within your browser • No need to use your key file that was downloaded • The “magic” is that a temporary key is uploaded onto EC2 by AWS • Works only out-of-the-box with Amazon Linux 2 • Need to make sure the port 22 is still opened!

### EC2 Instances Purchasing Options
On-Demand Instances – short workload, predictable pricing, pay by second • Reserved (1 & 3 years) • Reserved Instances – long workloads • Convertible Reserved Instances – long workloads with flexible instances • Savings Plans (1 & 3 years) –commitment to an amount of usage, long workload • Spot Instances – short workloads, cheap, can lose instances (less reliable) • Dedicated Hosts – book an entire physical server, control instance placement • Dedicated Instances – no other customers will share your hardware • Capacity Reservations – reserve capacity in a specific AZ for any duration

__EC2 On Demand__
Pay for what you use: • Linux or Windows - billing per second, after the first minute • All other operating systems - billing per hour 
• Has the highest cost but no upfront payment • No long-term commitment • Recommended for __short-term and un-interrupted workloads__, where you can't predict how the application will behave

__EC2 Reserved Instances__
Up to 72% discount compared to On-demand • You reserve a specific instance attributes (Instance Type, Region, Tenancy, OS) • Reservation Period – 1 year (+discount) or 3 years (+++discount) • Payment Options – No Upfront (+), Partial Upfront (++), All Upfront (+++) • Reserved Instance’s Scope – Regional or Zonal (reserve capacity in an AZ) • Recommended for steady-state usage applications (think database) • You can buy and sell in the Reserved Instance Marketplace • Convertible Reserved Instance • Can change the EC2 instance type, instance family, OS, scope and tenancy • Up to 66% discount(may vary over time)

__EC2 Savings Plan__
Get a discount based on long-term usage (up to 72% - same as RIs) • Commit to a certain type of usage ($10/hour for 1 or 3 years) • Usage beyond EC2 Savings Plans is billed at the On-Demand price • Locked to a specific instance family & AWS region (e.g., M5 in us-east-1) • Flexible across: • Instance Size (e.g., m5.xlarge, m5.2xlarge) • OS (e.g., Linux, Windows) • Tenancy (Host, Dedicated, Default)

__EC2 Spot Instances__
Can get a __discount of up to 90%__ compared to On-demand • Instances that you can “lose” at any point of time if your max price is less than the current spot price • The __MOST cost-efficient instances__ in AWS • Useful for workloads that are resilient to failure • Batch jobs • Data analysis • Image processing • Any distributed workloads • Workloads with a flexible start and end time • __Not suitable for critical jobs or databases__

__EC2 Dedicated Hosts__
A physical server with EC2 instance capacity fully dedicated to your use • Allows you address __compliance requirements and use your existing server- bound software licenses__ (per-socket, per-core, pe—VM software licenses) • Purchasing Options: • On-demand – pay per second for active Dedicated Host • Reserved - 1 or 3 years (No Upfront, Partial Upfront, All Upfront) • The most expensive option • Useful for software that have complicated licensing model (BYOL – Bring Your Own License) • Or for companies that have strong regulatory or compliance needs

__EC2 Dedicated Instances__
Instances run on hardware that’s dedicated to you • May share hardware with other instances in same account • No control over instance placement (can move hardware after Stop / Start)

__EC2 Capacity Reservations__
• Reserve On-Demand instances capacity in a specific AZ for any duration • You always have access to EC2 capacity when you need it • __No time commitment__ (create/cancel anytime), no billing discounts • Combine with Regional Reserved Instances and Savings Plans to benefit from billing discounts • __You’re charged at On-Demand rate whether you run instances or not__ • Suitable for short-term, uninterrupted workloads that needs to be
in a specific AZ


__EC2 Spot Instance Requests__
- Can get a discount of up to 90% compared to On-demand 
- Define max spot price and get the instance while current spot price < max
	- The hourly spot price varies based on offer and capacity 
	- If the current spot price > your max price you can choose to stop or terminate your instance with a 2 minutes grace period. 
- Other strategy: __Spot Block__
	- “block” spot instance during a specified time frame (1 to 6 hours) without interruptions 
	- In rare situations, the instance may be reclaimed 
- __Used for batch jobs, data analysis, or workloads that are resilient to failures.__
- __Not great for critical jobs or databases__

__Spot Fleets__
- Spot Fleets = set of Spot Instances + (optional) On-Demand Instances 
- The Spot Fleet will try to meet the target capacity with price constraints 
	- Define possible launch pools: instance type (m5.large), OS, Availability Zone 
	- Can have multiple launch pools, so that the fleet can choose 
	- Spot Fleet stops launching instances when reaching capacity or max cost 
- Strategies to allocate Spot Instances: 
	- __lowestPrice__: from the pool with the lowest price (cost optimization, short workload) 
	- __diversified__: distributed across all pools (great for availability, long workloads) 
	- __capacityOptimized__: pool with the optimal capacity for the number of instances 
	- __priceCapacityOptimized__ (recommended): pools with highest capacity available, then select the pool with the lowest price (best choice for most workloads) 
- <u>Spot Fleets allow us to automatically request Spot Instances with the lowest price</u>

### Elastic IP
When you stop and then start an EC2 instance, it can change its public IP. • If you need to have a fixed public IP for your instance, you need an Elastic IP • An Elastic IP is a public IPv4 IP you own as long as you don’t delete it • You can attach it to one instance at a time

• With an Elastic IP address, you can mask the failure of an instance or software by rapidly remapping the address to another instance in your account. • You can only have 5 Elastic IP in your account (you can ask AWS to increase that). • Overall, try to avoid using Elastic IP: • They often reflect poor architectural decisions • Instead, use a random public IP and register a DNS name to it • Or, as we’ll see later, use a Load Balancer and don’t use a public IP

### EC2 Storage
- [[EC2 Storage]] (EBS, AMI, EC2 Instance Store)
- [[AWS Storage - EFS]]

__EBS Vs EFS__
- EBS:
	- one instance (except multi-attach io1/io2) 
	- are locked at the Availability Zone (AZ) level 
	- gp2: IO increases if the disk size increases 
	- io1: can increase IO independently 
	- To migrate an EBS volume across AZ 
	- Take a snapshot 
	- Restore the snapshot to another AZ 
	- EBS backups use IO and you shouldn’t run them while your application is handling a lot of traffic 
	- Root EBS Volumes of instances get terminated by default if the EC2 instance gets terminated. (you can disable that)
	![[ebs migration.png|300]]

- EFS:
	- Mounting 100s of instances across AZ 
	- EFS share website files (WordPress) 
	- Only for Linux Instances (POSIX) 
	- EFS has a higher price point than EBS 
	- Can leverage EFS-IA for cost savings • Remember: EFS vs EBS vs Instance Store
	![[efs multi attach.png|300]]


### High Availability and Scalability for EC2
- Vertical Scaling: 
	- Increase instance size (= scale up / down) 
		- From: t2.nano - 0.5G of RAM, 1 vCPU 
		- To: u-12tb1.metal – 12.3 TB of RAM, 448 vCPUs 
- Horizontal Scaling: Increase number of instances (= scale out / in) 
	- Auto Scaling Group 
	- Load Balancer 
- High Availability: Run instances for the same application across multi AZ 
	- Auto Scaling Group multi AZ 
	- Load Balancer multi AZ