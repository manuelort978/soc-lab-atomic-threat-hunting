# Atomic Red Team Threat Hunting Report

## Summary
Multiple adversary techniques were simulated using Atomic Red Team.

## Techniques
- T1003 (Credential Access)
- T1057 (Process Discovery)
- T1082 (System Discovery)
- T1110 (Brute Force)

## Findings
- Suspicious process execution detected
- Enumeration behavior identified
- Authentication anomalies observed

## Conclusion
The lab successfully demonstrated adversary behavior and detection opportunities using Wazuh.

## Recommendations
- Monitor process creation events (4688 AND 600)
- Track authentication activity
- Implement detection rules
