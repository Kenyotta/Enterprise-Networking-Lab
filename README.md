\# Enterprise Networking Lab



A hands-on enterprise networking project built to develop practical skills in network configuration, troubleshooting, security, traffic analysis, and cloud networking.



This lab uses Windows Server, Windows client systems, Oracle VirtualBox, PowerShell, and networking tools to demonstrate how devices communicate in an enterprise environment. The project will eventually extend these same principles into Microsoft Azure.



\---



\## Project Overview



The Enterprise Networking Lab simulates a small business network containing domain services, file services, client workstations, virtual network adapters, IP addressing, DNS, DHCP, firewall rules, and network troubleshooting tools.



The purpose of this project is to move beyond memorizing networking terms and build experience designing, configuring, testing, securing, and documenting a functioning network.



\---



\## Project Goals



\* Build a functional virtual enterprise network.

\* Understand how network devices communicate.

\* Configure static and dynamic IP addressing.

\* Configure and verify DNS and DHCP.

\* Apply the OSI and TCP/IP models during troubleshooting.

\* Analyze network traffic using Wireshark.

\* Practice Windows and PowerShell networking commands.

\* Configure Windows Firewall rules.

\* Document network failures and their resolutions.

\* Connect traditional networking concepts to Microsoft Azure.



\---



\## Current Environment



| System        | Role                                     | Operating System    |

| ------------- | ---------------------------------------- | ------------------- |

| DC01          | Domain Controller, Active Directory, DNS | Windows Server 2022 |

| FILE01        | File Server                              | Windows Server      |

| CLIENT01      | Domain-Joined Workstation                | Windows 11          |

| Host Computer | Virtualization Host                      | Windows 11          |

| VirtualBox    | Type 2 Hypervisor and Virtual Networking | Oracle VirtualBox   |



\---



\## Current Network Architecture



```text

Physical Host Computer

&#x20;         |

&#x20;         v

&#x20;  Oracle VirtualBox

&#x20;         |

&#x20;         v

&#x20;  Virtual Network

&#x20;         |

&#x20;  +------+------+ 

&#x20;  |             |

&#x20; DC01         FILE01

&#x20;  |

&#x20;CLIENT01

```



The virtual machines communicate through virtual network interface cards and a VirtualBox virtual network.



As the project grows, the environment may include additional clients, servers, network segments, security controls, and Azure resources.



\---



\## Technologies and Tools



\* Microsoft Windows Server

\* Windows 11

\* Active Directory Domain Services

\* Domain Name System

\* Dynamic Host Configuration Protocol

\* Oracle VirtualBox

\* PowerShell

\* Command Prompt

\* Wireshark

\* Windows Defender Firewall

\* Server Message Block

\* Remote Desktop Protocol

\* Microsoft Azure

\* Git and GitHub



\---



\## Networking Concepts Covered



\### Networking Fundamentals



\* Local Area Networks

\* Wide Area Networks

\* Network topologies

\* Physical and logical networks

\* Clients and servers

\* Switches and routers

\* Network interface cards

\* Bandwidth, throughput, and latency



\### Network Models



\* OSI model

\* TCP/IP model

\* Encapsulation

\* Decapsulation

\* Frames

\* Packets

\* Segments

\* Ports and protocols



\### Addressing and Communication



\* IPv4 addressing

\* Subnet masks

\* Default gateways

\* MAC addresses

\* Address Resolution Protocol

\* Static IP addresses

\* Dynamic IP addresses

\* Classless Inter-Domain Routing



\### Core Network Services



\* DNS

\* DHCP

\* Active Directory communication

\* File sharing

\* Authentication

\* Name resolution



\### Troubleshooting



\* Physical and virtual connectivity

\* IP configuration

\* DNS resolution

\* Routing

\* Firewall rules

\* Service availability

\* Port connectivity

\* Network traffic analysis



\### Security



\* Windows Defender Firewall

\* Network segmentation

\* Port restrictions

\* Protocol security

\* Least privilege

\* Traffic monitoring

\* Defense in depth



\### Azure Networking



\* Azure Virtual Networks

\* Azure subnets

\* Azure network interfaces

\* Network Security Groups

\* Azure route tables

\* Azure Firewall

\* Azure Bastion

\* VPN Gateway

\* Private endpoints

\* Azure DNS



\---



\## Planned Lab Phases



\### Phase 1 — Network Discovery



\* Document the existing environment.

\* Record virtual network settings.

\* Identify each system's network adapter.

\* Collect current IP configuration.

