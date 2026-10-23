# AWS EC2 Hands-On Projects

## Project Overview

This repository documents my practical learning of Amazon EC2 and related AWS services. It includes step-by-step labs, Linux commands, screenshots, configuration details, troubleshooting, and cost-cleanup practices.

## Objectives

- Launch and manage Linux EC2 instances.
- Configure SSH access and Security Groups.
- Understand EBS volumes, mounting, and snapshots.
- Deploy a static website using Apache or Nginx.
- Monitor instance health and troubleshoot common issues.
- Understand IAM roles and the principle of least privilege.
- Practice secure and cost-conscious AWS resource management.

## Architecture

User Browser → Internet → EC2 Security Group → EC2 Linux Instance → Apache/Nginx Web Server

## Technologies Used

- Amazon Web Services (AWS)
- Amazon EC2
- Amazon EBS
- AWS IAM
- Amazon CloudWatch
- Linux / Bash
- Apache or Nginx
- Git and GitHub

## Practical Labs

| Lab | Topic | Status |
|---|---|---|
| 01 | Launch an EC2 Instance | Completed |
| 02 | Connect Using SSH | Completed |
| 03 | Configure Security Groups | Planned |
| 04 | Explore EC2 Instance States | Planned |
| 05 | Create and Mount an EBS Volume | Planned |
| 06 | Create an EBS Snapshot | Planned |
| 07 | Deploy a Web Server | Planned |
| 08 | Monitor and Troubleshoot EC2 | Planned |
| 09 | Explore IAM Roles | Planned |
| 10 | Cost Monitoring and Cleanup | Planned |

## Evidence and Screenshots

Each completed lab contains screenshots of AWS configuration, terminal output, and the final verification result.

## Security Practices

- Never upload private keys, passwords, access keys, or secret tokens.
- Restrict SSH access to my own public IP when possible.
- Use least-privilege IAM permissions.
- Review running resources and billing regularly.
- Remove temporary resources after completing labs.

## Learning Outcomes

This project is intended to demonstrate practical understanding of EC2 provisioning, Linux server administration, cloud networking, storage, web server deployment, monitoring, troubleshooting, and security fundamentals.

## Author

Aanchal Verma

GitHub: https://github.com/aanchalgitrepo

## Disclaimer

This is a hands-on learning portfolio. Only labs actually completed and verified are marked as completed. Resource configurations and costs may vary by AWS account, Region, and pricing eligibility.
