# Topic: Packets and Frames
## Packets and Frames Overview

![Packets and Frames](../assets/packets-and-frames.png)

## 1. Definition
A frame is a Layer 2 (Data Link) data unit used for local network transmission.  
It contains MAC addressing information but does not include IP addresses.  

A packet is a Layer 3 (Network) data unit.  
It contains logical addressing using IP addresses for routing between networks.  

## 2. Key Concepts
- Encapsulation → adding protocol headers at each OSI layer
- Decapsulation → removing headers at the receiving host
- TCP/IP model → Application, Transport, Internet, Network Interface
- TCP → connection-oriented protocol with reliability mechanisms
- UDP → connectionless protocol without delivery guarantees

## 3. How It Works
1. Application generates data for transmission
2. Transport layer (Layer 4) segments data (TCP/UDP) and assigns ports
3. Network layer (Layer 3) adds IP header (source/destination IP, TTL)
4. Data Link layer (Layer 2) encapsulates packet into a frame (MAC addresses)
5. Frame is transmitted over physical medium (Layer 1)
6. Receiving host performs decapsulation in reverse order

## 4. Practical Use (Security Context)
- Packet analysis used in traffic inspection (e.g., anomaly detection)
- TCP flags (SYN, ACK, RST, FIN) used to identify scanning or attacks
- TTL values used in network path analysis and detection of spoofing
- Checksum validation ensures data integrity during transmission
- Port-based filtering used in firewalls and IDS/IPS systems

## 5. Example
A client initiates a connection to a web server:
1. Client sends TCP SYN packet to destination port 443
2. Server responds with SYN/ACK
3. Client sends ACK to establish session
4. Encrypted HTTPS traffic is exchanged over TCP

## 6. Key Takeaways
- Frames operate at Layer 2 and use MAC addressing
- Packets operate at Layer 3 and use IP addressing
- TCP ensures reliable delivery using acknowledgments
- UDP provides faster transmission without reliability guarantees
- Encapsulation enables layered communication in networks

## 7. Tags
#networking #osi-model #tcp #udp #packets #frames #ip #ports