\* Create the initial network diagram.

\* Verify communication between systems.



\### Phase 2 — IP Addressing



\* Configure static IP addresses.

\* Document the addressing plan.

\* Verify subnet masks and gateways.

\* Test local and remote connectivity.

\* Identify and resolve addressing errors.



\### Phase 3 — DNS



\* Review the DNS role on DC01.

\* Verify forward and reverse name resolution.

\* Create and inspect DNS records.

\* Use `nslookup` and PowerShell for testing.

\* Troubleshoot DNS failures.



\### Phase 4 — DHCP



\* Install or verify the DHCP Server role.

\* Create a DHCP scope.

\* Configure exclusions and reservations.

\* Authorize the DHCP server.

\* Renew client leases.

\* Verify dynamic addressing.



\### Phase 5 — Ports and Protocols



\* Identify common enterprise ports.

\* Test TCP and UDP communication.

\* Review SMB, RDP, DNS, and DHCP traffic.

\* Use PowerShell to test specific ports.

\* Document blocked and permitted connections.



\### Phase 6 — Network Troubleshooting



\* Diagnose simulated connectivity failures.

\* Apply the OSI model.

\* Test physical, data-link, network, transport, and application layers.

\* Record symptoms, evidence, root causes, and resolutions.



\### Phase 7 — Traffic Analysis



\* Install and configure Wireshark.

\* Capture network traffic.

\* Filter DNS, ICMP, TCP, SMB, and DHCP packets.

\* Analyze connection establishment.

\* Identify normal and suspicious traffic patterns.



\### Phase 8 — Network Security



\* Review Windows Defender Firewall profiles.

\* Create inbound and outbound firewall rules.

\* Restrict unnecessary services.

\* Test permitted and blocked traffic.

\* Document security improvements.



\### Phase 9 — Azure Networking



\* Create an Azure Virtual Network.

\* Create multiple subnets.

\* Deploy Azure virtual machines.

\* Configure Network Security Groups.

\* Review Azure routing.

\* Compare the Azure environment to the VirtualBox lab.



\---



\## Planned Repository Structure



```text

Enterprise-Networking-Lab/

|

|-- README.md

|-- LICENSE

|

|-- diagrams/

|   |-- initial-network-diagram.png

|   |-- final-network-diagram.png

|

|-- labs/

|   |-- 01-network-discovery.md

|   |-- 02-static-ip-addressing.md

|   |-- 03-dns-configuration.md

|   |-- 04-dhcp-configuration.md

|   |-- 05-ports-and-protocols.md

|   |-- 06-network-troubleshooting.md

|   |-- 07-wireshark-analysis.md

|   |-- 08-windows-firewall.md

|   |-- 09-azure-networking.md

|

|-- screenshots/

|   |-- network-discovery/

|   |-- ip-addressing/

|   |-- dns/

|   |-- dhcp/

|   |-- troubleshooting/

|   |-- wireshark/

|   |-- firewall/

|   |-- azure/

|

|-- packet-captures/

|   |-- README.md

|

|-- scripts/

&#x20;   |-- network-diagnostics.ps1

```



The structure may be adjusted as the project develops.



\---



\## Core Networking Commands



\### Windows Command Prompt



```powershell

ipconfig

ipconfig /all

ipconfig /release

ipconfig /renew

ipconfig /flushdns

ping

tracert

nslookup

arp -a

netstat -ano

route print

hostname

getmac

```



\### PowerShell



```powershell

Get-NetIPAddress

Get-NetIPConfiguration

Get-NetAdapter

Get-NetRoute

Get-DnsClientServerAddress

Resolve-DnsName

Test-Connection

Test-NetConnection

Get-NetTCPConnection

Get-NetFirewallProfile

Get-NetFirewallRule

```



\---



\## Troubleshooting Methodology



Network problems will be investigated systematically rather than through random changes.



\### Step 1 — Identify the Problem



\* What is the user experiencing?

\* Which systems are affected?

\* When did the problem begin?

\* What changed recently?



\### Step 2 — Establish a Theory



Potential causes may include:



\* Disconnected or disabled network adapter

\* Incorrect IP address

\* Incorrect subnet mask

\* Incorrect default gateway

\* DNS failure

\* DHCP failure

\* Firewall restriction

\* Service failure

\* Routing problem

\* VirtualBox network misconfiguration



\### Step 3 — Test the Theory



Examples:



```powershell

ipconfig /all

ping <gateway>

ping <server-ip>

nslookup <hostname>

Test-NetConnection <hostname> -Port <port>

```



