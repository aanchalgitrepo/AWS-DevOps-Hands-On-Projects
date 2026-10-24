# Lab 06 - Create an EBS Snapshot

## Objective
To create a snapshot of an Amazon EBS volume and verify its status in the AWS Management Console.

## What is an EBS Snapshot?
An EBS Snapshot is a point-in-time backup of an Amazon EBS volume. It can be used to restore data by creating a new EBS volume from the snapshot.

## AWS Services Used
- Amazon EC2
- Amazon EBS
- EBS Snapshots

## Steps Performed

1. Logged in to the AWS Management Console.
2. Opened the EC2 Dashboard.
3. Navigated to Elastic Block Store → Volumes.
4. Selected the existing EBS volume.
5. Clicked Actions → Create snapshot.
6. Added the description `Lab-06-EBS-Snapshot`.
7. Created the snapshot.
8. Navigated to Elastic Block Store → Snapshots.
9. Verified the snapshot status was `Completed`.

## Snapshot Details

- **Snapshot Name:** Lab-06-EBS-Snapshot
- **Snapshot ID:** `<your-snapshot-id>`
- **Source Volume ID:** `<your-volume-id>`
- **Snapshot Status:** Completed

## Screenshots

### 1. EBS Volume Selected
![EBS Volume Selected](screenshots/01-ebs-volume-selected.png)

### 2. Create Snapshot
![Create Snapshot](screenshots/02-create-snapshot.png)

### 3. Snapshot Pending
![Snapshot Pending](screenshots/03-snapshot-pending.png)

### 4. Snapshot Completed
![Snapshot Completed](screenshots/04-snapshot-completed.png)

## Key Learnings

- Learned how to create an EBS Snapshot.
- Understood how snapshots help with backup and recovery.
- Learned how to verify snapshot status in AWS.
- Understood that a snapshot can be used to create a new EBS volume.

## Important Note
EBS Snapshots may incur storage charges. Check AWS pricing and Billing before creating resources. Delete unnecessary snapshots when they are no longer required.

## Conclusion
Successfully created an EBS Snapshot and verified its status in the AWS Management Console.
