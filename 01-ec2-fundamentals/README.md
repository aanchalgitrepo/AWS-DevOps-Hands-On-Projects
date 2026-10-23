# Lab 01: Launch an EC2 Instance

## 1. Objective

To launch a Linux EC2 instance and understand its basic configuration.

## 2. AWS Services Used

- Amazon EC2
- Amazon VPC
- Security Groups
- Amazon EBS

## 3. Configuration

- Instance name: ec2-portfolio-lab
- AMI name: al2023-ami-2023.12.20261021.0-kernel-6.18-x86_64
- Instance type: t3.micro
- Region: Asia Pacific (Sydney)
- Availability Zone: ap-southeast-2b
- Storage: actual volume size is 8 GiB and type is gp3

## 4. Steps Performed

1. Opened the EC2 Console.
2. Selected a suitable Linux AMI.
3. Configured the instance type and key pair.
4. Reviewed network and Security Group settings.
5. Launched the instance.
6. Verified instance state and status checks.
7. Connected to Linux and ran verification commands.

## 5. Commands

```bash
whoami
hostname
cat /etc/os-release
uptime
df -h
lsblk
```

## 6. Screenshots

Add actual screenshots from the screenshots folder.

## 7. Verification

- [ ] Instance reached Running state.
- [ ] Status checks completed successfully.
- [ ] Linux terminal connection worked.
- [ ] Commands returned expected output.

## 8. What I Learned

Document what you learned about AMIs, instance types, key pairs, Security Groups, and EBS.

## 9. Issues and Troubleshooting

Record any issue you encountered, its cause, and how you resolved it.

## 10. Cleanup

Record whether the instance was stopped or terminated and verify that temporary resources were cleaned up.

## 11. Lab Status

Completed only after all steps and evidence have been verified.
