## CloudTrail Event Analysis

**IAM User:** `soc-test-user`

---

### 1. Failed Console Login (Brute Force Simulation)

- **Event Name:** ConsoleLogin  
- **Event Time:** 2026-02-05 10:15 UTC  
- **Source IP:** 203.0.113.5  
- **Result:** Failure  

**Description:**  
Simulated repeated AWS Management Console login failures using an incorrect password to represent a brute-force authentication attempt against an IAM user.

**SOC Analysis:**  
Multiple failed authentication attempts from a single source IP may indicate credential guessing or brute-force activity. If successful, this behavior could lead to account compromise.

**Mitigation / Response:**  
- Temporarily lock or disable the affected IAM user  
- Enable multi-factor authentication (MFA)  
- Monitor for continued failed login attempts from the same IP  


---

### 2. Access Denied API Call (IAM Enumeration Attempt)

- **Event Name:** ListUsers  
- **Event Time:** 2026-02-05 10:20 UTC  
- **Source IP:** 203.0.113.5  
- **Result:** AccessDenied  

**Description:**  
A low-privilege IAM user attempted to call the `ListUsers` API without sufficient permissions. The request was denied and logged by AWS CloudTrail.

**SOC Analysis:**  
Unauthorized IAM enumeration attempts may indicate reconnaissance activity, particularly when correlated with prior failed authentication attempts from the same source IP.

**Mitigation / Response:**  
- Review IAM policies to ensure least-privilege access  
- Monitor for repeated AccessDenied API calls  
- Investigate correlated activity from the same source IP  

---

## Incident Correlation Summary
Both events originated from the same source IP within a short time window, indicating a potential attack sequence involving authentication attempts followed by authorization probing.

