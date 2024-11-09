
### Network Layer (Layer 3) of OSI:

- **Functions**:
  - **Logical Addressing**: Identifies individual network nodes.
  - **Routing**: Transfers data packets from node to node until they reach the target.
  - **Data Flow Control**: Manages data transmission efficiency.
  - **Connection Management**: Sets up and clears connection channels.

- **Process**:
  - **Address Evaluation**: Determines packet destinations based on addresses.
  - **Routing Tables**: Constructs and uses routing tables for packet forwarding.
  - **Node-to-Node Transfer**: Moves packets from one node to the next, not processing data from higher layers.

- **Common Protocols**:
  - **IPv4 / IPv6**
  - **IPsec**
  - **ICMP**
  - **IGMP**
  - **RIP**
  - **OSPF**

- **Packet Routing**:
  - **Within or Outside Subnets**: Ensures packets reach destinations regardless of subnet differences.
  - **Intermediate Nodes**: Forwards packets through routers to reach the final destination.
  - **Layer Transparency**: Protocols are independent of layers above or below.

- **Key Points**:
  - Manages the routing of packets.
  - Handles addressing schemes and routing across different subnets.
  - Ensures packets reach intermediate nodes when direct communication isn't possible.