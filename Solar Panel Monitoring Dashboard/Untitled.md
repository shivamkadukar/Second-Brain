Solar Panel Monitoring Dashboard

## IOT Core
- create thing
- download connect to device file
- replace pem and key file in IOTcore src
- update .start.sh

## ECR
- create ecr repository - `aws-workshop-ecr`
- add tags

## EC2
replicating a solar panel sending data
- launch instance
- ssh to the instance

```bash
sudo yum update

sudo yum install docker

sudo systemctl start docker
```

- add inline policy to allow all action over ecr

- login to aws cli with ecr
- pull image
- run container

## Lambda

- create lambda 
- user solar panel replica code
- update permission

- create lambda
- use iotCoreRuleAction lambda code
- update permission

back to iot core
create rule attach iotcoreruleaction as trigger
open ec2 connect run docker image 
check items being put to db

s3


API gateway
- websocket api gateway
- add connect, disconnect, sendMessage route

LAMBDA
 - create lambda
 - use solar_panel_data_stream code
 - attach api gateway full access to post message
 - attach full dynamodb full access to post message

Cognito
- authenticate and authorize tool
- dont need to create custom tool
- user pools - oauth2.0

user pool - app authentication
idenitfy pool - tempory access to aws service with aws sts

amplify
turn on acl in permission tab











