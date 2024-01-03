# nginx-ec2-cloudformation

This repository contains an AWS CloudFormation template to deploy a secure and scalable Nginx web server on an EC2 instance.

## Getting Started

### Prerequisites

Before deploying the CloudFormation template, make sure you have the following prerequisites:

- AWS CLI installed and configured with the necessary credentials.
- An existing EC2 Key Pair to enable SSH access.

### Deployment

To deploy the Nginx EC2 instance, follow these steps:

```bash
git clone https://github.com/your-username/nginx-ec2-cloudformation.git
cd nginx-ec2-cloudformation

aws cloudformation create-stack \
  --stack-name MyNginxStack \
  --template-body file://nginx-ec2-template.yaml \
  --parameters ParameterKey=KeyName,ParameterValue=YourKeyName

aws cloudformation wait stack-create-complete --stack-name MyNginxStack

aws cloudformation describe-stacks --stack-name MyNginxStack --query 'Stacks[0].Outputs'
