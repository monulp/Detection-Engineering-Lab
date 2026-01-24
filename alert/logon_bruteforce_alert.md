# Alert: Failed Logons Followed by Success

## Description
Detects potential brute-force or password spray activity
where multiple authentication failures are followed by a successful logon.

## Detection Source
Windows Security Event Log  
Event IDs: 4625, 4624

## Trigger Logic
- 3 or more failed logons
- At least 1 successful logon
- Logon types: Network (3), RDP (10)

## Severity
Medium

## Analyst Actions
1. Validate account ownership
2. Check logon source
3. Review surrounding authentication activity
4. Escalate if behavior is anomalous

## Notes
Service and machine accounts may generate noise.
