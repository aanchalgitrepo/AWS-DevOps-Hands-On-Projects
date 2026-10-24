# Lab 07 — Deploy a Web Server on AWS EC2

## Objective
Deploy a web server on an Amazon EC2 instance using Apache HTTP Server and access the website through a web browser.

## AWS Services and Technologies
- Amazon EC2
- Amazon Linux 2023
- Security Groups
- Apache HTTP Server
- HTTP Protocol

## Architecture

User Browser → Internet → EC2 Security Group (Port 80) → EC2 Instance → Apache Web Server → HTML Website

## Prerequisites
- AWS account
- Amazon EC2 instance
- Public IPv4 address
- Security group allowing HTTP traffic on port 80
- Apache HTTP Server

## Implementation Steps

### Step 1: Launch EC2 Instance
- AMI: Amazon Linux 2023
- Instance name: lab-07-web-server
- Select an instance type eligible for the account's Free Tier offer.

### Step 2: Configure Security Group
Configure the inbound rule:

| Type | Protocol | Port | Source |
|---|---|---|---|
| HTTP | TCP | 80 | 0.0.0.0/0 |

SSH access on port 22 should be restricted to My IP when required.

### Step 3: Install Apache

```bash
sudo dnf update -y
sudo dnf install httpd -y
```

### Step 4: Start and Enable Apache

```bash
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
```

### Step 5: Create a Custom Web Page

```bash
echo '<h1>My First AWS Web Server</h1><p>Deployed using Amazon EC2 and Apache.</p>' | sudo tee /var/www/html/index.html
```

### Step 6: Verify the Website

```bash
curl http://localhost
```

Open the following URL in a browser:

```text
http://YOUR-PUBLIC-IP
```

Replace `YOUR-PUBLIC-IP` with the instance's actual public IPv4 address.

## Screenshots

### 1. EC2 Instance Running
![EC2 Instance Running](screenshots/01-ec2-instance-running.png)

### 2. HTTP Security Group Rule
![HTTP Security Group Rule](screenshots/02-security-group-http-rule.png)

### 3. Apache Installation
![Apache Installation](screenshots/03-apache-installation.png)

### 4. Apache Service Running
![Apache Service Running](screenshots/04-apache-service-running.png)

### 5. Website Browser Output
![Website Browser Output](screenshots/05-website-browser-output.png)

## Learning Outcomes
- Learned how to launch an EC2 instance.
- Configured an HTTP inbound security group rule.
- Installed and managed Apache using systemd.
- Deployed a custom HTML page.
- Accessed a web server through its public IPv4 address.

## Cleanup
After completing the lab, terminate the EC2 instance if it is no longer required. Check for leftover EBS volumes, snapshots, Elastic IP addresses, and other billable resources.

## Lab Status
Completed after successful browser verification.

## Author
Aanchal Verma
