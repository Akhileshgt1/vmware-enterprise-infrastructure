# VMware Storage

## Overview

This document covers enterprise VMware storage architecture, configuration, connectivity, multipathing and production validation.

The objective is to provide reliable, redundant and high-performance storage for VMware workloads.

---

## 1. VMware Storage Architecture

Typical production architecture:

```text
                    vCenter Server
                         |
        +----------------+----------------+
        |                                 |
      ESXi01                            ESXi02
        |                                 |
   +----+----+                       +----+----+
   |         |                       |         |
 vmnic2    vmnic3                   vmnic2    vmnic3
   |         |                       |         |
   +----+----+                       +----+----+
        |                                 |
        +------------ Storage ------------+
                         |
                  SAN / NAS / vSAN
