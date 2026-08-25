# Indicators of Compromise (IOCs)

The following indicators were identified during analysis of the simulated phishing email.

| Type | Indicator | Assessment |
|---|---|---|
| Email Address | security-alert@micros0ft-security.example | Suspicious |
| Sender Domain | micros0ft-security.example | Suspicious / Typosquatting |
| URL Domain | login-microsoft-security.example | Suspicious |
| URL Path | /verify | Potential credential-harvesting page |
| Subject | Urgent: Your account will be suspended | Phishing indicator |

## Analysis Notes

### Typosquatting

The sender uses `micros0ft` with the number `0` replacing the letter `o`.

This is a common impersonation technique intended to make a fraudulent domain appear similar to a legitimate organization.

### Suspicious Domain

The verification link uses a domain that does not belong to the legitimate Microsoft domain.

The URL should not be accessed during an investigation unless it is being analyzed in an approved, isolated security environment.

### Urgency

The account-suspension deadline is designed to pressure the recipient into taking immediate action.

## IOC Handling

For a real SOC investigation, these indicators could be used to:

- Search email logs
- Search proxy/DNS logs
- Identify additional recipients
- Search endpoint telemetry
- Block malicious domains where appropriate
- Determine whether users interacted with the message
