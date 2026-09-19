# AWS Cloud Support & Security Lab

## Project Overview

This project is a hands-on AWS Cloud Support and Security Lab designed to develop practical skills in cloud infrastructure, Linux administration, networking, IAM, storage, monitoring, and troubleshooting.

The project was completed through a 10-day practical lab covering AWS networking, EC2, Nginx, IAM, S3, CloudWatch, and real-world troubleshooting scenarios.

The goal of this project is to build practical skills relevant to entry-level roles such as:

- Cloud Support Engineer
- Cloud Support Associate
- Cloud Operations Engineer
- Junior Cloud Engineer
- Junior Cloud Security Engineer
- Technical Support Engineer

---

# Project Objectives

The main objectives of this project were to:

- Build and configure an AWS VPC
- Understand CIDR and subnetting
- Configure public and private subnets
- Configure Internet Gateway and route tables
- Deploy and manage an EC2 Linux server
- Configure Security Groups
- Configure SSH and HTTP access
- Install and configure Nginx
- Manage Linux services using systemd
- Work with IAM users, groups, roles, and policies
- Apply least-privilege access
- Create and manage S3 buckets and objects
- Access S3 using the AWS CLI
- Configure CloudWatch monitoring
- Work with metrics, logs, and alarms
- Troubleshoot SSH and HTTP connectivity
- Troubleshoot Nginx and EC2 issues
- Troubleshoot disk, CPU, and memory problems
- Troubleshoot DNS and networking problems
- Troubleshoot IAM AccessDenied errors
- Create a basic health-check script

---

# AWS Services & Technologies

| Technology | Purpose |
|---|---|
| Amazon VPC | Network infrastructure |
| Amazon EC2 | Linux cloud server |
| Security Groups | Network access control |
| Nginx | Linux cloud server |
| IAM | Identity and access management |
| Amazon S3 | Object storage |
| Amazon CloudWatch | Monitoring and logging |
| Internet Gateway | Internet connectivity |
| Route Tables | Network traffic routing |
| Nginx | Web server |
| Ubuntu Linux | Server operating system |
| SSH | Remote server administration |
| AWS CLI | AWS command-line management |
| Bash | Linux administration and scripting |

---

# Project Architecture

```
                         Internet
                            |
                            |
                    Internet Gateway
                            |
                            |
                    +---------------+
                    |      VPC      |
                    |               |
                    |   Route Table |
                    |       |       |
                    |       |       |
              +-----+-------+-------+-----+
              |                         |
              |                         |
       Public Subnet              Private Subnet
              |                         |
              |                         |
           EC2 Linux                 Resources
              |
              |
           Nginx
              |
              |
         HTTP / SSH

              |
              |
         CloudWatch
       Metrics / Logs
```
The following architecture represents the AWS environment used throughout the lab:

![AWS Cloud Security Architecture](images/aws-cloud-security-architecture.jpeg)

### Architecture Components

- **Amazon VPC** — Custom network environment
- **Public Subnet** — Hosts the EC2 Linux instance
- **Private Subnet** — Reserved for future workloads
- **Internet Gateway** — Provides internet connectivity
- **Security Group** — Controls SSH and HTTP access
- **EC2** — Ubuntu Linux server running Nginx
- **IAM** — Users, groups, roles, and policies
- **Amazon S3** — Object storage and IAM-controlled access
- **CloudWatch** — Metrics, logs, alarms, and monitoring
- **Troubleshooting** — Network, SSH, Nginx, resource, DNS, and IAM scenarios
---

# 10-Day Project Breakdown

## Day 1 — VPC & Networking

### Topics

- VPC
- CIDR
- Public subnet
- Private subnet
- Internet Gateway
- Route tables
- Basic AWS networking

### Tasks

The VPC networking environment was created and configured.

The lab covered:

- Creating a VPC
- Defining CIDR ranges
- Creating public and private subnets
- Creating an Internet Gateway
- Associating the Internet Gateway with the VPC
- Creating route tables
- Configuring routes
- Associating subnets with route tables

### Skills Demonstrated

- AWS VPC fundamentals
- CIDR understanding
- Subnetting
- Routing
- Public vs private network design

---

# Day 2 — EC2 & Security

### Topics

- EC2
- Security Groups
- Ports
- SSH
- HTTP
- Network basics

### Tasks

An EC2 Linux server was deployed and configured.

The instance was accessed remotely using SSH.

Security Group rules were configured for required traffic.

Important ports included:

```
22  → SSH
80  → HTTP
```

### SSH Access

Example:

```
ssh -i "<private-key>" ec2-user@<PUBLIC-IP>
```

### Skills Demonstrated

- EC2 deployment
- Linux server access
- SSH
- Security Groups
- Port-based network access
- Basic network troubleshooting

---

# Day 3 — Nginx

### Topics

- Nginx installation
- Nginx configuration
- Website hosting
- systemd
- Logs

### Installation

```
sudo apt update
sudo apt install nginx -y
```

### Service Verification

```
sudo systemctl status nginx
```

The Nginx service was verified and managed using systemd.

