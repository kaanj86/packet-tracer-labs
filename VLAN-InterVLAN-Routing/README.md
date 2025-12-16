# Lab Title: VLAN Segmentation with Inter-VLAN Routing

## Objective
The purpose of this lab was to design and configure a segmented network using VLANs and enable communication between VLANs using Router-on-a-Stick.

## Topology Overview
**Devices Used**
- 1 Cisco Router
- 2 Cisco Switches
- 6 End Devices (PCs)
- 3 VLANs (10, 20, 30)

> See `topology.png` for the network layout.

## IP Addressing Scheme
| Device | Interface | IP Address | Subnet Mask | VLAN |
|------|-----------|------------|-------------|------|
| PC1  | NIC       | 192.168.10.10 | 255.255.255.0 | 10 |
| PC2  | NIC       | 192.168.20.10 | 255.255.255.0 | 20 |
| PC3  | NIC       | 192.168.30.10 | 255.255.255.0 | 30 |
| R1   | G0/0.10   | 192.168.10.1 | 255.255.255.0 | 10 |
| R1   | G0/0.20   | 192.168.20.1 | 255.255.255.0 | 20 |
| R1   | G0/0.30   | 192.168.30.1 | 255.255.255.0 | 30 |

## Key Configurations

### VLAN Configuration (Switch)
```bash
vlan 10
name Sales
vlan 20
name IT
vlan 30
name HR
