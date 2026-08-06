\# Lab 04 – Exploring DNS on DC01



\## Objective



Explore the Windows Server DNS service, examine the Active Directory-integrated DNS zone, and understand how DNS supports name resolution within the enterprise environment.



\---



\# Environment



| System | Role |

|----------|------|

| DC01 | Domain Controller / DNS |

| FILE01 | File Server |

| CLIENT01 | Domain Workstation |



Domain:



corp.local



\---



\# DNS Manager Exploration



Opened DNS Manager on DC01 and explored the following components:



\- Forward Lookup Zones

\- Reverse Lookup Zones

\- Conditional Forwarders

\- Root Hints

\- Forwarders



Verified that the DNS service was operating correctly.



\---



\# Forward Lookup Zone



Examined:



corp.local



Observed DNS record types including:



\- SOA

\- NS

\- Host (A)

\- Host (AAAA)



Also observed Active Directory folders:



\- \_msdcs

\- \_sites

\- \_tcp

\- \_udp

\- DomainDnsZones

\- ForestDnsZones



These folders contain service records used by Active Directory.



\---



\# Host Records



Verified the following A Records:



| Host | Address |

|------|---------|

| DC01 | 192.168.10.10 |

| FILE01 | 192.168.10.11 |

| CLIENT01 | 192.168.10.20 |



Also observed that DC01 contains an additional NAT address due to the VirtualBox NAT adapter.



\---



\# Name Resolution Testing



Executed:



```cmd

nslookup FILE01

```



Executed:



```cmd

ping FILE01

```



Observed that Windows performs DNS name resolution before attempting communication.



\---



\# Active Directory Integration



Learned that Active Directory relies heavily on DNS.



DNS provides the location of:



\- Domain Controllers

\- LDAP Services

\- Kerberos Services



Without DNS, domain authentication and Group Policy processing would fail.



\---



\# Key Concepts Learned



\- DNS translates hostnames into IP addresses.

\- Forward Lookup Zones contain hostname records.

\- Active Directory stores service records inside DNS.

\- DNS is required before most network communication begins.

\- Ping relies on successful DNS resolution when using hostnames.



\---



\# Skills Demonstrated



\- Windows DNS Administration

\- DNS Manager Navigation

\- Active Directory DNS

\- Name Resolution

\- DNS Record Identification

\- Enterprise Windows Server Administration



\---



\# Lessons Learned



\- DNS is critical to Active Directory.

\- A Records map hostnames to IPv4 addresses.

\- Windows uses DNS before initiating communication.

\- Active Directory automatically registers DNS service records.

\- Enterprise environments depend on reliable DNS services.

