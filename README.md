# Interacting-with-AWS-CLI


##  Overview
This project demonstrates how to manage AWS infrastructure using the AWS CLI.  
It includes creating EC2 instances, configuring IAM users and groups, setting up security groups, and managing SSH access.

---

## Technologies Used
- AWS EC2
- AWS IAM (Users, Groups, Policies)
- AWS CLI
- SSH (OpenSSH)
- Windows CMD

---

## Architecture
- VPC with public subnet
- EC2 instance running Amazon Linux
- Security Group with SSH (port 22) and custom ports
- IAM user-based access control
- Key Pair authentication for SSH

---

## IAM Setup

### Created Resources:
- IAM User: `MyUserCli`
- IAM Group: `MyGroupCli`
- IAM Policy: `AllowChangePassword`

### Policy Purpose:
Allows IAM users to change their own password securely.

---

## IAM Policy Example

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowChangeOwnPassword",
      "Effect": "Allow",
      "Action": "iam:ChangePassword",
      "Resource": "arn:aws:iam::*:user/${aws:username}"
    }
  ]
}
