\# Lab 02 – Enterprise IPv4 Addressing



\## Objective



Analyze the enterprise IPv4 addressing scheme, document the current network configuration, and develop an organized IP Address Management (IPAM) plan for future expansion.



\---



\# Environment



| System | Role |

|----------|------|

| DC01 | Domain Controller / DNS |

| FILE01 | File Server |

| CLIENT01 | Domain Workstation |



Network:



```

192.168.10.0/24

```



\---



\# Existing Network Information



| Item | Value |

|------|-------|

| Network Name | LABNET |

| Network Address | 192.168.10.0 |

| Subnet Mask | 255.255.255.0 |

| CIDR | /24 |

| Total IPv4 Addresses | 256 |

| Usable Host Addresses | 254 |

| Broadcast Address | 192.168.10.255 |



\---



\# Existing Device Addressing



| Device | Address | Assignment | Purpose |

|----------|-------------|------------|---------|

| DC01 | 192.168.10.10 | Static | Active Directory / DNS |

| FILE01 | 192.168.10.11 | Static | File Server |

| CLIENT01 | 192.168.10.20 | Static | Domain Workstation |



\---



\# Address Analysis



\## Network Address



```

192.168.10.0

```



This address identifies the subnet itself and cannot be assigned to a device.



\---



\## Broadcast Address



```

192.168.10.255

```



This address represents every device on the subnet and cannot be assigned to a host.



\---



\## Host Address Range



```

192.168.10.1

↓



192.168.10.254

```



There are \*\*254 usable host addresses\*\* available within this subnet.



\---



\# Static vs Dynamic Addressing



Current lab configuration:



| Device | Address Type |

|----------|--------------|

| DC01 | Static |

| FILE01 | Static |

| CLIENT01 | Static (temporary for lab exercises) |



Infrastructure servers use static IP addresses because they must always be reachable at the same address.



Future client workstations will receive dynamic addresses from DHCP.



\---



\# Proposed Enterprise IP Addressing Plan



| Device | IPv4 Address | Reason |

|----------|-------------|--------|

| DC01 | 192.168.10.10 | Domain Controller |

| FILE01 | 192.168.10.11 | File Server |

| WEB01 | 192.168.10.12 | Web Server |

| SQL01 | 192.168.10.13 | Database Server |

| PRINT01 | 192.168.10.14 | Print Server |

| MGMT01 | 192.168.10.15 | Management Server |

| CLIENT01 | 192.168.10.20 | Workstation |

| CLIENT02 | 192.168.10.21 | Workstation |

| CLIENT03 | 192.168.10.22 | Workstation |



\---



\# IP Address Management Strategy



The addressing plan groups similar systems together.



| Address Range | Purpose |

|---------------|----------|

| .1 – .9 | Network Infrastructure |

| .10 – .19 | Servers |

| .20 – .99 | Workstations |

| .100 – .199 | DHCP Scope |

| .200 – .239 | Printers / Specialty Devices |

| .240 – .254 | Reserved |



This organization makes the network easier to manage, troubleshoot, and expand.



\---



\# Key Observations



\- All systems belong to the same 192.168.10.0/24 subnet.

\- All infrastructure servers use static addressing.

\- Workstations are grouped into their own address range.

\- The subnet supports 254 usable devices.

\- The current addressing scheme is organized and scalable.



\---



\# Lessons Learned



\- IPv4 addresses identify both a device and its location on a network.

\- Static IP addresses are best suited for infrastructure servers.

\- Dynamic IP addresses simplify workstation management.

\- A /24 network contains 256 total addresses and 254 usable host addresses.

\- Organized IP address planning improves scalability and troubleshooting.

\- IP Address Management (IPAM) is an important part of enterprise network design.



\---



\# Skills Demonstrated



\- IPv4 Address Planning

\- Static IP Addressing

\- IP Address Management (IPAM)

\- Network Documentation

\- Enterprise Network Design

\- Network Analysis

\- Windows Networking Fundamentals

