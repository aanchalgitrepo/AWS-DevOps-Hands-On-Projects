# Lab-03-AWS Managed vs Customer Managed Policies

## Objective

To understand the difference between AWS managed policies and customer managed policies.

## AWS Managed Policies

AWS managed policies are predefined policies created and maintained by AWS.

Example:

`AmazonS3ReadOnlyAccess`

These policies can be attached to IAM users, groups, and roles.

## Customer Managed Policies

Customer managed policies are custom policies created and maintained by AWS customers.

They allow administrators to define permissions according to application and business requirements.

Example:

`Custom-S3-List-Policy`

## Key Differences

| AWS Managed Policies | Customer Managed Policies |
|---|---|
| Maintained by AWS | Maintained by customer |
| Predefined permissions | Custom permissions |
| Cannot edit directly | Can edit |
| Shared AWS policy definitions | Account-specific policy |

## Practical Steps

1. Open IAM Policies.
2. Search for AmazonS3ReadOnlyAccess.
3. Explore its permissions.
4. Open the previously created custom policy.
5. Compare their JSON documents and permissions.

## Key Concepts Learned

- AWS managed policies.
- Customer managed policies.
- Policy administration.
- Policy permissions.
- Reusability of IAM policies.

## Conclusion

In this lab, I learned how AWS managed and customer managed policies differ and how they help manage permissions in AWS.
