- The AWS CLI installed and configured with appropriate permissions.

  1. **Install the AWS CLI:**

     - For Windows, download and run the [AWS CLI MSI installer](https://aws.amazon.com/cli/).
     - For macOS and Linux, use the following command:

       ```
       curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
       sudo installer -pkg AWSCLIV2.pkg -target /
       ```

       Note: This command is for macOS. Linux users can find installation instructions in the [AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).

  2. **Configure the AWS CLI:**

     Run the following command and follow the on-screen prompts to configure the AWS CLI with your credentials:

     ```
     aws configure
     ```

     You'll need to provide your AWS Access Key ID, Secret Access Key, region, and output format. These details are associated with your AWS account and can be obtained from the AWS Management Console.

  3. **Verify the Installation:**

     Ensure that the AWS CLI is installed correctly by running:

     ```
     aws --version
     ```

     If the installation was successful, you should see the version of the AWS CLI displayed.
