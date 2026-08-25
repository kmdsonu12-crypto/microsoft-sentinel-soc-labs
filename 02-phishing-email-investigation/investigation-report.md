# Phishing Email Investigation Report

## 1. Executive Summary

A simulated phishing email was analyzed to identify indicators of compromise (IOCs), determine the likelihood of malicious intent, and recommend appropriate SOC response actions.

The message uses an urgent account-suspension theme and directs the recipient to a suspicious verification website.

## 2. Email Details

| Field | Observation |
|---|---|
| Sender | security-alert@micros0ft-security.example |
| Recipient | admin@contoso.com |
| Subject | Urgent: Your account will be suspended |
| Theme | Account verification |
| Requested Action | Verify account |
| URL | https://login-microsoft-security.example/verify |

## 3. Indicators of Suspicion

### Sender Domain

The sender uses:

`micros0ft-security.example`

The use of `micros0ft` instead of `microsoft` is a classic typosquatting indicator.

### Urgency

The message claims that the account will be suspended within 24 hours.

Urgent threats are commonly used in phishing campaigns to pressure users into acting without verifying the request.

### Suspicious URL

The email directs the user to:

`login-microsoft-security.example/verify`

The domain does not represent the legitimate Microsoft domain.

The URL should be treated as suspicious and should not be opened.

### Credential-Harvesting Theme

The message asks the recipient to verify their identity through an external link, which could be used to collect credentials.

## 4. Analyst Assessment

**Verdict: Suspicious / Likely Phishing**

The message contains multiple phishing indicators:

- Typosquatted sender domain
- Suspicious external domain
- Urgent account-suspension language
- Credential-verification request
- Brand impersonation

Because this is a simulated lab email, no real malicious infrastructure or credential collection is involved.

## 5. Recommended SOC Response

If this were a real enterprise incident:

1. Quarantine the email.
2. Prevent users from accessing the suspicious URL.
3. Search for the same sender/domain across the environment.
4. Search for other recipients of the same campaign.
5. Check whether any users clicked the URL.
6. Check for credential submission.
7. Reset credentials if compromise is confirmed.
8. Revoke active sessions where appropriate.
9. Block malicious indicators according to organizational policy.
10. Document the incident and notify affected users.

## 6. MITRE ATT&CK

Potentially relevant techniques include:

- **T1566 – Phishing**
- **T1566.002 – Phishing: Spearphishing Link**
- **T1583.001 – Acquire Infrastructure: Domains**, if malicious infrastructure acquisition is confirmed.

The final ATT&CK mapping should be based on the evidence available during a real investigation.

## 7. SOC Skills Demonstrated

- Phishing analysis
- Email investigation
- IOC identification
- Domain analysis
- URL analysis
- Threat assessment
- Incident response recommendations
- MITRE ATT&CK mapping

## 8. Conclusion

The simulated email demonstrates a realistic phishing scenario involving brand impersonation, typosquatting, urgency, and a suspicious verification link.

The investigation identified multiple indicators consistent with phishing and recommended containment, investigation, and remediation actions.
