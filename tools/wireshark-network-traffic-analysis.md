# Topic: Wireshark Network Traffic Analysis

## 1. Definition
Wireshark is a packet analysis tool used to inspect network traffic at multiple OSI layers.  
It enables protocol analysis, communication pattern identification, and detection of security anomalies.

## 2. Key Concepts
- Packet analysis follows OSI model decomposition (Layer 2–7 visible).
- Frame (Layer 1): capture metadata, timestamp, interface.
- MAC addresses (Layer 2): source and destination hardware identifiers.
- IP addresses (Layer 3): logical addressing, TTL, protocol type.
- TCP/UDP (Layer 4): ports, flags, sequence numbers.
- Application layer (Layer 5–7): HTTP, DNS, SMB data.
- Display filters refine analysis scope.
- Capture filters limit recorded traffic at ingestion.
- Logical operators: `and`, `or`, `==`, `!=`.
- Common filters:
  - `ip.addr == X`
  - `tcp.port == X`
  - `arp.opcode == 2`

## 3. How It Works
- Capture traffic via interface, tap, or port mirroring.
- Decompose packets into OSI layers.
- Apply display filters to isolate relevant traffic.
- Identify communication patterns instead of reviewing all packets.
- Analyze protocol-specific behavior:
  - ARP resolves IP to MAC (Layer 2).
  - ICMP provides diagnostics (Layer 3).
  - TCP ensures reliable transport (Layer 4).
  - DNS resolves domain names (Layer 7 over UDP/TCP).
  - HTTP/HTTPS handles application data (Layer 7).
- Inspect metadata when payload is encrypted (HTTPS).

## 4. Practical Use (Security Context)
- Detect ARP poisoning:
  - One IP mapped to multiple MAC addresses.
  - Excessive unsolicited ARP replies.
- Detect ICMP tunneling:
  - Abnormal payload size in ICMP packets.
- Identify closed ports:
  - TCP `RST, ACK` responses.
- Detect suspicious DNS activity:
  - DNS over TCP (port 53).
- Analyze HTTPS behavior:
  - TLS handshake anomalies.
  - Certificate issuer and domain mismatch.
  - Packet size and timing patterns (C2 beaconing, data exfiltration).
- Investigate exploitation attempts:
  - RPC traffic to domain controllers.
  - SMB traffic associated with credential dumping.

## 5. Example
- Filter DNS traffic:
  - `dns`
- Identify target IP:
  - `ip.addr == 192.168.1.1`
- Detect ARP replies:
  - `arp.opcode == 2`
- Observation:
  - Multiple MAC addresses associated with one IP.
- Conclusion:
  - Possible ARP poisoning attack.

## 6. Key Takeaways
- Effective analysis relies on filtering and pattern recognition.
- OSI layer understanding is critical for packet interpretation.
- Encrypted traffic still exposes behavioral indicators.
- Protocol anomalies often indicate malicious activity.
- Statistical tools improve visibility in large datasets.

## 7. Tags
wireshark, packet-analysis, network-security, tcp-ip, dns, arp, icmp, http, https, soc