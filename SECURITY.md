# Security Policy

## Supported Versions

Only the latest state of the `main` branch is actively maintained and supported with security updates.

| Branch / Version | Supported |
| ---------------- | --------- |
| `main`           | Yes       |
| Older commits    | No        |

## Reporting a Vulnerability

Please **do not** report security vulnerabilities, MFA verification bypasses, session/polling flaws, or exposed API credentials through public GitHub Issues or Pull Requests.

Instead, report vulnerabilities privately via one of the following channels:

1. **GitHub Private Vulnerability Reporting:** Use the **Report a vulnerability** button under the **Security** tab of `apensabene/Okta-User-Verify`.
2. **Direct Contact:** Email **apensabene@pm.me** with the subject line `[SECURITY] Okta-User-Verify - <Brief Summary>`.

### What to Include
* Description of the issue and affected component(s) (Okta Factors/Authenticators API integration, push challenge polling handler, or session management)
* Potential impact (e.g., unauthorized MFA push approval bypass, challenge replay, or token exposure)
* Steps to reproduce or suggested remediation

### Response Timeline
* **Initial Acknowledgment:** Within 48 hours
* **Triage & Remediation Assessment:** Within 5 business days

## Security Architecture & Baseline Controls

This repository enforces the following security practices:
* **Out-of-Band Cryptographic Verification:** Replaces static knowledge-based authentication (KBA) with device-bound Okta Verify push challenges.
* **Environment-Isolated Secrets:** Keeps Okta domain URLs and scoped API credentials strictly in environment variables excluded from source control via `.gitignore`.
* **Least-Privilege API Access:** Restricts Okta API permissions to factor verification and challenge status polling.
