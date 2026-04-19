# Day 03 - Three PC Switched Network

## Objective
Expand the local network to three devices and observe how a switch learns multiple MAC addresses.

## Topology
- 1 Switch (2960)
- 3 PCs

## Connections
- PC0 to Switch0 Fa0/1 using Copper Straight-Through cable
- PC1 to Switch0 Fa0/2 using Copper Straight-Through cable
- PC2 to Switch0 Fa0/3 using Copper Straight-Through cable

## Configuration

PC0:
- IP Address: 192.168.1.1
- Subnet Mask: 255.255.255.0

PC1:
- IP Address: 192.168.1.2
- Subnet Mask: 255.255.255.0

PC2:
- IP Address: 192.168.1.3
- Subnet Mask: 255.255.255.0

## Verification

From PC0:

```bash
ping 192.168.1.2
ping 192.168.1.3
```

From PC1:

```bash
ping 192.168.1.3
```

- Successful replies received between all devices

On Switch0:

```bash
show mac address-table
```

- Verified the switch learned MAC addresses on Fa0/1, Fa0/2 and Fa0/3

## What I Learned
- Multiple devices can communicate on the same local network through a switch
- Devices in the same subnet do not need a router to communicate
- A switch learns which MAC address is connected to each port
- The MAC address table grows as more devices communicate

## Key Concept
- A switch forwards frames based on MAC addresses
- Devices in the same subnet use Layer 2 switching for communication

## Real World Context
This simulates a small office LAN where multiple computers share the same switch and network segment.

## Files
- topology.pkt
