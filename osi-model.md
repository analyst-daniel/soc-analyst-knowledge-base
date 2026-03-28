# Topic: OSI Model

## 1. Definition
The OSI (Open Systems Interconnection) model is a conceptual framework for standardizing network communication.  
It defines a 7-layer architecture that enables interoperability between different systems and hardware.

## 2. Key Concepts
- Encapsulation: adding headers/trailers at each layer
- MAC address: physical identifier of a device (Layer 2)
- IP address: logical identifier of a device (Layer 3)
- NIC: network interface card with assigned MAC address
- Packet: unit of data transmission (Layer 3)
- Frame: data unit at Layer 2
- Segment: data unit at Layer 4

## 3. How It Works
1. Layer 7 (Application): user-facing services (HTTP, DNS, FTP)
2. Layer 6 (Presentation): data formatting, encryption (e.g., TLS/HTTPS)
3. Layer 5 (Session): session creation, maintenance, termination
4. Layer 4 (Transport): data delivery via TCP or UDP
5. Layer 3 (Network): routing using IP addressing
6. Layer 2 (Data Link): framing and MAC-based delivery
7. Layer 1 (Physical): transmission of binary signals over media

Data flows downward with encapsulation and upward with decapsulation.

## 4. Practical Use (Security Context)
- Layer 2: detect MAC spoofing and ARP poisoning
- Layer 3: monitor IP-based attacks and routing anomalies
- Layer 4: analyze TCP/UDP behavior for anomalies
- Layer 6: enforce encryption (TLS) for data confidentiality
- Layer 7: inspect application-layer traffic (HTTP, DNS)
- Segmentation: isolate traffic across layers to reduce attack surface

## 5. Example
A user accesses a website:
- Layer 7: HTTP request is generated
- Layer 6: data is encrypted via TLS
- Layer 4: TCP ensures reliable delivery
- Layer 3: IP routes packets to destination
- Layer 2: frames delivered via MAC addresses
- Layer 1: signals transmitted over network medium

## 6. Key Takeaways
- OSI model defines 7 layers of network communication
- Encapsulation adds metadata at each layer
- MAC operates at Layer 2, IP at Layer 3
- TCP provides reliability, UDP provides speed
- Security monitoring applies across all layers

## 7. Tags
osi, networking, tcp-ip, layers, protocols, encapsulation, soc