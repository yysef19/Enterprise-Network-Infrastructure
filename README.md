# Enterprise-Network-Infrastructure
![Cisco](https://img.shields.io/badge/Cisco-Packet_Tracer-blue?logo=cisco) ![Routing](https://img.shields.io/badge/Routing-OSPF%20%7C%20Static-success) ![Switching](https://img.shields.io/badge/Switching-VLAN%20%7C%20STP%20%7C%20EtherChannel-orange) ![Security](https://img.shields.io/badge/Security-Port_Security%20%7C%20DAI%20%7C%20DHCP_Snooping-red)

![Enterprise Campus Network Topology](Architecture%20&%20Topology/Network-Infrastructure.jpg)

## 📌 Project Overview

A fully documented, enterprise-grade, two-office campus network designed and simulated in Cisco Packet Tracer. **Built upon Jeremy’s IT Lab CCNA Mega Lab**, this project expands on the original lab with a focus on enterprise network architecture, high availability, centralized wireless management, and layered security.

It features a **3-Tier Hierarchical Architecture** with a redundant routed core, high-availability gateways, and edge security mechanisms across **26 network devices**.


---

## 📂 Repository Structure

Navigate through the repository to explore the engineering logic, documentation, and raw configurations:

| Directory | Contents & Purpose |
| :--- | :--- |
| 🏗️ **[`Architecture & Topology/`](Architecture%20&%20Topology/)** | The "Brain" of the project. Contains the Packet Tracer `.pkt` file, the topology map, and `Architecture.md` which explains the **Engineering Decisions** and end-to-end traffic flows. |
| 📄 **[`Network Documentation/`](Network%20Documentation/)** | The "Hard Facts". Contains clean markdown tables referencing VLAN schemes, HSRP Virtual IPs, Point-to-Point routed links (/30), and Loopbacks. |
| ⚙️ **[`Device Configurations/`](Device%20Configurations/)** | The "Code". Contains the extracted `Running-Config` `.txt` files for every router and switch in the network. |
| 🧪 **[`Testing & Verification/`](Testing%20&%20Verification/)** | The "Proof". Contains screenshots and logs verifying network convergence, failover scenarios, and end-to-end reachability. |

---

## 🏗️ Architecture at a Glance (3-Tier Model)

- **Edge (R1):** The single boundary to the outside world. Handles NAT/PAT, serves as the central DHCP and NTP server, and manages **Dual-ISP failover** using floating static routes.
- **Core (CSW1, CSW2):** A high-speed, purely Layer 3 routed backbone. It connects Office A, Office B, and R1 via **Routed EtherChannels**, utilizing OSPF Equal-Cost Multipath (ECMP).
- **Distribution (DSW Pairs):** The Layer 2 / Layer 3 boundary. Handles inter-VLAN routing (SVIs), First-Hop Redundancy (**HSRPv2**), and acts as the Spanning Tree Root Bridges.
- **Access (ASW Layer):** Purely Layer 2 switches connecting end-users, IP Phones, APs, and Servers. Enforces strict edge security.

---

## 🚀 Core Technologies Implemented

### 🔄 Switching & Layer 2
- **VLAN Segmentation:** Dedicated VLANs for PCs, Phones, Servers, Wi-Fi, and Management.
- **EtherChannel:** Layer 2 link aggregation using both PAgP and LACP.
- **Spanning Tree:** Rapid PVST+ with engineered Root Bridge priorities aligned with HSRP active roles.
- **Edge Tuning:** PortFast and BPDU Guard on all host-facing ports.

### 🛣️ Routing & High Availability
- **Dynamic Routing:** OSPF Area 0 with passive interfaces and Loopback Router IDs.
- **First-Hop Redundancy:** HSRPv2 with distributed Active/Standby roles for per-VLAN load balancing.
- **Failover:** Dual-ISP default routes with floating static failover (Administrative Distance tuning).

### 🛡️ Network Security
- **Access Layer Defense:** Port Security (Sticky MAC), DHCP Snooping, and Dynamic ARP Inspection (DAI).
- **Traffic Filtering:** Extended and Standard ACLs to restrict inter-VLAN traffic and secure VTY lines.
- **Device Hardening:** DTP disabled, unused native VLANs (1000), unused ports shut down, and SSHv2 only.

### 📡 Wireless & Services
- **Wireless:** Centralized WLC (Split-MAC architecture) managing Lightweight APs via CAPWAP tunnels (WPA2-Enterprise/PSK).
- **Network Services:** DHCP (with Relay Agents), DNS, NTP, Syslog, and Static NAT / Dynamic PAT.

