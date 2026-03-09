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
