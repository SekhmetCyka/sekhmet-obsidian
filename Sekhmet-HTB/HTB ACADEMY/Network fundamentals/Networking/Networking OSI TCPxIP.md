
Two networking models describe the communication and transfer of data from one host to another, called `ISO/OSI model` and the `TCP/IP model`. This is a simplified representation of the so-called `layers` representing transferred Bits in readable contents for us.


![[Pasted image 20240725201420.png]]

## ISO/OSI vs. TCP/IP

`TCP/IP` is a communication protocol that allows hosts to connect to the Internet. It refers to the `Transmission Control Protocol` used in and by applications on the Internet. In contrast to `OSI`, it allows a lightening of the rules that must be followed, provided that general guidelines are followed.

`OSI`, on the other hand, is a communication gateway between the network and end-users. The OSI model is usually referred to as the reference model because it is newer and more widely used. It is also known for its strict protocol and limitations.

## Packet

- **Layered System**: Devices exchange data in a format called a protocol data unit (PDU) at each layer.
- **Data Transfer**:
  - When browsing a website, the remote server sends data to the application layer.
  - The data is processed layer by layer, each layer performing its specific functions.
  - The data travels through the network's physical layer to reach the destination server or device.
  - The data is routed back through the layers at the destination, with each layer performing its operations until the receiving software utilizes the data.

![[Pasted image 20240725202124.png]]

During the transmission, each layer adds a `header` to the `PDU` from the upper layer, which controls and identifies the packet. This process is called `encapsulation`. The header and the data together form the PDU for the next layer. The process continues to the `Physical Layer` or `Network Layer`, where the data is transmitted to the receiver. The receiver reverses the process and unpacks the data on each layer with the header information. After that, the application finally uses the data. This process continues until all data has been sent and received.

![[Pasted image 20240725202256.png]]