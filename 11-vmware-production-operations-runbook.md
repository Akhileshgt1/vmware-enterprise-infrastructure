# VMware Production Operations Runbook

## Overview

This runbook defines routine VMware production operations, health checks, maintenance procedures, change implementation, validation and production handover.

---

## 1. Daily VMware Health Check

Check:

- vCenter health
- ESXi host status
- Cluster status
- HA status
- DRS status
- Datastore capacity
- Storage paths
- Network status
- VM alarms
- Hardware health
- Backup status
- Critical events

---

## 2. Start-of-Day Checks

Daily checks should include:

```text
vCenter
   ↓
ESXi Hosts
   ↓
Cluster
   ↓
Storage
   ↓
Network
   ↓
VMs
   ↓
Backup
   ↓
Monitoring
