# Lab-04-Explore IAM Roles

## Objective

To understand IAM roles and how AWS services use roles to access AWS resources securely.

## What is an IAM Role?

An IAM role is an AWS identity that provides temporary security credentials to trusted entities.

IAM roles are commonly used by AWS services such as EC2, Lambda, and ECS.

## What is a Trust Policy?

A trust policy defines which entities are allowed to assume an IAM role.

For example, an EC2 trust policy allows the EC2 service to assume a particular role.

## Practical Steps

1. Open IAM.
2. Navigate to Roles.
3. Click Create role.
4. Select AWS service.
5. Choose EC2.
6. Create a role named `EC2-S3-Access-Role`.
7. Explore its trust relationship.
8. Review the role's permissions.

## Key Concepts Learned

- What is an IAM role?
- IAM role vs IAM user.
- Temporary security credentials.
- Trust policies.
- AssumeRole.
- AWS service roles.

## Conclusion

In this lab, I learned how IAM roles provide temporary permissions to trusted AWS services without requiring permanent access keys.
