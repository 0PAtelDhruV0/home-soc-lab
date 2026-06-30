# Incident Report Template

## Incident Title
Example: Multiple Failed Login Attempts Detected

## Date and Time
YYYY-MM-DD HH:MM

## Detection Source
Splunk Search / Windows Event Log / Sysmon

## Alert Query
```spl
Paste SPL query here
```

## Summary
Briefly describe what happened.

## Evidence
- Event ID:
- Source IP:
- Username:
- Hostname:
- Process Name:
- Screenshot Filename:

## Investigation Steps
1. Reviewed Splunk alert results.
2. Checked affected username and source IP.
3. Reviewed related Windows Event Logs.
4. Checked for successful login after failed attempts.
5. Documented findings.

## Impact
Low / Medium / High

## Recommended Remediation
- Reset affected password if needed.
- Lock account after repeated failed attempts.
- Enable MFA.
- Review endpoint for suspicious activity.
- Monitor source IP.

## Final Conclusion
Write your final analyst conclusion here.
