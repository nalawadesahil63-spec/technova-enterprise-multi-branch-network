# TECHNOVA Enterprise Multi-Branch Office Network

A CCNA-level enterprise multi-branch office network built in Cisco Packet Tracer.

## Project Overview

This project simulates an enterprise network with a Head Office and two branch offices: **Pune** and **Bengaluru**. The network uses VLAN segmentation, inter-VLAN routing, centralized DHCP services, static routing, and Layer 2 security features.

The project was designed to develop practical understanding of enterprise network configuration, connectivity testing, and systematic troubleshooting.

## Network Topology

![Network Topology](images/01_network_topology.png)

## Technologies and Features

* Cisco Packet Tracer
* VLAN segmentation
* Access and trunk port configuration
* Inter-VLAN routing using multilayer switches
* Switched Virtual Interfaces (SVIs)
* Centralized DHCP server
* DHCP Relay using `ip helper-address`
* Static routing
* Default routing
* Port Security
* DHCP Snooping
* STP PortFast
* HQ-to-branch connectivity
* End-to-end connectivity testing

## VLAN and IP Addressing Plan

| VLAN    | Department  | Network         | Default Gateway |
| ------- | ----------- | --------------- | --------------- |
| VLAN 10 | HR          | 192.168.10.0/24 | 192.168.10.1    |
| VLAN 20 | IT          | 192.168.20.0/24 | 192.168.20.1    |
| VLAN 30 | Finance     | 192.168.30.0/24 | 192.168.30.1    |
| VLAN 40 | Sales       | 192.168.40.0/24 | 192.168.40.1    |
| VLAN 50 | Admin       | 192.168.50.0/24 | 192.168.50.1    |
| VLAN 60 | Server Farm | 192.168.60.0/24 | 192.168.60.1    |

![IP Addressing and VLAN Plan](images/02_ip_addressing_vlan_plan.png)

## Branch Networks

| Location         | Network         |
| ---------------- | --------------- |
| Pune Branch      | 192.168.70.0/24 |
| Bengaluru Branch | 192.168.80.0/24 |

## Routing Design

The HQ core multilayer switch performs inter-VLAN routing and provides connectivity to branch networks using static routes.

A default route is configured for traffic toward the upstream network.

## Security Features

### Port Security

Port Security is configured on access ports to limit unauthorized device connections.

Example verification:

```text
MaxSecureAddr: 1
CurrentAddr: 1
SecurityViolation: 0
Security Action: Shutdown
```

### DHCP Snooping

DHCP Snooping is enabled to protect the network from unauthorized DHCP servers.

The legitimate uplink interface is configured as a trusted port.

![Security Verification](images/03_security_verification.png)

## Connectivity Testing

Successful end-to-end connectivity was verified between the HQ network and branch offices.

Example result:

```text
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

![Connectivity Testing](images/04_connectivity_testing.png)

## Project Structure

```text
technova-enterprise-multi-branch-network/
├── TECHNOVA_Enterprise_Multi_Branch_Network.pkt
├── README.md
├── images/
│   ├── 01_network_topology.png
│   ├── 02_ip_addressing_vlan_plan.png
│   ├── 03_security_verification.png
│   └── 04_connectivity_testing.png
└── docs/
```

## Skills Demonstrated

* Network Design
* VLAN Configuration
* Trunking
* Inter-VLAN Routing
* DHCP and DHCP Relay
* Static Routing
* Network Security
* Cisco IOS Configuration
* Network Troubleshooting
* Cisco Packet Tracer

## Verification and Troubleshooting

The following commands were used to verify and troubleshoot the network:

```text
show ip interface brief
show vlan brief
show interfaces trunk
show ip route
show port-security
show ip dhcp snooping
show mac address-table
show access-lists
ping
```

## Project Purpose

This project was built as a practical CCNA-level networking lab to develop hands-on skills in enterprise network design, configuration, security, testing, and troubleshooting.

---

**Tools:** Cisco Packet Tracer
**Project Level:** CCNA
**Status:** Completed
