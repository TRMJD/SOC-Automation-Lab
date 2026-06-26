# Problems I ran into 

## Problem 1: Browser not connecting to IP Address 10.0.2.15 (Wazuh)
Upon setting up Wazuh and trying to check my endpoints, I was not able to connect to the website from the Windows 11 client.
### Cause: Ubuntu (Server) and Windows 11 were attached to different NAT networks
### Solution: Connected both VMs to the same NAT Network (SOC-NAT)

## Problem 2: Missing Wazuh Alerts
After generating sysmon events locally, I found that no alerts were appearing in Wazuh.
### Cause: Events were not shown because the Ubuntu Server disk was full
### Solution: Expanded the virtual disk, extended the Linus partition, and restarted the Wazuh services

## Problem 3: Wazuh Dashboard not Fetching
Upon logging into the Wazuh Dashboard, the API was not connected.
(images/Detection-Error.png)
### Solution: Restart the Wazuh Services in Ubuntu
- sudo systemctl restart wazuh-indexer
- sudo systemctl restart wazuh-manager
- sudo systemctl restart wazuh-dashboard
