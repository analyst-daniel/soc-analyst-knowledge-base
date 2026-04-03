# Topic: Wireshark Network Traffic Analysis

## 1. Definition
Wireshark is a packet analysis tool used to capture, inspect, and analyze network traffic at multiple OSI layers.  
It enables protocol-level visibility for troubleshooting, threat detection, and forensic analysis.

## 2. Key Concepts
- Packet structure follows the OSI model (Layer 1–7).
- Frame → metadata, timestamp, capture details (Layer 1).
- Ethernet → source and destination MAC addresses (Layer 2).
- IP → source/destination IP, TTL, fragmentation (Layer 3).
- TCP/UDP → ports, sequence numbers, flags (Layer 4).
- Application layer → protocols such as HTTP, DNS (Layer 7).
- Display filters reduce noise and isolate relevant traffic.
- Statistical tools summarize traffic patterns and relationships.

## 3. How It Works
- Select an active network interface for capture.
- Capture packets and stop capture for static analysis.
- Inspect packets by expanding OSI layers.
- Apply filters to isolate relevant traffic.
- Analyze protocol behavior and sequences:
  - ARP → IP-to-MAC resolution.
  - ICMP → diagnostic communication.
  - TCP → connection establishment and reliability.
  - DNS → domain-to-IP resolution.
  - HTTP/HTTPS → web communication.
- Use statistics tools:
  - Protocol Hierarchy → protocol distribution.
  - Endpoints → communicating hosts.
  - Conversations → session-level communication.

## 4. Practical Use (Security Context)
- Detect ARP spoofing:
  - One IP mapped to multiple MAC addresses.
  - Excess ARP replies without requests.
- Detect ICMP tunneling:
  - Unusual payload size in ICMP packets.
- Detect port scanning:
  - TCP RST, ACK responses indicate closed ports.
- Detect DNS anomalies:
  - DNS over TCP (port 53) may indicate abnormal behavior.
- Inspect HTTP traffic:
  - Plaintext data visible (URI, headers, content).
- Decrypt HTTPS traffic:
  - Requires private keys (e.g., RSA key import).
- Reconstruct host activity:
  - DNS queries reveal accessed domains.

## 5. Example
- Filter ARP replies:
  - `arp.opcode == 2`
- Filter traffic for specific host:
  - `ip.addr == 192.168.1.1`
- Detect suspicious ARP behavior:
  - Same IP associated with multiple MAC addresses.
- Identify closed port:
  - TCP response with `RST, ACK`.

## 6. Key Takeaways
- Analyze traffic using OSI layer structure.
- Always stop capture before detailed analysis.
- Focus on patterns, not individual packets.
- Use filters to isolate relevant data.
- Validate normal protocol behavior before identifying anomalies.
- Combine protocol analysis with statistical views for context.

## 7. Tags
wireshark, packet-analysis, networking, tcp-ip, arp, dns, http, soc, traffic-analysis