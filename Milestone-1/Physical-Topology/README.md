# Physical Topology

## Botsho Geotechnical Engineers — CLI-068

The proposed physical topology represents the devices and physical connections that will be implemented in Cisco Packet Tracer.

The network will contain one router, one Cisco 2960 Layer 2 switch, four departmental client computers, one shared network printer and one server.

## Proposed Device Inventory

| Device | Quantity | Purpose |
|---|---:|---|
| R1 Router | 1 | Inter-VLAN routing and DHCP services |
| SW1 Cisco 2960 Switch | 1 | VLAN switching and end-device connectivity |
| Engineering PCs | 2 | DHCP clients in VLAN 10 |
| Administration PCs | 2 | DHCP clients in VLAN 20 |
| BOTSHO-PRINTER | 1 | Shared printer required by CR8 |
| BOTSHO-SERVER | 1 | Critical file/application services |

## Proposed Physical Connections

| SW1 Port | Connected Device | Connection |
|---|---|---|
| G0/1 | R1 | 802.1Q trunk |
| Fa0/1 | ENG-PC1 | Access port |
| Fa0/2 | ENG-PC2 | Access port |
| Fa0/3 | ADMIN-PC1 | Access port |
| Fa0/4 | ADMIN-PC2 | Access port |
| Fa0/5 | BOTSHO-PRINTER | Access port |
| Fa0/6 | BOTSHO-SERVER | Access port |

The router-to-switch connection will operate as an 802.1Q trunk during implementation. Each end device will have its own Ethernet connection to SW1.

The exact router interface name will be confirmed according to the router model selected in Cisco Packet Tracer.
