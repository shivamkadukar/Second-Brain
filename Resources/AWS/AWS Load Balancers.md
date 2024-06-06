Load Balances are servers that forward traffic to multiple servers (e.g., EC2 instances) downstream

__Why use Load Balancers__
• Spread load across multiple downstream instances • Expose a single point of access (DNS) to your application • Seamlessly handle failures of downstream instances • Do regular health checks to your instances • Provide SSL termination (HTTPS) for your websites • Enforce stickiness with cookies • High availability across zones • Separate public traffic from private traffic

__Why use Elastic Load Balancers__
- An Elastic Load Balancer is a __managed load balancer __
	- AWS guarantees that it will be working 
	- AWS takes care of upgrades, maintenance, high availability 
	- AWS provides only a few configuration knobs 
- It costs less to setup your own load balancer but it will be a lot more effort on your end 
- It is integrated with many AWS offerings / services 
	- EC2, EC2 Auto Scaling Groups, Amazon ECS 
	- AWS Certificate Manager (ACM), CloudWatch 
	- Route 53, AWS WAF, AWS Global Accelerator

### Types of ELB
AWS has 4 kinds of managed Load Balancers 
- Classic Load Balancer (v1 - old generation) – 2009 – CLB 
	- HTTP, HTTPS, TCP, SSL (secure TCP) 
- Application Load Balancer (v2 - new generation) – 2016 – ALB 
	- HTTP, HTTPS, WebSocket 
- Network Load Balancer (v2 - new generation) – 2017 – NLB 
	- TCP, TLS (secure TCP), UDP 
- Gateway Load Balancer – 2020 – GWLB 
	- Operates at layer 3 (Network layer) – IP Protocol 
- Overall, it is recommended to use the newer generation load balancers as they provide more features 
- Some load balancers can be setup as internal (private) or external (public) ELBs

__Classic Load Balancers (CLB)__
Supports TCP (Layer 4), HTTP & HTTPS (Layer 7) • Health checks are TCP or HTTP based • Fixed hostname XXX.region.elb.amazonaws.com