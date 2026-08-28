# Logical Topology

## Botsho Geotechnical Engineers — CLI-068

The logical topology describes how the proposed network is divided into VLANs and how communication will occur between the different network segments.

The network will use four VLANs and router-on-a-stick inter-VLAN routing.

## VLAN Design

| VLAN ID | VLAN Name | Purpose | Address Assignment |
|---:|---|---|---|
| 10 | ENGINEERING | Engineering departmental clients | DHCP |
| 20 | ADMINISTRATION | Administration departmental clients | DHCP |
| 30 | SHARED-PRINTER | Shared printer zone required by CR8 | Static |
| 40 | SERVERS | Critical file/application services | Static |

## Inter-VLAN Routing

Router R1 will provide inter-VLAN routing using IEEE 802.1Q subinterfaces.

| Router Subinterface | VLAN | Purpose | Gateway |
|---|---:|---|---|
| G0/0.10 | 10 | Engineering gateway | 172.30.42.1/26 |
| G0/0.20 | 20 | Administration gateway | 172.30.42.65/26 |
| G0/0.30 | 30 | Shared Printer gateway | 172.30.42.129/28 |
| G0/0.40 | 40 | Server gateway | 172.30.42.145/28 |

The exact physical router interface designation will be confirmed according to the router model selected in Cisco Packet Tracer.

## CR8 Shared Printer Communication

The shared printer will be placed in VLAN 30 and will be accessible from both proposed departmental VLANs through inter-VLAN routing.

Engineering users in VLAN 10 will communicate with the printer through R1, while Administration users in VLAN 20 will also reach the same printer through R1.

This logical design directly addresses CR8 while maintaining separation between departmental clients and the shared printer resource.
