# Lab 01 — Explore IAM Users and Groups

## Objective

The objective of this lab is to understand IAM users and groups and learn how to manage identities in AWS.

## What is AWS IAM?

AWS Identity and Access Management (IAM) is a service that allows us to securely manage access to AWS resources.

It controls who can access AWS resources and what actions they can perform.

## What is an IAM User?

An IAM user is an identity created for a person or application that needs access to AWS resources.

Examples:

- `developer-user`
- `admin-user`
- `backup-user`

Each IAM user can have its own permissions through attached policies or group memberships.

## What is an IAM Group?

An IAM group is a collection of IAM users.

Permissions can be assigned to a group, and all users in that group inherit the permissions assigned to it.

Examples:

- Developers
- Administrators
- Testers

**Note:** An IAM group is used to manage permissions for multiple IAM users. Groups cannot be used to sign in to AWS.

## Lab Status

- [x] Opened AWS Management Console
- [x] Navigated to IAM Dashboard
- [x] Explored IAM Users
- [x] Created an IAM User named `developer-user`
- [x] Explored IAM User details
- [x] Checked user permissions
- [ ] Explored IAM User Groups (Pending - option not available in current console)
- [ ] Created an IAM Group
- [ ] Added `developer-user` to an IAM Group
- [ ] Verified user group membership

## Practical Steps

### Part 1 — Explore IAM Console

1. Open the AWS Management Console.
2. Search for IAM.
3. Open the IAM Dashboard.
4. Explore the IAM navigation options, including Users, Policies, and Roles.

### Part 2 — Create an IAM User

1. Navigate to **IAM → Users**.
2. Click **Create user**.
3. Enter the username:

   `developer-user`

4. Complete the user creation process.
5. Open the created user and explore its details.
6. Navigate to the Permissions tab.

### Part 3 — Check User Permissions

1. Open the `developer-user` details page.
2. Select the **Permissions** tab.
3. Check the attached permissions policies.

**Observation:**

The `developer-user` was created successfully without attaching any permissions or policies.

The Permissions tab displays:

- Permissions policies: `0`
- No directly attached policies.

By default, IAM users have no permissions unless permissions are explicitly granted through policies. AWS uses an implicit deny when no applicable Allow permission exists.

### Part 4 — Explore IAM User Groups (Pending)

The User Groups section was not available in the current IAM console navigation during this lab.

Therefore, the following tasks are pending:

1. Create an IAM group named `Developers`.
2. Add `developer-user` to the group.
3. Attach a suitable permissions policy to the group.
4. Verify the user's group membership.

## Key Concepts Learned

- What is AWS IAM?
- What is an IAM user?
- What is an IAM group?
- How to create an IAM user.
- How to explore IAM user details.
- How to check attached permissions policies.
- Why IAM users should be given only the permissions they need.
- How users can inherit permissions through group membership.

## Screenshots

Add the following screenshots to the lab's `screenshots` folder:

1. IAM Dashboard
2. IAM Users List showing `developer-user`
3. Created `developer-user` details page
4. Permissions tab showing zero attached policies

**Note:** IAM Group and group membership screenshots will be added after completing the pending tasks.

## Conclusion

In this lab, I explored AWS IAM and learned how IAM users and groups help manage identities and permissions.

I successfully created an IAM user named `developer-user` and verified that no permissions policies were attached to it.

The IAM User Groups practical is currently pending because the User Groups option was not available in my current AWS console.

This lab helped me understand the importance of managing user permissions and following the principle of least privilege.
