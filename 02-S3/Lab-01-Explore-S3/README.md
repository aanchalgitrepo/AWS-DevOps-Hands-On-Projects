
# Lab 01: Explore Amazon S3 Buckets

## Objective
To understand Amazon S3 and explore the S3 console.

## AWS Service
Amazon Simple Storage Service (S3)


## Concepts Learned

### 1. What is Amazon S3?

Amazon Simple Storage Service (Amazon S3) is an object storage service provided by AWS. It allows users to store and retrieve data from anywhere over the internet.

S3 is highly scalable, durable, and secure. It can store different types of data, such as images, videos, documents, backups, log files, and website files.

**Real-world Example:**
A company can use Amazon S3 to store customer documents, application backups, images, and website content.

### 2. What is an S3 Bucket?

An S3 bucket is a logical container used to store objects (files) in Amazon S3.

Every object must be stored inside a bucket. A bucket is created in a specific AWS Region and its name must be globally unique across all AWS accounts within the AWS partition.

**Key Points:**
- A bucket stores objects (files).
- Each bucket has a globally unique name.
- A bucket is created in a selected AWS Region.
- A bucket can contain multiple objects.
- Bucket permissions and security settings control access to stored data.

**Real-world Example:**
A company can create a bucket named `company-backup-storage` to store database backups and important documents.

### 3. What is an S3 Object?

An S3 object is an individual file stored inside an S3 bucket.

An object consists of three main components:

- **Key:** The unique name used to identify an object within a bucket.
- **Data:** The actual content of the file.
- **Metadata:** Additional information about the object, such as content type, size, and last modified date.

**Example:**

Suppose an S3 bucket contains the following objects:

```text
company-backup-storage/
│
├── documents/
│   ├── employee.pdf
│   └── report.docx
│
├── images/
│   ├── logo.png
│   └── profile.jpg
│
└── backups/
    └── database-backup.sql
```

Here:
- `employee.pdf` is an S3 object.
- `logo.png` is an S3 object.
- `database-backup.sql` is an S3 object.
- `documents/`, `images/`, and `backups/` are key prefixes that organize objects.

### 4. What are S3 Bucket Naming Rules?

Amazon S3 bucket names must follow specific naming conventions.

**Important Rules:**

1. Bucket names must be between 3 and 63 characters long.
2. Bucket names must be globally unique within the AWS partition.
3. Bucket names must contain only lowercase letters, numbers, hyphens (-), and periods (.).
4. Bucket names must start and end with a letter or number.
5. Bucket names cannot contain uppercase letters or underscores (_).
6. Bucket names must not be formatted as an IP address.
7. Bucket names cannot contain consecutive periods.
8. Bucket names must follow AWS reserved naming restrictions.

**Valid Bucket Names:**

```text
my-company-backups
aws-learning-bucket-2026
aanchal-s3-practice
website-storage-123
```

**Invalid Bucket Names:**

```text
MyBucket
my_bucket
ab
192.168.1.1
```

**Note:** Bucket names are globally unique, so if another AWS user has already created a bucket with your chosen name, you must choose a different name.

### 5. What are AWS Regions?

An AWS Region is a separate geographical area where AWS provides its cloud services.

AWS has multiple Regions around the world. Each Region contains multiple Availability Zones.

When creating an S3 bucket, you must select an AWS Region.

**Examples of AWS Regions:**

| Region Name | Region Code |
|---|---|
| Mumbai | ap-south-1 |
| Hyderabad | ap-south-2 |
| Singapore | ap-southeast-1 |
| Sydney | ap-southeast-2 |
| Frankfurt | eu-central-1 |
| Stockholm | eu-north-1 |
| N. Virginia | us-east-1 |

**Why is Region Selection Important?**

- It helps reduce network latency by choosing a geographically suitable Region.
- It determines where your data is stored.
- AWS service availability can vary between Regions.
- Storage and data transfer pricing can vary by Region.
- Data residency and compliance requirements may affect Region selection.

**Real-world Example:**

If a company mainly serves customers in India, it may choose the Mumbai Region (`ap-south-1`) to keep its application infrastructure closer to its users.

### 6. What are the Basic Use Cases of Amazon S3?

Amazon S3 is used for many storage-related purposes.

**Common Use Cases:**

1. **Backup and Restore:** Store important files, database backups, and recovery data.

2. **Static Website Hosting:** Store HTML, CSS, JavaScript, and image files used by static websites.

3. **Media Storage:** Store images, audio files, and videos.

4. **Log Storage:** Store application logs, server logs, and AWS service logs.

5. **Data Lakes:** Store large amounts of structured and unstructured data for analytics.

6. **Application Storage:** Store documents, user uploads, and other application files.

7. **Disaster Recovery:** Maintain backup copies of important business data.

**Real-world Example:**

An e-commerce company can use Amazon S3 to store product images, customer documents, website files, and application backups.

## Summary

Amazon S3 is a scalable object storage service used to store and retrieve data.

- A Bucket is a container for storing objects.
- An Object is an individual file stored in a bucket.
- A Key identifies an object within a bucket.
- AWS Regions determine where S3 bucket data is stored.
- Bucket naming rules ensure valid and globally unique bucket names.
- S3 supports backups, static website hosting, media storage, and data analytics.

## Practical Steps
1. Signed in to the AWS Management Console.
2. Opened Amazon S3.
3. Navigated to the Buckets section.
4. Observed the bucket list and available options.
5. Reviewed the relationship between buckets and objects.

## Key Learnings
- S3 is an object storage service.
- A bucket stores objects.
- Each bucket is created in a selected AWS Region.
- Bucket names must be globally unique.
- S3 can store website files, documents, images and backups.

## Screenshots
- `01-s3-buckets-page.png`
- `02-s3-bucket-observation.png`

## Security Notes
- Keep private data private.
- Do not enable public access unnecessarily.
- Never upload credentials or secret keys.
- Avoid modifying existing buckets without permission.

## Cost Notes
Exploring the S3 console does not require creating
a new bucket. Storage and other operations may incur
charges depending on usage and pricing eligibility.

## Result
Explored the Amazon S3 console and documented
the basic concepts of S3 buckets and objects.
