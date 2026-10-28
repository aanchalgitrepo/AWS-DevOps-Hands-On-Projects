# 09 — Explore IAM Roles

## Objective
To understand AWS IAM Roles, trust relationships, permissions policies, and how IAM Roles are used by EC2 instances.

## Services Used
- AWS Identity and Access Management (IAM)
- Amazon EC2 (conceptual use case)

## What is an IAM Role?
An IAM Role is an AWS identity that provides temporary credentials to an authorized user or AWS service.

IAM Roles help applications access AWS resources without storing long-term access keys on servers.

## Real-World Use Case
An EC2 instance needs to read files from an S3 bucket. An IAM Role can provide the required permissions without storing AWS access keys on the EC2 instance.

## Steps Performed
1. Opened the AWS Management Console.
2. Navigated to IAM → Roles.
3. Explored the Create role workflow.
4. Selected AWS service as the trusted entity.
5. Selected EC2 as the use case.
6. Reviewed permissions policies.
7. Created an IAM Role (if completed).
8. Examined the role's permissions, trust relationship, and ARN.

## Key Concepts Learned

### 1. Trust Relationship
Defines which identities or AWS services can assume a role.

### 2. Permissions Policy
Defines which AWS actions are allowed or denied.

### 3. Role ARN
The unique Amazon Resource Name used to identify an IAM Role.

### 4. EC2 Instance Profile
A mechanism used to pass an IAM Role to an EC2 instance.

## Security Best Practices
- Follow the principle of least privilege.
- Never store AWS access keys directly in application code.
- Review trust relationships and attached policies.
- Avoid granting unnecessary permissions.

## Cost and Cleanup
IAM Roles do not have a separate charge for creation.
No EC2 instance was launched for this exploration-only lab.

## Screenshots
Add screenshots showing:
- IAM Roles page
- EC2 trusted entity selection
- Permissions review
- Created role details
- Trust relationship
- Role ARN

## Result
Understood the purpose of IAM Roles and how trust relationships and permissions control access to AWS resources.

## Interview Questions
1. What is an IAM Role?
2. What is the difference between an IAM User and an IAM Role?
3. What is a trust relationship?
4. What is the difference between a trust policy and a permissions policy?
5. Why should an EC2 instance use an IAM Role?
6. What is an instance profile?
7. What is the principle of least privilege?

## Official References
- https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html
- https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html
