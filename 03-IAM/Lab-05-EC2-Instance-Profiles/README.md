# Lab-05-Understand EC2 Instance Profiles

## Objective

To understand how EC2 instances receive IAM role permissions through instance profiles.

## What is an EC2 Instance Profile?

An instance profile is a container for an IAM role that allows an EC2 instance to use the role.

When an IAM role is attached to an EC2 instance, AWS makes the role available through an instance profile.

## How It Works

1. Create an IAM role for EC2.
2. Attach the required IAM permissions.
3. Associate the role with an EC2 instance.
4. EC2 receives temporary security credentials.
5. The instance can access permitted AWS resources.

## Practical Steps

1. Open IAM and explore the EC2 role.
2. Open EC2.
3. Select an existing instance.
4. Navigate to Actions.
5. Select Security.
6. Choose Modify IAM role.
7. Associate the IAM role with the instance.
8. Verify the role association.

## Key Concepts Learned

- EC2 instance profiles.
- IAM role association.
- Temporary security credentials.
- EC2 and IAM integration.
- Secure AWS resource access.

## Conclusion

In this lab, I learned how EC2 uses an IAM role through an instance profile to access AWS resources securely.
