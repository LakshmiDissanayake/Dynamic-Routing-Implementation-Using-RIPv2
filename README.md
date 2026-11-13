# Dynamic Routing Implementation Using RIPv2

## Project Overview

This project demonstrates the design and implementation of a multi-router network using Cisco Packet Tracer, with Routing Information Protocol Version 2 (RIPv2) configured for dynamic routing.

The network consists of three Cisco routers connected through serial links, three LAN networks, three switches, and six end devices.

RIPv2 enables routers to automatically exchange routing information and learn routes to remote networks, allowing communication between different LANs without manually configuring individual static routes.

## Technologies Used

- Cisco Packet Tracer
- Cisco 2911 Routers
- Cisco 2960 Switches
- Routing Information Protocol Version 2 (RIPv2)
- Dynamic Routing
- Serial WAN Connections
- IPv4 Addressing and Subnetting
- Cisco IOS CLI

## Network Topology

The network consists of three routers (R1, R2, and R3), connected using serial connections.

Each router connects to a separate LAN containing a switch and two PCs.

**Network components:**
- 3 Cisco 2911 Routers
- 3 Cisco 2960 Switches
- 6 PCs
- 3 LAN networks
- 2 Serial connections between routers

## IP Addressing Scheme

### LAN Networks

| Router | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| R1 | Fa0/0 | 192.168.10.1 | 255.255.255.0 |
| R2 | Fa0/0 | 192.168.20.1 | 255.255.255.0 |
| R3 | Fa0/0 | 192.168.30.1 | 255.255.255.0 |

### Serial Connections

| Connection | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| R1 – R2 | R1 Se2/0 | 192.168.40.1 | 255.255.255.252 |
| R1 – R2 | R2 Se2/0 | 192.168.40.2 | 255.255.255.252 |
| R2 – R3 | R2 Se3/0 | 192.168.50.1 | 255.255.255.252 |
| R2 – R3 | R3 Se3/0 | 192.168.50.2 | 255.255.255.252 |

### PC Addressing

| PC | IP Address | Default Gateway |
|---|---|---|
| PC0 | 192.168.10.10 | 192.168.10.1 |
| PC1 | 192.168.10.11 | 192.168.10.1 |
| PC2 | 192.168.20.10 | 192.168.20.1 |
| PC3 | 192.168.20.11 | 192.168.20.1 |
| PC4 | 192.168.30.10 | 192.168.30.1 |
| PC5 | 192.168.30.11 | 192.168.30.1 |

## Implementation and Configuration

### 1. Network Topology Setup

- Created a network topology using three Cisco 2911 routers.
- Connected routers through serial interfaces.
- Connected each router to a LAN using a Cisco 2960 switch.
- Connected two PCs to each LAN.

### 2. IP Address Configuration

- Configured IPv4 addresses on router LAN interfaces.
- Assigned IP addresses to serial interfaces.
- Configured subnet masks and default gateways on all PCs.
- Established addressing for all three LAN networks and both serial links.

### 3. Serial Interface Configuration

- Configured serial connections between R1, R2, and R3.
- Checked serial interface controllers to identify DCE connections.
- Configured clock rates on the DCE ends where required.
- Verified interface status.

### 4. RIPv2 Dynamic Routing Configuration

Configured RIPv2 on all three routers to exchange routing information.

The configuration process includes:

- Enabling the RIP routing process.
- Selecting RIP Version 2.
- Advertising directly connected networks.
- Disabling automatic summarization using `no auto-summary`.
- Allowing routers to learn remote LAN networks dynamically.

### 5. Routing Table Verification

Used Cisco IOS commands to inspect routing information and verify dynamically learned routes.

```bash
show ip protocols
show ip route
```

The routing table can identify routes learned through RIP using the `R` routing code.

### 6. Network Connectivity Testing

Performed connectivity tests to examine communication between devices.

- Tested communication between PCs within the same LAN.
- Tested communication between PCs in different LANs.
- Examined dynamically learned routes between routers.

## Testing and Validation

The following tests are used to validate the network implementation:

| Test | Expected Result |
|---|---|
| PC0 to PC1 (LAN 1) | Successful |
| PC2 to PC3 (LAN 2) | Successful |
| PC4 to PC5 (LAN 3) | Successful |
| PC0 to PC2 (Different LANs) | Successful |
| PC0 to PC4 (Different LANs) | Successful |

Additional verification commands:

```bash
show ip interface brief
show ip protocols
show ip route
```

## Key Concepts Demonstrated

- Dynamic routing fundamentals.
- RIPv2 configuration and operation.
- Router-to-router communication.
- IPv4 addressing and subnetting.
- Serial WAN connections.
- DCE and DTE serial configuration.
- Dynamic route advertisement and learning.
- Routing table inspection.
- End-to-end connectivity between multiple LANs.

## Project Outcome

This project demonstrates the practical implementation of dynamic routing using RIPv2 in a multi-router network environment.

It provides hands-on experience in router configuration, IP addressing, serial connections, routing protocol configuration, and communication between geographically or logically separate LAN networks.

## Project Files
- [Packet Tracer Project](./Dynamic-Routing-Implementation-Using-RIPv2.pkt)
- [Screenshots](./Screenshots/)

---

**Tools & Technologies:** Cisco Packet Tracer | Cisco IOS | RIPv2 | IPv4 | Dynamic Routing
