# 🌐 Cisco Packet Tracer Networking Labs

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco_Packet_Tracer-v8.0+-005073?style=for-the-badge&logo=cisco&logoColor=white)](https://www.netacad.com/courses/packet-tracer)
[![Repository](https://img.shields.io/badge/Repository-Networking--Labs-blue?style=for-the-badge&logo=github&logoColor=white)](#)
[![Networking](https://img.shields.io/badge/Networking-CCNA_Prep-blue?style=for-the-badge&logo=wireshark&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

A structured collection of hands-on computer networking lab topologies and practical coursework completed using **Cisco Packet Tracer**. This repository covers fundamental to advanced networking concepts including LAN switching, IPv4 subnetting/VLSM, multi-hop and redundant routing, VLAN segmentation, secure SSH remote device administration, and enterprise server integration.

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Summary of Labs](#-summary-of-labs)
- [Detailed Lab Descriptions & Configurations](#-detailed-lab-descriptions--configurations)
  - [1. 1.Basic.pkt — Basic LAN Connectivity](#1-1basicpkt--basic-lan-connectivity)
  - [2. 2.Routing.pkt — Inter-Network Routing](#2-2routingpkt--inter-network-routing)
  - [3. 3.Triangle.pkt — Redundant Triangle Topology](#3-3trianglepkt--redundant-triangle-topology)
  - [4. 4.Routing_CLI.pkt — Cisco IOS CLI Configuration](#4-4routing_clipkt--cisco-ios-cli-configuration)
  - [5. 5.IP-subnetting.pkt — IPv4 Subnetting & VLSM Design](#5-5ip-subnettingpkt--ipv4-subnetting--vlsm-design)
  - [6. 5.Static Routing.pkt — Static & Default Route Engineering](#6-5static-routingpkt--static--default-route-engineering)
  - [7. 6.SSH_config.pkt — Secure Remote Management (SSHv2)](#7-6ssh_configpkt--secure-remote-management-sshv2)
  - [8. 7.VLAN config.pkt — VLANs, 802.1Q Trunking & Inter-VLAN Routing](#8-7vlan-configpkt--vlans-8021q-trunking--inter-vlan-routing)
  - [9. 8.Server Config.pkt — Multi-Service Network Server](#9-8server-configpkt--multi-service-network-server)
  - [10. 9.Vlan with server.pkt — Enterprise Multi-VLAN Architecture with Central Services](#10-9vlan-with-serverpkt--enterprise-multi-vlan-architecture-with-central-services)
- [Prerequisites & Software](#-prerequisites--software)
- [How to Run These Labs](#-how-to-run-these-labs)
- [Individual Git Commit Guide](#-individual-git-commit-guide)
- [Essential Cisco IOS Commands Reference](#-essential-cisco-ios-commands-reference)
- [Testing & Verification](#-testing--verification)
- [License](#-license)

---

## 📌 Overview

**Repository Name:** `Networking-Labs`  
**Simulation Tool:** Cisco Packet Tracer (v8.0+)  
**Scope:** Fundamental to Intermediate Computer Networking (CCNA-level concepts)

This repository serves as a practical, reproducible portfolio of network designs. Each lab focuses on solving specific architectural challenges such as packet collision isolation, secure device management, route optimization across multiple hops, and cross-VLAN communication.

---

## 📊 Summary of Labs

| # | File Name | Primary Topic | Core Protocols & Techniques |
|:---:|:---|:---|:---|
| **01** | [`1.Basic.pkt`](1.Basic.pkt) | **Basic LAN Setup** | Peer-to-peer / Star topology, IPv4 addressing, Layer 2 switching, ICMP (`ping`) |
| **02** | [`2.Routing.pkt`](2.Routing.pkt) | **Inter-Network Routing** | Connecting multiple subnets, default gateways, router interface configuration |
| **03** | [`3.Triangle.pkt`](3.Triangle.pkt) | **Triangle / Redundant Topology** | 3-router meshed design, multi-hop routing, path selection, link redundancy |
| **04** | [`4.Routing_CLI.pkt`](4.Routing_CLI.pkt) | **Router CLI Configuration** | Cisco IOS CLI modes, interface configuration, saving configs to NVRAM |
| **05** | [`5.IP-subnetting.pkt`](5.IP-subnetting.pkt) | **Subnetting & VLSM** | Variable Length Subnet Masking, CIDR notation, broadcast domain conservation |
| **06** | [`5.Static Routing.pkt`](5.Static%20Routing.pkt) | **Static & Default Routing** | `ip route` next-hop / exit-interface, default route forwarding (`0.0.0.0/0`) |
| **07** | [`6.SSH_config.pkt`](6.SSH_config.pkt) | **Secure Remote Administration** | SSHv2, RSA key generation, local authentication, VTY line security |
| **08** | [`7.VLAN config.pkt`](7.VLAN%20config.pkt) | **VLANs & 802.1Q Trunking** | Layer 2 broadcast segmentation, 802.1Q trunks, Router-on-a-Stick (sub-interfaces) |
| **09** | [`8.Server Config.pkt`](8.Server%20Config.pkt) | **Network Infrastructure Services** | DHCP pool distribution, DNS name resolution, HTTP/Web server hosting |
| **10** | [`9.Vlan with server.pkt`](9.Vlan%20with%20server.pkt) | **Multi-VLAN with Central Services** | Inter-VLAN routing, DHCP Relay (`ip helper-address`), central DNS/Web access |

---

## 🔬 Detailed Lab Descriptions & Configurations

### 1. `1.Basic.pkt` — Basic LAN Connectivity
- **Objective:** Establish physical and logical communication between multiple host endpoints within a single local area network (LAN).
- **Topology & Design:**
  - Client workstations (PCs/Laptops) interconnected through a centralized Layer 2 Cisco Catalyst switch using standard straight-through Ethernet patch cables.
  - Hosts reside within the same IPv4 network space and broadcast domain.
- **Key Concepts:**
  - IPv4 static host address and subnet mask assignment.
  - Broadcast domain fundamentals and Layer 2 frame forwarding using MAC address tables.
  - Verification using ICMP Echo Request/Reply (`ping`) and ARP inspection.

---

### 2. `2.Routing.pkt` — Inter-Network Routing
- **Objective:** Route packets between distinct local area networks located on separate IP subnets.
- **Topology & Design:**
  - Two or more LAN segments connected to independent FastEthernet / GigabitEthernet interfaces on a Cisco router.
  - Workstations on each LAN configured with their respective router interface IP as their Default Gateway.
- **Key Concepts:**
  - Default Gateway operation: how end devices forward traffic destined outside their local subnet.
  - Router interface configuration (`ip address`, `no shutdown`).
  - Layer 3 packet inspection and routing table lookups.

---

### 3. `3.Triangle.pkt` — Redundant Triangle Topology
- **Objective:** Construct a resilient, 3-router mesh topology to evaluate path redundancy, failover, and multi-hop forwarding.
- **Topology & Design:**
  - Three Cisco routers interconnected in a triangular arrangement via Serial (WAN) or GigabitEthernet links.
  - Each router services its own local LAN while maintaining alternate routes to reach remote LANs.
- **Key Concepts:**
  - Redundant link architectures and loop avoidance.
  - Multi-hop route convergence and metric evaluation.
  - Packet path tracing (`traceroute`) and testing link failure recovery in Simulation Mode.

---

### 4. `4.Routing_CLI.pkt` — Cisco IOS CLI Configuration
- **Objective:** Configure, secure, and administer router settings entirely through the Cisco IOS Command-Line Interface (CLI).
- **Topology & Design:**
  - Cisco Router accessed via console/terminal simulation.
  - Clean setup from factory default to fully configured and operational state.
- **Key Concepts:**
  - Navigating IOS execution hierarchy: User EXEC (`>`), Privileged EXEC (`#`), Global Configuration (`(config)#`), and Interface Configuration (`(config-if)#`).
  - Interface addressing, clock rate settings (for serial interfaces), and link activation.
  - Persisting running configuration to NVRAM (`copy running-config startup-config`).

---

### 5. `5.IP-subnetting.pkt` — IPv4 Subnetting & VLSM Design
- **Objective:** Divide a given network address block into multiple variable-sized subnets tailored to department-specific host requirements.
- **Topology & Design:**
  - Multi-department enterprise structure (e.g., Administration, Engineering, Guest).
  - Allocation of distinct subnet blocks derived through Variable Length Subnet Masking (VLSM).
- **Key Concepts:**
  - CIDR prefix notation (`/24`, `/25`, `/26`, `/28`, etc.) and subnet calculation.
  - Calculating Network ID, First Usable Host, Last Usable Host, and Broadcast Address.
  - Eliminating address wastage while preventing overlapping subnets.

---

### 6. `5.Static Routing.pkt` — Static & Default Route Engineering
- **Objective:** Program deterministic routing paths across multi-router segments using manual route definitions.
- **Topology & Design:**
  - Multi-router backbone connecting remote LANs without dynamic routing overhead.
- **Key Configuration Highlights:**
  ```cisco
  // Static Route to remote subnet:
  ip route 192.168.3.0 255.255.255.0 10.0.0.2

  // Default Route (Gateway of Last Resort):
  ip route 0.0.0.0 0.0.0.0 10.0.0.2
  ```
- **Key Concepts:**
  - Next-hop IP addressing vs. exit-interface syntax.
  - Default route injection for unknown destinations.
  - Routing table inspection (`show ip route`) identifying static (`S`) and candidate default (`S*`) entries.

---

### 7. `6.SSH_config.pkt` — Secure Remote Management (SSHv2)
- **Objective:** Harden network appliances by replacing unencrypted Telnet with encrypted Secure Shell (SSH version 2) remote terminal management.
- **Topology & Design:**
  - Client workstation connected via switch/network to manage a remote Cisco router.
- **Key Configuration Highlights:**
  ```cisco
  hostname R1
  ip domain-name lab.local
  crypto key generate rsa modulus 1024
  username admin privilege 15 secret Admin@123
  ip ssh version 2
  line vty 0 4
   login local
   transport input ssh
  ```
- **Key Concepts:**
  - Asymmetric cryptographic key generation (RSA).
  - Securing Virtual Teletype (`vty`) lines and blocking insecure plaintext transmission.
  - Role-based privilege access and encrypted secret storage.

---

### 8. `7.VLAN config.pkt` — VLANs, 802.1Q Trunking & Inter-VLAN Routing
- **Objective:** Partition physical switch hardware into isolated logical broadcast domains (VLANs) and route between them using Router-on-a-Stick.
- **Topology & Design:**
  - Cisco Catalyst 2960 switch segmented into multiple VLANs (e.g., VLAN 10, VLAN 20).
  - An 802.1Q trunk link carrying tagged frames to a Cisco router sub-interface gateway.
- **Key Configuration Highlights:**
  ```cisco
  // Switch: VLAN and Trunk
  Switch(config)# vlan 10
  Switch(config-vlan)# name Faculty
  Switch(config)# interface f0/1
  Switch(config-if)# switchport mode access
  Switch(config-if)# switchport access vlan 10
  Switch(config)# interface f0/24
  Switch(config-if)# switchport mode trunk

  // Router: Sub-interface Inter-VLAN Routing
  Router(config)# interface g0/0/0.10
  Router(config-subif)# encapsulation dot1Q 10
  Router(config-subif)# ip address 192.168.10.1 255.255.255.0
  ```
- **Key Concepts:**
  - Layer 2 traffic isolation and security segmentation.
  - IEEE 802.1Q frame tagging on trunk links.
  - Sub-interface routing with encapsulation binding.

---

### 9. `8.Server Config.pkt` — Multi-Service Network Server
- **Objective:** Deploy and integrate central network infrastructure services using a Cisco Packet Tracer generic server.
- **Topology & Design:**
  - Client workstations connected to a server running concurrent services over a unified LAN.
- **Configured Services:**
  - **DHCP Service:** Automated dynamic IP address, subnet mask, default gateway, and DNS server lease distribution to clients.
  - **DNS Service:** Resolving hostnames/domain names (e.g., `www.ciscotest.local`) to corresponding IP addresses.
  - **HTTP/Web Service:** Hosting custom HTML pages served across the intranet to client web browsers.
- **Key Concepts:**
  - DORA process (Discover, Offer, Request, Acknowledge) in DHCP.
  - Name resolution flow and HTTP client-server request/response verification.

---

### 10. `9.Vlan with server.pkt` — Enterprise Multi-VLAN Architecture with Central Services
- **Objective:** Build a complete enterprise campus topology where clients distributed across isolated VLANs seamlessly access centralized server farm resources.
- **Topology & Design:**
  - Multiple segregated client VLANs spanning switches.
  - Dedicated Server VLAN housing DHCP, DNS, and Web servers.
  - Router configured with DHCP Relay (`ip helper-address`) to forward broadcast discovery requests across subnets.
- **Key Configuration Highlights:**
  ```cisco
  Router(config)# interface g0/0/0.10
  Router(config-subif)# encapsulation dot1Q 10
  Router(config-subif)# ip address 192.168.10.1 255.255.255.0
  Router(config-subif)# ip helper-address 192.168.100.2  // Central DHCP Server IP
  ```
- **Key Concepts:**
  - Converting client DHCP broadcast requests into unicast packets routed to the server farm.
  - Centralized IP pool management across distinct subnets.
  - Cross-VLAN client-server service delivery with full routing security.

---

## 💻 Prerequisites & Software

- **Cisco Packet Tracer:** Version **8.0 or higher** (Download from [Cisco Networking Academy](https://www.netacad.com/courses/packet-tracer)).
- **Operating System:** Windows 10/11, macOS, or Ubuntu Linux.
- **Foundational Knowledge:** Basic understanding of the OSI/TCP-IP models, IPv4 addressing, and standard Cisco IOS commands.

---

## 🚀 How to Run These Labs

1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-username>/Networking-Labs.git
   cd Networking-Labs
   ```
2. **Launch Cisco Packet Tracer.**
3. Click **File** > **Open** (`Ctrl + O`), browse to this directory, and select any `.pkt` file.
4. Use **Simulation Mode** (bottom-right toggle) to view packet encapsulation and inspect PDUs layer-by-layer.
5. Use the device **CLI tabs** to inspect configurations and execute verification commands.

---

## 📝 Individual Git Commit Guide

If you wish to commit each lab file manually with a dedicated, professional commit message, follow this sequence in your terminal:

```bash
# 0. Initialize repository and add documentation / configuration files
git init
git add .gitignore
git commit -m "chore: add .gitignore for OS and Packet Tracer artifacts"

git add LICENSE
git commit -m "docs: add MIT License"

git add README.md
git commit -m "docs: add comprehensive README with serial lab breakdown and guides"

# 01. Lab 1
git add "1.Basic.pkt"
git commit -m "feat(lab-01): add basic LAN connectivity and host ping topology"

# 02. Lab 2
git add "2.Routing.pkt"
git commit -m "feat(lab-02): add multi-subnet inter-network routing topology"

# 03. Lab 3
git add "3.Triangle.pkt"
git commit -m "feat(lab-03): add redundant 3-router triangle mesh routing topology"

# 04. Lab 4
git add "4.Routing_CLI.pkt"
git commit -m "feat(lab-04): add Cisco IOS router CLI configuration lab"

# 05. Lab 5
git add "5.IP-subnetting.pkt"
git commit -m "feat(lab-05): add IPv4 subnetting and VLSM address scheme lab"

# 06. Lab 6
git add "5.Static Routing.pkt"
git commit -m "feat(lab-06): add static route and default gateway configuration lab"

# 07. Lab 7
git add "6.SSH_config.pkt"
git commit -m "feat(lab-07): add secure remote management with SSHv2 and RSA keys"

# 08. Lab 8
git add "7.VLAN config.pkt"
git commit -m "feat(lab-08): add VLAN segmentation, 802.1Q trunking, and Router-on-a-Stick"

# 09. Lab 9
git add "8.Server Config.pkt"
git commit -m "feat(lab-09): add multi-service server deployment for DHCP, DNS, and HTTP"

# 10. Lab 10
git add "9.Vlan with server.pkt"
git commit -m "feat(lab-10): add enterprise multi-VLAN topology with DHCP helper and central services"
```

### Linking and Pushing to GitHub:
```bash
# Rename branch to main
git branch -M main

# Add your GitHub remote (replace <your-username> with your GitHub account)
git remote add origin https://github.com/<your-username>/Networking-Labs.git

# Push all commits to GitHub
git push -u origin main
```

---

## 🛠️ Essential Cisco IOS Commands Reference

| Task | Command Syntax |
|:---|:---|
| **Enter Privileged EXEC** | `enable` |
| **Enter Global Configuration** | `configure terminal` |
| **Assign Hostname** | `hostname <device-name>` |
| **Assign Interface IP** | `interface <interface-id>` <br> `ip address <ip> <subnet-mask>` <br> `no shutdown` |
| **Configure Static Route** | `ip route <dest-network> <subnet-mask> <next-hop-ip>` |
| **Configure Default Route** | `ip route 0.0.0.0 0.0.0.0 <next-hop-ip>` |
| **Create VLAN** | `vlan <vlan-id>` <br> `name <vlan-name>` |
| **Configure Access Port** | `switchport mode access` <br> `switchport access vlan <vlan-id>` |
| **Configure Trunk Port** | `switchport mode trunk` |
| **Configure Sub-Interface** | `interface <int>.<sub-id>` <br> `encapsulation dot1Q <vlan-id>` <br> `ip address <ip> <subnet-mask>` |
| **Configure DHCP Helper** | `ip helper-address <server-ip>` |
| **Save Running Configuration** | `copy running-config startup-config` (or `write memory`) |

---

## 🔍 Testing & Verification

| Verification Goal | Command |
|:---|:---|
| Check all interface IP addresses & Up/Down status | `show ip interface brief` |
| View the active routing table | `show ip route` |
| Verify configured VLANs and assigned ports | `show vlan brief` |
| Check trunk link operational state and allowed VLANs | `show interfaces trunk` |
| Verify active SSH session status | `show ip ssh` |
| Verify running configuration in memory | `show running-config` |
| Test end-to-end connectivity | `ping <destination-ip>` |
| Trace hop-by-hop path across routers | `traceroute <destination-ip>` |

---

## 📄 License

This repository is licensed under the [MIT License](LICENSE). You are free to reference, study, and expand these network lab configurations for educational purposes.
