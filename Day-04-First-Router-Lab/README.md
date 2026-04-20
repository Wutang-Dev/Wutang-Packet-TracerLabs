# Day 04 - First Router Lab Between Two Networks

## Objective
Understand how a router allows devices on different networks to communicate.

## Topology
- 1 Router
- 2 PCs

## Connections
- PC0 to Router0 GigabitEthernet0/0 using Copper Straight-Through cable
- PC1 to Router0 GigabitEthernet0/1 using Copper Straight-Through cable

## Configuration

### PC0
- IP Address: 192.168.1.10
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.1.1

### PC1
- IP Address: 192.168.2.10
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.2.1

### Router0

```bash
enable
configure terminal

interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface g0/1
ip address 192.168.2.1 255.255.255.0
no shutdown
exit
```

## Verification

From PC0:

```bash
ping 192.168.2.10
```

- Successful replies received

On Router0:

```bash
show ip interface brief
show ip route
```

- Verified interfaces were up/up
- Verified connected routes for both networks

## What I Learned
- Devices on different networks need a router to communicate
- A default gateway sends traffic to another network
- Router interfaces act as gateways for each subnet
- Connected networks appear automatically in the routing table

## Key Concept
- Same subnet traffic uses switching
- Different subnet traffic uses routing

## Real World Context
This simulates two separate office networks connected through a router, allowing communication between departments or sites.

## Files
- topology.pkt
