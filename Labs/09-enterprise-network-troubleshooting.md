\# Lab 09 - Enterprise Network Troubleshooting



\## Objective



Learn a structured methodology for diagnosing and troubleshooting enterprise networking issues using built-in Windows networking tools.



\---



\# Commands Practiced



hostname



ipconfig



ipconfig /all



ping



nslookup



arp -a



\---



\# Key Concepts



Troubleshooting should follow a logical process rather than guessing.



Typical troubleshooting order:



1\. Physical connectivity

2\. IP configuration

3\. Gateway

4\. DNS

5\. Connectivity

6\. Routing

7\. Services



\---



\# Scenarios Covered



\## Scenario 1



Hostname failed.



IP address responded.



Diagnosis:



DNS issue.



Tools Used:



ping



nslookup



\---



\## Scenario 2



APIPA Address



169.254.x.x



Diagnosis:



Client could not obtain a DHCP lease.



Possible causes:



\- DHCP server unavailable

\- Network connectivity issue

\- DHCP scope exhausted



Tools Used:



ipconfig



ipconfig /renew



\---



\## Commands Learned



\### hostname



Displays the local computer name.



Useful for confirming the correct device is being managed.



\---



\### ipconfig



Displays current network configuration.



Useful for verifying IP address, subnet mask, and gateway.



\---



\### ping



Tests network connectivity.



Can verify both name resolution and IP connectivity.



\---



\### nslookup



Queries DNS directly.



Useful for diagnosing DNS issues.



\---



\### arp -a



Displays the local ARP cache.



Maps IP addresses to MAC addresses.



Useful for Layer 2 troubleshooting.



\---



\# Lessons Learned



Successful troubleshooting is based on evidence, not guessing.



A successful ping to an IP address but a failed ping to a hostname usually indicates a DNS problem rather than a network connectivity problem.



A 169.254.x.x address indicates a DHCP issue because Windows assigned itself an Automatic Private IP Address (APIPA) after failing to contact a DHCP server.

