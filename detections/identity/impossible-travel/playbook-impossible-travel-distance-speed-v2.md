# Impossible Travel Detection Playbook

## Objective
Detect account compromise through geographically impossible sign-ins based on distance and speed

## Threat Model
- MITRE ATT&CK: T1078 - Valid Accounts
- Risk: Stolen credentials, session hijacking, token replay

## Detection Logic
- Time delta ≤ 120 minutes
- Distance ≥ 500 km
- Speed ≥ 850 km/h
- Risk-based scoring model

## Tuning Strategy
- Exclude Trusted IP watchlist
- Exclude Service Accounts watchlist
- Adjustable:
  - MaxSpeedKmh
  - MaxTravelTimeMinutes
  - MinDistanceKM

## False Positives
- VPN usage
- Corporate proxy gateways
- Mobile carrier NAT
- Satellite internet

## Investigation Steps
1. Validate IP ASN and ownership
2. Check device ID change
3. Review MFA status
4. Validate travel history
5. Check other concurrent sessions

## Automated Response (Optional SOAR)
- Trigger Conditional Access policy
- Force password reset
- Revoke active sessions
- Notify SOC Tier 2

## Metrics
- Alert-to-incident ratio
- Mean Time To Triage (MTTT)
- False positive rate