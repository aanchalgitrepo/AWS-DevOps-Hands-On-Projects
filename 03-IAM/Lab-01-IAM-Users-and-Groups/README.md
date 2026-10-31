# Lab 01 — Explore IAM Users and Groups

## Objective

The objective of this lab is to understand IAM users and groups and learn how to manage identities in AWS.

## What is AWS IAM?

AWS Identity and Access Management (IAM) is a service that allows us to securely manage access to AWS resources.

It controls who can access AWS resources and what actions they can perform.

## What is an IAM User?

An IAM user is an identity created for a person or application that needs access to AWS resources.

Example:

- developer-user
- admin-user
- backup-user

## What is an IAM Group?

An IAM group is a collection of IAM users.

Permissions can be assigned to a group, and all users in that group inherit the group's permissions.

Example:

- Developers
- Administrators
- Testers

## Practical Steps

1. Open AWS Management Console.
2. Search for IAM.
3. Navigate to User groups.
4. Create a group named `Developers`.
5. Navigate to Users.
6. Create a user named `developer-user`.
7. Add the user to the Developers group.
8. Verify the user's group membership.

## Key Concepts Learned

- What is AWS IAM?
- What is an IAM user?
- What is an IAM group?
- How to create IAM users.
- How to create IAM groups.
- How to add users to groups.
- How users inherit group permissions.

## Screenshots

Add screenshots of:

1. IAM Dashboard
2. Created IAM Group
3. Created IAM User
4. User Group Membership

## Conclusion

In this lab, I learned how to create IAM users and groups and organize AWS identities for centralized permission management.
