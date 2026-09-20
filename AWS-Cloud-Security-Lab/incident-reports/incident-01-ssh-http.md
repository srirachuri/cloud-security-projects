# Incident 01 — SSH and HTTP Connectivity Troubleshooting

## Problem

The EC2 instance could not be accessed correctly through SSH, and the web application was initially unreachable through HTTP.

## Investigation

I checked the EC2 instance state, Security Group rules, network connectivity, and service availability.

For SSH, I verified:

- EC2 instance was running
- SSH port 22 was configured in the Security Group
- Network connectivity was tested
- SSH authentication was verified

For HTTP, I checked:

- Port 80 access
- Web server status
- Localhost connectivity
- Security Group inbound rules
- External website connectivity

## Troubleshooting Approach

1. Check EC2 instance state.
2. Check Security Group inbound rules.
3. Verify SSH connectivity.
4. Check whether the web server is running.
5. Test HTTP locally.
6. Check port 80 access from the internet.
7. Restore the required Security Group rule.
8. Verify connectivity again.

## Root Cause

The connectivity problems were caused by incorrect or missing network access configuration and service availability during the controlled troubleshooting exercises.

## Resolution

The required Security Group rules and services were restored.

SSH connectivity was verified successfully.

HTTP connectivity was also restored after correcting the required configuration.

## Verification

The final tests confirmed:

- SSH connection successful
- HTTP connectivity restored
- Website accessible
- Required ports available

## Skills Demonstrated

- EC2 troubleshooting
- Security Groups
- SSH
- HTTP
- TCP ports
- Network troubleshooting
- Linux troubleshooting

## Evidence

Related screenshots:

- `screenshots/day07-troubleshooting/`
