# Networks Simulation

## Overview
This repository contains Cisco Packet Tracer simulations for computer networks laboratory exercises (Labs 3 and 4). Lab 3 (Module 1) focuses on basic network setup with hubs, switches, PCs, IP assignment, and connectivity testing using ping in realtime and simulation modes. Lab 4 (Module 2) involves advanced topology design with multiple routers (R1-R4), switches, PCs, and an Eagle Server, including VLSM IP addressing, WAN/LAN configurations, and routing verification. The simulations demonstrate key networking concepts like ARP, ICMP, Spanning Tree, and routing protocols.

## Technologies
- **Simulation Tool**: Cisco Packet Tracer (latest stable version recommended)
- **Protocols**: IP, ICMP, ARP, RIP (for dynamic routing in Lab 4 Part B)
- **Networking Concepts**: VLSM subnetting, static routing, WAN/LAN links, interface configuration

## Features
- Basic network with hub-switch interconnection, IP assignment (192.168.1.0/24), and ping testing (Lab 3).
- Multi-router topology (R1-R4) with VLSM from 172.16.18.0/22 for LANs (110, 20, 32, 62 hosts) and 188.15.0.0/27 for WAN links (Lab 4 Part A).
- Advanced setup with ISP routers, web servers, RIP v2 routing, default routes, and full end-to-end connectivity (Lab 4 Part B).
- Simulation mode for packet flow visualization and protocol analysis.

## Installation
1. Download and install Cisco Packet Tracer from [NetAcad](https://www.netacad.com) (requires free registration).
2. Clone the repository:
   ```
   git clone https://github.com/OzzYBcc/networks-simulation.git
   ```
3. Open the `.pkt` files in Packet Tracer.

## Usage
- **Lab 3 (Module 1)**: Open the corresponding `.pkt` file. Assign IPs (e.g., PC0: 192.168.1.2/24), test connectivity with ping in Realtime and Simulation modes. Observe ARP requests and ICMP echoes.
- **Lab 4 Part A (Module 2)**: Open the `.pkt` file. Complete IP addressing per the lab specs (e.g., subnet 172.16.18.0/22 into appropriate sizes), configure router interfaces, and verify pings between all hosts and the Eagle Server.
- **Lab 4 Part B**: Extend the topology with VLSM (e.g., 10.160.0.0/14 for Region 1), configure RIP v2 on routers, add static/default routes, and test full connectivity.
- **Testing**: Use Simple PDU or CLI ping commands to validate. Switch to Simulation mode to inspect packet paths.
- **Example Configuration (Router Interface - Lab 4)**:
  ```bash
  # CLI example for R1 Fa0/0 (assuming subnet 172.16.18.0/23 for 110 hosts)
  enable
  configure terminal
  interface Fa0/0
  ip address 172.16.18.1 255.255.254.0
  no shutdown
  exit
  ```
- **Example Routing (RIP v2 - Lab 4 Part B)**:
  ```bash
  router rip
  version 2
  network 10.160.0.0
  no auto-summary
  ```

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

Potential improvements include adding VLANs, OSPF routing, or ACLs for enhanced simulations.

## License
MIT License