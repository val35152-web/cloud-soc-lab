# Cloud SOC Lab – AWS CloudTrail

## Objective
Simulate a Security Operations Center (SOC) workflow using AWS CloudTrail by generating and analyzing security-relevant events in a cloud environment. This lab focuses on detecting, investigating, and responding to authentication and authorization failures.

---

## Key Components
- **IAM Users:** Test IAM accounts used to simulate attacker and employee behavior  
- **AWS CloudTrail:** Captures AWS management events such as console logins and API calls  
- **Simulated Threat Activity:** Failed console login attempts and unauthorized IAM API calls  

---

## Lab Goals
- Generate security events using a test IAM user  
- Collect and review events in AWS CloudTrail  
- Analyze logs to identify suspicious behavior  
- Document SOC findings and recommended response actions  

---

## Simulated Security Events

### 1. Failed Console Login (Brute Force Simulation)
- **Event Name:** ConsoleLogin  
- **Result:** Failure  

**Description:**  
Simulated repeated AWS Management Console login failures using an incorrect password to represent a brute-force authentication attempt.

**SOC Response:**  
- Lock or temporarily disable the affected IAM user  
- Enable multi-factor authentication (MFA)  
- Monitor for continued failed login attempts  

**Evidence:**  
`screenshots/failed-login.png`

---

### 2. Access Denied API Call (IAM Enumeration Attempt)
- **Event Name:** ListUsers  
- **Result:** AccessDenied  

**Description:**  
A low-privilege IAM user attempted to list IAM users without sufficient permissions. The request was denied and logged by AWS CloudTrail.

**SOC Response:**  
- Review IAM policies for least-privilege enforcement  
- Monitor for repeated unauthorized API calls  
- Investigate correlated activity from the same source

  **Evidence:**  
`screenshots/failed-console-login-json.png`


---

## Key Takeaways
- Demonstrated detection of authentication and authorization failures using AWS CloudTrail  
- Practiced SOC-style log analysis and incident response documentation  
- Reinforced IAM security best practices such as MFA and least privilege  
