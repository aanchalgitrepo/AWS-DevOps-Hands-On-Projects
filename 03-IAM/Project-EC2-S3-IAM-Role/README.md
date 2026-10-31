# AWS Project — Access Amazon S3 from EC2 Using IAM Role

## Project Overview

This project demonstrates how to securely access an Amazon S3 bucket from an Amazon EC2 instance using an IAM Role.

Instead of storing AWS Access Keys and Secret Access Keys on the EC2 instance, an IAM Role provides temporary security credentials to the instance.

The project follows the **Principle of Least Privilege**, granting only the permissions required to perform specific S3 operations.

## Objectives

- Understand IAM Roles and IAM Policies.
- Attach an IAM Role to an EC2 instance.
- Configure permissions to access Amazon S3.
- List S3 buckets and objects.
- Upload files from EC2 to S3.
- Download files from S3 to EC2.
- Access AWS services without storing long-term access keys.

## AWS Services Used

| AWS Service | Purpose |
|---|---|
| Amazon EC2 | Virtual Linux server |
| Amazon S3 | Object storage |
| AWS IAM | Identity and access management |
| IAM Role | Provides temporary credentials to EC2 |
| IAM Policies | Define permissions for S3 operations |
| AWS CLI | Interact with AWS services through commands |

## Project Architecture

```text
             AWS Cloud
                 |
                 |
          EC2 Instance
          (Amazon Linux)
                 |
                 |
        EC2 Instance Profile
                 |
                 |
          IAM Role
    EC2-S3-Access-Role
                 |
                 |
        IAM Permission Policies
                 |
       +---------+---------+
       |         |         |
    List S3   Upload    Download
    Buckets   Objects   Objects
       |         |         |
       +---------+---------+
                 |
                 |
           Amazon S3
                 |
                 |
       aanchal-ec2-iam-s3-demo
                 |
                 |
              test.txt
```

## AWS Resource Details

| Resource | Name |
|---|---|
| EC2 Instance | Amazon Linux EC2 instance |
| IAM Role | `EC2-S3-Access-Role` |
| S3 Bucket | `aanchal-ec2-iam-s3-demo` |
| Test File | `test.txt` |
| AWS CLI | Installed on EC2 instance |

## Step 1 — Create an S3 Bucket

Created an S3 bucket with the following name:

```text
aanchal-ec2-iam-s3-demo
```

The bucket was used to test file listing, uploading, and downloading operations.

## Step 2 — Create an IAM Role for EC2

Created an IAM Role named:

```text
EC2-S3-Access-Role
```

The trusted entity was configured as an AWS service, and EC2 was selected as the use case.

### Trust Relationship

The trust policy allows EC2 to assume the IAM Role.

Example trust policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "ec2.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

## Step 3 — Attach IAM Role to EC2

Attached the `EC2-S3-Access-Role` to the EC2 instance.

This allows the EC2 instance to obtain temporary AWS credentials through its instance profile.

### Verify IAM Role

Command:

```bash
aws sts get-caller-identity
```

Output:

```json
{
  "UserId": "AROAXJTVG3W4K6VUQ3Z7U:i-034bc29a85bf7cfd9",
  "Account": "501683248568",
  "Arn": "arn:aws:sts::501683248568:assumed-role/EC2-S3-Access-Role/i-034bc29a85bf7cfd9"
}
```

Observation:

- The EC2 instance successfully assumed the IAM Role.
- The role name was `EC2-S3-Access-Role`.
- AWS CLI was using role-based temporary credentials.

## Step 4 — Create IAM Permission Policies

Created custom IAM policies to grant specific S3 permissions to the EC2 Role.

### Policy 1 — S3ListAllBucketsPolicy

**Purpose:** Allows EC2 to list all S3 buckets in the AWS account.

Policy JSON:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListAllMyBuckets",
      "Resource": "*"
    }
  ]
}
```

Permission:

- `s3:ListAllMyBuckets` — Allows listing bucket names.

### Policy 2 — S3ListSpecificBucketPolicy

**Purpose:** Allows EC2 to list objects inside a specific S3 bucket.

Policy JSON:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::aanchal-ec2-iam-s3-demo"
    }
  ]
}
```

Permission:

- `s3:ListBucket` — Allows listing objects inside the specified bucket.

### Policy 3 — EC2-S3-Custom-Policy

**Purpose:** Allows EC2 to upload objects to the specified S3 bucket and download objects from s3.