### Service Management

```
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl status nginx
```

### Skills Demonstrated

- Web server installation
- Nginx configuration
- Linux service management
- systemd
- Log investigation
- HTTP troubleshooting

---

# Day 4 — IAM

### Topics

- IAM users
- IAM groups
- IAM roles
- IAM policies
- Least privilege

### Tasks

IAM was used to understand identity and access management in AWS.

The lab covered:

- Creating IAM users
- Creating groups
- Assigning permissions
- Understanding IAM policies
- Understanding IAM roles
- Applying least-privilege principles

### Security Principle

The **least privilege** principle means users and services should receive only the permissions required to perform their tasks.

### Skills Demonstrated

- AWS IAM
- Identity management
- Access control
- IAM policies
- Roles
- Least privilege

---

# Day 5 — Amazon S3

### Topics

- S3 buckets
- S3 objects
- AWS CLI
- IAM → S3 access

### Tasks

An S3 bucket was created and used to practice object storage operations.

The lab included:

- Creating an S3 bucket
- Working with objects
- Uploading files
- Accessing S3 through the AWS CLI
- Testing IAM permissions for S3 access

### AWS CLI

Example commands:

```
aws s3 ls
```

```
aws s3 ls s3://<bucket-name>
```

```
aws s3 cp <file> s3://<bucket-name>/
```

### Skills Demonstrated

- Amazon S3
- Object storage
- AWS CLI
- IAM permissions
- Cloud storage troubleshooting

---

# Day 6 — CloudWatch

### Topics

- Metrics
- Logs
- Basic alarms
- Monitoring

### Tasks

Amazon CloudWatch was used to understand basic AWS monitoring.

The lab covered:

- EC2 metrics
- Monitoring system activity
- CloudWatch logs
- Basic alarms
- Monitoring resource health

### Skills Demonstrated

- AWS monitoring
- CloudWatch metrics
- CloudWatch logs
- Basic alerting
- Operational monitoring

---

# Day 7 — Troubleshooting #1

## SSH Failure, Port 80 & Website Not Loading

This troubleshooting scenario focused on diagnosing common connectivity problems.

### Problems Investigated

- SSH connection failure
- Port 22 access
- Port 80 access
- Website not loading
- Security Group configuration
- Nginx status

### Troubleshooting Approach

The following areas were checked:

```
1. EC2 instance state
2. Status checks
3. Security Group rules
4. SSH configuration
5. Nginx service
6. Port 80
7. Network connectivity
8. Website response
```

### Skills Demonstrated

- Structured troubleshooting
- Network diagnosis
- SSH troubleshooting
- HTTP troubleshooting
- Security Group analysis

---

# Day 8 — Troubleshooting #2

## Nginx Failure, EC2 Unreachable & Service Problems

This scenario focused on server and service troubleshooting.

### Problems Investigated

- Nginx failure
- EC2 connectivity problems
- Service failures
- Linux service status
- Logs

### Important Commands

```
sudo systemctl status nginx
```

```
sudo systemctl restart nginx
```

```
sudo journalctl -xe
```

```
ss -tulpn
```

### Troubleshooting Process

```
Check EC2
      ↓
Check connectivity
      ↓
Check service status
      ↓
Check configuration
      ↓
Check logs
      ↓
Restart service if appropriate
      ↓
Verify service
```

### Skills Demonstrated

- Nginx troubleshooting
- systemd troubleshooting
- Linux log analysis
- Service recovery
- Cloud server troubleshooting

---

# Day 9 — Troubleshooting #3

## Disk Full, High CPU & Memory Issues

This troubleshooting scenario focused on Linux system resource problems.

### Problems Investigated

- Disk usage
- High CPU usage
- Memory usage
- Running processes
- System resource monitoring

### Useful Commands

```
df -h
```

```
free -h
```

```
top
```

```
ps aux
```

### Troubleshooting Process

```
Identify the resource problem
        ↓
Check disk / CPU / memory
        ↓
Identify affected process
        ↓
Investigate cause
        ↓
Take corrective action
        ↓
Verify system health
```

### Skills Demonstrated

- Linux resource monitoring
- Disk troubleshooting
- CPU troubleshooting
- Memory troubleshooting
- Process investigation

---

# Day 10 — Troubleshooting #4

## Network/DNS + IAM AccessDenied + Health-Check Script

The final troubleshooting scenario combined networking, DNS, IAM permissions, and basic automation.

### Part 1 — Network & DNS

The lab involved investigating network and DNS-related problems.

Areas considered:

- Network connectivity
- DNS resolution
- Service availability
- Port accessibility

Useful commands include:

```
ping <hostname>
```

```
nslookup <hostname>
```

```
curl -I <URL>
```

---

## Part 2 — IAM AccessDenied

IAM permissions were investigated when an AWS operation returned an `AccessDenied` error.

The troubleshooting process included checking:

```text
1. IAM identity
2. IAM policy
3. Required permissions
4. Resource being accessed
5. Policy scope
6. Least-privilege requirements
```

The goal was to understand why access was denied rather than simply granting excessive permissions.

