# Incident Response Recommendations

| Finding Type                 | Severity | Recommended Action                                   | MITRE ATT&CK ID |
|-------------------------------|---------|-----------------------------------------------------|----------------|
| Failed Console Login          | Medium  | Lock account, investigate source IP, enable MFA     | T1110          |
| Access Denied API Call        | Low     | Review IAM permissions, verify user intent          | T1078          |
| Unauthorized Password Change  | High    | Force password reset, check for other suspicious activity | T1078  |

## Notes
- Document each simulated incident as if it were a real SOC alert
- Cross-reference CloudTrail logs for context
- Use this workflow for SOC interview demonstrations
