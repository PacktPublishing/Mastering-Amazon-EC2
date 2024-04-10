# AWS CloudFormation Web Server Deployment

This repository contains an AWS CloudFormation template to provision a simple web server on AWS EC2. The template creates an EC2 instance and configures a security group to allow HTTP access.

## Prerequisites

- An AWS account.
- The AWS CLI installed and configured with appropriate permissions.For detailed installation instructions, please refer to the [README.md file](../../Prerequesites/AWSCLI-Installation/README.md)
- An existing key pair in your AWS account (`my-aws-key-pair`).

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
   aws cloudformation create-stack --stack-name WebServerStack --template-body file://ec2_web_server_template.yaml --parameters ParameterKey=KeyName,ParameterValue=my-aws-key-pair
   ```

   Replace [repository-url] with the URL of your repository and [repository-directory] with the name of the directory into which the repository was cloned.

   Ensure the template file name (`ec2_web_server_template.yaml`) matches the name of the template file in your repository.

3. **Verify the Stack Creation:**

   Check the AWS CloudFormation console to ensure the stack is being created successfully. You can also use the following AWS CLI command to describe the stack's status:

   ```
   aws cloudformation describe-stacks --stack-name WebServerStack
   ```

## Additional Notes

- The EC2 instance is provisioned with a `t2.micro` instance type, which is eligible for the AWS free tier.
- The security group allows HTTP traffic on port 80 from any IP address. Modify the `CidrIp` value in the template for more restrictive access.
- Remember to delete the stack when it's no longer needed to avoid incurring unnecessary costs:

  ```
  aws cloudformation delete-stack --stack-name WebServerStack
  ```

For more details on AWS CloudFormation and AWS CLI, visit the [AWS CloudFormation User Guide](https://docs.aws.amazon.com/cloudformation/index.html) and the [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html).
