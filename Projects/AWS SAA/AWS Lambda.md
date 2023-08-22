| EC2                                              | Lambda                                   |
| ------------------------------------------------ | ---------------------------------------- |
| Virtual Servers in cloud                         | Virtual __functions__ - no servers to manage |
| Limted by RAM and CPU                            | Limited by time - __short executions__   |
| Continously running                              | Run __on-demand__                        |
| Scaling means intervention to add/remove servers | Scaling is __automated__                 | 

### Benefits of AWS Lambda
-  Easy Pricing: 
	-  Pay per request and compute time 
	-  Free tier of 1,000,000 AWS Lambda requests and 400,000 GBs of compute time
-  Integrated with the whole AWS suite of services 
-  Integrated with many programming languages 
-  Easy monitoring through AWS CloudWatch 
-  Easy to get more resources per functions (up to 10GB of RAM!) 
-  Increasing RAM will also improve CPU and network

### AWS Lambda Language support
- Node.js (JavaScript), Python, Java (Java 8 compatible), C# (.NET Core) , Golang,
    C#/Powershell , Ruby
- Custom Runtime API (community supported, example Rust) 
- Lambda Container Image 
	- The container image must implement the Lambda Runtime API 
	- ECS / Fargate is preferred for running arbitrary Docker images

### AWS Lambda Pricing
You can find overall pricing information here: https://aws.amazon.com/lambda/pricing/ 
- Pay per calls : 
- First 1,000,000 requests are free 
- $0.20 per 1 million requests thereafter ($0.0000002 per request)
- Pay per duration: (in increment of 1 ms ) 
- 400,000 GB -seconds of compute time per month for FREE 
	- == 400,000 seconds if function is 1GB RAM 
	- == 3,200,000 seconds if function is 128 MB RAM 
- After that $1.00 for 600,000 GB-seconds 
- It is usually very cheap to run AWS Lambda so it’s very popular

### AWS  Lambda Limitations (per region)

- __Execution__: 
	-  Memory allocation: 128 MB – 10GB (1 MB increments) 
	-  Maximum execution time: 900 seconds (15 minutes) 
	-  Environment variables (4 KB) 
	-  Disk capacity in the “function container” (in /tmp): 512 MB to 10GB 
	-  Concurrency executions: 1000 (can be increased) 
-  __Deployment__: 
	-  Lambda function deployment size (compressed .zip): 50 MB 
	-  Size of uncompressed deployment (code + dependencies): 250 MB 
	-  Can use the /tmp directory to load other files at startup 
	-  Size of environment variables: 4 KB
