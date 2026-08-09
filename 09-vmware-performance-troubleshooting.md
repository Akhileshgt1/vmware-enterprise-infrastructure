# VMware Performance Monitoring and Troubleshooting

## Overview

This document covers VMware performance monitoring, bottleneck identification and production troubleshooting.

The objective is to identify CPU, memory, storage and network performance issues systematically.

## Performance Domains

- CPU
- Memory
- Storage
- Network
- VM Performance
- ESXi Host Performance
- Datastore Performance
- Cluster Performance

## 1. CPU Performance

Important metrics:

- CPU utilization
- CPU ready
- CPU co-stop
- CPU contention
- CPU reservation
- CPU limit
- CPU shares

### CPU Ready

CPU Ready indicates the time a VM is ready to run but is waiting for physical CPU resources.

High CPU Ready may indicate CPU contention or excessive vCPU allocation.

### Troubleshooting

Check:

- Host CPU utilization
- VM CPU utilization
- Number of vCPUs
- CPU Ready
- CPU limits
- CPU reservations
- Other busy VMs

Avoid adding vCPUs without identifying the actual bottleneck.

## 2. Memory Performance

Important metrics:

- Active memory
- Consumed memory
- Ballooning
- Compression
- Swapping
- Memory utilization

### Memory Troubleshooting

Check:

- ESXi host memory utilization
- VM memory utilization
- Ballooning
- Compression
- Swap activity
- Memory reservations
- Memory limits

High memory pressure can significantly affect VM performance.

## 3. Storage Performance

Important metrics:

- Latency
- IOPS
- Throughput
- Queue depth
- Read latency
- Write latency

High storage latency can cause:

- Application slowness
- Database performance problems
- VM delays
- Guest OS freezes

### Storage Troubleshooting

Check:

- Datastore latency
- Storage device latency
- Storage paths
- Multipathing
- HBA/NIC health
- Storage array health
- Datastore capacity

## 4. Network Performance

Important metrics:

- Throughput
- Packets
- Errors
- Drops
- Retransmissions
- Link status

Check:

- Physical NIC
- vSwitch/vDS
- Port Group
- VLAN
- VMkernel
- Physical switch
- Routing

## 5. ESXi Host Troubleshooting

Start with:

- Host connectivity
- CPU
- Memory
- Storage
- Network
- Hardware health
- Datastore availability
- VM status

Useful ESXi commands:

```bash
esxcli network nic list
esxcli storage filesystem list
esxcli storage core path list
esxcli system version get
