# IP Addressing Plan

## Botsho Geotechnical Engineers — CLI-068

The assigned IPv4 addressing block for the Botsho Geotechnical Engineers network is:

**172.30.42.0/23**

The /23 subnet mask is:

**255.255.254.0**

The assigned block extends from **172.30.42.0 to 172.30.43.255** and contains 512 total addresses.

The network requires multiple VLANs; therefore, the assigned /23 block is subdivided using Variable Length Subnet Masking (VLSM).

## VLAN Subnet Allocation

| VLAN | Network Address | Prefix | Subnet Mask | Usable Host Range | Broadcast Address |
|---:|---|---|---|---|---|
| 10 | 172.30.42.0 | /26 | 255.255.255.192 | 172.30.42.1–172.30.42.62 | 172.30.42.63 |
| 20 | 172.30.42.64 | /26 | 255.255.255.192 | 172.30.42.65–172.30.42.126 | 172.30.42.127 |
| 30 | 172.30.42.128 | /28 | 255.255.255.240 | 172.30.42.129–172.30.42.142 | 172.30.42.143 |
| 40 | 172.30.42.144 | /28 | 255.255.255.240 | 172.30.42.145–172.30.42.158 | 172.30.42.159 |

The /26 networks provide 62 usable host addresses each for the departmental VLANs, while the /28 networks provide 14 usable host addresses each for the smaller shared-resource networks.

The remaining portion of the assigned /23 block is reserved for future expansion.

## Device IP Addressing Plan

| Device / Function | VLAN | IP Address / Allocation | Subnet Mask | Default Gateway | Method |
|---|---:|---|---|---|---|
| Engineering Gateway | 10 | 172.30.42.1 | 255.255.255.192 | — | Static |
| ENG-PC1 | 10 | Engineering DHCP pool | 255.255.255.192 | 172.30.42.1 | DHCP |
| ENG-PC2 | 10 | Engineering DHCP pool | 255.255.255.192 | 172.30.42.1 | DHCP |
| Administration Gateway | 20 | 172.30.42.65 | 255.255.255.192 | — | Static |
| ADMIN-PC1 | 20 | Administration DHCP pool | 255.255.255.192 | 172.30.42.65 | DHCP |
| ADMIN-PC2 | 20 | Administration DHCP pool | 255.255.255.192 | 172.30.42.65 | DHCP |
| Printer Gateway | 30 | 172.30.42.129 | 255.255.255.240 | — | Static |
| BOTSHO-PRINTER | 30 | 172.30.42.130 | 255.255.255.240 | 172.30.42.129 | Static |
| Server Gateway | 40 | 172.30.42.145 | 255.255.255.240 | — | Static |
| BOTSHO-SERVER | 40 | 172.30.42.146 | 255.255.255.240 | 172.30.42.145 | Static |

## DHCP Scope Design

The assigned networking challenge requires scoped multi-VLAN DHCP. Separate DHCP scopes are therefore planned for VLAN 10 and VLAN 20.

| DHCP Pool | VLAN | Network | Default Gateway | Dynamic Client Range |
|---|---:|---|---|---|
| ENGINEERING | 10 | 172.30.42.0/26 | 172.30.42.1 | 172.30.42.10–172.30.42.62 |
| ADMINISTRATION | 20 | 172.30.42.64/26 | 172.30.42.65 | 172.30.42.70–172.30.42.126 |

For the Engineering DHCP scope, addresses **172.30.42.1–172.30.42.9** will be excluded from dynamic allocation.

For the Administration DHCP scope, addresses **172.30.42.65–172.30.42.69** will be excluded from dynamic allocation.

The shared printer and server will not use DHCP because these critical shared resources require predictable network addresses.