Policy JSON:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::aanchal-ec2-iam-s3-demo"
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Resource": "arn:aws:s3:::aanchal-ec2-iam-s3-demo/*"
    }
  ]
}
```

Permission:

- `s3:GetObject` — Allows downloading objects from the bucket.
- `s3:PutObject` — Allows uploading objects to the bucket.

## Step 5 — Attach Policies to IAM Role

Attached the custom IAM permission policies to:

```text
EC2-S3-Access-Role
```

The policies grant the following permissions:

| Policy Name | IAM Action | Purpose |
|---|---|---|
| S3ListAllBucketsPolicy | `s3:ListAllMyBuckets` | List all S3 buckets |
| S3ListSpecificBucketPolicy | `s3:ListBucket` | List objects in a specific bucket |
| EC2-S3-Custom-Policy | `s3:GetObject','s3:PutObject` | Upload and Download objects |

## Step 6 — Verify S3 Bucket Access

Initially, the following command returned an AccessDenied error:

```bash
aws s3 ls
```

Error:

```text
not authorized to perform: s3:ListAllMyBuckets
because no identity-based policy allows the s3:ListAllMyBuckets action
```

After attaching `S3ListAllBucketsPolicy` to the EC2 Role, the command executed successfully.

Command:

```bash
aws s3 ls
```

This verified that EC2 could list S3 buckets.

## Step 7 — List Objects Inside the S3 Bucket

Command:

```bash
aws s3 ls s3://aanchal-ec2-iam-s3-demo/
```

The command executed successfully.

Initially, the output was empty because the bucket did not contain any objects.

## Step 8 — Create a Test File on EC2

Created a file named `test.txt`.

Command:

```bash
echo "Hello AWS IAM and S3" > test.txt
```

Verified the file content:

```bash
cat test.txt
```

Output:

```text
Hello AWS IAM and S3
```

## Step 9 — Upload File from EC2 to S3

Uploaded the test file to the S3 bucket.

Command:

```bash
aws s3 cp test.txt s3://aanchal-ec2-iam-s3-demo/
```

Expected successful output:

```text
upload: ./test.txt to s3://aanchal-ec2-iam-s3-demo/test.txt
```

The upload operation was completed successfully.

## Step 10 — Verify Uploaded Object

Command:

```bash
aws s3 ls s3://aanchal-ec2-iam-s3-demo/
```

Expected object:

```text
test.txt
```

## Step 11 — Download File from S3 to EC2

After attaching `S3DownloadObjectPolicy`, the following steps can be used to verify the download permission.

Remove the local test file:

```bash
rm test.txt
```

Download the file from S3:

```bash
aws s3 cp s3://aanchal-ec2-iam-s3-demo/test.txt ./test.txt
```

Verify the downloaded content:

```bash
cat test.txt
```

Expected output:

```text
Hello AWS IAM and S3
```

## Step 12 — Final Verification Checklist

- [x] Created an S3 bucket.
- [x] Created an IAM Role for EC2.
- [x] Attached IAM Role to EC2.
- [x] Verified IAM Role using AWS STS.
- [x] Created S3ListAllBucketsPolicy.
- [x] Created S3ListSpecificBucketPolicy.
- [x] Created EC2-S3-Custom-Policy.
- [x] Listed S3 buckets from EC2.
- [x] Listed objects inside the S3 bucket.
- [x] Created a test file on EC2.
- [x] Uploaded the file to S3.
- [x] Downloaded the file from S3 and verified its contents.

## Troubleshooting

### Issue 1 — AccessDenied while listing S3 buckets

Error:

```text
not authorized to perform: s3:ListAllMyBuckets
```

Solution:

Created and attached `S3ListAllBucketsPolicy` to the EC2 Role.

### Issue 2 — Empty output while listing bucket objects

Command:

```bash
aws s3 ls s3://aanchal-ec2-iam-s3-demo/
```

Reason:

The bucket was initially empty.

Solution:

Created a test file and uploaded it to the bucket.

## Resource Cleanup

After completing the project, I removed the AWS resources created for this hands-on practice to avoid unnecessary charges.

### 1. Delete S3 Objects and Bucket

- Open the **Amazon S3** console.
- Select the bucket: `aanchal-ec2-iam-s3-demo`.
- Delete all objects inside the bucket, including `test.txt`.
- Delete the S3 bucket.

**Verification:** Confirm that the bucket no longer appears in the S3 bucket list.

### 2. Detach IAM Role from EC2

- Open the **Amazon EC2** console.
- Select the EC2 instance.
- Go to **Actions → Security → Modify IAM role**.
- Remove the attached IAM role, if it is still attached.
- Save the changes.

### 3. Delete IAM Role

- Open the **IAM** console.
- Navigate to **Roles**.
- Search for `EC2-S3-Access-Role`.
- Detach all attached policies.
- Delete the IAM role.

### 4. Delete Custom IAM Policies

The following custom policies were created for this project:

- `S3ListAllBucketsPolicy`
- `S3ListSpecificBucketPolicy`
- `EC2-S3-Custom-Policy`

Steps:

1. Open **IAM → Policies**.
2. Search for each custom policy.
3. Make sure the policy is not attached to any other IAM user, group, or role.
4. Delete the policies.

### 5. Terminate EC2 Instance

- Open the **EC2** console.
- Select the project EC2 instance.
- Choose **Instance state → Terminate (delete) instance**.
- Confirm the termination.

**Verification:** Wait until the instance state changes to `Terminated`.

> **Warning:** Terminating an EC2 instance is irreversible. Any data stored only on its instance store or non-persistent local storage may be lost. Save important files and screenshots before termination.

### 6. Check Other AWS Resources

After terminating the EC2 instance, check the following services for any resources created during the project:

| AWS Service | What to Check |
|---|---|
| EBS Volumes | Delete unused volumes after confirming they are not needed. |
| EBS Snapshots | Delete project snapshots if they are no longer required. |
| Elastic IPs | Release unused allocated Elastic IP addresses. |
| Network Interfaces | Check for unused network interfaces. |
| Load Balancers | Delete project load balancers, if created. |

Only delete resources that belong to this project and are no longer required. Do not delete AWS-managed or shared resources without checking their purpose.

### 7. Verify AWS Billing and Usage

- Open **Billing and Cost Management**.
- Review the **Bills** section.
- Check Free Tier / Free Plan usage, where available.
- Review the selected AWS Region and other regions if you created resources there.

**Important:** Deleting project resources helps prevent further resource-related charges, but it does not automatically remove charges already incurred or charges from other resources.

### Cleanup Status

- [x] S3 object deleted
- [x] S3 bucket deleted
- [x] IAM role detached from EC2
- [x] Custom policies detached from the role
- [x] IAM role deleted
- [x] Custom IAM policies deleted
- [x] EC2 instance terminated
- [x] EBS volumes checked
- [x] EBS snapshots checked
- [x] Elastic IPs checked
- [x] Billing and usage reviewed

**Note:** Update the remaining checkboxes after verifying each cleanup step in the AWS Console.

## Security Best Practices

- Do not store AWS Access Keys or Secret Access Keys on EC2.
- Use IAM Roles to provide temporary credentials to EC2.
- Follow the Principle of Least Privilege.
- Grant only the permissions required by the application.
- Restrict S3 permissions to specific bucket ARNs wherever possible.
- Never upload AWS credentials to GitHub.
- Review IAM policies and remove unnecessary permissions.

## Key Concepts Learned

- IAM Users and IAM Roles are different.
- EC2 uses an IAM Role through an instance profile.
- IAM Roles provide temporary credentials.
- IAM Policies define what actions are allowed or denied.
- `s3:ListAllMyBuckets` and `s3:ListBucket` have different purposes.
- `s3:PutObject` is used for uploading objects.
- `s3:GetObject` is used for reading and downloading objects.
- AWS CLI can access S3 through an EC2 IAM Role without manually configuring access keys.

## Conclusion

In this project, I learned how to securely connect an Amazon EC2 instance to Amazon S3 using an IAM Role.

I created custom IAM policies to control S3 permissions and successfully listed S3 buckets, listed bucket contents, and uploaded a file from EC2 to S3.

This project helped me understand IAM Roles, IAM Policies, temporary credentials, AWS CLI, and the Principle of Least Privilege.

## Screenshots

Add your practical screenshots in this section:

1. EC2 Instance details showing IAM Role.
2. IAM Role details — `EC2-S3-Access-Role`.
3. IAM Role permissions and attached policies.
4. Successful `aws sts get-caller-identity` output.
5. Successful `aws s3 ls` output.
6. Successful S3 bucket listing.
7. Test file creation using `cat test.txt`.
8. Successful file upload output.
9. S3 bucket showing `test.txt`.
10. Successful file download and content verification.

---

**Note:** Never include AWS Secret Access Keys, passwords, private keys, or other credentials in screenshots or GitHub documentation.
