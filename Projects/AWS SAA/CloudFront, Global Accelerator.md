### CloudFront
- content delivery network(CDN)
- __Improves read performance, contents is cached at the edge__
- 
- __DDoS protection(because worldwide), integration with Shield, AWS Web Application Firewall__
![[aws cloudfront.png]]

### CloudFront - Origins
- __S3 Bucket__
	- For distributing files and caching them at the edge
	- Enhanced security with CloudFront __Origin Access Control (OAC)
	- Legacy security - Origin Access Identity (OAI)
	- CloudFront can be used as an _ingress_ (to upload files to S3)
	- ![[cloudront s3 as origin.png]]


- __Custom Origin (HTTP)__
	- ALB, EC2 instances
	- S3 website (must first enable the bucket as a static website)
	- Any HTTP backend you want
	![[cloufront ec2 alb.png]]

### CloudFront - Geo Restriction
- __Allowlist__ - allow users to access your content only if they're in one of the countries on a list of approved countries.
- __Blocklist__ - Prevent users from acessing your content if they're in one of the countries on a list of banned countries.
- The 'country' is determined using a 3rd party Geo-IP database.
- Use Case: Copyright laws to control access to content.

### CloudFront - Pricing, Price Classes
- CloudFront Edge locations are all around the world 
- The cost of data out per edge location varies

- Number of edge locations can be reduces for __cost reduction__
- Three price classes: 
	1. Price Class All: all regions – best performance 
	2. Price Class 200: most regions, but excludes the most expensive regions 
	3. Price Class 100: only the least expensive regions

### CloudFront - Cache Invalidations
- If back-end origin is updated, cloufront will only get refreshed content after TTL expiration.
- Entire or partial cache refresh can be forced bypassing TTL by performing a __CloudFront Invalidation__
- We can invalidate all files(\*) or a special path (/images/\*)
![[cloudront cache invalidation.png]]




### Global users for application
- You have deployed an application and have global users who want to access it directly.
- They go over the public internet, which can add a lot of latency due to many hops 
- We wish to go as fast as possible through AWS network to minimize latency
![[cloufront global users.png]]

| Unicast IP                      | Anycast IP                                                                        |
| ------------------------------- | --------------------------------------------------------------------------------- |
| one server holds one ip Address | all servers hold the same id address and the client is routed to the nearest one. |

### Global Accelerator
- Leverage the AWS internal network to route to your application 
-  __2 Anycast IP are created for your application__
-  The Anycast IP send traffic directly to Edge Locations 
-  The Edge locations send the traffic to your application
![[global acclerator.png]]
- Works with Elastic IP, EC2 instances, ALB, NLB, public or private 
-  Consistent Performance 
	-  Intelligent routing to lowest latency and fast regional failover 
	-  No issue with client cache (because the IP doesn’t change) 
	-  Internal AWS network 
- • Health Checks
	-  Global Accelerator performs a health check of your applications 
	-  Helps make your application global (failover less than 1 minute for unhealthy) 
	-  Great for disaster recovery (thanks to the health checks) 
- • Security 
	-  only 2 external IP need to be whitelisted 
	-  DDoS protection thanks to AWS Shield


### Global Accelerator vs CloudFront
They both use the AWS global network and its edge locations around the world 
Both services integrate with AWS Shield for DDoS protection.

| __CloudFront__                                                       | __Global Accelerator__                                                              |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Improves performance for both cacheable content(like - images & videos)                      | improves performance for a wide range of application over TCP or UDP                |
| Dynamic content (such as API acceleration and dynamic site delivery) | Proxying packets at the edge to applications running in one or more AWS Regions.    |
| Content is served at the edge                                        | Good fit for non-HTTP use cases, such as gaming (UDP), IoT (MQTT), or Voice over IP |
|                                                                      | Good for HTTP use cases that require static IP addresses                            |
|                                                                      | Good for HTTP use cases that required deterministic, fast regional failover         |
