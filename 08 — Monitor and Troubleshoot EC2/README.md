
# Lab 08 — Monitor and Troubleshoot EC2

## Objective
Learn how to monitor an Amazon EC2 instance and troubleshoot
common performance, connectivity, and status-check issues.

## AWS Services Used
- Amazon EC2
- Amazon CloudWatch

## Prerequisites
- AWS account
- Basic knowledge of EC2 instances
- Basic knowledge of Security Groups and SSH

## Tasks Performed

### 1. EC2 Instance Monitoring
- Created or selected a test EC2 instance.
- Checked the instance state.
- Reviewed EC2 status checks.
- Observed CPU utilization in the Monitoring tab.

### 2. CloudWatch Metrics
Reviewed the following metrics:
- CPUUtilization
- NetworkIn
- NetworkOut
- StatusCheckFailed

### 3. System Monitoring
Used Linux commands to inspect system health:

```bash
top
free -h
df -h
uptime
sudo journalctl -p err -n 20
```

### 4. Troubleshooting
Reviewed common EC2 issues:
- SSH connection timeout
- SSH public key authentication failure
- High CPU utilization
- Low disk space
- Failed instance status checks

## Key Learnings
- Understood EC2 system and instance status checks.
- Learned how to view CloudWatch metrics.
- Practiced Linux system monitoring commands.
- Learned basic EC2 connectivity troubleshooting.
- Understood the importance of monitoring for reliability.

## Result
Documented the EC2 monitoring workflow and common
troubleshooting steps.

## AWS Documentation
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring_ec2.html
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/viewing_status.html
- https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesConnecting.html
