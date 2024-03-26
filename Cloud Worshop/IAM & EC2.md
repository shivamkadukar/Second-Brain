- __Users__: mapped to a physical user, has a password for AWS Console 
- __Groups__: contains users only 
- __Policies__: JSON document that outlines permissions for users or groups 
- __Roles__: for EC2 instances or AWS services 
- __Security__: MFA + Password Policy 
- __AWS CLI__: manage your AWS services using the command-line 
- __AWS SDK__: manage your AWS services using a programming language 
- __Access Keys__: access AWS using the CLI or SDK 
- __Audit__: IAM Credential Reports & IAM Access Advisor

### IAM Best Practices
- Don’t use the root account except for AWS account setup 
- One physical user = One AWS user 
- __Assign users to groups and assign permissions to groups__ 
- Create a __strong password policy__
- Use and enforce the use of Multi Factor Authentication (MFA) 
- Create and use Roles for giving permissions to AWS services 
- Use Access Keys for Programmatic Access (CLI / SDK) 
- Audit permissions of your account using IAM Credentials Report & IAM Access Advisor 
- Never share IAM users & Access Keys

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

user data script
```bash
#!/bin/bash

# install httpd (Linux 2 version)

yum update -y

yum install -y httpd

systemctl start httpd

systemctl enable httpd

echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```

EC2 Instance Types

EC2 Instances Purchasing Options





