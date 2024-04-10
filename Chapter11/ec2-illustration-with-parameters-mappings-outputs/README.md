# AWS CloudFormation EC2 Instance Deployment

This repository contains an AWS CloudFormation template for provisioning a simple EC2 instance in AWS, with the ability to dynamically select the instance type and region-specific AMIs.

## Prerequisites

- An AWS account.
- The AWS CLI installed and configured with appropriate permissions.For detailed installation instructions, please refer to the [README.md file](../../Prerequesites/AWSCLI-Installation/README.md)

## Deployment Steps

1. **Clone the Repository:**

   Clone this repository to your local machine to get the template.

   ```
   git clone [repository-url]
   cd [repository-directory]
   ```

2. **Deploy the CloudFormation Stack:**

   Deploy the template using the AWS CLI with the following command:

   ```
   aws cloudformation create-stack --stack-name MyDynamicEC2Instance --template-body file://ec2-parameters-mapping-outputs.yaml --parameters ParameterKey=InstanceTypeParameter,ParameterValue=[desired-instance-type]
   ```

   Replace [repository-url] and [repository-directory] with your repository details. [desired-instance-type] should be replaced with `t2.micro`, `m3.medium`, or `m3.large` according to your needs.

   Ensure the template file name (`dynamic_ec2_template.yaml`) matches the name of your template file.

3. **Verify the Stack Creation:**

   Monitor the stack creation process in the AWS CloudFormation console or use the following command to check the creation status:

   ```
   aws cloudformation describe-stacks --stack-name MyDynamicEC2Instance
   ```

## Outputs

Once the stack is successfully created, retrieve the instance ID and public DNS name:

- **Instance ID:** Get the ID of the created EC2 instance using:

  ```
  aws cloudformation describe-stacks --stack-name MyDynamicEC2Instance --query "Stacks[0].Outputs[?OutputKey=='InstanceID'].OutputValue" --output text
  ```

- **Instance DNS Name:** Retrieve the public DNS of the EC2 instance with:

  ```
  aws cloudformation describe-stacks --stack-name MyDynamicEC2Instance --query "Stacks[0].Outputs[?OutputKey=='InstanceDNSName'].OutputValue" --output text
  ```

Refer to the [AWS CloudFormation User Guide](https://docs.aws.amazon.com/cloudformation/index.html) and the [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html) for more information.
