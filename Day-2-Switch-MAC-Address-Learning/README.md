# Day 02 - Switch Basics and MAC Address Learning

## Objective
Build a small switched network and understand how a switch learns device MAC addresses to forward traffic.

## Topology
- 1 Switch (2960)
- 2 PCs

## Connections
- PC0 to Switch0 Fa0/1 using Copper Straight-Through cable
- PC1 to Switch0 Fa0/2 using Copper Straight-Through cable

## Configuration

PC0:
- IP Address: 192.168.1.1
- Subnet Mask: 255.255.255.0

PC1:
- IP Address: 192.168.1.2
- Subnet Mask: 255.255.255.0

## Verification

From PC0:

```bash
ping 192.168.1.2
```

- Successful replies received

On Switch0:

```bash
show mac address-table
```

- Verified the switch learned MAC addresses on Fa0/1 and Fa0/2

## What I Learned
- Switches connect devices within the same local network
- Switches forward traffic using MAC addresses, not IP addresses
- A switch builds a MAC address table dynamically when devices communicate
- Ping traffic can trigger MAC learning

## Key Concept
- IP addresses operate at Layer 3
- MAC addresses operate at Layer 2
- A switch mainly works at Layer 2

## Real World Context
This simulates a basic office LAN where multiple devices connect through a switch to communicate efficiently.

## Files
- topology.pkt
