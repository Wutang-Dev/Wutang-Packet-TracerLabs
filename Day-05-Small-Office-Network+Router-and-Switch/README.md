# Day 05 - Small Office Network (Switch and Router)

## Objective
Build a small office local area network where multiple PCs connect to a switch and use a router as the default gateway.

## Topology
- 1 Router
- 1 Switch (2960)
- 2 PCs

## Connections
- PC0 to Switch0 Fa0/1 using Copper Straight-Through cable
- PC1 to Switch0 Fa0/2 using Copper Straight-Through cable
- Switch0 Fa0/24 to Router0 GigabitEthernet0/0 using Copper Straight-Through cable

## Configuration

### Router0

```bash
enable
configure terminal

interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
```

### PC0
- IP Address: 192.168.1.10
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.1.1

### PC1
- IP Address: 192.168.1.20
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.1.1

## Verification

From PC0:

```bash
ping 192.168.1.20
ping 192.168.1.1
```

- Successful replies received from PC1
- Successful replies received from Router0 gateway

On Router0:

```bash
show ip interface brief
```

- Verified GigabitEthernet0/0 was up/up

## What I Learned
- A switch connects multiple devices on the same local network
- A router provides the default gateway for devices to reach other networks
- Devices on the same subnet can communicate through the switch
- End devices must know their gateway to leave the subnet

## Key Concept
- Local traffic uses switching
- Off-network traffic uses the default gateway

## Real World Context
This simulates a small office network where staff devices connect to a switch and use a router for internet or external network access.

## Files
- topology.pkt
