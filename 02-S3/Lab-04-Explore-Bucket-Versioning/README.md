# Lab 04 — Explore S3 Bucket Versioning

## Objective

The objective of this lab is to understand Amazon S3 Bucket Versioning and learn how to enable versioning, upload multiple versions of an object, view previous versions, and restore an older version.

## What is S3 Bucket Versioning?

Amazon S3 Bucket Versioning is a feature that allows users to maintain multiple versions of the same object in an S3 bucket.

Whenever a user uploads an object with the same name, Amazon S3 stores it as a new version instead of permanently replacing the previous version.

### Example

If we upload a file named `version-demo.txt` three times, S3 maintains three different versions:

- Version 1
- Version 2
- Version 3

Users can access and restore previous versions whenever required.

## Prerequisites

- AWS Account
- Amazon S3 Bucket
- Internet Connection
- A text file named `version-demo.txt`

## Steps Performed

### Step 1: Open Amazon S3

- Logged in to AWS Management Console.
- Searched for Amazon S3.
- Opened the existing S3 bucket.

### Step 2: Enable Bucket Versioning

- Opened the bucket Properties tab.
- Located the Bucket Versioning section.
- Clicked Edit.
- Selected Enable.
- Saved the changes.

**Result:** Bucket Versioning was successfully enabled.

### Step 3: Upload First Version

Created a file named `version-demo.txt`.

Content:

```text
This is Version 1 of my S3 object.
```

Uploaded the file to the S3 bucket.

### Step 4: Upload Second Version

Modified the same file.

Content:

```text
This is Version 2 of my S3 object.
```

Uploaded the file again using the same filename.

S3 created a new version of the object.

### Step 5: Upload Third Version

Modified the file again.

Content:

```text
This is Version 3 of my S3 object.
```

Uploaded the file again.

S3 maintained multiple versions of the same object.

### Step 6: View Object Versions

- Opened the Objects tab.
- Enabled the Show versions option.
- Viewed all available versions of `version-demo.txt`.
- Checked the Version ID and Last modified details.

### Step 7: Download Previous Version

- Selected an older version of the object.
- Downloaded the file.
- Verified its original content.

### Step 8: Restore Previous Version

Downloaded an older version and uploaded it again using the same filename.

S3 created a new latest version containing the older content.

## Concepts Learned

1. What is S3 Bucket Versioning?
2. How to enable Bucket Versioning.
3. How to upload multiple versions of an object.
4. How to view previous object versions.
5. What is a Version ID?
6. How to download an older version.
7. How to restore a previous version.
8. What is a Delete Marker?

## Benefits of S3 Versioning

- Protects objects from accidental overwrites.
- Helps recover previous versions of files.
- Provides data recovery capabilities.
- Maintains object history.
- Helps protect important files from accidental deletion.

## Important Notes

- Versioning can be enabled or suspended.
- Once enabled, versioning cannot be returned to the never-enabled state.
- Existing object versions remain stored when versioning is suspended.
- Multiple object versions consume storage and may incur charges.

## Screenshots

Screenshots captured during this lab:

1. S3 Bucket Properties
2. Bucket Versioning Enabled
3. Upload First Version
4. Upload Second Version
5. Upload Third Version
6. Show All Object Versions
7. Download Previous Version

## Conclusion

Successfully explored Amazon S3 Bucket Versioning.

Learned how to enable versioning, upload multiple versions of an object, view previous versions, download older versions, and restore previous object content.

**Status:** Completed
