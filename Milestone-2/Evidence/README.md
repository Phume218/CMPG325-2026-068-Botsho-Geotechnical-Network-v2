# Milestone 2 – Network Implementation and Testing Evidence

## Client
**Organisation:** Botsho Geotechnical Engineers  
**Client ID:** CLI-068  
**Module:** CMPG 325  

## Overview

Milestone 2 focuses on the implementation, configuration, and testing of the proposed network designed for Botsho Geotechnical Engineers.

The network was implemented in Cisco Packet Tracer using a Router-on-a-Stick design. VLANs were created to logically separate the different departments and network resources while allowing controlled communication between VLANs through the router.

## VLAN Configuration

The following VLANs were implemented:

| VLAN | Name | Assigned Ports |
|------|------|----------------|
| 10 | ENGINEERING | Fa0/1 – Fa0/2 |
| 20 | ADMINISTRATION | Fa0/3 – Fa0/4 |
| 30 | PRINTER | Fa0/5 |
| 40 | SERVERS | Fa0/6 |

The VLAN and access-port configuration is verified using the `show vlan brief` command on SW1.

Evidence:

- `SW1_VLAN_Port_Assignments.jpg`

## Inter-VLAN Routing

Router-on-a-Stick was used to provide communication between the VLANs.

Router subinterfaces were configured for each VLAN using IEEE 802.1Q encapsulation. Each subinterface acts as the default gateway for devices within its corresponding VLAN.

This allows devices from different VLANs to communicate while maintaining logical network segmentation.

## DHCP Configuration

DHCP was configured on router R1 to automatically assign IP addresses to client devices in the Engineering and Administration VLANs.

DHCP configuration and successful address allocation were verified using router DHCP commands and client IP configuration information.

Evidence:

- `01-DHCP-Pools-and-Bindings.jpg`
- `R1_DHCP_Pools_and_Bindings.jpg`
- `DHCP_ADMIN_PC1.jpg`
- `Admin-pc2-dhcp-success.jpg`
- `DHCP_ENG_PC2.jpg`

## Static IP Addressing

Devices that require permanent and predictable addresses were configured using static IP addresses.

This includes infrastructure resources such as the network printer and server.

Evidence:

- `printer-static-ip.jpg`

## Connectivity Testing

Connectivity tests were performed to verify communication between devices within the network.

Successful ping tests confirm that:

- End devices can communicate with their default gateways.
- Devices can communicate across different VLANs.
- The server is reachable from other authorised network segments.
- Administration and Engineering devices have working network connectivity.

Evidence:

- `02-Admin-PC-Connectivity-Testing.jpg`
- `ENG-PC1_Inter-VLAN_Connectivity_Test.jpg`
- `Server1_InterVLAN_Connectivity_Test.jpg`

## Switch Configuration

SW1 was configured with VLANs and access ports according to the network design.

The switch provides Layer 2 connectivity for the different departments while the trunk connection to R1 carries traffic for multiple VLANs.

Evidence:

- `SW1_VLAN_Port_Assignments.jpg`

## Testing Summary

The implemented network successfully demonstrates:

- VLAN segmentation
- DHCP address allocation
- Static IP addressing
- Router-on-a-Stick inter-VLAN routing
- IEEE 802.1Q VLAN tagging
- Communication between authorised network devices
- Connectivity to shared network resources

The testing results confirm that the implemented network meets the main functional requirements of the proposed Botsho Geotechnical Engineers network.
