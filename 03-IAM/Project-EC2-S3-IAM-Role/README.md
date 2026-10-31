# Project - Access Amazon S3 from EC2 Using IAM Role

## Project Overview

This project demonstrates how to securely access an Amazon S3 bucket from an Amazon EC2 instance using an IAM role.

The project follows AWS security best practices by avoiding hardcoded AWS access keys in application code or on the EC2 instance.

## Objective

To establish secure communication between an EC2 instance and an S3 bucket using IAM roles and custom IAM policies.

## AWS Services Used

- Amazon EC2
- Amazon S3
- AWS IAM
- AWS CLI

## Architecture

```text
AWS Account
    |
    v
IAM Role
    |
    v
Custom S3 Policy
    |
    v
EC2 Instance
    |
    v
AWS CLI
    |
    v
Amazon S3 Bucket
```

## Implementation Steps

### Step 1 — Create S3 Bucket

Created a private S3 bucket to store project files.

### Step 2 — Create IAM Policy

Created a custom IAM policy with the following permissions:

- s3:ListBucket
- s3:GetObject
- s3:PutObject

The permissions were restricted to the specific S3 bucket.

### Step 3 — Create IAM Role

Created an IAM role named `EC2-S3-Access-Role`.

Configured EC2 as the trusted service and attached the custom S3 policy.

### Step 4 — Launch EC2 Instance

Launched an Amazon Linux EC2 instance and associated the IAM role with it.

### Step 5 — Verify IAM Role

Executed the following command:

```bash
aws sts get-caller-identity
```

Verified that the EC2 instance was using the assumed IAM role.

### Step 6 — Access S3 Using AWS CLI

Listed available S3 buckets:

```bash
aws s3 ls
```

Listed objects in the project bucket:

```bash
aws s3 ls s3://aanchal-ec2-iam-s3-demo
```

### Step 7 — Upload File to S3

Created a test file:

```bash
echo "Hello AWS IAM Role" > test.txt
```

Uploaded the file:

```bash
aws s3 cp test.txt s3://aanchal-ec2-iam-s3-demo/
```

### Step 8 — Download File from S3

```bash
aws s3 cp s3://aanchal-ec2-iam-s3-demo/test.txt ./test.txt
```

## Security Best Practices

- Avoid hardcoding AWS access keys.
- Use IAM roles for EC2 applications.
- Follow the least privilege principle.
- Use custom IAM policies with limited permissions.
- Keep S3 buckets private.
- Enable MFA for privileged IAM users.
- Regularly review IAM permissions.

## Project Outcome

Successfully accessed an Amazon S3 bucket from an EC2 instance using an IAM role without manually configuring permanent AWS access keys.

## Screenshots

Add the following screenshots:

1. S3 Bucket Created
2. Custom IAM Policy
3. IAM Role Created
4. IAM Role Attached to EC2
5. EC2 Instance Running
6. AWS STS Get Caller Identity Output
7. S3 Bucket Listing from EC2
8. File Upload to S3
9. File Download from S3

## Conclusion

This project demonstrates secure AWS service-to-service communication using IAM roles.

It also demonstrates the practical implementation of IAM policies, EC2 instance profiles, temporary credentials, and the principle of least privilege.
