# Topic: Network Fundamentals

## 1. Definition
A network is a system of two or more connected devices that exchange data using wired or wireless communication.  
It enables resource sharing, communication, and centralized control of systems.

## 2. Key Concepts
- Network: interconnected devices exchanging data
- Internet: global network of interconnected networks
- Private network: isolated internal infrastructure
- Public network: externally accessible network
- Protocol: standardized rules for communication
- IPv4: 32-bit logical addressing (Layer 3)
- IPv6: 128-bit logical addressing (Layer 3)
- MAC address: physical device identifier (Layer 2)
- ICMP: protocol used for diagnostics (Layer 3)

## 3. How It Works
1. Devices connect via network interfaces (NICs)
2. Each device is assigned a MAC address (Layer 2)
3. Devices obtain an IP address for logical identification (Layer 3)
4. Data is split into packets and transmitted across the network
5. Protocols define packet structure and communication rules
6. Routers forward packets between networks based on IP
7. Switches forward frames within local networks using MAC

## 4. Practical Use (Security Context)
- Identify hosts using IP and MAC correlation in logs
- Detect unauthorized devices in network segments
- Monitor ICMP traffic for reconnaissance activity
- Validate connectivity during incident response
- Enforce network segmentation and access control

## 5. Example
An analyst detects ICMP echo requests from an unknown IP scanning internal hosts.  
Correlation with MAC address reveals a spoofed device bypassing network access controls.

## 6. Key Takeaways
- Networks require at least two connected devices
- IP provides logical addressing at Layer 3
- MAC provides physical identification at Layer 2
- IPv4 uses 32-bit addressing, IPv6 uses 128-bit
- ICMP is used for diagnostics and reconnaissance
- MAC spoofing enables identity impersonation

## 7. Tags
networking, ip, mac, icmp, osi, layer2, layer3
