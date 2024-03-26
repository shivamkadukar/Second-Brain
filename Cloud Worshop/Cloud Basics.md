## Cloud Computing
- Definition: Cloud computing refers to the delivery of computing services over the internet.
- Characteristics: On-demand access, scalability, pay-as-you-go pricing, and shared resources.

## Cloud Computing Models

- Infrastructure as a Service (IaaS): Provides virtualized computing resources over the internet.
- Platform as a Service (PaaS): Offers a platform allowing customers to develop, run, and manage applications without dealing with infrastructure.
- Software as a Service (SaaS): Delivers software applications over the internet on a subscription basis.
## Cloud Deployment Models

- Public Cloud: Services are delivered over the internet and shared across multiple organizations.
- Private Cloud: Cloud infrastructure is solely dedicated to a single organization.
- Hybrid Cloud: Combination of public and private cloud services, offering flexibility and scalability.

## Cloud Computing compared to traditional data centers
|                                              | cloud computing                                                                                                                                                                                                                                             | traditional data centers                                                                                                                                            |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Infrastructure Ownership and Management:** | Infrastructure is owned and maintained by cloud service providers (CSPs). Users access resources remotely over the internet.                                                                                                                                | Companies own and manage their physical servers, storage, networking equipment, and cooling systems on-site or in colocation facilities.                            |
| **Scalability**                              | Offers scalability on-demand. Users can easily scale up or down their resources based on demand without the need for upfront investment in hardware.                                                                                                        | Scaling up requires purchasing new hardware, configuring it, and integrating it into the existing infrastructure. Scaling down may lead to underutilized resources. |
| **Cost Structure**                           | Operating expenditure (OpEx) model where users pay for the resources they consume on a pay-as-you-go basis. This often leads to cost savings as users only pay for what they use.                                                                           | Capital expenditure (CapEx) model where companies invest in physical infrastructure upfront and bear maintenance and operational costs.                             |
| **Redundancy and Reliability**               | Cloud providers offer built-in redundancy and high availability across multiple data centers. Data replication and automatic failover mechanisms ensure reliability.                                                                                        | Companies need to implement redundancy measures such as backup power supplies, redundant networking, and data replication to ensure reliability                     |
| **Security**                                 | Cloud providers invest heavily in security measures including encryption, identity and access management (IAM), and compliance certifications. However, the responsibility for securing data and applications still lies with the user to a certain extent. | Security measures such as firewalls, intrusion detection systems, and physical access controls are implemented and managed by the organization                      |
| **Maintenance and Updates**                  | Companies are responsible for maintaining hardware, applying software updates, and managing backups and disaster recovery                                                                                                                                   | Cloud providers handle maintenance, updates, and security patches, freeing users from these operational tasks.                                                      |
## Cloud Terminology

- Virtualization: Technique of creating virtual versions of computing resources.
- Scalability: Ability to handle increasing workload by adding resources dynamically.
- Elasticity: Capability to scale resources up or down based on demand.
- Multi-tenancy: Principle where multiple users share the same resources securely.
- Serverless Computing: Serverless computing is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers. Developers focus on writing code in the form of functions, which are executed in response to events triggered by external sources.
	- Characteristics:
		- No server management: Users do not need to provision or manage servers. The cloud provider handles server provisioning, scaling, and maintenance automatically.
		- Pay-per-use: Users are charged based on the actual execution time and resources consumed by their functions, rather than paying for provisioned servers.
		- Event-driven: Functions are triggered by events such as HTTP requests, database changes, or file uploads, allowing for efficient use of resources.
- Load Balancing
	- Definition: Load balancing is the process of distributing incoming network traffic across multiple servers or resources to ensure optimal resource utilization, reliability, and performance.
		- Characteristics:
		    - Distribution of workload: Incoming requests are evenly distributed across multiple servers or resources to prevent overloading and ensure efficient resource utilization.
		    - High availability: Load balancers monitor the health of servers and reroute traffic away from unhealthy or overloaded servers to healthy ones, ensuring uninterrupted service availability.
		    - Scalability: Load balancers can automatically scale resources horizontally by adding or removing servers based on traffic demands, allowing for seamless handling of fluctuations in workload.
- Autoscaling
	- Definition: Auto-scaling, also known as autoscaling or auto-scaling, is a cloud computing feature that automatically adjusts the number of resources allocated to an application based on changes in workload demand.

## Key Cloud Providers

[https://comparecloud.in/](https://comparecloud.in/)
- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- IBM Cloud

## AWS Global Infrastructure

[https://aws.amazon.com/about-aws/global-infrastructure/](https://aws.amazon.com/about-aws/global-infrastructure/)

• AWS Regions 
	- A region is a cluster of data centers 
	• Most AWS services are region-scoped
• AWS Availability Zones 
• AWS Data Centers 
• AWS Edge Locations / Points of Presence

## How to choose AWS Region
- Compliance with data governance and legal requirements: data never leaves a region without your explicit permission 
- Proximity to customers: reduced latency 
- Available services within a Region: new services and new features aren’t available in every Region 
- Pricing: pricing varies region to region and is transparent in the service pricing page
