# VMware HA and DRS

## Overview

This document covers VMware vSphere High Availability (HA), Distributed Resource Scheduler (DRS), cluster configuration, host failure recovery and workload balancing.

The objective is to maintain application availability and efficiently distribute workloads across ESXi hosts.

---

## 1. VMware Cluster

A VMware cluster groups multiple ESXi hosts and provides centralized resource management and availability features.

```text
                  vCenter Server
                        |
                Production Cluster
                 /       |       \
                /        |        \
           ESXi-01   ESXi-02   ESXi-03
              |         |         |
             VMs       VMs       VMs
