&#x20;                          Internet

&#x20;                              │

&#x20;                        VirtualBox NAT

&#x20;                              │

&#x20;       ┌──────────────────────┴──────────────────────┐



&#x20;                Internal Network (LABNET)

&#x20;                   192.168.10.0/24



&#x20;       ┌──────────────┬──────────────┬──────────────┐

&#x20;       │              │              │

&#x20;       │              │              │

&#x20;    DC01           FILE01        CLIENT01

&#x20;192.168.10.10   192.168.10.11   DHCP (.21)



Roles:

──────────────────────────────────────────────

DC01

• Active Directory

• DNS

• DHCP



FILE01

• Enterprise File Server



CLIENT01

• Domain Joined

• DHCP Client

