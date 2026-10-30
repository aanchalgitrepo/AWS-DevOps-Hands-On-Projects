# Lab-05-Explore Bucket Policies and Access Control

## Objective

The objective of this lab is to understand Amazon S3 Bucket Policies and access control mechanisms. I explored how bucket policies control access to S3 resources and how permissions can be used to protect objects.

## What is an S3 Bucket Policy?

An S3 Bucket Policy is a JSON-based resource policy attached to an Amazon S3 bucket.

It defines who can access the bucket and what actions they are allowed or denied to perform.

### Key Features

- Controls access to S3 buckets and objects.
- Allows or denies specific actions.
- Supports IAM users, roles, accounts, and public access policies.
- Helps secure sensitive data.
- Provides fine-grained access control.

## What is Access Control?

Access Control is a security mechanism that determines who can access AWS resources and what actions they can perform.

### Types of S3 Access Control

| Access Control | Description |
|---|---|
| IAM Policies | Manage permissions for IAM users and roles. |
| Bucket Policies | Control access at the S3 bucket level. |
| Block Public Access | Prevents public access to S3 buckets and objects. |
| ACLs | Provide legacy access permissions for buckets and objects. |

## Practical Implementation

### Step 1: Open S3 Bucket Permissions

1. Open the AWS Management Console.
2. Navigate to Amazon S3.
3. Select an existing bucket.
4. Open the Permissions tab.
5. Explore the bucket permission settings.

### Step 2: Explore Block Public Access

1. Locate Block Public Access settings.
2. Check all four public access protection settings.
3. Keep all settings enabled.
4. Understand how these settings prevent accidental public exposure.

### Step 3: Create a Bucket Policy

1. Navigate to the Bucket Policy section.
2. Click Edit.
3. Add a JSON policy.
4. Replace the bucket name with your actual bucket name.
5. Save the policy.

### Step 4: Test Access Control

Applied a bucket policy with an explicit Deny effect for the `s3:DeleteObject` action.

This policy prevents users from deleting objects from the bucket.

**Expected Result:** An Access Denied error when attempting to delete an object.

### Step 5: Cleanup

Removed the temporary bucket policy after testing to restore the previous permissions.

## Sample Bucket Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyObjectDeletion",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:DeleteObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}
```

## Important Concepts Learned

- What is an S3 Bucket Policy?
- What is Access Control?
- Difference between IAM Policy and Bucket Policy.
- What is Block Public Access?
- Difference between Allow and Deny.
- How to control access to S3 objects.
- How explicit Deny affects AWS permissions.
- Importance of securing S3 buckets.

## Screenshots

| Screenshot | Description |
|---|---|
| 01-bucket-permissions.png | S3 bucket permissions tab |
| 02-block-public-access.png | Block Public Access settings |
| 03-bucket-policy-editor.png | Bucket policy editor |
| 04-deny-delete-policy.png | Sample JSON bucket policy |
| 05-access-denied-result.png | Access Denied test result |

## Key Learnings

Through this lab, I learned how Amazon S3 Bucket Policies work and how access permissions can be controlled using JSON policies.

I also understood the importance of Block Public Access and explicit Deny permissions for protecting S3 objects.

## Conclusion

Successfully explored Amazon S3 Bucket Policies and Access Control.

Learned how to apply a bucket policy, test object deletion restrictions, and restore the original bucket permissions after completing the practical.

