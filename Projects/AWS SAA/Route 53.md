- A highly available, scalable, fully managed and _Authoritative_ DNS.
- Route 53 is also a domain registrar.
- Ability to check the health of our resources.
- Only AWS service providing 100% availability SLA.

![[route53.png]]

> 53 is reference to traditional DNS port.

### Route 53 -  Records
Each record contains
- Domain/subdomain name - example.com
- Record Type - A or AAAA, etc.
- Value - IP address
- Routing policy - how route 53 responds to queries.
- TTL - amount of time the record cached at DNS resolves.
- Record types
	- must know
		- A - maps hostname to IPv4
		- AAAA - maps hostname to IPv6
		- CNAME - maps hostname to another hostname, target domain must be A or AAAA
		- NS - name servers for the hosted zones
	- advanced (out of scope for SAA)
		- CAA/DS/MX/NAPTR/PTR/SOA/TXT/SPF/SRV

### Route 53 - Hosted Zones
- container for records that defines how to route traffice to a domain and its subdomains.
- __Public Hosed zones__ - route traffic on the internet(public domain names).
- __Private hosted zones__ - route traffice within one or more VPCs (private domain names)
- $0.5 per month per hosted zone.
![[route 53 hosted zones 1.png]]

### Route 53 - Records TTL (Time to Live)
- __High TTL__ - less traffice on route 53, possibly outdated records.
- __Low TTL__ - more traffic - more bill, less outdated record, easy to change records.
![[route 53 ttl.png]]
### Route 53 - Routing Policy
- defines how route 53 responds to dns queries.
- Not same as load balancer routing which routes the traffic.
- DNS does not route any traffic, it only responds to DNS quereis.
- Route 53 supports the following routing policies
	- __Simple__
		- Route traffic to a single resource.
		- can specify multiple values in the same record.
		- If multiple values are returned, a random one is chosen by client.
		- when alias enabled, specify only one AWS resouce.
		- cant be associated with health check.
		![[route 53 routing simple.png]]
	- __Weighted__
		- control the % of requests that go to each specific resource.
		- assign each record a relative weight
			```traffic(%) = weight of a speific record/sum of all weights ofrecords```
		- DNS records must have the same name and type
		- can be associated with health checks
		- assign weight of 0 to a record to stop sending traffic to a resource.
		- if all records have weight of 0, then all records will be returned equally.
		- _USE CASE_ - load balancing between regions, testing new application versions.
		![[route 53 routing weighted.png]]
	- __Latency-Based__
		- Redirect to resource that has the least latency close to us.
		- helpful when latency for users is a priority.
		- __latency is based on traffic between users and AWS regions__.
		- can be associate with health checks (has failover capability)
		![[route 53 latency based.png]]

### Route 53 - Health Checks
- HTTP health checks are __only for public resources__.
- Health check => automated DNS failover:
	- health checks that monitor an endpoint(application, server, other aws resource).
	- health checks that monitor other health checks (calculated health checks).
	- health checks that monitor cloudwatch alarms- e.g. throttles of dynamodb, alarms on RDS, (helpful for private resources).
- health checks are integrated with CW metrics.
![[route 53 health checks.png|350]]
- __Health checks - monitor endpoint__
	- About 15 global health checkers will check the endpoint health 
		-  Healthy/Unhealthy Threshold – 3 (default)
		-  Interval – 30 sec (can set to 10 sec – higher cost)
		-  Supported protocol: HTTP, HTTPS and TCP
		-  If > 18% of health checkers report the endpoint is healthy, Route 53 considers it Healthy. Otherwise, it’s Unhealthy 
		-  Ability to choose which locations you want Route 53 to use 
	-  Health Checks pass only when the endpoint responds with the 2xx and 3xx status codes 
	-  Health Checks can be setup to pass / fail based on the text in the first 5120 bytes of the response
	-  Configure you router/firewall to allow incoming requests from Route 53 Health Checkers
		![[route 53 monitor endpoints.png|350]]

- Health checks - 