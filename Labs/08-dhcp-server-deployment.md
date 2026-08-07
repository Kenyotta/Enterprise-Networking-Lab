\# Lab 08 - Enterprise DHCP Server Deployment



\## Objective



Deploy and configure a Windows Server DHCP server capable of automatically assigning IPv4 addresses and network configuration to enterprise clients.



\---



\# Environment



Domain: corp.local



Server:

DC01



Client:

CLIENT01



Network:

192.168.10.0/24



\---



\# Tasks Completed



\- Installed the DHCP Server role.

\- Installed DHCP management tools (RSAT).

\- Completed post-deployment configuration.

\- Authorized the DHCP server in Active Directory.

\- Created the LABNET Clients IPv4 scope.

\- Configured the address pool.

\- Configured DNS options.

\- Activated the DHCP scope.

\- Converted CLIENT01 from a static IP configuration to DHCP.

\- Verified DHCP lease assignment.



\---



\# DHCP Scope Configuration



Scope Name:



LABNET Clients



Network:



192.168.10.0/24



Address Pool:



192.168.10.21 – 192.168.10.254



Lease Duration:



8 Days



DNS Server:



192.168.10.10



DNS Domain:



corp.local



Gateway:



Not configured (Lab environment)



\---



\# Validation



Verified:



\- DHCP server authorized.

\- Scope active.

\- CLIENT01 received an IP address via DHCP.

\- Lease recorded in Address Leases.

\- DNS server automatically assigned.

\- Domain suffix automatically assigned.



CLIENT01 received:



IP Address:

192.168.10.21



DNS Server:

192.168.10.10



Domain:

corp.local



Lease:

8 Days



\---



\# Skills Practiced



\- Windows Server DHCP installation

\- DHCP authorization

\- Scope creation

\- DHCP options

\- Dynamic IP addressing

\- Enterprise DHCP deployment

\- DHCP verification

\- Client migration from static to DHCP



\---



\# Lessons Learned



DHCP automates network configuration by assigning IP addresses, subnet masks, DNS servers, and lease information to clients.



Infrastructure devices such as Domain Controllers and File Servers should use static IP addresses, while client workstations should typically use DHCP.



DHCP integrates closely with DNS and Active Directory to provide seamless network connectivity for enterprise environments.

