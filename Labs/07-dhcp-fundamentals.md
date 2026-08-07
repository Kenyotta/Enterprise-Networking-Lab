\# Lab 07 - DHCP Fundamentals



\## Objective



Understand the purpose of Dynamic Host Configuration Protocol (DHCP), how it automates network configuration, and why it is a critical service in enterprise environments.



\---



\# Environment



Domain:

corp.local



Network:

192.168.10.0/24



Server:

DC01



Client:

CLIENT01



\---



\# Topics Covered



\- Static vs. Dynamic IP Addressing

\- DHCP Overview

\- DHCP Lease Process

\- DHCP Scope

\- DHCP Reservations

\- DHCP Exclusions

\- Lease Duration

\- Enterprise DHCP Design



\---



\# Concepts Learned



\## Static IP Address



A manually assigned IP address that remains fixed until changed by an administrator.



Typical devices:



\- Domain Controllers

\- File Servers

\- DNS Servers

\- DHCP Servers

\- Network Printers

\- Firewalls

\- Network Appliances



\---



\## Dynamic IP Address



An IP address automatically assigned by a DHCP server.



Typical devices:



\- Workstations

\- Laptops

\- Tablets

\- Mobile Devices



\---



\## What DHCP Provides



DHCP automatically assigns:



\- IPv4 Address

\- Subnet Mask

\- Default Gateway

\- DNS Server

\- DNS Domain Name

\- Lease Duration



This eliminates the need to manually configure every client.



\---



\# The DORA Process



DHCP uses a four-step communication process:



\### Discover



The client broadcasts a request asking if a DHCP server is available.



\---



\### Offer



The DHCP server responds with an available IP address.



\---



\### Request



The client requests to use the offered address.



\---



\### Acknowledge (ACK)



The DHCP server approves the request and leases the IP address to the client.



\---



\# DHCP Scope



A DHCP scope defines:



\- Network

\- Address Pool

\- Lease Duration

\- DHCP Options



Example:



Network:



192.168.10.0/24



Address Pool:



192.168.10.21 – 192.168.10.254



\---



\# Scope Design



Infrastructure devices should use static IP addresses.



Example reserved range:



| Address Range | Purpose |

|---------------|---------|

| .1 | Future Gateway |

| .2 – .9 | Future Infrastructure |

| .10 | DC01 |

| .11 | FILE01 |

| .12 | WEB01 |

| .13 | SQL01 |

| .14 | PRINT01 |

| .15 | MGMT01 |

| .16 – .20 | Reserved for Growth |

| .21 – .254 | DHCP Client Pool |



This layout keeps infrastructure organized and allows room for future expansion.



\---



\# DHCP Exclusions



Exclusions prevent DHCP from assigning specific IP addresses within the scope.



Example:



Scope:



192.168.10.21 – 192.168.10.254



Exclusion:



192.168.10.100



The address remains reserved for future use.



\---



\# DHCP Reservations



Reservations permanently assign the same IP address to a specific device using its MAC address.



Benefits:



\- Predictable addressing

\- Centralized management

\- Automatic DNS updates

\- Easier administration



Typical reserved devices:



\- Printers

\- NAS Devices

\- VoIP Phones

\- Cameras



\---



\# Lease Duration



Default lease:



8 Days



Lease durations vary depending on the environment.



Examples:



Enterprise LAN:

8 Days



Guest Wi-Fi:

4–12 Hours



Conferences:

1–2 Hours



Public Hotspots:

30 Minutes – 2 Hours



Shorter leases allow IP addresses to be recycled more quickly.



\---



\# Enterprise Design Principles



Infrastructure should receive static addresses.



Clients should receive dynamic addresses.



Reserve address ranges for future growth.



Organize IP addresses logically to simplify troubleshooting and documentation.



\---



\# Skills Practiced



\- Differentiating static and dynamic addressing

\- Understanding DHCP architecture

\- Learning the DORA process

\- Designing an enterprise DHCP scope

\- Planning address pools

\- Understanding lease durations

\- Planning infrastructure growth



\---



\# Lessons Learned



DHCP is much more than an IP address server.



It is an infrastructure service that automatically provides clients with the network configuration required to communicate on the enterprise network.



Proper scope planning, address reservation, and logical IP organization improve scalability, simplify troubleshooting, and reduce administrative overhead.

