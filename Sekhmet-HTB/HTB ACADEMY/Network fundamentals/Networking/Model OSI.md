
The `OSI` model, often referred to as `ISO/OSI` layer model, is a reference model that can be used to describe and define the communication between systems. The reference model has `seven` individual layers, each with clearly separated tasks.

The term `OSI` stands for `Open Systems Interconnection` model, published by the `International Telecommunication Union` (`ITU`) and the `International Organization for Standardization` (`ISO`). Therefore, the `OSI` model is often referred to as the `ISO/OSI` layer model.

|**Layer**|**Function**|
|---|---|
|`7.Application`|Among other things, this layer controls the input and output of data and provides the application functions.|
|`6.Presentation`|The presentation layer's task is to transfer the system-dependent presentation of data into a form independent of the application.|
|`5.Session`|The session layer controls the logical connection between two systems and prevents, for example, connection breakdowns or other problems.|
|`4.Transport`|Layer 4 is used for end-to-end control of the transferred data. The Transport Layer can detect and avoid congestion situations and segment data streams.|
|`3.Network`|On the networking layer, connections are established in circuit-switched networks, and data packets are forwarded in packet-switched networks. Data is transmitted over the entire network from the sender to the receiver.|
|`2.Data Link`|The central task of layer 2 is to enable reliable and error-free transmissions on the respective medium. For this purpose, the bitstreams from layer 1 are divided into blocks or frames.|
|`1.Physical`|The transmission techniques used are, for example, electrical signals, optical signals, or electromagnetic waves. Through layer 1, the transmission takes place on wired or wireless transmission lines.|


- **Layer Functions**:
  - **Layers 2-4**: Transport-oriented (e.g., data link, network, transport layers).
  - **Layers 5-7**: Application-oriented (e.g., session, presentation, application layers).

- **Layer Interactions**:
  - Each layer performs specific tasks and uses services from the layer below while offering services to the layer above.
  - Communication involves all seven layers of the OSI model being processed at least twice (once by the sender and once by the receiver).

- **Data Transmission**:
  - **Sender**: Processes the packet from layer 7 down to layer 1.
  - **Receiver**: Unpacks the packet from layer 1 up to layer 7.

- **Purpose**: Ensures the communication's security, reliability, and performance through tasks performed in each layer.