# Investigation Report – Brute Force Detection

## 1. Incident Scenario

A simulated Microsoft 365 account experienced multiple failed authentication attempts followed by a successful login from the same source IP address.

The activity was investigated as a potential brute-force or compromised-account scenario.

## 2. Evidence

| Indicator | Observation |
|---|---|
| User | admin@contoso.com |
| Source IP | 185.220.101.45 |
| Application | Microsoft 365 |
| Failed attempts | 5 |
| Successful logins | 1 |

## 3. Detection

The KQL detection identifies authentication activity where:

- Three or more failed attempts occur.
- At least one successful login occurs.
- The activity is associated with the same user and IP context.

The detection successfully identified the simulated activity in Microsoft Sentinel Log Analytics.

## 4. Analyst Analysis

The sequence of repeated authentication failures followed by a successful login is suspicious and can be consistent with:

- Brute-force activity
- Password spraying
- Use of compromised credentials

The available lab data alone is not sufficient to confirm account compromise.

Additional investigation should include:

1. Review sign-in timestamps.
2. Review the source IP reputation and geographic location.
3. Check whether the user normally authenticates from this IP/location.
4. Review other sign-in activity for the account.
5. Check for MFA failures or unusual authentication methods.
6. Review endpoint activity associated with the user.
7. Look for additional accounts targeted from the same IP.

## 5. MITRE ATT&CK

Potentially relevant techniques:

- **T1110 – Brute Force**
- **T1078 – Valid Accounts**

The exact technique should be confirmed based on the complete investigation.

## 6. Recommended Response

If the activity is confirmed as malicious:

1. Validate the activity with the user.
2. Revoke active sessions.
3. Reset the affected account credentials.
4. Require MFA or re-authentication where appropriate.
5. Block or investigate the source IP according to organizational policy.
6. Search for related activity across the environment.
7. Document the investigation and response actions.

## 7. Conclusion

The Microsoft Sentinel KQL detection successfully identified a suspicious authentication pattern involving five failed login attempts followed by one successful login from the same IP address.

This lab demonstrates practical skills in:

- KQL
- Authentication analysis
- Detection engineering
- Microsoft Sentinel
- Threat investigation
- MITRE ATT&CK
- Incident response
