# Azure AD Password Spray Detection (With Success Correlation)

## Objective
Detect password spray activity in Azure AD by identifying multiple failed
authentication attempts across several users from a single IP address
within a 30-minute window. Correlates whether the activity resulted in
successful login.

## MITRE ATT&CK
- T1110 – Brute Force
- T1110.003 – Password Spraying
- T1078 – Valid Accounts
- T1078.004 – Cloud Accounts (if success observed)

## Detection Logic
- ≥ 9 failed attempts
- ≥ 3 distinct users targeted
- ≤ 3 attempts per user
- 30 minute lookback window
- Correlates successful login events from same IP

## Output Fields
- IPAddress
- TotalFailures
- DistinctUsers
- TargetedUsers
- SuccessfulUsers
- SprayLedToSuccess

## Tuning Guidance
Adjust thresholds based on:
- Tenant size
- VPN/NAT architecture
- Normal authentication failure baseline

## False Positives
- Corporate NAT/VPN IP addresses
- Password expiration day
- MFA registration campaigns
- Red team simulations
- Service accounts retrying authentication

## Version
v1.0 – Initial Implementation.
