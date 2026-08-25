# Brute Force Detection & Investigation

## Objective

Detect suspicious authentication activity involving multiple failed login attempts followed by a successful login from the same user and IP address.

## Environment

- Microsoft Azure
- Microsoft Sentinel
- Azure Log Analytics
- Kusto Query Language (KQL)

## Scenario

A user account experienced multiple failed authentication attempts followed by a successful login from the same source IP.

The activity may indicate:

- Brute-force attack
- Password spraying
- Compromised credentials

## Detection Logic

The detection identifies authentication activity where:

- Failed attempts >= 3
- Successful logins >= 1
- Activity is associated with the same user/IP context

## Test Result

The KQL test successfully identified:

| Field | Value |
|---|---|
| User | admin@contoso.com |
| Source IP | 185.220.101.45 |
| Application | Microsoft 365 |
| Failed Attempts | 5 |
| Successful Logins | 1 |

## KQL

The detection query is available in:

`brute-force-detection.kql`

## Investigation Steps

1. Identify the affected user.
2. Identify the source IP address.
3. Review the number of failed authentication attempts.
4. Confirm whether a successful login occurred.
5. Review the application involved.
6. Determine whether the activity appears legitimate or suspicious.
7. Check for additional authentication activity from the same IP.
8. Recommend appropriate containment or remediation.

## MITRE ATT&CK

Potentially relevant techniques:

- T1110 – Brute Force
- T1078 – Valid Accounts

The final ATT&CK mapping should be confirmed based on the complete investigation.

## Analyst Assessment

The test data demonstrates a suspicious authentication pattern consisting of five failed login attempts followed by one successful login from the same IP address.

Further investigation would be required before determining whether the activity represents an actual compromise.

## Evidence

Screenshots from the Microsoft Sentinel Log Analytics investigation will be added to this project.

## Disclaimer

This project is a security lab created for educational and professional portfolio purposes. The authentication data used in the lab is simulated test data.
