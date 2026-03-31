# Topic: HTTP Protocol and Communication Structure

## 1. Definition
HTTP is an application-layer protocol (Layer 7) used to transfer web resources between client and server.  
HTTPS is HTTP over TLS, providing encryption and server authentication.

## 2. Key Concepts
- URL: Standardized resource identifier.
- Scheme: Protocol used (HTTP, HTTPS, FTP).
- Host: Domain name or IP address of the server.
- Port: Communication endpoint (default: 80 for HTTP, 443 for HTTPS).
- Path: Resource location on the server.
- Query String: Parameters passed to the resource (e.g., ?id=1).
- Fragment: Reference to a section within the resource.
- Stateless: Each request is independent and contains all required context.

## 3. How It Works
- Client initiates communication with an HTTP request.
- Request structure:
  - Request Line: Method + Path + Protocol version.
  - Headers: Metadata (e.g., Host, User-Agent).
  - Empty line: Terminates headers.
  - Optional body: Data payload (e.g., POST).
- Server processes the request and returns a response.
- Response structure:
  - Status Line: Protocol version + status code.
  - Headers: Metadata (e.g., Content-Type, Server).
  - Empty line: Terminates headers.
  - Body: Requested resource.

## 4. Practical Use (Security Context)
- HTTP (port 80): No encryption. Susceptible to interception (MITM).
- HTTPS (port 443): Uses TLS for confidentiality and integrity.
- Certificates validate server identity via trusted Certificate Authorities.
- Cookies maintain session state and authentication.
- Improper header handling may lead to attacks:
  - HTTP Request Smuggling (Content-Length manipulation).
- Status codes provide indicators:
  - 4xx: Client errors (potential probing or misuse).
  - 5xx: Server errors (misconfiguration or vulnerabilities).

## 5. Example
Request:
GET /index.html HTTP/1.1  
Host: example.com  
User-Agent: Mozilla/5.0  

Response:
HTTP/1.1 200 OK  
Content-Type: text/html  
Content-Length: 1256  

<html>...</html>

## 6. Key Takeaways
- HTTP operates at Layer 7 of the OSI model.
- Communication is based on request-response architecture.
- Each request ends with an empty line separating headers and body.
- HTTPS ensures encryption and server authentication via TLS.
- Status codes classify response outcomes (1xx–5xx).
- Cookies enable session persistence in a stateless protocol.
- Misconfigurations in headers can introduce security vulnerabilities.

## 7. Tags
http, https, web, protocol, osi-layer7, request-response, tls, cookies, status-codes, web-security