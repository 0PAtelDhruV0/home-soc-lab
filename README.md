# Home SOC Lab

## Objective
This project demonstrates how to build a basic Security Operations Center (SOC) lab using Splunk, Windows Event Logs, Sysmon, and virtual machines. The lab collects Windows security logs, forwards them to Splunk, and detects suspicious activity such as failed login attempts, PowerShell execution, new user creation, and suspicious processes.

## Tools Used
- Splunk Enterprise Free
- Splunk Universal Forwarder
- Windows 10/11 Virtual Machine
- Ubuntu Virtual Machine
- Sysmon
- VirtualBox
- Kali Linux Optional

## Lab Architecture
Windows VM sends security and Sysmon logs to Splunk running on an Ubuntu VM.

```text
Windows VM + Sysmon
        |
        | Splunk Universal Forwarder
        v
Ubuntu VM running Splunk
        |
        v
Splunk Search, Alerts, Dashboards
```

## Skills Demonstrated
- SIEM setup
- Windows Event Log analysis
- Sysmon configuration
- Log forwarding
- Threat detection
- SOC investigation workflow
- Basic incident response documentation

## Detection Use Cases
1. Failed login attempts
2. Successful login monitoring
3. New user creation
4. PowerShell activity
5. Suspicious process execution
6. Basic port scan detection

## Sample SPL Queries

### Failed Login Detection
```spl
index=main EventCode=4625
| stats count by Account_Name, Source_Network_Address
| where count > 5
```

### Successful Login Events
```spl
index=main EventCode=4624
| stats count by Account_Name, Source_Network_Address
```

### New User Created
```spl
index=main EventCode=4720
```

### PowerShell Activity
```spl
index=main powershell
```

### Suspicious Process Execution
```spl
index=main Image="*cmd.exe*" OR Image="*powershell.exe*"
```

## Screenshots
Add screenshots in the `/screenshots` folder:
- VirtualBox lab setup
- Splunk dashboard
- Windows logs received in Splunk
- Failed login detection
- Sysmon process logs
- Detection query results

## What I Learned
This lab helped me understand how SOC analysts collect logs, investigate suspicious activity, and create basic detections using SIEM tools.

## What I Built
Built a Home SOC Lab using Splunk, Sysmon, and Windows Event Logs to collect, analyze, and detect suspicious activities including failed logins, PowerShell execution, and new user creation.
