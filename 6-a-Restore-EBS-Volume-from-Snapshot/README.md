# Lab 07 - Restore an EBS Volume from a Snapshot

## Objective

To understand how to restore data by creating a new Amazon EBS volume from an existing EBS Snapshot.

## What is EBS Volume Restoration?

EBS Volume restoration is the process of creating a new EBS volume from a previously created snapshot.

For example, if an application server's data needs to be recovered, an administrator can create a new EBS volume from a snapshot and attach it to an EC2 instance.

## AWS Services Used

- Amazon EC2
- Amazon Elastic Block Store (EBS)
- EBS Snapshots

## Prerequisites

- An AWS account
- An existing EBS Snapshot
- Knowledge of EBS volumes and Availability Zones

**Note:** This lab is documented for learning purposes. No AWS resources were created during this practice.

## Steps to Restore an EBS Volume from a Snapshot

1. Sign in to the AWS Management Console.
2. Open the Amazon EC2 service.
3. Navigate to Elastic Block Store → Snapshots.
4. Select the snapshot from which the volume needs to be restored.
5. Choose Actions → Create volume from snapshot.
6. Select the required volume type and size.
7. Select the Availability Zone where the volume will be used.
8. Review the configuration and create the volume.
9. Navigate to Elastic Block Store → Volumes.
10. Verify that the new volume has been created successfully.

## How to Attach the Restored Volume

1. Open EC2 → Volumes.
2. Select the restored EBS volume.
3. Choose Actions → Attach volume.
4. Select an EC2 instance in the same Availability Zone.
5. Confirm the attachment.
6. Connect to the instance and identify the new disk.
7. Mount the filesystem if required.

**Important:** Do not format the restored volume if it contains data you want to recover. First identify the disk and inspect its existing filesystem.

## Verification

Verify the following after creating the volume:

- A new Volume ID is generated.
- The volume is in the expected Availability Zone.
- The volume size and type are correct.
- The volume can be attached to a compatible EC2 instance.

## Practical Status

- Documentation: Completed
- AWS hands-on: Not performed
- Source Snapshot ID: Not applicable
- Restored Volume ID: Not applicable
- Screenshots: Not available because no AWS resources were created

## Cost Considerations

- EBS volume storage may incur charges.
- Snapshot storage may also incur charges.
- Check current AWS pricing, Free Tier eligibility, and available credits before performing the hands-on lab.
- Delete unnecessary test resources after confirming that they are no longer required.

## Key Learnings

- Understood how to create an EBS volume from a snapshot.
- Learned why Availability Zone selection matters.
- Understood the basic volume attachment workflow.
- Learned important precautions for data recovery.

## Conclusion

An EBS Snapshot can be used to create a new EBS volume for data recovery. The restored volume can be attached to a compatible EC2 instance when required. This lab documents the recovery workflow; the hands-on activity has not yet been performed.
