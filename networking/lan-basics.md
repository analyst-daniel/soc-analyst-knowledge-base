# Topic: Local Area Network (LAN)

## 1. Definition
A Local Area Network (LAN) is a private network connecting devices within a limited geographic area.  
It enables communication and resource sharing between hosts using Layer 2 and Layer 3 protocols.

## 2. Key Concepts
- LAN: private network within a limited area
- Topology: physical or logical network structure
- Router (Layer 3): routes packets between different IP networks
- Switch (Layer 2): connects devices within the same network using MAC addresses
- Subnetting: division of a network into smaller logical segments
- IP address (Layer 3): logical identifier of a host
- MAC address (Layer 2): physical identifier of a network interface
- ARP: maps IP addresses to MAC addresses
- DHCP: dynamically assigns IP configuration to hosts

## 3. How It Works
1. Devices connect to a switch within a LAN (Layer 2).
2. Each device is identified by a MAC address (Layer 2).
3. Devices obtain IP addresses manually or via DHCP (Layer 3).
4. Switch forwards frames using MAC address tables.
5. Router forwards packets between different networks using IP routing.
6. ARP resolves IP addresses to MAC addresses for local communication.
7. Subnetting divides the network to reduce broadcast traffic.

## 4. Practical Use (Security Context)
- Network segmentation limits lateral movement of attackers.
- Subnetting isolates critical systems (e.g., POS, servers).
- ARP monitoring detects spoofing attacks.
- DHCP logs help identify unauthorized devices.
- Switch port security restricts device access.
- Router enforces access control between network segments.

## 5. Example
A corporate LAN:
- Workstations: 192.168.10.0/24
- POS systems: 192.168.20.0/24
- Router connects both subnets
- Switch connects devices within each subnet
- ARP resolves local communication
- DHCP assigns IP addresses automatically

## 6. Key Takeaways
- LAN operates primarily at Layer 2 and Layer 3.
- Switch handles local communication using MAC addresses.
- Router enables communication between networks using IP.
- ARP is required for local IP-to-MAC resolution.
- DHCP automates IP address assignment.
- Subnetting improves security and performance.

## 7. Tags
#networking #lan #osi-model #arp #dhcp #subnetting #switch #router