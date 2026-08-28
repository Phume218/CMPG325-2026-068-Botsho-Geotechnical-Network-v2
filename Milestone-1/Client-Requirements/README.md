# Client Requirements

## Botsho Geotechnical Engineers — CLI-068

This section documents the client requirements identified for the proposed Botsho Geotechnical Engineers network.

The network design must use the assigned addressing block **172.30.42.0/23** and address the assigned networking challenge of **DHCP — Scoped Multi-VLAN Address Assignment**.

The design must also accommodate the requirement that critical file, print and application services remain available during business hours.

The assigned change request, **CR8**, requires a shared printer zone that can serve two departments that currently cannot print.

For the Cisco Packet Tracer simulation, Engineering and Administration are proposed as the two departmental user groups. These departmental names are design assumptions used for the simulation and are not presented as confirmed departments specified by the client brief.

## Proposed Network Response

| Client Requirement | Proposed Network Response |
|---|---|
| Assigned addressing block | Use 172.30.42.0/23 as the basis of the IP addressing plan |
| Scoped multi-VLAN DHCP | Configure separate DHCP scopes for Engineering and Administration |
| Network segmentation | Implement four VLANs for users and shared resources |
| Inter-VLAN communication | Use router-on-a-stick routing |
| CR8 shared printing | Place the shared printer in a dedicated VLAN accessible by both departments |
| Critical services | Place critical server resources in a dedicated Server VLAN |
| Stable infrastructure addressing | Use static IP addresses for the shared printer and server |
| Network simulation | Implement and test the design using Cisco Packet Tracer |
