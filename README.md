# MPLS VPN Network Project – GNS3

## 📌 Project Overview

This project is a complete **MPLS Layer 3 VPN network simulation** built with **GNS3**.  
It represents a professional enterprise network where multiple customer sites are interconnected through an MPLS backbone using routing, switching, VLANs, DHCP, HSRP, OSPF, and VRF concepts.

The goal of this project is to design, configure, test, and document a realistic ISP/customer network infrastructure similar to what can be found in enterprise and service provider environments.

---

## 🎯 Project Objectives

The main objectives of this project are:

- Build a functional MPLS VPN topology using GNS3
- Configure a provider backbone with PE and P routers
- Create customer VPN isolation using VRF
- Connect multiple customer sites through the MPLS network
- Configure VLANs for segmentation
- Configure DHCP for automatic IP addressing
- Configure OSPF routing between sites
- Implement HSRP for gateway redundancy
- Test communication between remote branches
- Document the full network design and configuration

---

## 🧠 Skills Demonstrated

This project demonstrates knowledge in:

- Network design and architecture
- MPLS VPN concepts
- VRF configuration
- OSPF routing
- VLANs and trunking
- DHCP configuration
- HSRP redundancy
- Cisco router and switch configuration
- GNS3 network simulation
- Troubleshooting routing and switching problems
- Technical documentation

---

## 🛠️ Technologies and Tools Used

- **GNS3**
- **Cisco IOS**
- **Cisco routers**
- **Cisco switches**
- **VPCS**
- **MPLS**
- **VRF**
- **OSPF**
- **VLAN**
- **DHCP**
- **HSRP**

---

## 🏗️ Network Architecture

The topology contains:

### Provider Network

- PE1
- PE2
- P1
- P2

### Customer Sites

- Siège 1
- Branch 1
- Siège 2
- Branch 2

### Main Design Idea

The customer sites are connected through an MPLS provider backbone.  
VRF is used to isolate the customer routing table from the provider network.  
OSPF is used for routing between customer sites and inside the customer network.

---

## 🌐 IP Addressing Plan

### MPLS Backbone

| Link | Network |
|---|---|
| PE1 - P1 | 10.1.1.0/30 |
| PE1 - P2 | 10.1.1.4/30 |
| PE2 - P2 | 10.1.1.8/30 |
| PE2 - P1 | 10.1.1.12/30 |
| P1 - P2 | 10.1.1.20/30 |

### Loopbacks

| Device | Loopback |
|---|---|
| PE1 | 1.1.1.1 |
| PE2 | 2.2.2.2 |
| P1 | 3.3.3.3 |
| P2 | 4.4.4.4 |

---

## 🧩 VLAN Design

### Siège

| VLAN | Name | Network |
|---|---|---|
| VLAN 10 | ISG1 | 172.16.210.0/24 |
| VLAN 15 | ISG2 | 172.16.215.0/24 |
| VLAN 20 | Management | 172.16.220.0/24 |

### Branch 1

| VLAN | Name | Network |
|---|---|---|
| VLAN 201 | Management | 172.16.201.0/24 |
| VLAN 202 | Data | 172.16.202.0/24 |

### Branch 2

| VLAN | Name | Network |
|---|---|---|
| VLAN 203 | Management | 172.16.203.0/24 |
| VLAN 204 | Data | 172.16.204.0/24 |

---

## 🔐 VRF Configuration

A VRF named `VPN_CYBER` is used to separate the customer routes from the provider network.

| Parameter | Value |
|---|---|
| VRF Name | VPN_CYBER |
| RD | 300 |
| Route Target Import | 300:1 |
| Route Target Export | 300:1 |

---

## 🔁 Routing

The project uses **OSPF** for dynamic routing.

### OSPF Areas

| Site | OSPF Area |
|---|---|
| Siège | Area 11 |
| Branch 1 | Area 12 |
| Branch 2 | Area 22 |

Route redistribution is configured where needed to allow communication between different parts of the network.

---

## ✅ Features Implemented

- MPLS backbone configuration
- PE/P router setup
- VRF creation
- Route target import/export
- Customer site interconnection
- VLAN segmentation
- Trunk configuration
- DHCP services
- OSPF routing
- HSRP gateway redundancy
- End-to-end connectivity tests
- Troubleshooting and validation

---

## 🧪 Testing and Validation

The network was tested using:

- `ping`
- `traceroute`
- `show ip route`
- `show ip ospf neighbor`
- `show vlan brief`
- `show standby brief`
- `show ip dhcp binding`
- `show ip vrf`
- `show ip route vrf VPN_CYBER`

Successful tests include:

- DHCP address assignment for client PCs
- Inter-VLAN routing
- OSPF neighbor establishment
- Remote site connectivity
- Communication between Branch 1 and Branch 2
- Route propagation through the MPLS VPN

---

## 📸 Screenshots and Documentation

This repository contains project documentation, screenshots, configuration files, and additional details explaining the design and implementation.

---

## ⚠️ Notes

This project is for academic and learning purposes.  
It does not include private credentials, licenses, Cisco IOS images, or virtual machine disk files.

---

## 📚 What I Learned

Through this project, I improved my understanding of:

- How MPLS VPN networks are designed
- How providers isolate customer traffic using VRF
- How routing works between provider and customer networks
- How VLANs organize enterprise networks
- How HSRP improves availability
- How to troubleshoot real networking problems step by step
- How to document a technical infrastructure project professionally

---

## 🚀 Future Improvements

Possible future improvements:

- Add BGP between PE routers
- Add more customer sites
- Add firewall security rules
- Add monitoring with SNMP or Zabbix
- Automate configuration backup
- Add network diagrams
- Add full configuration files for every router and switch
- Create a professional PDF report

---

## 👤 Author

**Abdurrahmen Neji**  
Master SSI Student  
Network, Cybersecurity, and Software Development Enthusiast

GitHub: [abdurrahmenNeji](https://github.com/abdurrahmenNeji)
