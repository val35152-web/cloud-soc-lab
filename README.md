# Cloud SOC Lab – AWS Simulation

## Objective
Simulate a Security Operations Center (SOC) workflow using AWS CloudTrail.  
Generate and analyze events to practice detection, investigation, and response.

## Key Components
- **IAM Users**: Test accounts to simulate attackers / employees
- **CloudTrail**: Logs all management events (console logins, API calls)
- **Simulated Threats**: Failed logins, AccessDenied API calls, password changes

## Lab Goals
1. Generate AWS events using a test IAM user
2. Collect events in CloudTrail
3. Analyze logs to detect suspicious activity
4. Document findings and recommended responses

## Notes
- No GuardDuty required
- Fully Free Tier compatible
