# Incident 02 — Nginx Service Failure

## Problem

The Nginx web server became unavailable during a controlled troubleshooting exercise.

## Investigation

I checked the Nginx service status and tested HTTP connectivity locally.

Commands used included:

```
sudo systemctl status nginx
sudo systemctl is-active nginx
curl -I http://localhost
The Nginx service was inactive, and the local HTTP request failed because the service was stopped.
```
## Root Cause
I intentionally stopped the Nginx service to simulate a web server failure.

## Resolution
I restarted the Nginx service:
```
sudo systemctl start nginx

Then I verified the service:

sudo systemctl is-active nginx

The result was:
active
```
## Verification
HTTP connectivity was tested again:
```
curl -I http://localhost
```
The response returned:
```
HTTP/1.1 200 OK
```
This confirmed that Nginx was running and serving HTTP requests.

## Skills Demonstrated
Nginx
Linux systemd
Service troubleshooting
HTTP troubleshooting
Localhost testing
Recovery verification
Evidence

## Related screenshots:
screenshots/day08-nginx-troubleshooting/
