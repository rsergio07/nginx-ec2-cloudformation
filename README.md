# nginx-ec2-cloudformation

This repository contains an AWS CloudFormation template to deploy a secure and scalable Nginx web server on an EC2 instance.

## Getting Started

### Prerequisites

Before deploying the CloudFormation template, make sure you have the following prerequisites:

- AWS CLI installed and configured with the necessary credentials.
- An existing EC2 Key Pair to enable SSH access.

### Deployment

To deploy the Nginx EC2 instance, follow these steps:

1. Clone the repository

```bash
git clone https://github.com/your-username/nginx-ec2-cloudformation.git
cd nginx-ec2-cloudformation
```
2. Deploy the CloudFormation stack using the AWS CLI:

```bash
aws cloudformation create-stack \
  --stack-name MyNginxStack \
  --template-body file://nginx-ec2-template.yaml \
  --parameters ParameterKey=KeyName,ParameterValue=YourKeyName
```
Replace MyNginxStack with your desired stack name and YourKeyName with your existing EC2 Key Pair name.

3. Retrieve the public IP address of the EC2 instance:

```bash
aws cloudformation describe-stacks --stack-name MyNginxStack --query 'Stacks[0].Outputs'
```

4. Access the Nginx web server using the provided public IP address.

### Cleanup

To delete the CloudFormation stack and associated resources, run:

```bash
aws cloudformation delete-stack --stack-name MyNginxStack
```

### License

This project is licensed under the [MIT License](LICENSE). See the [LICENSE](LICENSE) file for details.

If you have any questions, feel free to reach out.

---



