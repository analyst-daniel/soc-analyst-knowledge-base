# Topic: DNS Resolution and Record Types

## DNS Resolution and Record Types Overview
![DNS Resolution and Record Types](../assets/dns-resolution-and-records.png)

## 1. Definition
- Domain Name System (DNS) maps domain names to IP addresses.
- Enables communication between devices in IP-based networks.
- Eliminates the need to use numeric IP addresses.
- IP address uniquely identifies a host in a network.

## 2. Key Concepts
- IP Address → Unique identifier of a network host (Layer 3).
- Octet → One of four segments in an IPv4 address.
- TLD (Top-Level Domain) → Rightmost part of a domain (e.g., .com).
- gTLD → Generic TLD indicating purpose (e.g., .com, .org).
- ccTLD → Country-code TLD indicating location (e.g., .no, .uk).
- SLD (Second-Level Domain) → Domain name before TLD (e.g., google in google.com).
- Subdomain → Prefix before SLD (e.g., www, mail).

## 3. How It Works
- Client checks local DNS cache.
- Query sent to Recursive DNS resolver.
- Resolver checks its cache.
- If not found, query sent to Root DNS servers.
- Root servers respond with appropriate TLD servers.
- TLD servers provide Authoritative DNS server.
- Authoritative server returns final DNS record.
- Response includes TTL (Time To Live) in seconds.
- Result is cached for future queries.

## 4. Practical Use (Security Context)
- MX records identify email infrastructure attack surface.
- TXT records used for SPF, DKIM, and domain verification.
- DNS structure impacts cookie scope and security boundaries.
- DNS monitoring detects suspicious domain activity.
- TTL analysis helps identify fast-flux or malicious infrastructure.

## 5. Example
- `dig A example.com` → Returns IPv4 address.
- `dig AAAA example.com` → Returns IPv6 address.
- `dig MX example.com` → Returns mail servers with priority.
- `dig TXT example.com` → Returns verification or SPF records.
- `dig CNAME shop.example.com` → Returns canonical domain mapping.

## 6. Key Takeaways
- DNS operates as a hierarchical distributed system.
- Resolution path: Client → Recursive → Root → TLD → Authoritative.
- A record maps to IPv4; AAAA maps to IPv6.
- CNAME maps domain to another domain.
- TTL defines cache duration in seconds.
- Domain labels limited to 63 characters.
- Full domain name limited to 253 characters.

## 7. Tags
dns, networking, tcp-ip, layer-3, domain-resolution, records, soc-analysis