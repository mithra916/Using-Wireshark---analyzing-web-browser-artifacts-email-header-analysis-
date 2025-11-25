# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information
<img width="1920" height="1080" alt="Screenshot 2025-10-04 090538" src="https://github.com/user-attachments/assets/b2fa01f9-5013-4216-85d4-d2087c9a7111" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 092123" src="https://github.com/user-attachments/assets/3a176148-595c-486f-ae2f-b7f71e774876" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 092211" src="https://github.com/user-attachments/assets/a35b0af1-291d-491f-b33c-304f8d595bfa" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 095011" src="https://github.com/user-attachments/assets/64f94878-c884-42c9-99b7-e033ec0467f4" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 104036" src="https://github.com/user-attachments/assets/3ee2a3e2-db04-4117-8db5-cace698218f7" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 110905" src="https://github.com/user-attachments/assets/be5a32f9-595c-472f-a6a6-1762126878ce" />

<img width="1920" height="1080" alt="Screenshot 2025-10-04 112216" src="https://github.com/user-attachments/assets/71fe4c8b-7542-4df6-8efe-60fc6776cd82" />

## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

