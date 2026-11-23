# Hospital Network Segmentation & Multi-Floor VLAN Implementation

## Project Overview

This project demonstrates VLAN-based network segmentation and inter-switch connectivity using **Cisco Packet Tracer**.

The project consists of two network scenarios designed to demonstrate how VLANs can be used to logically separate departments, reduce broadcast domains, and extend departmental networks across multiple physical locations.

## Part 1: Hospital Department Segmentation

A hospital network is divided into four independent departments using VLANs, with all end devices connected to a central managed switch.

### Department Distribution

| Department | VLAN ID | Number of Devices |
|---|---:|---:|
| Administration | 10 | 2 |
| Doctors | 20 | 3 |
| Nursery | 30 | 6 |
| Pharmacy | 40 | 4 |
| **Total** | **4 VLANs** | **15 Devices** |

### Implementation

- Created four separate VLANs on the central switch.
- Assigned switch ports to their corresponding departmental VLANs.
- Connected all departmental devices through dedicated access ports.
- Implemented logical network segmentation without requiring separate physical switches for each department.

## Part 2: Multi-Floor VLAN Implementation Using Trunk Links

This scenario demonstrates how VLANs can be extended across multiple floors of a building using two Cisco 2960 switches connected through an IEEE 802.1Q trunk link.

Instead of creating separate networks for each floor, both switches share the same VLAN configuration, allowing devices belonging to the same department to remain in the same logical broadcast domain regardless of their physical location.

### Network Distribution

| Department | VLAN ID | Devices |
|---|---:|---|
| Accounting | 10 | 2 PCs |
| Sales | 20 | 2 Laptops |

### Implementation

- Configured VLAN 10 for the Accounting Department.
- Configured VLAN 20 for the Sales Department.
- Assigned end-device switch ports as access ports.
- Configured an inter-switch connection as a trunk link.
- Enabled VLAN traffic to traverse between the first and second floors.
- Used trunking to carry multiple VLANs over a single physical connection.

### Key Concept: VLAN Trunking

The trunk link allows traffic from multiple VLANs to travel between switches using IEEE 802.1Q tagging.

This eliminates the need for a separate physical connection for every VLAN between the two floors.

## Technologies & Concepts

- Cisco Packet Tracer
- Cisco Catalyst 2960 Switches
- Virtual Local Area Networks (VLANs)
- Access Port Configuration
- IEEE 802.1Q Trunking
- Inter-Switch Connectivity
- Broadcast Domain Segmentation
- Layer 2 Switching

## Verification

The following Cisco IOS commands can be used to verify the configurations:

```bash
show vlan brief
show interfaces trunk
show interfaces switchport
show interfaces status
```

Connectivity testing using ICMP (Ping) can verify communication between devices belonging to the same VLAN across different switches.

## Project Scope & Limitations

This project focuses on Layer 2 switching, VLAN segmentation, and trunk connectivity.

Inter-VLAN routing, firewall policies, and advanced network security configurations are not included in the current implementation.

## Future Improvements

- Implement Inter-VLAN Routing using Router-on-a-Stick.
- Configure ACLs to control communication between departments.
- Implement Port Security to restrict unauthorized devices.
- Configure SSH for secure remote switch management.
- Introduce DHCP for automated IP address allocation.

## Tools

- Cisco Packet Tracer

---

**Project Category:** Computer Networking  
**Project Focus:** VLAN Segmentation & IEEE 802.1Q Trunking  
**Implementation:** Layer 2 Switching  
**Status:** Completed
