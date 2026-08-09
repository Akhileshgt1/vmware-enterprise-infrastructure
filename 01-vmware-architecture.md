# VMware Enterprise Infrastructure

## Overview

This repository documents enterprise VMware vSphere infrastructure deployment, administration, networking, storage, high availability, performance management and production troubleshooting.

The objective is to build a practical enterprise VMware administration reference from deployment to production operations.

## VMware Scope

- VMware ESXi
- VMware vCenter Server
- Virtual Machine Administration
- ESXi Host Administration
- VMware Networking
- VMkernel Networking
- Standard vSwitch
- Distributed vSwitch
- Port Groups
- VLAN Configuration
- VMware Storage
- VMFS
- NFS
- iSCSI
- Datastores
- Multipathing
- vMotion
- Storage vMotion
- VMware HA
- VMware DRS
- Clusters
- Resource Pools
- Templates
- Cloning
- Snapshots
- Host Maintenance
- Performance Troubleshooting
- ESXi Troubleshooting
- vCenter Troubleshooting
- Backup and Recovery
- Disaster Recovery

## Target Enterprise Architecture

```text
Management Workstation
        |
        v
     vCenter
        |
   VMware Cluster
     /       \
 ESXi-01    ESXi-02
   |          |
 RHEL VMs   RHEL VMs
     \       /
       Storage
          |
      SAN / NAS
