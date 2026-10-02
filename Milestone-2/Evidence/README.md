# Milestone 2 – Evidence

This folder contains supporting evidence for the implementation, configuration, verification and testing of the Botsho Geotechnical Engineers network in Cisco Packet Tracer.

## Evidence Categories

### 1. DHCP Configuration and Verification
Evidence of the assigned networking challenge: scoped multi-VLAN DHCP address assignment.

The evidence demonstrates:
- Separate DHCP scopes for the Engineering and Administration networks.
- Correct network masks and default gateways.
- Excluded addresses reserved for gateways and infrastructure.
- Successful dynamic address allocation to client devices.
- DHCP bindings confirming addresses leased by the router.

### 2. Network Connectivity Testing
End-to-end connectivity was tested using ICMP ping tests.

Testing verifies:
- Communication within the Engineering network.
- Communication within the Administration network.
- Inter-VLAN communication through router-on-a-stick.
- Connectivity between client devices and required network resources.
- Successful communication with 0% packet loss during the demonstrated tests.

### 3. CR8 – Shared Printer Zone
The client change request required a shared printer zone capable of serving the two departments that previously could not print.

The shared printer was configured using IP address `172.30.42.130`.

Connectivity testing demonstrates that devices from the required departmental networks can successfully reach the shared printer across the routed network.

### 4. Configuration Verification
Configuration evidence demonstrates the implementation of:
- VLAN-based network segmentation.
- Router-on-a-stick inter-VLAN routing.
- DHCP services.
- Correct client addressing and default gateways.
- Network connectivity between the required devices and services.

### 5. Troubleshooting and Validation
During implementation, network configuration and connectivity were checked using client IP configuration, gateway testing, DHCP verification and end-to-end ping tests.

The final tests confirm that the implemented network provides successful communication between the required network segments and resources.
