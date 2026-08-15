# AWS EC2 Linux Server Administration & Support Lab

## Project Overview

This project demonstrates deploying and administering an **Ubuntu Linux server on AWS EC2** using the AWS Free Tier.

The goal of this lab was to gain practical experience with Linux system administration, remote server access, system services, logs, permissions, package management, web server configuration, and basic troubleshooting.

This project was completed as hands-on preparation for **Linux Support, Technical Support, Cloud Support, and Junior Linux Administration** roles.

---

## Environment

* **Cloud Platform:** AWS
* **Service:** Amazon EC2
* **Operating System:** Ubuntu 24.04 LTS
* **Instance Type:** AWS EC2
* **Architecture:** x86_64
* **Remote Access:** SSH
* **Web Server:** Nginx
* **Package Manager:** APT
* **Service Manager:** systemd
* **Shell:** Bash

---

## Objectives

The main objectives of this project were to:

* Deploy a Linux server using AWS EC2
* Connect to the server securely using SSH
* Perform basic Linux system administration
* Manage files, directories, users, permissions, and ownership
* Install and manage software packages
* Monitor system services
* Work with Linux system and authentication logs
* Install and configure Nginx
* Verify and troubleshoot Linux services
* Practice basic Linux support and troubleshooting workflows

---

## Tasks Performed

### 1. AWS EC2 Linux Server Deployment

Created an Ubuntu Linux EC2 instance using AWS.

The instance was configured for hands-on Linux administration and cloud infrastructure practice.

---

### 2. SSH Remote Access

Connected to the Ubuntu EC2 instance remotely from Windows PowerShell using SSH.

Example:

```
ssh -i "linux-key.pem" ubuntu@<EC2-PUBLIC-IP>
```

This provided hands-on experience with:

* SSH
* SSH key authentication
* Remote Linux administration
* Linux command-line access

> **Security Note:** Private SSH keys and sensitive AWS credentials were never uploaded to GitHub.

---

### 3. Linux System Administration

Performed basic Linux administration tasks including:

```
whoami
pwd
ls -l
mkdir
```

These commands were used to verify the current user, working directory, files, directories, and permissions.

---

### 4. File Permissions and Ownership

Practised Linux permission management using:

```bash
chmod
chown
ls -ld
```

Example workflow:

```
mkdir test_app
chmod 777 test_app
ls -ld test_app

chmod 755 test_app
sudo chown ubuntu:ubuntu test_app
ls -ld test_app
```

This demonstrated practical understanding of:

* Linux permissions
* Read/write/execute permissions
* File ownership
* User and group ownership

---

### 5. Package Management

Updated the Ubuntu package repositories using:

```
sudo apt update
```

Installed Nginx using:

```
sudo apt install nginx -y
```

This provided hands-on experience with the Ubuntu APT package management system.

---

### 6. Nginx Web Server Installation

Installed and configured the Nginx web server on the EC2 Ubuntu instance.

Verified the service using:

```
sudo systemctl status nginx
```

The service was successfully shown as:

```
Active: active (running)
```

This demonstrated experience with:

* Software installation
* Nginx
* systemd
* Service status verification
* Linux web-server administration

---

### 7. Linux Service Management

Used systemd to inspect running services:

```
systemctl list-units --type=service --state=running
```

This provided practical experience identifying active Linux services such as:

* nginx
* ssh
* cron
* systemd-journald
* systemd-networkd
* systemd-resolved
* unattended-upgrades

---

### 8. Linux Log Analysis

Inspected system logs using:

```
sudo journalctl -xe
```

Also examined authentication logs:

```
sudo cat /var/log/auth.log
```

Used log information to understand:

* SSH connections
* User sessions
* Authentication activity
* sudo activity
* System services
* System startup/shutdown events

This is particularly relevant to Linux Support and Technical Support roles.

---

## Troubleshooting Skills Practised

During the project, I practised the basic troubleshooting workflow used when investigating Linux server problems:

```
Identify the problem
        ↓
Check system/service status
        ↓
Review logs
        ↓
Check configuration
        ↓
Apply corrective action
        ↓
Verify the result
```

Examples of tools and commands used:

```
systemctl
journalctl
cat
grep
ls -l
chmod
chown
apt
ssh
```

---

## Skills Demonstrated

### Linux

* Ubuntu Linux
* Bash command line
* File and directory management
* Users and groups
* File permissions
* File ownership
* Package management
* Process/service management
* systemd
* Linux logs
* SSH
* Basic troubleshooting

### AWS

* Amazon EC2
* Linux cloud server deployment
* EC2 networking fundamentals
* Remote server administration

### Web Server

* Nginx installation
* Nginx service management
* systemd service verification

### Support Skills

* Troubleshooting methodology
* Log analysis
* Service verification
* Permission troubleshooting
* Remote server administration

---

## Project Evidence

Screenshots demonstrating the project are stored in the `Screenshots/` directory.

The screenshots include evidence of:

1. SSH connection to the Ubuntu EC2 instance
2. Linux system information
3. `journalctl` log analysis
4. Authentication log analysis
5. File permissions and ownership
6. APT package management
7. Nginx installation
8. Nginx service verification
9. Running Linux services
10. AWS EC2 instance configuration

---

## What I Learned

Through this project, I gained practical experience administering a Linux server running in a cloud environment.

The project helped me understand how Linux administration and cloud infrastructure work together and gave me hands-on practice with the types of tasks commonly encountered in entry-level Linux and cloud support environments.

---

## Career Relevance

This project was created to build practical skills for entry-level roles such as:

* Linux Support Trainee
* Linux Support Intern
* Junior Linux Support Engineer
* Linux Technical Support Engineer
* Linux Operations Trainee
* Junior System Administrator
* Cloud Support Associate

It also provides a foundation for progressing toward **Cloud Support and Cloud Security** roles.

---

## Technologies Used

```
AWS EC2
Ubuntu 24.04 LTS
Linux
Bash
SSH
systemd
Nginx
APT
Git/GitHub
```

## Project Status

**Completed — Initial Linux EC2 Administration Lab**

