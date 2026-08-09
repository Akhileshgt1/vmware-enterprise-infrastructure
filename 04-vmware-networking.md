# VMware Networking

## Overview

This document covers enterprise VMware networking from physical NIC configuration to virtual machine networking.

The objective is to build a redundant, secure and production-ready VMware network.

---

## 1. VMware Network Architecture

Typical production design:

```text
                    Physical Network
                           |
              +------------+------------+
              |                         |
            vmnic0                    vmnic1
              |                         |
              +------------+------------+
                           |
                    Virtual Switch
                           |
              +------------+------------+
              |                         |
        Management PG              VM Network PG
              |                         |
        Management VMkernel          Virtual Machines
