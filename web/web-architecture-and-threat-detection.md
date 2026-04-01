# Topic: Web Architecture and Threat Detection

## 1. Definition
- Web architecture is based on the client-server model.
- A client sends HTTP requests to a web server.
- The server processes the request and returns an HTTP response.
- This interaction defines all web traffic observed in logs.

## 2. Key Concepts
- Client → Browser initiating HTTP requests.
- Server → System processing requests and returning responses.
- HTTP Request → Client-to-server communication.
- HTTP Response → Server-to-client reply with status code and data.
- HTTP Status Codes:
  - 200 → Successful response.
  - 403 → Access denied; possible unauthorized probing.
  - 404 → Resource not found; indicator of directory enumeration.
- DOM (Document Object Model) → Structured representation of HTML content.
- Front-end Components:
  - HTML → Structure (Layer 7).
  - CSS → Presentation.
  - JavaScript → Logic and interaction.
- Input Sanitization → Filtering user input before processing.

## 3. How It Works
- Client sends HTTP request to server over the network.
- Server processes request and returns HTTP response.
- Browser renders response into visual content (DOM).
- Data flow:
  - Request → Network → Web Server → Response → Rendering
- User input is processed by application logic.
- If input is not sanitized, it is injected into execution context (DOM or JavaScript).

## 4. Practical Use (Security Context)
- Monitor HTTP status codes for anomaly detection:
  - High volume of 404 → Directory brute-forcing.
  - Repeated 403 → Access probing attempts.
- Inspect GET/POST parameters for malicious payloads:
  - Presence of `<`, `>`, `"`, `/` → Injection attempts.
- Detect suspicious JavaScript events in input:
  - onclick, onerror, onhover → Possible XSS vectors.
- Monitor access logs and WAF logs for abnormal patterns.
- Review exposed front-end code for sensitive data:
  - Credentials in comments.
  - Hidden endpoints or admin panels.
- Identify abnormal outbound requests:
  - `<img src>` used for data exfiltration.

## 5. Example
- Input field accepts unsanitized user data.
- Attacker submits:
  - `<a href="http://malicious.com">Click here</a>`
- Application renders input directly in DOM.
- Result:
  - Malicious link appears on trusted website.
  - Enables phishing within legitimate domain.
- Log indicators:
  - Special characters in parameters.
  - Unexpected outbound requests.

## 6. Key Takeaways
- Every web interaction follows request-response model.
- HTTP status codes provide critical detection signals.
- Unsanitized input leads to injection vulnerabilities.
- Front-end code is fully visible and must not contain sensitive data.
- DOM manipulation is a primary attack vector.
- Effective SOC monitoring requires correlation of logs and behavior.

## 7. Tags
- web
- http
- client-server
- dom
- xss
- html-injection
- soc
- detection
- waf
- logs