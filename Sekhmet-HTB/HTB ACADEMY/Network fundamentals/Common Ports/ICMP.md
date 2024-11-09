
### Internet Control Message Protocol (ICMP)

- **Purpose**:
  - **Communication**: Used by devices to communicate on the Internet.
  - **Functions**: Error reporting and status information.

- **ICMP Requests**:
  - **Definition**: A message sent to request information or perform an action.
  - **Example**: Ping request tests connectivity between devices.
  - **Process**: Device A sends a ping request, Device B responds with a ping reply.

- **ICMP Messages**:
  - **Types**: Requests and replies.
  - **Functions**: Includes error messages like destination unreachable and time exceeded.
  - **Example**: If a packet cannot be delivered, ICMP sends an error message back to the sender.

- **Versions**:
  - **ICMPv4**: 
    - Developed for IPv4.
    - Most common and widely used version.
  - **ICMPv6**: 
    - Developed for IPv6.
    - Includes additional functionalities and addresses ICMPv4 limitations.

|**Request Type**|**Description**|
|---|---|
|`Echo Request`|This message tests whether a device is reachable on the network. When a device sends an echo request, it expects to receive an echo reply message. For example, the tools `tracert` (Windows) or `traceroute` (Linux) always send ICMP echo requests.|
|`Timestamp Request`|This message determines the time on a remote device.|
|`Address Mask Request`|This message is used to request the subnet mask of a device.|

|**Message Type**|**Description**|
|---|---|
|`Echo reply`|This message is sent in response to an echo request message.|
|`Destination unreachable`|This message is sent when a device cannot deliver a packet to its destination.|
|`Redirect`|A router sends this message to inform a device that it should send its packets to a different router.|
|`time exceeded`|This message is sent when a packet has taken too long to reach its destination.|
|`Parameter problem`|This message is sent when there is a problem with a packet's header.|
|`Source quench`|This message is sent when a device receives packets too quickly and cannot keep up. It is used to slow down the flow of packets.|

### Key Aspects of ICMP and Time-To-Live (TTL)

- **Time-To-Live (TTL) Field**:
  - **Function**: Limits the packet's lifetime as it travels through the network.
  - **Purpose**: Prevents packets from circulating indefinitely due to routing loops.
  - **Operation**: 
    - Each router decrements the TTL value by 1.
    - When TTL reaches 0, the router discards the packet and sends an ICMP Time Exceeded message back to the sender.

- **Determining Hops and Distance**:
  - **Usage**: TTL can be used to determine the number of hops a packet has taken.
  - **Example**: A packet with an initial TTL of 10 that takes 5 hops will have a TTL of 5 upon reaching its destination.
  - **Approximate Distance**: 
    - If a ping returns with a TTL of 122, the destination might be 6 hops away from a system with a default TTL of 128 (e.g., Windows).

- **Inferring Operating Systems**:
  - **Default TTL Values**:
    - Windows (2000/XP/2003/Vista/10): 128
    - macOS: 64
    - Linux: 64
    - Solaris: 255
  - **Interpretation**:
    - By examining the TTL value, one can infer the likely operating system of the device.
    - **Example**: A packet with a TTL of 122 suggests a Windows system, initially with a TTL of 128, 6 hops away.
  - **Caveat**: Users can change default TTL values, so this method should not be solely relied upon for definitive OS identification.