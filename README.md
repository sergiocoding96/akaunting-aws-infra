# Akaunting AWS Infrastructure

This repository contains CloudFormation templates for deploying [Akaunting](https://akaunting.com/) - an open source accounting software - on AWS.

## Current Status

We have successfully:
- Created a CloudFormation template for deploying Akaunting on AWS
- Configured a t2.micro EC2 instance with proper security group settings (HTTP, HTTPS, SSH)
- Implemented a UserData script to install and configure Apache, PHP, and MariaDB
- Created IAM roles for the EC2 instance to support SSM Session Manager

## Current Issues

Initial deployment encountered connectivity issues:
- The CloudFormation stack completed successfully
- The EC2 instance is running but not responding to HTTP requests
- We cannot access the instance via SSH due to the lack of a key pair in the initial template
- SSM Session Manager access is configured but unavailable due to permission issues

## Latest Updates

- Added SSH KeyPair parameter to the CloudFormation template to enable troubleshooting
- Updated the security group to allow SSH access (port 22)

## Next Steps

1. Terminate the current CloudFormation stack
2. Deploy a new stack using the updated template with an existing SSH key pair
3. Use SSH to access the EC2 instance and debug the installation:
   - Check Apache logs and service status
   - Verify MariaDB configuration
   - Examine the UserData script execution logs
4. Complete the Akaunting setup process
5. Document the finalized solution

## Deployment Instructions

To deploy the CloudFormation stack:

1. Log in to the AWS Management Console
2. Navigate to CloudFormation
3. Create a new stack with the template from this repository
4. Provide the required parameters:
   - DBPassword: Password for the MariaDB database
   - EnvironmentType: development, staging, or production
   - KeyName: Name of an existing EC2 KeyPair for SSH access

Once deployed, access the Akaunting installation via the URL provided in the stack outputs.

## Resources

- [Akaunting Official Website](https://akaunting.com/)
- [AWS CloudFormation Documentation](https://docs.aws.amazon.com/cloudformation/)