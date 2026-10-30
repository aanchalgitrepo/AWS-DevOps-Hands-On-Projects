# Lab 06 — Host a Static Website on Amazon S3

## Objective

The objective of this lab is to host a static website using Amazon S3. In this lab, I created an S3 bucket, enabled static website hosting, uploaded an HTML file, configured public read access using a bucket policy, and accessed the website through the S3 website endpoint.

## What is Static Website Hosting?

Static website hosting allows us to host websites containing HTML, CSS, and JavaScript files without managing a web server.

Amazon S3 provides object storage and can serve static website content directly to website visitors.

### Examples of Static Websites

- Personal portfolio websites
- Business landing pages
- Company information websites
- Documentation websites

## AWS Services Used

- Amazon S3
- S3 Bucket Policy
- Static Website Hosting

## Practical Implementation

### Step 1: Create an S3 Bucket

- Open the Amazon S3 console.
- Create a new S3 bucket.
- Select the AWS Region.
- Configure the bucket settings.
- Create the bucket.

### Step 2: Enable Static Website Hosting

- Open the S3 bucket.
- Navigate to the Properties tab.
- Find Static Website Hosting.
- Enable static website hosting.
- Set the index document to `index.html`.
- Save the configuration.

### Step 3: Create an HTML File

Created a simple HTML webpage named `index.html`.

The webpage contains:
- Welcome message
- Website heading
- Basic website description

### Step 4: Upload Website Files

- Open the Objects tab.
- Upload the `index.html` file.
- Verify that the file is successfully uploaded.

### Step 5: Configure Public Access

- Navigate to the Permissions tab.
- Edit Block Public Access settings.
- Disable Block all public access for this learning exercise.
- Acknowledge the public access warning.

### Step 6: Configure Bucket Policy

Added a bucket policy to allow public read access to website objects.

The policy uses the following permission:

- `s3:GetObject`

This allows website visitors to read the objects stored in the bucket.

### Step 7: Test the Website

- Navigate to the Properties tab.
- Find the Static Website Hosting section.
- Open the Bucket Website Endpoint.
- Verify that the website loads successfully in the browser.

## Concepts Learned

1. Static Website Hosting
2. Amazon S3 Website Endpoint
3. HTML File Upload
4. S3 Block Public Access
5. Bucket Policies
6. Public Read Access
7. S3 Object Permissions

## Screenshots

Screenshots of the practical implementation are available in the `screenshots/` folder.

## Key Learnings

- Learned how to host a static website using Amazon S3.
- Understood how to enable static website hosting.
- Learned how to upload website files to an S3 bucket.
- Understood the role of Block Public Access settings.
- Learned how bucket policies control access to S3 objects.
- Successfully accessed a static website using the S3 website endpoint.

## Security Considerations

- Public access should only be enabled when required.
- Never upload confidential or sensitive information to a public bucket.
- Grant only the minimum permissions required.
- For production websites, consider using Amazon CloudFront with Origin Access Control (OAC) to keep the S3 bucket private and provide HTTPS.

## Cleanup

After completing the lab:

- Delete the uploaded website objects.
- Delete the S3 bucket if it is no longer required.
- Verify that no unnecessary AWS resources remain.

## Conclusion

Successfully hosted a static website using Amazon S3.

This lab provided practical experience with S3 website hosting, bucket policies, public access configuration, and website deployment on AWS.

**Status:** Completed
