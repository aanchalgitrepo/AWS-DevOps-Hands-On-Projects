# Lab-03-Upload, Download and Delete Objects in Amazon S3

## Objective

The objective of this lab is to learn how to upload, download, view, and delete objects in an Amazon S3 bucket using the AWS Management Console.

## Concepts Learned

### 1. What is an S3 Object?

An S3 object is a file stored inside an Amazon S3 bucket.

An object consists of:
- Object Key (file name)
- Object Data (file content)
- Metadata (information about the object)

### 2. How to Upload an Object?

Uploading means transferring a file from a local computer to an Amazon S3 bucket.

Steps:
1. Open the Amazon S3 console.
2. Select an existing bucket.
3. Click the Upload button.
4. Select Add files.
5. Choose a file from the local computer.
6. Click Upload.

### 3. How to Download an Object?

Downloading means retrieving a file from an S3 bucket to a local computer.

Steps:
1. Open the S3 bucket.
2. Select the required object.
3. Click Download.
4. Verify the downloaded file on the local computer.

### 4. How to Delete an Object?

Deleting means removing an object from an S3 bucket.

Steps:
1. Open the S3 bucket.
2. Select the object.
3. Click Delete.
4. Confirm the deletion.

**Note:** If bucket versioning is enabled, deleting an object may create a delete marker instead of permanently removing previous versions.

## Practical Implementation

| Task | Status |
|---|---|
| Created a sample text file | Completed |
| Uploaded file to S3 | Completed |
| Viewed the uploaded object | Completed |
| Downloaded the object | Completed |
| Verified the downloaded file | Completed |
| Deleted the object | Completed |

## Screenshots

The screenshots folder contains evidence of the following operations:

1. S3 bucket before uploading.
2. Uploading a sample file.
3. Upload successful.
4. Object visible in the bucket.
5. Downloading an object.
6. Downloaded file verification.
7. Deleting an object.

## Key Learnings

- Learned how to upload files to Amazon S3.
- Understood how S3 stores objects.
- Learned how to download objects from S3.
- Practiced deleting objects from an S3 bucket.
- Understood the basic behavior of S3 Versioning.

## AWS Service Used

- Amazon S3 (Simple Storage Service)

## Conclusion

In this lab, I successfully practiced uploading, downloading, viewing, and deleting objects in Amazon S3 using the AWS Management Console.

This practical helped me understand basic S3 object management operations.

