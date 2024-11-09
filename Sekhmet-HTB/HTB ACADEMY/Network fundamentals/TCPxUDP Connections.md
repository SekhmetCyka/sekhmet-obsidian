**Summary Points:**

1. **Purpose and Use**:
   - TCP and UDP are protocols used for data transmission on the Internet.
   - **TCP**: Used for important data like web pages and emails.
   - **UDP**: Used for real-time data like streaming video and online gaming.

2. **TCP Characteristics**:
   - **Connection-Oriented**: Establishes a connection before data is sent.
   - **Reliability**: Ensures all data is received correctly.
   - **Error Handling**: Receiver requests resending of missing data if an error occurs.
   - **Performance**: Reliable but slower due to error recovery processes.

3. **UDP Characteristics**:
   - **Connectionless**: No need to establish a connection before data is sent.
   - **Speed**: Faster transmission without error checking.
   - **Reliability**: Does not guarantee that all data is received or is error-free.
   - **Usage**: Suitable for applications where speed is prioritized over reliability, such as video streaming and online gaming.

4. **Comparison**:
   - **TCP**: Reliable and slower, with error recovery.
   - **UDP**: Faster and less reliable, with potential data loss.


| **Field**                | **Description**                                                                |
| ------------------------ | ------------------------------------------------------------------------------ |
| `Version`                | Indicates which version of the IP protocol is being used                       |
| `Internet Header Length` | Indicates the size of the header in 32-bit words                               |
| `Class of Service`       | Means how important the transmission of the data is                            |
| `Total length`           | Specifies the total length of the packet in bytes                              |
| `Identification (ID)`    | Is used to identify fragments of the packet when fragmented into smaller parts |
| `Flags`                  | Used to indicate fragmentation                                                 |
| `Fragment Offset`        | Indicates where the current fragment is placed in the packet                   |
| `Time to Live`           | Specifies how long the packet may remain on the network                        |
| `Protocol`               | Specifies which protocol is used to transmit the data, such as TCP or UDP      |
| `Checksum`               | Is used to detect errors in the header                                         |
| `Source/Destination`     | Indicate where the packet was sent from and where it is being sent to          |
| `Options`                | Contain optional information for routing                                       |
| `Padding`                | Pads the packet to a full word length                                          |
### Transmission Control Protocol (TCP)

TCP is a connection-oriented protocol that ensures reliable data transmission between hosts. Each TCP segment consists of a header and a payload. The header is crucial for managing the communication and includes the following fields:

- **Source Port:** Identifies the port number of the sending device.
- **Destination Port:** Identifies the port number of the receiving device.
- **Sequence Number:** Used to ensure the correct order of data packets.
- **Acknowledgment Number:** Confirms receipt of data packets.
- **Control Flags:** Manage the state of the connection (e.g., SYN, ACK, FIN).
- **Window Size:** Indicates the amount of data the receiver can process at a time.
- **Checksum:** Verifies the integrity of the header and payload.
- **Urgent Pointer:** Flags urgent data that needs immediate processing.

The **payload** contains the actual data being transferred.

### User Datagram Protocol (UDP)

UDP is a connectionless protocol used for sending small data packets, known as datagrams, between hosts. Unlike TCP, UDP does not establish a connection before data transfer, making it faster but less reliable. Each UDP datagram includes:

- **Source Port:** Identifies the port number of the sending device.
- **Destination Port:** Identifies the port number of the receiving device.
- **Length:** Specifies the length of the UDP header and payload.
- **Checksum:** Verifies the integrity of the header and payload.

UDP is often used in applications where speed is more critical than reliability, such as streaming and online gaming.

### Traceroute with UDP

When using traceroute with UDP, packets are sent to the target device incrementally with increasing TTL (Time To Live) values. As the packets traverse the network, each hop decrements the TTL and sends back an ICMP "Time Exceeded" message when the TTL reaches zero. Upon reaching the target device, if the port is unreachable, a "Destination Unreachable" and "Port Unreachable" message is returned. This helps map the path taken by packets to their destination.

### Blind Spoofing

Blind spoofing is a network attack where the attacker sends falsified packets to a target without seeing the actual responses. This involves:

- **Manipulating IP Headers:** The attacker alters the source and destination IP addresses.
- **False Port Numbers and ISNs:** Fake source and destination port numbers and Initial Sequence Numbers (ISNs) are used.

The attacker sends TCP packets with these manipulated headers to trick the target into establishing a connection or disrupting an existing one. This technique can be employed for:

- **Disrupting Network Integrity:** Causing connections to drop or misbehave.
- **Monitoring Traffic:** Intercepting or spying on data being sent across the network.

Blind spoofing is a significant security threat as it can undermine the trust and reliability of network communications.