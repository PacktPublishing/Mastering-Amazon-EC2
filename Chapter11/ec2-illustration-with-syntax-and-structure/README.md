# AWS CloudFormation Example Template Deployment

This repository contains an AWS CloudFormation template to provision a simple EC2 instance on AWS. The template includes parameters to customize the instance type and outputs the IP address of the created instance.

## Prerequisites

- An AWS account.
- The AWS CLI installed and configured with appropriate permissions.For detailed installation instructions, please refer to the [README.md file](../../Prerequesites/AWSCLI-Installation/README.md)

## Deployment Steps

1. **Clone the Repository:**

   Clone this repository to your local machine to get started.

   ```
   git clone [repository-url]
   cd [repository-directory]
   ```

2. **Deploy the CloudFormation Stack:**

   Use the following AWS CLI command to deploy the stack:

   ```
   aws cloudformation create-stack --stack-name ExampleEC2Instance --template-body file://ec2-syntax-and-structure.yaml --parameters ParameterKey=InstanceTypeParameter,ParameterValue=t2.micro
   ```

   Replace `[repository-url]` with the URL of your repository and `[repository-directory]` with the name of the directory into which the repository was cloned. Adjust the `ParameterValue` if you wish to specify a different instance type.

   Ensure the template file name (`ec2-syntax-and-structure.yaml`) matches the name of the template file in your repository.

3. **Verify the Stack Creation:**

   Check the AWS CloudFormation console to ensure the stack is being created successfully. You can also use the following AWS CLI command to describe the stack's status:

   ```
   aws cloudformation describe-stacks --stack-name ExampleEC2Instance
   ```

## Outputs

After the stack creation is complete, you can retrieve the IP address of the EC2 instance by using the following command:

```
aws cloudformation describe-stacks --stack-name ExampleEC2Instance --query "Stacks[0].Outputs[0].OutputValue"
```

This command will return the public IP address of the created EC2 instance.

For more details on AWS CloudFormation and AWS CLI, visit the [AWS CloudFormation User Guide](https://docs.aws.amazon.com/cloudformation/index.html) and the [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html).
