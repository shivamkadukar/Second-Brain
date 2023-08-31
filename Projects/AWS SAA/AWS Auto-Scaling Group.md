- In real-life, the load on your websites and application can change 
- In the cloud, you can create and get rid of servers very quickly 
- The goal of an Auto Scaling Group (ASG) is to: 
	- __Scale out__ (add EC2 instances) to match an increased load 
	- __Scale in__ (remove EC2 instances) to match a decreased load 
	- Ensure we have a minimum and a maximum number of EC2 instances running 
	- Automatically register new instances to a load balancer 
	- Re-create an EC2 instance in case a previous one is terminated (ex: if unhealthy) 
- ASG are free (you only pay for the underlying EC2 instances)

### Auto-Scaling Group Attributes
- A Launch Template (older “Launch Configurations” are deprecated) 
	- AMI + Instance Type 
	- EC2 User Data 
	- EBS Volumes 
	- Security Groups 
	- SSH Key Pair 
	- IAM Roles for your EC2 Instances 
	- Network + Subnets Information 
	- Load Balancer Information 
- Min Size / Max Size / Initial Capacity 
- Scaling Policies
### Cloudwatch Alarms & Scaling
- It is possible to scale an ASG based on CloudWatch alarms 
- An alarm monitors a metric (such as Average CPU, or a custom metric) 
- Metrics such as Average CPU are computed for the overall ASG instances 
- Based on the alarm: 
	- We can create scale-out policies (increase the number of instances) 
	- We can create scale-in policies (decrease the number of instances)
### Dynamic Scaling Policies
- __Target Tracking Scaling__ 
	- Most simple and easy to set-up 
	- Example: I want the average ASG CPU to stay at around 40% 
- __Simple / Step Scaling__ 
	- When a CloudWatch alarm is triggered (example CPU > 70%), then add 2 units 
	- When a CloudWatch alarm is triggered (example CPU < 30%), then remove 1 
- __Scheduled Actions__
	- Anticipate a scaling based on known usage patterns 
	- Example: increase the min capacity to 10 at 5 pm on Fridays


• Predictive scaling: continuously forecast load and schedule scaling ahead

### Good Metrics to Scale On
- __CPU Utilization__: Average CPU utilization across your instances 
- __RequestCountPerTarget__: to make sure the number of requests per EC2 instances is stable 
- __Average Network In / Out__ (if you’re application is network bound) 
- __Any custom metric__ (that you push using CloudWatch)

### Scaling Cooldowns
- After a scaling activity happens, you are in the __cooldown period (default 300 seconds)__
- During the cooldown period, the ASG will not launch or terminate additional instances (to allow for metrics to stabilize) 
- Advice: Use a ready-to-use AMI to reduce configuration time in order to be serving request fasters and reduce the cooldown period