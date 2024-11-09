
### User Datagram Protocol (UDP)

- **Definition**: 
  - **Connectionless Protocol**: No virtual connection is established before data transmission.
  - **Transmission**: Sends data packets directly to the destination without ensuring receipt.

- **Characteristics**:
  - **Speed over Reliability**: Faster than TCP as it skips the connection establishment step.
  - **No Guarantee**: No assurance that packets will reach their destination or be in the correct order.

- **Example**:
  - **Video Streaming**: Platforms like YouTube use UDP for video data transmission.
  - **Data Loss Tolerance**: Some data loss is acceptable in streaming, prioritizing speed over reliability.
  - **Impact**: Minor packet loss does not significantly affect video quality.

- **Comparison to TCP**:
  - **Speed**: UDP is faster due to the absence of connection overhead.
  - **Reliability**: Less reliable than TCP, as it does not check for packet delivery or order.
