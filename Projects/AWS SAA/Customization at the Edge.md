- Many modern applications execute some form of the logic at the edge 
- __Edge Function__: 
	- A code that you write and attach to CloudFront distributions 
	- Runs close to your users to minimize latency 
- CloudFront provides two types: __CloudFront Functions__ & __Lambda@Edge__ 
- You don’t have to manage any servers, deployed globally 
- Use case: customize the CDN content 
- Pay only for what you use 
- Fully serverless
### Use Cases
- Website Security and Privacy 
- Dynamic Web Application at the Edge 
- Search Engine Optimization (SEO) 
- Intelligently Route Across Origins and Data Centers 
- Bot Mitigation at the Edge 
- Real-time Image Transformation 
- A/B Testing
- User Authentication and Authorization 
- User Prioritization 
- User Tracking and Analytics

### CloudFront Functions

![[aws cloufront functions.png|150]]
- Lightweight functions written in JavaScript 
- For high-scale, latency-sensitive CDN customizations 
- Sub-ms startup times, millions of requests/second 
- Used to change Viewer requests and responses: 
- Viewer Request: after CloudFront receives a request from a viewer
- Viewer Response: before CloudFront forwards the response to the viewer 
- Native feature of CloudFront (manage code entirely within CloudFront)

### Lambda@Edge

![[aws lambda@edge.png|150]]
- Lambda functions written in NodeJS or Python 
-  Scales to 1000s of requests/second 
-  Used to change CloudFront requests and responses: 
	-  Viewer Request – after CloudFront receives a request from a viewer 
	-  Origin Request – before CloudFront forwards the request to the origin 
	-  Origin Response – after CloudFront receives the response from the origin 
-  Viewer Response – before CloudFront forwards the response to the viewer 
-  Author your functions in one AWS Region (us-east-1), then CloudFront replicates to its locations

