# 4-VLAN Configuration with 2 Switches and a Router

A Cisco Packet Tracer lab that segments a small organization into four VLANs
across two switches, with inter-VLAN routing handled by a Cisco 1941 router
(router-on-a-stick).

## Topology

![Network Topology](topology.png)

The network is split into two departments:

- **Administration** (Switch0): Directorate and Finance
- **Technical Office** (Switch2): IT and Support

Switch0 and Switch2 are connected by a trunk link, and Switch0 connects
to Router0, which routes traffic between the VLANs.

## Devices

| Device  | Model      | Location         |
|---------|------------|------------------|
| Router0 | Cisco 1941 | Core             |
| Switch0 | Cisco 2960 | Administration   |
| Switch2 | Cisco 2960 | Technical Office |
| PC0     | PC-PT      | Directorate      |
| PC1     | PC-PT      | Finance          |
| PC2     | PC-PT      | IT               |
| PC3     | PC-PT      | Support          |

## VLAN Table

| VLAN ID | Name        | Subnet          | Gateway      | Host |
|---------|-------------|-----------------|--------------|------|
| 10      | Directorate | 192.168.10.0/24 | 192.168.10.1 | PC0  |
| 20      | Finance     | 192.168.20.0/24 | 192.168.20.1 | PC1  |
| 30      | IT          | 192.168.30.0/24 | 192.168.30.1 | PC2  |
| 40      | Support     | 192.168.40.0/24 | 192.168.40.1 | PC3  |

## Features

- 4 VLANs distributed across 2 switches
- 802.1Q trunk between Switch0 and Switch2
- Inter-VLAN routing using router subinterfaces (G0/0.10, G0/0.20, G0/0.30, G0/0.40)
- Full connectivity between all departments

## How to Use

1. Install Cisco Packet Tracer.
2. Open the `.pkt` file from this repository.
3. Open the command prompt on any PC and ping a PC in another VLAN
   (e.g. from PC0: `ping 192.168.40.2`) to verify inter-VLAN routing.

## Technologies

- Cisco Packet Tracer
- VLANs (802.1Q)
- Trunking
- Inter-VLAN Routing (router-on-a-stick)

## Author

[Amarildo Veliaj]