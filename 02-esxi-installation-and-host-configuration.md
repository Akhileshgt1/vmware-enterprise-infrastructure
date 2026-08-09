# VMware ESXi Installation and Host Configuration

## Overview

This document covers VMware ESXi installation and enterprise host configuration for production environments.

The objective is to prepare a stable, secure and production-ready ESXi host.

---

## 1. Pre-Installation Planning

Before installing ESXi, validate:

- Server hardware compatibility
- CPU and RAM capacity
- RAID configuration
- Storage controller
- Network adapters
- Firmware versions
- BIOS/UEFI configuration
- ESXi version compatibility
- VMware Hardware Compatibility List (HCL)
- Management network details
- DNS and NTP requirements
- Hostname and IP address
- Gateway and VLAN information

---

## 2. ESXi Host Hardware Validation

Check the following:

- CPU model and virtualization support
- Total physical memory
- RAID controller status
- Local disks
- SAN/NAS connectivity
- NIC count and speed
- Redundant power supplies
- Hardware health status

Production hosts should have redundant components wherever possible.

---

## 3. BIOS/UEFI Configuration

Recommended configuration:

- Enable Intel VT-x or AMD-V
- Enable CPU virtualization
- Enable NX/XD protection
- Configure boot mode as required
- Configure RAID controller
- Verify boot device
- Configure power management according to workload
- Disable unnecessary hardware devices

---

## 4. ESXi Installation

Installation flow:

1. Boot server from ESXi installation media.
2. Start ESXi installer.
3. Accept the VMware license agreement.
4. Select the installation disk.
5. Select keyboard layout.
6. Configure the root password.
7. Start ESXi installation.
8. Reboot the server after installation.
9. Remove installation media.
10. Boot into ESXi.

---

## 5. Initial ESXi Configuration

After installation configure:

- Hostname
- Management IP address
- Subnet mask
- Default gateway
- DNS servers
- DNS hostname
- NTP
- Management VLAN
- Root access policy

---

## 6. Management Network Configuration

Management traffic should use a dedicated network where possible.

Example:

| Parameter | Example |
|---|---|
| Hostname | esxi01.example.local |
| Management IP | 10.10.10.21 |
| Subnet | 255.255.255.0 |
| Gateway | 10.10.10.1 |
| DNS | 10.10.10.10 |
| VLAN | 100 |
| NTP | 10.10.10.20 |

Use organization-approved IP addressing and VLANs in production.

---

## 7. ESXi Networking

Configure:

- Physical NICs
- VMkernel adapters
- Management network
- vMotion network
- Storage network
- VM networks
- VLANs
- Standard vSwitch
- Distributed vSwitch where applicable
- NIC teaming
- Failover policy

Network redundancy should be implemented for production hosts.

---

## 8. VMkernel Configuration

Common VMkernel services include:

- Management
- vMotion
- Provisioning
- IP Storage
- vSAN
- Fault Tolerance

Separate traffic types when required by the production architecture.

---

## 9. Storage Configuration

Validate:

- Local datastore
- SAN storage
- NAS storage
- iSCSI
- Fibre Channel
- NFS
- VMFS
- Multipathing
- Storage visibility
- Datastore capacity

Verify storage redundancy and path availability.

---

## 10. Time Synchronization

Configure reliable NTP servers.

Validate:

```bash
esxcli system ntp get
