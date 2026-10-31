# Lab 02 — Create and Attach IAM Policies

## Objective

To create a custom IAM policy using JSON and attach it to an IAM user.

## What is an IAM Policy?

An IAM policy is a JSON document that defines permissions for AWS identities and resources.

It specifies which actions are allowed or denied on AWS resources.

## JSON Policy Structure

An IAM policy contains the following elements:

- Version: Specifies the policy language version.
- Statement: Contains permission rules.
- Effect: Defines Allow or Deny.
- Action: Specifies AWS actions.
- Resource: Specifies the AWS resources.

## Practical Steps

1. Open IAM in AWS Console.
2. Navigate to Policies.
3. Click Create policy.
4. Select the JSON editor.
5. Add a custom S3 listing policy.
6. Name the policy `Custom-S3-List-Policy`.
7. Create the policy.
8. Open the IAM user `developer-user`.
9. Attach the custom policy.
10. Verify the attached permissions.

## Policy Used

The policy allows the `s3:ListAllMyBuckets` action.

## Key Concepts Learned

- IAM JSON policies.
- Policy elements.
- Allow and Deny permissions.
- Custom IAM policies.
- Attaching policies to users.

## Screenshots

1. IAM Policy JSON Editor
2. Created Custom Policy
3. Attached Policy to IAM User

## Conclusion

In this lab, I learned how to create custom IAM policies using JSON and attach permissions to IAM users.
