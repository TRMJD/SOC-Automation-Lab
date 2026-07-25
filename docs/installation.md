# Installation Guide
Overview

This project simulates a Security Operations Center (SOC) using Wazuh to monitor a Windows 11 endpoint. Sysmon provides detailed Windows telemetry, while Atomic Red Team is used to simulate adversary behavior based on the MITRE ATT&CK framework.

Prerequisites
- Oracle VirtualBox
- Ubuntu Server 22.04 LTS
- Windows 11 VM
- At least 8 GB RAM allocated to the Ubuntu VM
- At least 40 GB of virtual disk space (recommended)
- Internet connectivity for both virtual machines

# Installation Steps
1. Configure the Virtual Environment
Create two virtual machines:
Ubuntu Server 22.04
Windows 11
Attach both VMs to the same VirtualBox NAT Network (e.g., SOC-NAT) to allow communication between the endpoint and the Wazuh server.

2. Install the Wazuh Platform

On the Ubuntu Server:

Install the Wazuh Manager
Install the Wazuh Indexer
Install the Wazuh Dashboard

Verify that all services are running:
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard

3. Deploy the Windows Agent

On the Windows 11 VM:

Install the Wazuh Agent.
Configure the agent to connect to the Wazuh Manager using the server's IP address.
Register the agent with the manager.
Restart the Wazuh Agent service.

Confirm that the endpoint appears as Active in the Wazuh dashboard.

4. Install Sysmon

Download and install Microsoft Sysmon using an appropriate configuration file.

5. Verify Event Collection

Generate several Windows events, such as:

Opening Command Prompt
Launching PowerShell
Creating temporary files

Confirm that Sysmon events are visible in the Wazuh dashboard.

6. Install Atomic Red Team

Download the Atomic Red Team atomics repository.

Use the PowerShell module to execute MITRE ATT&CK simulations.

# Running the System
1. Access the Dashboard

Open a web browser and navigate to:

https://<WAZUH_SERVER_IP>

Log in using the configured Wazuh credentials.

2. Generate Activity

Generate normal system activity or execute Atomic Red Team tests to produce telemetry.

Examples include:

Opening PowerShell
Executing Command Prompt
Running Atomic Red Team simulations

3. Investigate Alerts

Navigate to:

Security Events → Events

Review the generated alerts, inspect event metadata, and analyze the associated MITRE ATT&CK techniques.
