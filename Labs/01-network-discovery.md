\# Lab 01 – Network Discovery



\## Objective



Document the existing enterprise network environment before making configuration changes. The purpose of this lab is to establish a baseline inventory of the current network, verify communication between systems, and validate core services such as DNS and Active Directory.



\---



\## Environment



| System | Role | Operating System |

|----------|------|------------------|

| DC01 | Domain Controller / DNS | Windows Server 2022 |

| FILE01 | File Server | Windows Server |

| CLIENT01 | Domain Workstation | Windows 11 |

| Host Computer | Virtualization Host | Windows 11 |

| Oracle VirtualBox | Type 2 Hypervisor | Current Version |



\---



\## Objectives



\- Identify each system's hostname.

\- Document IPv4 configuration.

\- Record DNS server information.

\- Record MAC addresses.

\- Verify connectivity between systems.

\- Verify DNS name resolution.

\- Confirm Active Directory domain membership.

\- Document the VirtualBox network configuration.



\---



\# Network Inventory



| Device | IPv4 Address | Subnet Mask | DNS Server | Assignment |

|----------|-------------|-------------|------------|------------|

| DC01 | 192.168.10.10 | 255.255.255.0 | 127.0.0.1 | Static |

| FILE01 | 192.168.10.11 | 255.255.255.0 | 192.168.10.10 | Static |

| CLIENT01 | 192.168.10.20 | 255.255.255.0 | 192.168.10.10 | Static |



\---



\# Virtual Network Configuration



Each virtual machine uses two network adapters.



\## Adapter 1



\- Attached To: NAT

\- Purpose: Internet connectivity



\## Adapter 2



\- Attached To: Internal Network

\- Network Name: LABNET

\- Purpose: Internal enterprise communication



\---



\# Verification Performed



\## Hostname



Verified on:



\- DC01

\- FILE01

\- CLIENT01



\---



\## IP Configuration



Collected using:



```cmd

ipconfig /all

```



Verified:



\- IPv4 address

\- Subnet mask

\- DNS server

\- MAC address

\- DHCP status



\---



\## Connectivity Testing



Performed from CLIENT01.



\### Ping DC01



\*\*Result:\*\* Successful



\- 4 packets sent

\- 4 packets received

\- 0% packet loss



\---



\### Ping FILE01



\*\*Result:\*\* Successful



\- 4 packets sent

\- 4 packets received

\- 0% packet loss



\---



\## DNS Verification



Command used:



```cmd

nslookup DC01

```



Result:



Forward lookup successful.



\---



Command used:



```cmd

nslookup FILE01

```



Result:



Forward lookup successful.



\---



\## Domain Verification



Command used:



```cmd

systeminfo | findstr /B /C:"Domain"

```



Result:



CLIENT01 is successfully joined to the \*\*corp.local\*\* domain.



\---



\# Network Diagram



```text

&#x20;                   Internet

&#x20;                       │

&#x20;               VirtualBox NAT

&#x20;                 10.0.2.0/24

&#x20;                       │

──────────────────────────────────────────

&#x20;       Internal Network (LABNET)

&#x20;          192.168.10.0/24

──────────────────────────────────────────



&#x20;     DC01

&#x20;     192.168.10.10

&#x20;     Active Directory

&#x20;     DNS



&#x20;         │



&#x20;     FILE01

&#x20;     192.168.10.11

&#x20;     File Services



&#x20;         │



&#x20;     CLIENT01

&#x20;     192.168.10.20

&#x20;     Domain Workstation

```



\---



\# Findings



\- Internal communication is functioning correctly.

\- All three systems successfully communicate over LABNET.

\- Forward DNS resolution is operational.

\- Active Directory authentication is functioning correctly.

\- All infrastructure servers use static IPv4 addresses.

\- Internet connectivity is provided through separate NAT adapters.

\- The enterprise network is healthy and ready for future configuration.



\---



\# Lessons Learned



\- Always document the existing environment before making changes.

\- Verify IP configuration before troubleshooting applications.

\- Successful ping tests confirm basic Layer 1 through Layer 3 connectivity.

\- Successful `nslookup` confirms forward DNS resolution.

\- Multiple network adapters can serve different purposes within the same environment.

\- A documented network baseline makes future troubleshooting significantly easier.



\---



\# Skills Demonstrated



\- Network discovery

\- Windows networking

\- IPv4 configuration analysis

\- DNS verification

\- Active Directory validation

\- Network documentation

\- VirtualBox networking

\- Enterprise network inventory

\- Systems administration

