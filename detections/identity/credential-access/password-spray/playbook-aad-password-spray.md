# Incident Response Playbook – AAD Password Spray

## Detection
AAD-PasswordSpray-WithSuccess-Correlation

## Severity
High

## MITRE ATT&CK
- T1110.003 – Password Spraying
- T1078 – Valid Accounts

---

## Triage

1. Check SprayLedToSuccess field.
2. Review IP reputation.
3. Validate if IP belongs to corporate NAT/VPN.
4. Identify targeted users.
5. Identify successful users (if any)

---

## Investigation

- Review full login timeline for IP.
- Check for MFA bypass.
- Verify conditional access policies.
- Check Azure AD Identity Protection risk events.
- Confirm if accounts have privileged roles.

---

## Response

If SprayLedToSuccess = false:
- Block IP.
- Monitor repeat attempts.
- Notify targeted users.

If SprayLedToSuccess = true:
- Force password reset.
- Revoke refresh tokens.
- Review lateral movement.
- Block IP immediately.
- Escalate to IR team.

---

## Automation Opportunities

- Auto-block high-risk IP.
- Auto-force password reset.
- Add IP to watchlist.
- Send Teams/Email notification.

---

## Lessons Learned

Track recurring IPs and analyze spray campaigns over time.
