# Lab 06 - Create an EBS Snapshot

## Objective
To understand how to create an Amazon EBS Snapshot and how it is used for backup and recovery.

## What is an EBS Snapshot?

An Amazon EBS Snapshot is a point-in-time backup of an EBS volume. It helps protect data and allows us to create a new EBS volume from the snapshot when required.

## AWS Service Used
- Amazon EC2
- Amazon Elastic Block Store (EBS)
- EBS Snapshots

## Prerequisites
- An AWS account
- Access to the AWS Management Console
- An existing EBS volume for the hands-on activity

**Note:** This lab is documented for learning purposes. No AWS resources were created during this practice.

## Steps to Create an EBS Snapshot

1. Sign in to the AWS Management Console.
2. Open the Amazon EC2 service.
3. Navigate to Elastic Block Store → Volumes.
4. Select the EBS volume to back up.
5. Choose Actions → Create snapshot.
6. Enter a description: `Lab-06-EBS-Snapshot`.
7. Click Create snapshot.
8. Navigate to Elastic Block Store → Snapshots.
9. Find the snapshot and verify its status.

## Snapshot Status

- `Pending`: The snapshot is being created.
- `Completed`: The snapshot has completed successfully.
- `Error`: The snapshot creation encountered a problem.

## Use Cases

- Backing up important data.
- Supporting data recovery.
- Creating a new EBS volume from a snapshot.
- Maintaining backups before major system changes.

## Cost Considerations

- EBS Snapshot storage may incur charges.
- Check AWS Free Tier eligibility, available credits, and current pricing before creating resources.
- Delete unnecessary snapshots when they are no longer needed.
- Deleting a snapshot does not delete the original EBS volume.

## Practical Status

- Documentation: Completed
- AWS hands-on: Not performed
- Snapshot ID: Not applicable
- Screenshot: Not available because no AWS resources were created

## Key Learnings

- Understood the purpose of EBS Snapshots.
- Learned the console workflow for snapshot creation.
- Understood snapshot status and backup use cases.
- Learned basic snapshot cost and cleanup precautions.

## Conclusion

This lab explains the EBS Snapshot creation workflow and its role in AWS backup and recovery. The practical activity can be performed later when suitable cost coverage is confirmed.
