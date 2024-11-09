### Forward Proxy / Dedicated Proxy:
- **Definition**: A Forward Proxy is a server that makes requests on behalf of a client. It is what most people typically think of when they hear "proxy."

### Use Cases:
- **Corporate Networks**: 
  - Sensitive computers access the internet through a proxy or web filter, enhancing security.
  - Acts as a defense against malware by requiring it to be proxy-aware or use non-traditional command and control (C2) mechanisms.

### Browser Behavior:
- **System Proxy Settings**:
  - **Internet Explorer, Edge, Chrome**: Obey system proxy settings by default. Malware using WinSock (Native Windows API) will likely be proxy-aware.
  - **Firefox**: Uses libcurl instead of WinSock, requiring malware to explicitly pull proxy settings for Firefox, which is unlikely.

### Malware Considerations:
- **Proxy Awareness**: 
  - Malware needs to be designed to bypass web filters and be proxy-aware to communicate through a Forward Proxy.
- **Alternative C2 Mechanisms**:
  - **DNS**: Malware could use DNS as a C2 mechanism. However, monitoring DNS with tools like Sysmon can quickly detect such traffic.

### Example:
- **Burp Suite**: 
  - Often used to forward HTTP requests, acting as a Forward Proxy.
  - Versatile tool, configurable as a reverse proxy or transparent proxy.

By understanding the function and importance of a Forward Proxy, organizations can better secure their networks against unauthorized access and malware.

![[Pasted image 20240725195512.png]]
