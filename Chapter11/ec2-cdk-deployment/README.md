# AWS CDK EC2 Instance Deployment

This repository contains an AWS CDK script to provision an EC2 instance within the default VPC of your AWS account using Amazon Linux 2 AMI. The script specifically defines a `t3.micro` instance in the default VPC and assigns the latest Amazon Linux 2 AMI to it.

## Prerequisites

- AWS account with appropriate permissions.
- The AWS CLI installed and configured with appropriate permissions.For detailed installation instructions, please refer to the [README.md file](../../Prerequesites/AWSCLI-Installation/README.md)
- Node.js installed (required for the AWS CDK).
- AWS CDK installed. If you haven't installed it yet, you can install it using `npm install -g aws-cdk`.
- Python environment setup, including the AWS CDK for Python (`aws-cdk.aws-ec2`).

## Deployment Steps

1. **Clone the Repository:**

   Clone this repository to your local machine to get the CDK script provided.

   ```
   git clone [repository-url]
   cd [repository-directory]
   ```

2. **Install Dependencies:**

   Navigate to the script directory and install the necessary CDK libraries:

   ```
   pip install aws-cdk.core aws-cdk.aws-ec2
   ```

3. **Deploy the Stack:**

   Use the AWS CDK to deploy the stack defined in the script:

   ```
   cdk deploy
   ```

   This command will synthesize the CloudFormation template from the provided CDK script (`MyEc2InstanceStack`) and deploy it to your AWS account.

4. **Verify the Deployment:**

   After the deployment is complete, verify the creation of the EC2 instance in the AWS Management Console under the EC2 service.

## Cleanup

To avoid ongoing charges, remember to destroy the resources once you are done:

```
cdk destroy
```

This command will remove the resources created by the CDK script (`MyEc2InstanceStack`) from your AWS account.
