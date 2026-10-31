# Lab-06-Apply Least Privilege Principle

## Objective

To understand and implement the principle of least privilege in AWS IAM.

## What is Least Privilege?

The principle of least privilege means granting users and AWS services only the minimum permissions required to perform their tasks.

## Example

Suppose a developer needs to read files from an S3 bucket.

Instead of granting full S3 access, we provide only:

- s3:ListBucket
- s3:GetObject

This prevents unnecessary upload, modification, and deletion permissions.

## Why is Least Privilege Important?

- Improves AWS account security.
- Reduces unauthorized access.
- Minimizes security risks.
- Limits accidental resource modifications.
- Follows AWS security best practices.

## Practical Steps

1. Create a custom IAM policy.
2. Allow only required S3 actions.
3. Restrict access to a specific S3 bucket.
4. Attach the policy to the appropriate IAM role or user.
5. Verify allowed and denied actions.

## Key Concepts Learned

- Least privilege principle.
- IAM permission boundaries of access.
- Resource-level permissions.
- Restricted S3 access.
- AWS security best practices.

## Conclusion

In this lab, I learned how to apply least privilege by granting only the permissions required for a specific task.
