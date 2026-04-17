# Day 01 - Basic PC to PC Communication

## Objective
Build a simple network with two PCs and verify communication using IP addressing and ping.

## Topology
- 2 PCs connected directly using a copper cross-over cable

## Configuration

PC0:
- IP Address: 192.168.1.1
- Subnet Mask: 255.255.255.0

PC1:
- IP Address: 192.168.1.2
- Subnet Mask: 255.255.255.0

## Verification
- Successfully pinged PC1 from PC0 using:
  
```bash
ping 192.168.1.2
```

- Received replies confirming connectivity

## What I Learned
- Devices need IP addresses in the same network to communicate
- A direct connection allows communication without a switch or router
- Ping is used to test basic network connectivity

## Key Concept
- Communication at this level relies on proper IP configuration and physical connectivity

## Files
- topology.pkt

## Real World Context
This simulates two devices connected on a small local network where no switch or router is required.
