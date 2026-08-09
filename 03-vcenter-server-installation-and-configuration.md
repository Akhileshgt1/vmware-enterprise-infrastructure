# VMware vCenter Server Installation and Configuration

## Overview

This document covers VMware vCenter Server deployment and production configuration.

vCenter Server provides centralized management of ESXi hosts, virtual machines, clusters, networking, storage, permissions, monitoring and VMware services.

---

## 1. vCenter Architecture

A typical enterprise VMware environment:

```text
                    +----------------------+
                    |    vCenter Server    |
                    |     Management       |
                    +----------+-----------+
                               |
                +--------------+--------------+
                |                             |
        +-------+-------+             +-------+-------+
        |   ESXi Host 01 |             |   ESXi Host 02 |
        |                 |             |                 |
        |     VMs         |             |      VMs        |
        +-----------------+             +-----------------+
                |                             |
                +-------------+---------------+
                              |
                       Shared Storage
                    SAN / NAS / vSAN / NFS
