# SOC-Automation-Lab
Homemade virtual lab that simulates a SOC (Security Operations Center) all on my host PC using Wazuh, Sysmon, and Windows 11 to collect endpoint telemetry, simulate MITRE ATT&CK techniques, and investigate security alerts.

## Technologies Used
VirtualBox
Ubuntu 22.04
Windows 11
Wazuh
Sysmon
Atomic Red Team
MITRE ATT&CK

## Features
- Collect Windows endpoint logs
- Monitor Sysmon Event IDs
- Detect PowerShell activity
- Simulate attacks using Atomic Red Team
- Investigate alerts using the Wazuh Dashboard

## Example Detections
- T1059.001 : PowerShell
- T1055 : Process Injection

## Documentation

See "/docs" for installation, troubleshooting, and alert analysis.
