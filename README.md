# Brute-Force Attack Detection using Splunk

## Objective
Detect and investigate repeated SSH authentication failures
using Splunk in a simulated SOC environment.

## Tools Used
- Splunk Enterprise
- Splunk Universal Forwarder
- Linux
- Windows
- SSH
- VirtualBox

## Attack Flow
Attacker
   ↓
SSH Brute-Force Attempts
   ↓
Authentication Logs
   ↓
Splunk
   ↓
Detection
   ↓
Investigation
   ↓
Incident Response

## Key Detection
Repeated failed SSH authentication attempts from the same source IP.

## Incident Response
The incident was investigated by identifying the source IP,
reviewing authentication events, correlating login activity,
and documenting recommended response actions.

## Evidence
Screenshots and the incident response report are included
in this repository.