---

## Part 3 — Health-Check Script

A basic health-check script was created to check system/service health.

The purpose of the script was to demonstrate basic automation for cloud support tasks.

Example checks can include:

```
- Server availability
- Nginx status
- Disk usage
- Memory usage
- CPU usage
```

### Skills Demonstrated

- Network troubleshooting
- DNS troubleshooting
- IAM troubleshooting
- AccessDenied investigation
- Bash scripting
- Basic automation
- Cloud operations

---

# Troubleshooting Methodology

A major part of this project was learning to troubleshoot systematically rather than randomly changing configurations.

The general troubleshooting process used was:

```text
1. Identify the problem
        ↓
2. Gather information
        ↓
3. Check system/network status
        ↓
4. Check configuration
        ↓
5. Check logs
        ↓
6. Identify the root cause
        ↓
7. Apply a controlled fix
        ↓
8. Test the solution
        ↓
9. Verify normal operation
        ↓
10. Document the result
```

---

# Security Practices

Security concepts were incorporated throughout the project.

### Network Security

AWS Security Groups were used to control inbound and outbound traffic.

### IAM Security

IAM policies and least-privilege access were practised.

### SSH Security

SSH was used for secure remote Linux administration.

### Monitoring

CloudWatch and Linux logs were used to monitor system activity.

### Access Control

Linux permissions and AWS IAM permissions were used to control access to resources.

---

# Key Commands Practised

## Linux

```
whoami
pwd
ls
ls -l
df -h
free -h
top
ps aux
```

## SSH

```
ssh -i "linux-key.pem" ubuntu@<PUBLIC-IP>
```

## Nginx

```
sudo systemctl status nginx
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
```

## Logs

```
sudo journalctl -xe
sudo cat /var/log/auth.log
```

## Networking

```
ping <hostname>
nslookup <hostname>
curl -I <URL>
ss -tulpn
```

## AWS CLI

```bash
aws s3 ls
aws s3 ls s3://<bucket-name>
aws s3 cp <file> s3://<bucket-name>/
```

---

# Skills Demonstrated

### AWS

- Amazon VPC
- EC2
- Security Groups
- IAM
- S3
- CloudWatch
- Internet Gateway
- Route Tables

### Linux

- Ubuntu administration
- SSH
- File management
- Permissions
- Services
- systemd
- Logs
- Resource monitoring

### Networking

- CIDR
- Subnets
- Routing
- Ports
- HTTP
- SSH
- DNS
- Connectivity troubleshooting

### Security

- IAM
- Least privilege
- Security Groups
- Authentication
- Access control
- Log analysis

### Troubleshooting

- SSH failures
- HTTP failures
- Nginx failures
- EC2 connectivity
- Disk problems
- CPU problems
- Memory problems
- DNS problems
- IAM AccessDenied

### Automation

- AWS CLI
- Bash
- Health-check scripting

---

# Project Evidence

Screenshots and documentation are included for each stage of the project.

## Day 1

- VPC configuration
- CIDR configuration
- Public subnet
- Private subnet
- Internet Gateway
- Route tables

## Day 2

- EC2 instance
- Security Group
- SSH access
- HTTP access
- Network configuration

## Day 3

- Nginx installation
- Nginx configuration
- Website
- systemd
- Logs

## Day 4

- IAM users
- IAM groups
- IAM roles
- IAM policies
- Least-privilege configuration

## Day 5

- S3 bucket
- S3 objects
- AWS CLI
- IAM → S3 access

## Day 6

- CloudWatch metrics
- CloudWatch logs
- Alarms
- Monitoring

## Day 7

- SSH troubleshooting
- Port 80 troubleshooting
- Website troubleshooting

## Day 8

- Nginx troubleshooting
- EC2 troubleshooting
- Service troubleshooting

## Day 9

- Disk troubleshooting
- CPU troubleshooting
- Memory troubleshooting

## Day 10

- Network troubleshooting
- DNS troubleshooting
- IAM AccessDenied
- Health-check script

---

# What I Learned

This project helped me develop practical experience with AWS cloud infrastructure and Linux server administration.

I learned how to:

- Build basic AWS network infrastructure
- Deploy and access EC2 Linux servers
- Configure network access using Security Groups
- Install and manage Nginx
- Manage Linux services
- Work with IAM users, groups, roles, and policies
- Apply least-privilege principles
- Work with S3 and AWS CLI
- Monitor resources using CloudWatch
- Analyse Linux logs
- Troubleshoot cloud infrastructure problems
- Investigate network and DNS issues
- Troubleshoot IAM permission errors
- Create basic health-check automation

---

# Future Improvements

Possible future improvements include:

- Terraform infrastructure deployment
- Automated EC2 provisioning
- Advanced CloudWatch alarms
- Centralised log monitoring
- AWS CloudTrail integration
- Automated security checks
- CI/CD pipeline
- Automated health monitoring
- Security incident simulation
- Infrastructure-as-Code implementation

---

# Author

**Sri Gayathri**

Aspiring Cloud Security Engineer
