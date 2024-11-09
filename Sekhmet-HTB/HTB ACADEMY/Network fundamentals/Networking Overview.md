A network allows two computers to communicate, utilizing various topologies (mesh/tree/star), mediums (ethernet/fiber/coax/wireless), and protocols (TCP/UDP/IPX). Understanding networking is crucial for security professionals because network failures can be silent and go unnoticed.

Setting up a large, flat network is straightforward and reliable operationally, but it lacks security. By creating smaller networks and using Access Control Lists (ACLs), additional defense layers are added, making it harder for attackers to move quickly and undetected.

### Examples:

1. **Smaller Networks with ACLs**: Like a fence around a property with specific entry points, suspicious activities (e.g., printer network accessing servers over HTTP) can be detected quickly.
2. **Mapping and Documenting Networks**: Like placing lights around a property, this ensures visibility of all activities, such as why the printer network is accessing the internet.
3. **Intrusion Detection Systems**: Like bushes around windows deterring entry, IDS tools like Suricata or Snort deter network scans (e.g., port scans originating from the printer network).

In a flat network, it's challenging to impose restrictions, such as preventing a printer from performing unauthorized actions.

### Story of a Pentester's Oversight:

Penetration testers often use a /24 subnet, allowing all computers with the same first three IP address octets to communicate. However, setting the subnet mask to /25 divides the range, restricting communication to within each half. Misunderstanding this can lead to errors, like missing a Domain Controller on a different network. For example, with:

- Server Gateway: 10.20.0.1/25
- Domain Controller: 10.20.0.10/25
- Client Gateway: 10.20.0.129/25
- Client Workstation: 10.20.0.200/25
- Pentester IP: 10.20.0.252/24 (Gateway set to 10.20.0.1)

The Pentester interacted only with Client Workstations and missed high-value targets due to not understanding the network segmentation.