# Incident 03 — Disk, CPU and Memory Resource Troubleshooting

## Problem

The EC2 Linux instance was tested for disk, CPU and memory resource pressure.

## Investigation

### Disk

I checked disk usage using:

```
df -h
```
A controlled test file was created to simulate increased disk usage.
The test initially used /tmp. I observed that /tmp was backed by tmpfs, so the test did not affect the root filesystem as expected.
I then moved the test to /var/tmp and identified the large test file using:
```
du -sh /var/*
```
## Resolution
The test file was removed, and disk usage returned to normal levels.

## CPU
CPU usage was monitored using:
```
top
```
A controlled CPU-intensive process was started to simulate high CPU usage.
The process was identified and terminated.
CPU utilisation returned to normal.
## Memory
Memory usage was checked using:
```
free -h
```
A controlled memory-intensive Python process was used to simulate memory pressure.
The process was identified, and memory usage returned to normal after the process ended.

## Verification

The final checks confirmed that:

- Disk usage returned to normal
- CPU utilisation returned to normal
- Memory availability recovered

## Skills Demonstrated

- Linux resource monitoring
- Disk troubleshooting
- CPU troubleshooting
- Memory troubleshooting
- `df`
- `du`
- `top`
- `free`
- Process identification and termination

## Evidence

Related screenshots:

- `screenshots/day09-resource-troubleshooting/`
