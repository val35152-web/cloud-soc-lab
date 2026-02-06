# Incident Response Recommendations

| Finding Type           | Severity | Recommended Action                                  | MITRE ATT&CK ID |
|------------------------|----------|----------------------------------------------------|-----------------|
| Failed Console Login   | Medium   | Investigate source IP, enable MFA, monitor activity | T1110           |

## Notes
- Failed console login attempts may indicate brute-force activity.
- SOC analysts should review CloudTrail logs for repeated failures from the same source.
- This workflow demonstrates real-world SOC investigation using AWS CloudTrail.

