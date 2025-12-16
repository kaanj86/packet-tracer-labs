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

vlan 10
name Sales
vlan 20
name IT
vlan 30
name HR

## Trunk Configuration
interface g0/1
switchport mode trunk

## Router Subinterfaces
interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0

## Validation & Testing

Verified VLAN assignments using show vlan brief

Confirmed trunk status with show interfaces trunk

Tested inter-VLAN connectivity using ping

## Troubleshooting Performed
| Issue	| Cause	| Resolution |
|-------|-------|------------|
| No inter-VLAN ping	| Trunk not configured	| Enabled trunk mode |
| PC unreachable | Wrong gateway | Corrected default gateway |

## Outcome
Successfully enabled secure communication between multiple VLANs while maintaining logical segmentation.

## Skills Demonstrated

VLAN configuration and trunking

Router-on-a-Stick

IP addressing and subnetting

CLI-based troubleshooting
