# SOC Investigation Report

## Incident Title
Brief name of the incident.

Example: Suspicious Login Attempt Detected

---

## Incident Overview

A short description of the incident and how it was detected.

Example:
A security alert was triggered indicating multiple failed login attempts against a corporate user account followed by a successful authentication from an unfamiliar IP address.

---

## SOC Ticket Information

| Field | Value |
|------|------|
| Ticket ID | SOC-2024-001 |
| Detection Source | SIEM Alert |
| Alert Name | Suspicious Authentication Activity |
| Severity | Medium |
| Status | Investigating |

---

## Alert Triage

Initial triage performed by the SOC analyst.

Questions addressed during triage:

- Is this alert a true positive or false positive?
- Is the user account compromised?
- Is the IP address known or malicious?
- Has this behavior been observed before?

---

## Investigation Steps

1. Review SIEM alert details.
2. Analyze authentication logs.
3. Identify source IP addresses.
4. Check threat intelligence reputation.
5. Determine whether the activity is malicious.

---

## Log Analysis

Example authentication logs reviewed during investigation.

| Timestamp | Username | Source IP | Event |
|----------|----------|----------|------|
| 08:14 | user1 | 185.192.69.45 | Failed Login |
| 08:15 | user1 | 185.192.69.45 | Failed Login |
| 08:17 | user1 | 185.192.69.45 | Successful Login |

Observations:

- Multiple failed login attempts
- Same external IP address
- Successful authentication after failures

---

## IOC Identification

Indicators of Compromise identified during the investigation.

| IOC Type | Indicator | Description |
|------|------|------|
| IP Address | 185.192.69.45 | Source IP used during login attempts |
| Username | user1 | Targeted account |

---

## MITRE ATT&CK Mapping

| Technique | ID | Description |
|------|------|------|
| Brute Force | T1110 | Attempt to gain access using multiple authentication attempts |

---

## Incident Classification

Final determination of the incident.

Example:

The activity is classified as a **potential brute force attack** against a corporate user account.

---

## Severity Assessment

Severity level assigned to the incident.

Example:

Medium

Reason:
Multiple authentication failures followed by successful login from an external IP.

---

## Response Actions

Actions taken or recommended to mitigate the incident.

Examples:

- Reset the affected user password
- Enable MFA for the account
- Block the malicious IP address
- Monitor for additional login attempts

---

## Lessons Learned

Key takeaways from the investigation.

Examples:

- MFA should be enforced for external authentication
- SIEM alerts helped detect abnormal login patterns

---

## Analyst Notes

Additional observations made during the investigation.

Example:

Further monitoring recommended for the affected account to ensure no further suspicious activity occurs.
