

- HTTP requests are sent and processed in clear-text.
- Clear-text data transfer in HTTP is vulnerable to Man-in-the-middle (MiTM) attacks.
- HTTPS (HTTP Secure) was created to encrypt all communications, preventing data interception by third parties.
- HTTPS has become the mainstream protocol for websites, replacing HTTP.
- Most web browsers are phasing out HTTP and will soon not allow visiting HTTP websites.



Let's look at how HTTPS operates at a high level:

![[Pasted image 20240729050817.png]]

- Typing `http://` instead of `https://` for a website enforcing HTTPS:
  - Browser resolves the domain and sends an unencrypted request to port 80.
  - Server redirects to HTTPS port 443 using a 301 Moved Permanently response code.
- The client (web browser) sends a "client hello" packet with information about itself.
- The server replies with a "server hello" packet, followed by a key exchange for SSL certificates.
- The client verifies the server's key/certificate and sends its own.
- An encrypted handshake confirms encryption and transfer functionality.
- After a successful handshake, normal encrypted HTTP (HTTPS) communication continues.
- This is a high-level overview of the key exchange process.

cURL should automatically handle all HTTPS communication standards and perform a secure handshake and then encrypt and decrypt data automatically. However, if we ever contact a website with an invalid SSL certificate or an outdated one, then cURL by default would not proceed with the communication to protect against the earlier mentioned MITM attacks:

You can use cURL -k to ignore an invalid SSL certification

