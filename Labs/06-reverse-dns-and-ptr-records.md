\# Lab 06 – Reverse DNS and PTR Records



\## Objective



Configure a Reverse Lookup Zone, create Pointer (PTR) records, and verify reverse DNS functionality within an Active Directory-integrated DNS environment.



\---



\# Environment



| System | Role |

|---------|------|

| DC01 | Domain Controller / DNS Server |

| FILE01 | File Server |

| CLIENT01 | Domain Workstation |



Domain:



corp.local



Network:



192.168.10.0/24



\---



\# Background



Throughout previous networking labs, DNS forward lookups functioned correctly, but reverse lookups did not.



Running:



```cmd

nslookup DC01

```



returned:



```

Server: Unknown

Address: 192.168.10.10

```



This indicated that the DNS server could resolve hostnames to IP addresses but could not resolve its own IP address back to its hostname because no Reverse Lookup Zone or PTR record existed.



\---



\# Reverse Lookup Zone Configuration



Verified that no Reverse Lookup Zone previously existed.



Created a new:



\- Active Directory-Integrated Primary Zone

\- IPv4 Reverse Lookup Zone



Network ID:



```

192.168.10

```



Windows automatically created the zone:



```

10.168.192.in-addr.arpa

```



This zone manages reverse DNS records for the entire 192.168.10.0/24 network.



\---



\# PTR Record Creation



Created the first Pointer (PTR) record.



| IP Address | Hostname |

|------------|----------|

| 192.168.10.10 | DC01.corp.local |



During configuration, learned that Windows requests only the \*\*Host ID\*\* when creating PTR records.



Example:



Instead of entering:



```

192.168.10.10

```



only:



```

10

```



is required because the Reverse Lookup Zone already represents the network portion of the address.



\---



\# Reverse Lookup Verification



Executed on CLIENT01:



```cmd

nslookup 192.168.10.10

```



Result:



```

Name: DC01.corp.local

Address: 192.168.10.10

```



This confirmed that reverse DNS resolution was functioning correctly.



\---



\# Forward Lookup Verification



Executed:



```cmd

nslookup DC01

```



Result:



```

Server: DC01.corp.local

Address: 192.168.10.10



Name: DC01.corp.local

Addresses:

192.168.10.10

10.0.2.15

```



The previous "Server: Unknown" message was successfully resolved.



\---



\# Key Concepts Learned



\- Reverse Lookup Zones resolve IP addresses back to hostnames.

\- PTR records provide reverse DNS functionality.

\- Reverse DNS complements Forward DNS.

\- Windows requests only the Host ID when creating PTR records.

\- Reverse DNS improves troubleshooting and administration.

\- DNS Manager organizes reverse zones using the in-addr.arpa namespace.



\---



\# Enterprise Relevance



Reverse DNS is commonly used in enterprise environments for:



\- Troubleshooting

\- Security monitoring

\- SIEM platforms

\- Log analysis

\- Vulnerability scanners

\- Network monitoring

\- Mail server validation

\- Asset identification



Many enterprise tools automatically perform reverse lookups to display hostnames instead of raw IP addresses.



\---



\# Azure Connection



Reverse DNS concepts also apply within Microsoft Azure.



Azure environments use reverse lookups for:



\- Virtual Machine administration

\- Monitoring

\- Logging

\- Hybrid networking

\- Azure Private DNS

\- Azure network troubleshooting



Understanding reverse DNS on-premises provides the foundation for managing DNS within hybrid and cloud environments.



\---



\# Skills Demonstrated



\- Windows DNS Administration

\- Reverse Lookup Zone Configuration

\- PTR Record Management

\- DNS Troubleshooting

\- Name Resolution Testing

\- Windows Server Administration

\- Enterprise DNS Management



\---



\# Lessons Learned



\- Forward DNS and Reverse DNS serve different purposes.

\- PTR records map IP addresses back to hostnames.

\- Reverse Lookup Zones organize PTR records for a subnet.

\- Windows expects only the Host ID when manually creating PTR records.

\- Reverse DNS improves troubleshooting and system identification.

\- Proper DNS configuration is essential for enterprise Windows environments.



\---



\# Reflection



This lab connected subnetting and DNS administration by showing how the network portion of an IP address determines the Reverse Lookup Zone while the Host ID identifies the individual PTR record. Successfully resolving the "Server: Unknown" message demonstrated how forward and reverse DNS work together to provide complete name resolution within an Active Directory environment.

