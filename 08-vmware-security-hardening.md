# VMware Security and Hardening

## Overview

This document covers security hardening for VMware ESXi, vCenter Server, virtual machines and management infrastructure.

The objective is to reduce attack surface, protect management interfaces and follow least-privilege security principles.

---

## 1. Security Scope

VMware security should cover:

- ESXi hosts
- vCenter Server
- Management network
- Virtual machines
- Virtual switches
- Storage networks
- Authentication
- Authorization
- Certificates
- Logging
- Monitoring
- Backup
- Administrative access

---

## 2. Management Network Security

Management interfaces should be isolated from general user networks.

Recommended controls:

- Dedicated management VLAN
- Restricted firewall access
- Administrative jump host where applicable
- Restricted source IPs
- Secure protocols
- Network monitoring
- Centralized logging

Avoid exposing ESXi or vCenter management interfaces directly to untrusted networks.

---

## 3. ESXi Account Security

Follow least privilege.

Security practices:

- Use unique administrative accounts where supported
- Avoid unnecessary shared accounts
- Use strong passwords
- Review local accounts regularly
- Disable unnecessary accounts
- Monitor administrative activity

Do not use shared administrative credentials for routine operations.

---

## 4. Role-Based Access Control

Use role-based permissions.

Example roles:

```text
vCenter Administrator
VM Administrator
Network Administrator
Storage Administrator
Monitoring Operator
Read Only
Backup Operator
