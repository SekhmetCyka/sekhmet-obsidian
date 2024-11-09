### Reverse Proxy:
- **Definition**: A reverse proxy filters incoming requests rather than outgoing ones, forwarding traffic to a closed-off network.
- **Primary Goal**: Listens on a specific address and directs traffic to internal servers.

### Use Cases:
- **Cloudflare**:
  - Provides protection against DDoS attacks.
  - Filters the amount and type of traffic sent to web servers.

- **Penetration Testers**:
  - Configure reverse proxies on infected endpoints.
  - Forward client connections to the attacker, bypassing firewalls and evading logging.
  - Useful for evading IDS (Intrusion Detection Systems) by sending web requests through an SSH tunnel.

- **ModSecurity**:
  - A Web Application Firewall (WAF) that inspects and blocks malicious web requests.
  - Recommended to review the ModSecurity Core Rule Set for detailed information.

- **Cloudflare as WAF**:
  - Can also act as a WAF but requires decrypting HTTPS traffic, which some organizations may prefer to avoid.

![[Pasted image 20240725195818.png]]







