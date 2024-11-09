
### Wireless Networks

- **Definition**:
  - Use wireless data connections between network nodes.
  - Allow devices (laptops, smartphones, tablets) to communicate with each other and the Internet without cables.

- **Technology**:
  - Use radio frequency (RF) technology to transmit data.
  - Devices have wireless adapters to convert data into RF signals and vice versa.

- **Range**:
  - Varies by technology:
    - **WiFi (LAN)**: Covers small areas (e.g., home, office) with a range of a few hundred feet.
    - **WWAN**: Uses cellular data (3G, 4G LTE, 5G) to cover larger areas (e.g., city, region).

- **Connection Requirements**:
  - Device must be within range.
  - Must have correct network settings (network name, password).

- **Communication**:
  - Occurs over RF in 2.4 GHz or 5 GHz bands in WiFi networks.
  - Device communicates with a Wireless Access Point (WAP) to request transmission permission.
  - WAP connects wireless network to wired network and controls access.
  - Transmitting device sends data as RF signals, received by other devices' adapters.

- **Influencing Factors**:
  - Signal strength and travel distance affected by:
    - Transmitter power.
    - Obstacles.
    - RF noise density.

- **Techniques for Reliable Communication**:
  - Spread spectrum transmission.
  - Error correction.


### WiFi Connection

- **Configuration Requirements**:
  - Correct network settings: network name (SSID) and password.
  
- **Protocol**:
  - Uses IEEE 802.11 for communication details between devices and WAPs.

- **Connection Process**:
  1. **Request**:
     - Device sends an association request to WAP using IEEE 802.11.
     - Request frame contains:
       - **MAC address**: Unique identifier for device's wireless adapter.
       - **SSID**: Network name.
       - **Supported data rates**: List of compatible data rates.
       - **Supported channels**: List of communication channels.
       - **Supported security protocols**: List of security protocols like WPA2/WPA3.

  2. **Configuration**:
     - Device configures its adapter using this information.
  
  3. **Establishment**:
     - Connection is established.
     - Device communicates with WAP and other network devices.
     - Access to Internet and online resources through WAP (gateway to wired network).

- **SSID Handling**:
  - **Hidden SSID**:
    - Can be hidden by disabling broadcasting.
    - Devices can't identify hidden SSID through search.
    - Still found in authentication packet.

- **Additional Protocols**:
  - **TCP/IP**: For data transmission.
  - **DHCP**: For IP address assignment.
  - **WPA2**: For security.

### Summary

Devices connect to WiFi networks by configuring with the correct SSID and password, using the IEEE 802.11 protocol for communication. The process involves sending a connection request to the WAP, configuring the wireless adapter, and establishing the connection to access network resources. Hidden SSIDs can still be detected in authentication packets, and additional protocols like TCP/IP, DHCP, and WPA2 are used for various network tasks.