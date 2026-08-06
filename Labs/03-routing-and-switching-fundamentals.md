\# Lab 03 – Routing \& Switching Fundamentals



\## Objective



Understand the roles of switches and routers in an enterprise network and explain how devices communicate within and between networks.



\---



\# Environment



| System | Role |

|----------|------|

| DC01 | Domain Controller / DNS |

| FILE01 | File Server |

| CLIENT01 | Domain Workstation |



Network:



192.168.10.0/24



\---



\# Network Topology



```

&#x20;          Switch

&#x20;       ┌────┼────┐

&#x20;       │    │    │

&#x20;    DC01 FILE01 CLIENT01

```



All systems currently reside on the same subnet and communicate through a Layer 2 switch.



\---



\# Routing Overview



Routing is the process of forwarding network traffic between different networks.



Devices on the same subnet communicate directly.



Devices on different subnets require a router and a default gateway.



\---



\# Switching Overview



A switch connects devices on the same Local Area Network (LAN).



Switches forward traffic using MAC addresses and maintain a MAC Address Table that maps network devices to switch ports.



Unlike hubs, switches send traffic only to the intended destination, improving network performance.



\---



\# Key Concepts Learned



\- Difference between Layer 2 switching and Layer 3 routing.

\- Purpose of a default gateway.

\- How subnet masks determine whether traffic is local or remote.

\- Role of MAC addresses in local communication.

\- Difference between switches and hubs.

\- How switches learn MAC addresses through flooding and build MAC address tables.



\---



\# Enterprise Perspective



A modern enterprise network separates systems into multiple subnets connected through routers.



Example:



\- Server Network

\- Client Network

\- Management Network

\- Printer / IoT Network



This design improves scalability, performance, and security.



\---



\# Azure Connection



Azure Virtual Networks use the same networking principles.



Virtual networking replaces physical switching while Azure provides routing between subnets within a Virtual Network.



\---



\# Skills Demonstrated



\- Routing Fundamentals

\- Switching Fundamentals

\- MAC Addressing

\- Default Gateway Concepts

\- Enterprise Networking Concepts

\- Azure Networking Foundations



\---



\# Lessons Learned



\- Switches connect devices.

\- Routers connect networks.

\- Devices on the same subnet communicate directly.

\- Devices on different subnets communicate through a router.

\- Subnet masks determine when routing is required.

\- MAC addresses identify network interfaces on the local network.

