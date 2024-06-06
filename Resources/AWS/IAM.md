________________________________________
### Summary
- __Users__: mapped to a physical user, has a password for AWS Console 
- __Groups__: contains users only 
- __Policies__: JSON document that outlines permissions for users or groups 
- __Roles__: for EC2 instances or AWS services 
- __Security__: MFA + Password Policy 
- __AWS CLI__: manage your AWS services using the command-line 
- __AWS SDK__: manage your AWS services using a programming language 
- __Access Keys__: access AWS using the CLI or SDK 
- __Audit__: IAM Credential Reports & IAM Access Advisor
### IAM guidelines & Best Practices
- Don’t use the root account except for AWS account setup 
- One physical user = One AWS user 
- __Assign users to groups and assign permissions to groups__ 
- Create a __strong password policy__
- Use and enforce the use of Multi Factor Authentication (MFA) 
- Create and use Roles for giving permissions to AWS services 
- Use Access Keys for Programmatic Access (CLI / SDK) 
- Audit permissions of your account using IAM Credentials Report & IAM Access Advisor 
- Never share IAM users & Access Keys

__________________________________________
### IAM: Users & Groups
- IAM = Identity and Access Management, __Global service__
- __Root account__ created by default, shouldn’t be used or shared 
- __Users__ are people within your organization, and can be grouped 
- __Groups__ only contain users, not other groups 
- Users don’t have to belong to a group, and user can belong to multiple groups

### IAM: Permissions
- Users or Groups can be assigned JSON documents called __policies__ 
• These policies define the permissions of the users 
• In AWS you apply the __least privilege principle__: _don’t give more permissions than a user needs_

### IAM Policies
- IAM Policies inheritance
	![[iam policies inheritance.png]]
	
- IAM Policies Structure
	![[iam policy.png|400]]
	- Consists of 
		- Version: policy language version, always include “2012 -10 - 17” •
		- Id: an identifier for the policy (optional) 
		- Statement: one or more individual statements (required) 
	- Statements consists of 
	  -  Sid: an identifier for the statement (optional)
	  - Effect: whether the statement allows or denies access (Allow, Deny) 
	  - Principal: account/user/role to which this policy applied to 
	  - Action: list of actions this policy allows or denies 
	  -  Resource: list of resources to which the actions applied to 
	  -  Condition: conditions for when this policy is in effect (optional)

### IAM Password Policy
- Strong passwords = higher security for your account 
- In AWS, you can setup a password policy: 
	- Set a minimum password length 
	- Require specific character types: 
		- including uppercase letters 
		- lowercase letters 
		- numbers 
		- non-alphanumeric characters 
	- Allow all IAM users to change their own passwords 
	- Require users to change their password after some time (password expiration) 
	- Prevent password re-use

### Multi Factor Authentication - MFA

 - Users have access to your account and can possibly change configurations or delete resources in your AWS account 
 - __You want to protect your Root Accounts and IAM users__ 
 - MFA = password you know + security device you own 
 - __Main benefit of MFA__: if a password is stolen or hacked, the account is not compromised
- MFA devices options in AWS - Virtual MFA device(e.g. goole authenticator, Authy), U2F Seurity(Yubikey by Yubico),  Hardware key Fob MFA Device(Gemalto), Hardware key fob MFA device for AWS govcloud(US)(SurePassID)

### How can users access AWS?

To access AWS, you have three options: 
- __AWS Management Console__ (protected by password + MFA) 
- __AWS Command Line Interface (CLI)__: protected by access keys 
	- A tool that enables you to interact with AWS services using commands in your command-line shell 
	- Direct access to the public APIs of AWS services 
	- You can develop scripts to manage your resources 
	- It’s open-source https://github.com/aws/aws-cli
- __AWS Software Developer Kit (SDK)__ - for code: protected by access keys
	- Language-specific APIs (set of libraries) 
	-  Enables you to access and manage AWS services programmatically 
	-  Embedded within your application 
	-  Supports 
		- SDKs (JavaScript, Python, PHP, .NET, Ruby, Java, Go, Node.js, C++) 
		-  Mobile SDKs (Android, iOS, …) 
		- IoT Device SDKs (Embedded C, Arduino, …)
	- AWS CLI is built on AWS SDK for Python

- Access Keys are generated through the AWS Console 
- Users manage their own access keys

### IAM roles for Services
![[iam roles for services 1.png|300]]
- For AWs services performing actions on your behalf.
- To do so, we will assign permissions to AWS services with IAM Roles 
- Common roles: EC2 Instance Roles, Lambda Function Roles, Roles for CloudFormation

### IAM Security Tools
- __IAM Credentials Report (account-level) __
	- a report that lists all your account's users and the status of their various credentials 

- __IAM Access Advisor (user-level)__ 
	- Access advisor shows the service permissions granted to a user and when those services were last accessed. 
	- You can use this information to revise your policies



	

