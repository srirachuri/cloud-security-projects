# Incident 04 — Network, DNS and IAM Access Troubleshooting

## Problem

The EC2 instance was tested for network connectivity, DNS resolution, and AWS IAM authorisation.

## Network Investigation

I checked the network interface and routing configuration using:

```
ip addr
ip route
```
The EC2 instance had a private IP address and a default route through the VPC gateway.

## DNS Investigation

DNS configuration was checked, and hostname resolution was tested using:
```
getent hosts amazon.com
getent hosts google.com
```
DNS resolution succeeded.
I also tested HTTPS connectivity using:
```
curl -I https://amazon.com
curl -I https://google.com
```
HTTPS connectivity succeeded.
An ICMP ping test did not receive replies from the external host. This was treated separately from DNS and HTTPS because ICMP availability can differ from application-layer connectivity.

## IAM Investigation
The following command returned an authorisation error:
```
aws s3 ls
```
The caller identity was then checked:
aws sts get-caller-identity
The EC2 instance was using an IAM role.
The role permissions were inspected to determine why the request was denied.

## Root Cause
The aws s3 ls command attempted to list all S3 buckets, but the IAM role did not have permission to perform the required account-level bucket listing operation.
The role did have permission to access the specific lab S3 bucket.

## Verification
Access to the specific bucket was tested successfully:
```
aws s3 ls s3://cloud-security-sri-s3-lab-2026
```
This demonstrated the difference between:
Access to all S3 buckets
Access to a specific S3 bucket

## Health Check
A Linux health-check script was also created to report:

Hostname
Disk usage
Memory
CPU load
Nginx status
Network route

## Skills Demonstrated
Linux networking
DNS troubleshooting
Routing
HTTPS connectivity testing
AWS CLI
IAM roles
IAM policies
S3 permissions
AccessDenied troubleshooting
Bash scripting


## Related screenshots:
screenshots/day10-network-dns-iam/
