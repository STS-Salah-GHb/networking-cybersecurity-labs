# OSPF Multi-Area Routing Lab

## 1. Overview

This lab demonstrates the configuration and verification of OSPF (Open Shortest Path First) in a multi-area network using Cisco Packet Tracer.

The topology consists of five routers, four OSPF areas, and four LANs connected to PCs.

## 2. Objectives

- Configure OSPF across multiple areas.
- Establish OSPF neighbor adjacencies.
- Advertise LAN and inter-router networks.
- Verify learned routes using the routing table.
- Understand OSPF neighbor states and route selection.

## 3. Network Topology

- R2: Central router connected to the four other routers.
- R3: Area 0.
- R5: Area 1.
- R4: Area 2.
- R1: Area 3.

**Technologies:** Cisco IOS, OSPF, IPv4, routing tables, and Cisco Packet Tracer.

## 4. IP Addressing

| Network | Purpose |
|---|---|
| 192.0.0.0/24 | R4 LAN |
| 193.0.0.0/24 | R1 LAN |
| 194.0.0.0/24 | R3 LAN |
| 195.0.0.0/24 | R5 LAN |
| 10.0.0.0/24 | R2–R4 link |
| 20.0.0.0/24 | R2–R1 link |
| 30.0.0.0/24 | R2–R3 link |
| 40.0.0.0/24 | R2–R5 link |

## 5. Verification Commands

```text
show ip interface brief
show ip ospf neighbor
show ip route ospf
show ip protocols
```

## 6. Results

### OSPF Neighbor Adjacencies

On R2, four OSPF neighbors reached the FULL state:

- R4 — 10.0.0.1
- R1 — 20.0.0.2
- R3 — 30.0.0.2
- R5 — 40.0.0.2

### OSPF Routing Table

R2 successfully learned the following remote LAN routes:

```text
O 192.0.0.0 via 10.0.0.1
O 193.0.0.0 via 20.0.0.2
O 194.0.0.0 via 30.0.0.2
O 195.0.0.0 via 40.0.0.2
```

The routing table identifies these routes with the code `O`, indicating that they were learned through OSPF.

## 7. What I Learned

- How OSPF establishes neighbor relationships.
- How to verify OSPF adjacency states.
- How a router learns remote networks dynamically.
- How to troubleshoot routing using Cisco IOS commands.
- How to build and analyze a multi-router topology.

## 8. Conclusion

The verification results confirm that R2 has established four OSPF neighbor adjacencies and learned four remote LAN routes.

End-to-end connectivity should also be tested with ping between PCs to verify complete network communication.

## 9. Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI
- OSPF



<img width="1920" height="1280" alt="ospf_topology" src="https://github.com/user-attachments/assets/007f0a44-ce92-4451-8f6e-6ebb54490f05" />

<img width="853" height="130" alt="ospf_neighbor" src="https://github.com/user-attachments/assets/3a629e0c-cc26-4bd1-9509-73fc6524ee57" />

<img width="823" height="103" alt="route_ospf_" src="https://github.com/user-attachments/assets/72308b8f-5a16-4010-9c5c-3f4966e3ff57" />

<img width="833" height="297" alt="image" src="https://github.com/user-attachments/assets/20db8f2a-3f84-42a1-843d-60384f4bfaa9" />

<img width="823" height="103" alt="route_ospf_" src="https://github.com/user-attachments/assets/5ae0db78-6c6b-4f44-bc54-9a9aad1e7c2e" />

<img width="780" height="1022" alt="ospf_ping" src="https://github.com/user-attachments/assets/8b371672-187b-4c28-a3c3-92c019634a53" />

<img width="872" height="956" alt="protocols" src="https://github.com/user-attachments/assets/ae34b271-8d5a-416f-91d8-3ae71bf17905" />

<img width="892" height="1007" alt="ping_ospf_pcs" src="https://github.com/user-attachments/assets/144aa9dd-7700-4b61-a4ac-fec1e1a2094e" />

<img width="827" height="117" alt="R4_ospf_neighbor" src="https://github.com/user-attachments/assets/16d77f9d-4fe4-4242-b7fd-f40989ec1178" />

<img width="813" height="140" alt="route_ospf" src="https://github.com/user-attachments/assets/d253ee20-2ea9-4ae0-839d-aa494208ad19" />
