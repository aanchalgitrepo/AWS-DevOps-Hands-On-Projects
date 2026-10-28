# Lab 10: AWS Cost Monitoring and Cleanup

## Objective
To learn how to monitor AWS costs, review Free Tier usage, identify unused resources, and perform safe resource cleanup.

## Services Used
- AWS Billing and Cost Management
- AWS Cost Explorer
- AWS Free Tier usage dashboard (if available)
- Amazon EC2
- Amazon EBS
- Amazon EBS Snapshots

## Prerequisites
- AWS account
- Access to the AWS Management Console
- Appropriate permissions to view billing and EC2 resources

## Tasks Performed

### 1. Billing Dashboard Review
- Opened AWS Billing and Cost Management.
- Reviewed the available billing information.
- Checked current-month charges and estimated costs, where available.

### 2. Cost Explorer Review
- Checked Cost Explorer availability.
- Reviewed the available cost and usage reports.
- Observed service-wise cost information, where available.

### 3. Free Tier Usage Review
- Opened the Free Tier usage section, if available.
- Reviewed the displayed usage information and limits.

### 4. EC2 Resource Audit
- Checked EC2 instance states.
- Reviewed EBS volumes and their attachment status.
- Reviewed EBS snapshots.
- Checked Elastic IPs and other potentially chargeable resources.

### 5. Cleanup Verification
- Identified resources that could potentially generate charges.
- Verified whether resources were required before considering deletion.
- Recorded the cleanup status.

### 6. Budget Alerts
- Reviewed the AWS Budgets option, if available.
- Learned how cost thresholds and email alerts help monitor spending.

## Screenshots
Add your actual screenshots to the `screenshots/` folder and link them here.

1. Billing Dashboard
2. Cost Explorer
3. Free Tier Usage
4. EC2 Instances
5. EBS Volumes
6. EBS Snapshots
7. Cleanup Verification

## Key Learnings
- How to review AWS billing information.
- How to monitor service-wise AWS costs.
- How to inspect potentially chargeable resources.
- Why stopped EC2 instances may still incur storage charges.
- Why unused EBS volumes, snapshots, Elastic IPs, and network resources need review.
- Why resources must be verified before deletion.

## Cleanup Status
Update this section after completing your checks.

- EC2 instances reviewed: Yes / No
- EBS volumes reviewed: Yes / No
- Snapshots reviewed: Yes / No
- Elastic IPs reviewed: Yes / No
- Other resources reviewed: Yes / No
- Cleanup required: Yes / No
- Cleanup verified: Yes / No / Not applicable

## Result
Reviewed the AWS cost monitoring options and performed a resource audit to understand how to reduce the risk of unexpected AWS charges.

**Note:** AWS Free Tier eligibility, service limits, and charges depend on the account, region, service, and current pricing terms.
