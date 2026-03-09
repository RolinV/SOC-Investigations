# Brute Force Attack Investigation

## Incident Overview

A security alert was triggered in the organization's SIEM indicating a high number of failed login attempts against a corporate user account within a short period of time.

Such behavior may indicate a brute force attack where an attacker attempts multiple password combinations to gain unauthorized access to an account.

The SOC team initiated an investigation to determine whether the activity represented a legitimate user mistake or a malicious login attempt.

---

## SOC Ticket Information

| Field | Value |
|------|------|
| Ticket ID | SOC-2024-024 |
| Detection Source | SIEM Alert |
| Alert Name | Multiple Failed Login Attempts |
| Severity | Medium |
| Status | Investigating |

---

## Alert Triage

During initial triage, the SOC analyst reviewed the alert details in the SIEM dashboard.

Key questions addressed during triage:

- Are the login attempts originating from a known user location?
- Are multiple usernames being targeted?
- Is the source IP address associated with malicious activity?
- Has this IP been observed in previous alerts?

The alert indicated repeated failed authentication attempts against the same account.

---

## Investigation Steps

1. Review authentication logs from the SIEM.
2. Identify the number of failed login attempts.
3. Determine the source IP address.
4. Analyze whether the login attempts targeted multiple accounts.
5. Check the reputation of the source IP address.

---

## Log Analysis

Authentication logs revealed multiple failed login attempts originating from the same external IP address.

| Timestamp | Username | Source IP | Event |
|----------|----------|----------|------|
| 08:14:02 | j.smith | 185.192.69.45 | Failed Login |
| 08:14:11 | j.smith | 185.192.69.45 | Failed Login |
| 08:14:19 | j.smith | 185.192.69.45 | Failed Login |
| 08:14:33 | j.smith | 185.192.69.45 | Failed Login |
| 08:14:45 | j.smith | 185.192.69.45 | Failed Login |

Observations:

- Multiple authentication failures within a short timeframe
- Same source IP address
- Targeting a single user account

This pattern is consistent with brute force attack behavior.

---

## Indicators of Compromise (IOCs)

| IOC Type | Indicator | Description |
|------|------|------|
| IP Address | 185.192.69.45 | Source of repeated login attempts |
| Username | j.smith | Targeted user account |

---

## MITRE ATT&CK Mapping

| Technique | ID | Description |
|------|------|------|
| Brute Force | T1110 | Adversaries attempt to gain access by trying multiple passwords |

---

## Incident Classification

The activity was classified as a **suspected brute force attack** targeting a corporate user account.

Although no successful login was observed during the attack window, the behavior indicates malicious authentication attempts.

---

## Severity Assessment

Severity: Medium

Reason:

Multiple failed authentication attempts from an external IP address targeting a corporate account.

---

## Response Actions

The SOC team recommended the following actions:

- Block the malicious IP address at the firewall.
- Reset the affected user's password.
- Enable Multi-Factor Authentication (MFA) if not already configured.
- Monitor the account for further suspicious login attempts.

---

## Lessons Learned

This investigation demonstrates the importance of monitoring authentication logs for abnormal login patterns.

Key takeaways:

- SIEM alerts help detect brute force attempts early.
- MFA significantly reduces the risk of account compromise.

---

## Analyst Notes

The source IP address should be monitored for future suspicious activity across the environment.
