# Topic: Network Infrastructure and Security Mechanisms

## 1. Definition
Secure communication between devices across different networks using routing, segmentation, and encryption mechanisms.

## Network Infrastructure and Security Mechanisms Overview
![Network Infrastructure and Security Mechanisms](../assets/network-infrastructure-security.png)

## 2. Key Concepts
- VPN: Secure communication channel over untrusted networks
- Tunneling: Encapsulation of traffic within another protocol
- Encryption: Protection of data confidentiality against interception
- Routing (Layer 3): Path selection for packet delivery between networks
- VLAN (Layer 2): Logical segmentation within a physical network
- Port Forwarding: Exposure of internal services to external networks

## 3. How It Works
- VPN establishes an encrypted tunnel between endpoints
- Tunneling encapsulates private traffic inside public network packets
- Encryption ensures data confidentiality during transmission
- Routers (Layer 3) determine optimal paths using metrics such as distance and reliability
- Layer 2 switches forward frames based on MAC addresses
- Layer 3 switches perform both frame forwarding and IP routing
- VLANs isolate broadcast domains within the same infrastructure
- Port forwarding maps external ports to internal services via router rules
- Firewalls inspect traffic based on predefined rules and session state

### VPN Protocols
- PPP: Provides authentication and encryption; not routable outside local networks
- PPTP: Encapsulates PPP for transmission over IP networks
- IPsec: Encrypts IP packets at Layer 3 using secure key exchange

### Firewall Types
- Stateful Firewall: Tracks session state and connection behavior
- Stateless Firewall: Filters packets based on static rules (IP, port, protocol)

## 4. Practical Use (Security Context)
- VPN: Secure remote access to internal systems
- VLAN: Segmentation of departments to reduce lateral movement
- Firewall: Filtering inbound and outbound traffic based on security policies
- Port Forwarding: Controlled exposure of services (e.g., web server on port 80)
- Encryption: Protection against packet sniffing on public networks

## 5. Example
- Remote user connects to corporate network via IPsec VPN
- Router forwards encrypted traffic to internal resources
- Firewall allows only VPN traffic on specific ports (e.g., UDP 500, 4500)
- Internal network segmented using VLANs (e.g., finance vs operations)
- Web server exposed externally via port forwarding on TCP port 80

## 6. Key Takeaways
- VPN provides secure communication across untrusted networks
- Routing occurs at Layer 3 using IP addressing
- VLANs enforce logical isolation within Layer 2 networks
- Firewalls control traffic using rules and session inspection
- Port forwarding enables controlled external access to internal services
- Encryption prevents data interception and unauthorized access

## 7. Tags
networking, vpn, firewall, vlan, routing, encryption, osi-model, ports