# Phishing Investigation Report

## Incident Overview

A corporate user reported a suspicious email to the Security Operations Center (SOC) after receiving a message claiming to be from the IT department requesting account verification.

The email contained a link directing the user to an external website asking for login credentials. Due to the potential risk of credential theft, the SOC team initiated an investigation to determine whether the email was part of a phishing campaign.

---

## SOC Ticket Information

| Field | Value |
|------|------|
| Ticket ID | SOC-2024-017 |
| Detection Source | User Report |
| Alert Type | Phishing Email |
| Severity | Medium |
| Status | Investigating |

---

## Alert Triage

Initial triage was performed after the user submitted the suspicious email to the SOC team.

Key questions during triage:

- Is the email legitimate or malicious?
- Does the email contain suspicious links or attachments?
- Is the sender domain trusted?
- Has the domain been previously associated with phishing campaigns?

Preliminary analysis indicated that the email originated from an external domain not associated with the organization.

---

## Investigation Steps

1. Analyze the email headers to identify the sender and originating mail server.
2. Extract embedded URLs from the email body.
3. Check the domain reputation using threat intelligence platforms.
4. Investigate whether other employees received the same email.
5. Determine whether the phishing link leads to a credential harvesting page.
   
---

## Email Header Analysis

The email headers were analyzed to determine the true origin of the message.

Key observations:

- The sender domain does not match the official corporate domain.
- The message passed through multiple external mail servers before delivery.
- SPF and DKIM authentication checks failed.

These indicators suggest that the email may have been spoofed or sent from an unauthorized mail server.

Example header indicators reviewed:

| Header Field | Value |
|------|------|
| From | it-support@secure-authentication.com |
| Reply-To | support@secure-authentication.com |
| Return-Path | support@secure-authentication.com |

The domain used in the email was not associated with the organization's legitimate IT infrastructure.

---

## URL Analysis

The email contained a hyperlink directing the recipient to an external website requesting account verification.

The URL was extracted and analyzed using threat intelligence tools.

Example URL extracted from the email:

hxxp://secure-authentication-check[.]com/login

Observations:

- The domain is newly registered.
- The domain name attempts to mimic a legitimate authentication service.
- Threat intelligence lookup indicates the domain may be associated with phishing activity.

The website appears to be designed to collect user credentials.

---

## Indicators of Compromise (IOCs)

| IOC Type | Indicator | Description |
|------|------|------|
| Domain | secure-authentication-check[.]com | Phishing domain used in email |
| URL | hxxp://secure-authentication-check[.]com/login | Credential harvesting page |
| Email Address | it-support@secure-authentication.com | Suspicious sender address |

These indicators were extracted during the investigation and should be monitored or blocked within the organization's security controls.

---

## MITRE ATT&CK Mapping

| Technique | ID | Description |
|------|------|------|
| Phishing | T1566 | Adversaries send phishing emails to obtain sensitive information |
| Spearphishing Link | T1566.002 | Malicious link used to redirect victims to credential harvesting site |

---

## Incident Classification

Based on the investigation findings, this activity has been classified as a **phishing attempt targeting corporate users**.

The email was designed to trick recipients into visiting a malicious website and submitting their login credentials.

No evidence was found indicating that any user credentials were successfully compromised during this incident.

---

## Response Actions

The following actions were taken or recommended by the SOC team:

- The phishing email was reported and removed from user inboxes.
- The malicious domain was blocked at the organization's web filtering gateway.
- The sender email address was added to the email security blocklist.
- Users were advised not to interact with similar emails.
- Additional monitoring was implemented to detect similar phishing attempts.

---

## Lessons Learned

This investigation highlights the importance of user awareness and prompt reporting of suspicious emails.

Key takeaways:

- Users should be trained to identify phishing indicators.
- Email security filters should be configured to detect spoofed domains.
- Multi-factor authentication (MFA) can reduce the impact of credential harvesting attacks.

---

## Analyst Notes

The reported phishing email appears to be part of a broader phishing campaign targeting multiple organizations.

Continuous monitoring of similar domains and phishing indicators is recommended to prevent future attacks.