\### Step 4 — Implement the Fix



Apply the safest and least disruptive correction.



\### Step 5 — Verify Functionality



Confirm that the original problem is resolved and that other services still work.



\### Step 6 — Document the Results



Each issue should include:



\* Symptoms

\* Scope

\* Evidence

\* Root cause

\* Resolution

\* Verification

\* Lessons learned



\---



\## OSI Troubleshooting Framework



| Layer | Area to Investigate | Example                                       |

| ----: | ------------------- | --------------------------------------------- |

|     7 | Application         | DNS, SMB, RDP, browser, service configuration |

|     6 | Presentation        | Encryption, certificates, formatting          |

|     5 | Session             | Authentication or disconnected sessions       |

|     4 | Transport           | TCP, UDP, ports, firewall rules               |

|     3 | Network             | IP addresses, subnets, gateways, routing      |

|     2 | Data Link           | MAC addresses, virtual switches, VLANs        |

|     1 | Physical            | Cables, power, signal, virtual adapter status |



\---



\## Example Verification Workflow



When CLIENT01 cannot access FILE01:



```powershell

hostname

ipconfig /all

ping <FILE01-IP>

nslookup FILE01

Test-NetConnection FILE01 -Port 445

```



The tests help determine whether the failure involves:



\* Local connectivity

\* IP configuration

\* DNS

\* Routing

\* SMB

\* Windows Firewall

\* File-sharing permissions



\---



\## Traditional Networking and Azure



| Traditional Environment      | Azure                        |

| ---------------------------- | ---------------------------- |

| Physical network             | Azure Virtual Network        |

| Network segment              | Azure subnet                 |

| Physical NIC                 | Azure network interface      |

| Router                       | Azure route table or gateway |

| Firewall rule                | Network Security Group rule  |

| Perimeter firewall           | Azure Firewall               |

| Remote administrative access | Azure Bastion                |

| Site-to-site VPN device      | Azure VPN Gateway            |

| Private service connection   | Private endpoint             |

| Physical or virtual server   | Azure Virtual Machine        |



\---



\## Skills Demonstrated



This project is designed to demonstrate:



\* Network configuration

\* Windows Server administration

\* TCP/IP knowledge

\* DNS and DHCP administration

\* Active Directory networking

\* PowerShell

\* Network troubleshooting

\* Wireshark traffic analysis

\* Firewall administration

\* Technical documentation

\* Systems thinking

\* Cloud networking fundamentals

\* Microsoft Azure networking



\---



\## Project Status



\*\*Status:\*\* In Progress



\### Completed



\* \[x] Created the networking knowledge base.

\* \[x] Documented networking fundamentals.

\* \[x] Documented the OSI model.

\* \[x] Built the initial Windows Server virtual environment.

\* \[x] Deployed DC01, FILE01, and CLIENT01.



\### Upcoming



\* \[ ] Document the existing network configuration.

\* \[ ] Create an IP addressing table.

\* \[ ] Produce the initial network diagram.

\* \[ ] Verify connectivity between all systems.

\* \[ ] Begin the static IP addressing lab.

\* \[ ] Configure and test DNS.

\* \[ ] Configure and test DHCP.

\* \[ ] Capture and analyze network traffic.

\* \[ ] Configure firewall rules.

\* \[ ] Recreate networking concepts in Azure.



\---



\## Key Lessons



This section will be updated throughout the project.



Current lessons include:



\* Virtual machines still rely on traditional networking principles.

\* A switch connects devices within a local network.

\* A router connects different networks.

\* IP addresses identify devices and network locations.

\* MAC addresses support local network delivery.

\* DNS resolves names into IP addresses.

\* Ports identify specific services on a device.

\* The OSI model provides a structured troubleshooting method.

\* Successful connectivity at one layer does not guarantee that higher-layer services are working.



\---



\## Future Improvements



Potential future additions include:



\* Additional client and server virtual machines

\* Multiple virtual network segments

\* VLAN simulation

\* Linux networking

\* Centralized logging

\* Intrusion detection

\* Automated diagnostic scripts

\* Azure hybrid networking

\* Site-to-site VPN simulation

\* Network monitoring dashboards

\* Infrastructure as Code deployment



\---



\## Author



\*\*Kenyotta Eave\*\*



Aspiring Cloud Security Architect building practical experience in enterprise infrastructure, networking, cybersecurity, and Microsoft Azure.



\---



\## License



This project is licensed under the MIT License. See the `LICENSE` file for details.



