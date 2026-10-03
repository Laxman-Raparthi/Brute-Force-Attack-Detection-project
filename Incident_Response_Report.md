# Incident Response Report – Brute-Force Attack Detection

## 1. Incident Overview

**Incident Name:** Brute-Force Login Attack  
**Project:** SOC Environment – Brute-Force Attack Detection  
**SIEM:** Splunk Enterprise  
**Target:** Windows Machine  
**Attack Source:** Linux Attacker Machine  
**Severity:** Medium  
**Status:** Resolved / Investigated

## 2. Incident Description

A brute-force login attack was simulated in the SOC lab environment. The attacker repeatedly attempted to log in to the Windows target machine using incorrect credentials.

The authentication events were collected and forwarded to Splunk, where the repeated failed login attempts were detected and investigated.

## 3. Detection

Splunk was used to identify multiple authentication failures generated during the attack.

For Windows authentication, **Event ID 4625** indicates a failed logon attempt.

The investigation focused on:

- Repeated failed login attempts
- Source IP address
- Target username
- Target machine
- Time of the authentication attempts
- Successful login following multiple failures

## 4. Investigation

The SOC analyst investigated the events in Splunk to determine whether the activity represented a possible brute-force attack.

The following information was examined:

| Investigation Item | Details |
|---|---|
| Attack Type | Brute-Force Login Attack |
| Source IP | 10.20.30.6 |
| Target | 10.20.30.5 |
| Authentication | SSH authentication|
| Failed Login Event | Event ID 4625 |
| SIEM | Splunk Enterprise |
| Evidence | Splunk authentication logs |

Multiple failed authentication attempts from the same source were observed within a short period, indicating suspicious login activity.

## 5. Correlation

The authentication events were correlated in Splunk to understand the sequence of activity.

**Attack sequence:**

Multiple failed login attempts  
↓  
Same source IP identified  
↓  
Authentication activity investigated  
↓  
Successful login checked  
↓  
Activity assessed as suspicious

This correlation helps a SOC analyst determine whether repeated failed attempts were followed by a successful authentication.

## 6. Response Actions

After identifying the suspicious authentication activity, the following response actions can be performed in a real SOC environment:

1. Block the suspicious source IP address.
2. Lock or temporarily disable the targeted account if necessary.
3. Reset the affected user's password if compromise is suspected.
4. Terminate suspicious active sessions.
5. Check additional logs for further malicious activity.
6. Continue monitoring the source IP and affected account.

For this lab, Splunk was primarily used for **detection, investigation, and correlation**. Response actions are documented as the recommended SOC response procedure.

## 7. Evidence

The following screenshots were collected as evidence:

- Splunk login/authentication events
- Multiple failed login attempts
- Source IP address
- Successful login event
- Splunk correlation/investigation results
- Relevant Windows authentication events

Screenshots are included in the project documentation to demonstrate the detection and investigation process.

## 8. Incident Conclusion

The simulated brute-force attack generated multiple authentication failures on the target Windows machine. The events were successfully collected and analyzed using Splunk.

The source IP and authentication activity were investigated, and the login events were correlated to understand the attack sequence.

This project demonstrates a basic SOC workflow:

**Attack → Log Collection → SIEM Detection → Investigation → Correlation → Response → Incident Documentation**

## 9. Lessons Learned

This project demonstrated the importance of:

- Monitoring authentication logs
- Detecting repeated failed login attempts
- Identifying suspicious source IP addresses
- Correlating authentication events
- Investigating successful logins after repeated failures
- Documenting security incidents
- Following an incident response process

## 10. Final Status

**Incident:** Brute-Force Login Attack  
**Detection:** Successful  
**Investigation:** Completed  
**Correlation:** Completed  
**Evidence Collection:** Completed  
**Response Procedure:** Documented  
**Incident Status:** Resolved / Closed