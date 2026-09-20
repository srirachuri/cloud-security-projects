# Incident 01 — SSH and HTTP Connectivity Troubleshooting

## Problem

The EC2 instance could not be accessed correctly through SSH, and the website was initially unreachable through HTTP.

## Investigation

I checked the EC2 instance state, Security Group rules, network connectivity, and web server availability.

For SSH, I verified:

- The EC2 instance was running
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

1. Check the EC2 instance state.
2. Check Security Group inbound rules.
3. Test SSH connectivity.
4. Check web server availability.
5. Test HTTP locally.
6. Test HTTP connectivity externally.
7. Restore the required Security Group rule.
8. Verify connectivity again.

## Root Cause

The connectivity issues were caused by controlled changes to the Security Group configuration and service availability during the troubleshooting exercises.

In particular, removing the required HTTP port 80 inbound rule prevented external HTTP access even though the web server was running locally.

## Resolution

The required Security Group rules were restored, and the required services were started.

SSH connectivity was verified successfully.

HTTP connectivity was restored after allowing TCP port 80 in the Security Group.

## Verification

The final tests confirmed:

- SSH connection successful
- HTTP connectivity restored
- Website accessible
- Port 80 available
- Web server responding successfully

## Skills Demonstrated

- EC2 troubleshooting
- AWS Security Groups
- SSH
- HTTP
- TCP ports
- Network troubleshooting
- Linux troubleshooting
- Root-cause analysis

## Evidence

Related screenshots:

- `screenshots/day07-troubleshooting/`
