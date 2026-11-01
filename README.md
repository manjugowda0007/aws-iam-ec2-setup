AWS IAM and EC2 Setup: Users, Roles, Policies, and an EC2 Instance

A practical AWS project in which I explored access management using AWS Identity and Access Management (IAM) and launched an Amazon EC2 instance. This project covers creating IAM users, roles, and policies, along with configuring and launching a virtual server.

Table of Contents

Project Overview

Services Used

Prerequisites

Implementation Steps

Screenshots

Security Best Practices

Key Learnings

Author

Project Overview

Managing who can access AWS resources and what actions they can perform is an important part of cloud security. In this project, I worked on the following tasks:

Created an IAM user for regular AWS access.

Created an IAM role for <EC2 / another service>.

Attached IAM policies to provide the required permissions.

Launched an Amazon EC2 instance.

Project Goal: Understand how IAM identities, permissions, and EC2 compute resources work together within AWS.

Services Used

Service

Purpose

AWS IAM

Managing users, roles, and policies for access control

Amazon EC2

Launching and managing a virtual server

Prerequisites

An active AWS account

A web browser

Basic understanding of cloud computing concepts

Implementation Steps

1. Create an IAM User

Opened the IAM Console, selected Users, and clicked Create user.

Created the user <user-name>.

Configured <console access / programmatic access>.

Assigned permissions using <group name / policy name>.

2. Configure IAM Policies

Opened Policies in the IAM Console.

Selected <AWS managed policy name> or created a custom policy named <policy-name>.

Configured the policy to allow: <describe what it allows, e.g. read-only access to S3>.

3. Create an IAM Role

Opened Roles in the IAM Console and selected Create role.

Selected the trusted entity: <AWS service, e.g. EC2>.

Created the role <role-name> and attached the policy <policy-name>.

4. Launch an EC2 Instance

Opened the EC2 Console and selected Launch instance.

Name: <instance-name>

AMI: <e.g. Amazon Linux 2023>

Instance type: <e.g. t2.micro / t3.micro>

Key pair: <key-pair-name>

Security group: <describe inbound rules, e.g. SSH on port 22 from my IP>

IAM role attached to the instance: <role-name, or remove this line if you did not attach one>

Launched the instance and waited until its state changed to Running.

Screenshots

IAM Users

IAM Users (View image)

IAM Roles

IAM Roles (View image)

IAM Policies

IAM Policies (View image)

EC2 Instance

EC2 Instance (View image)

Security Best Practices

Avoid using the AWS root account for everyday tasks; use IAM users or roles instead.

Apply the principle of least privilege by granting only the permissions that are needed.

Prefer IAM roles over long-term access keys for AWS services such as EC2.

Enable multi-factor authentication (MFA) for users with console access.

Limit SSH access in the security group to your own IP address rather than 0.0.0.0/0.

Never upload access keys, secret keys, or .pem files to GitHub.

Stop or terminate EC2 instances when they are no longer required to help avoid unnecessary charges.

Key Learnings

Understanding the differences between IAM users, roles, and policies.

Learning how IAM policies control access to AWS resources.

Creating and configuring an EC2 instance.

Understanding why least-privilege access is important for cloud security.

Author

Manju Gowda
GitHub: manjugowda0007
