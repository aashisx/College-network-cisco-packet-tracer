# College LAN Network using Cisco Packet Tracer

A multi-department college network designed and implemented using **Cisco Packet Tracer**. The project demonstrates practical networking concepts including VLANs, OSPF dynamic routing, DHCP, DNS, HTTP, and Access Control Lists (ACLs).

## 📌 Project Overview

The network was designed for six areas of a college:

* Administration
* Computer Science
* Management
* Computer Lab
* Library
* Server Room

The network uses six routers and six Cisco 2960 switches. The routers are interconnected in a ring topology, providing multiple paths between different parts of the network.

## 🎯 Objectives

* Design a practical college network topology using Cisco Packet Tracer.
* Configure LAN connectivity for different departments.
* Implement VLANs for logical network segmentation.
* Configure OSPF for dynamic routing.
* Configure routers as DHCP servers.
* Configure DNS and HTTP servers.
* Implement ACL-based traffic restrictions.
* Test and verify network connectivity and services.

## 🛠️ Technologies & Concepts

* Cisco Packet Tracer
* IPv4 Addressing
* LAN
* VLAN
* OSPF
* DHCP
* DNS
* HTTP
* Access Control Lists (ACL)
* Network Troubleshooting & Testing

## 🌐 Network Addressing

| Department / Area | VLAN | Network         | Gateway      |
| ----------------- | ---: | --------------- | ------------ |
| Administration    |   10 | 192.168.10.0/24 | 192.168.10.1 |
| Computer Science  |   20 | 192.168.20.0/24 | 192.168.20.1 |
| Management        |   30 | 192.168.30.0/24 | 192.168.30.1 |
| Computer Lab      |   40 | 192.168.40.0/24 | 192.168.40.1 |
| Library           |   50 | 192.168.50.0/24 | 192.168.50.1 |
| Server Room       |   60 | 192.168.60.0/24 | 192.168.60.1 |

The inter-router connections use `/30` networks for point-to-point links.

## 🔀 VLAN Configuration

Six VLANs were configured:

| VLAN | Name         | Area             |
| ---: | ------------ | ---------------- |
|   10 | ADMIN        | Administration   |
|   20 | CS           | Computer Science |
|   30 | MANAGEMENT   | Management       |
|   40 | COMPUTER_LAB | Computer Lab     |
|   50 | LIBRARY      | Library          |
|   60 | SERVERS      | Server Room      |

VLANs provide logical separation between the different college areas.

## 🔄 OSPF Dynamic Routing

**OSPF Area 0** was configured on all six routers.

Each router advertises its local departmental network and connected inter-router networks. OSPF neighbor relationships and dynamically learned routes were verified during testing.

## 📡 DHCP

The routers were configured as DHCP servers for the departmental LANs.

The PCs automatically receive:

* IP address
* Subnet mask
* Default gateway
* DNS server

The DNS server provided through DHCP is `192.168.60.2`.

## 🌍 DNS & HTTP Server

A dedicated DNS server was configured with:

* **IP:** `192.168.60.2`
* **Domain:** `college.com`

The DNS record resolves `college.com` to the HTTP server at `192.168.60.3`.

The HTTP server hosts the college webpage and can be accessed using:

`http://college.com`

Both DNS resolution and HTTP connectivity were successfully tested from a PC.

## 🔐 Access Control List

An **extended ACL** was configured on the Computer Lab router.

### Security Rule

Traffic from:

`192.168.40.0/24` — Computer Lab

to:

`192.168.10.0/24` — Administration

is **denied**.

Other IP traffic is permitted.

The ACL was applied inbound on the interface connected to the Computer Lab LAN.

## Testing & Verification

The following tests were performed:

* ✅ DHCP address assignment
* ✅ Gateway connectivity
* ✅ Inter-department connectivity
* ✅ OSPF routing
* ✅ DNS resolution
* ✅ HTTP access using `college.com`
* ✅ ACL traffic restriction

The ACL was successfully verified by testing traffic from a Computer Lab PC toward the Administration network.

## 📁 Project Files

```text
college-lan-network-cisco-packet-tracer/
│
├── README.md
├── college-network.pkt
├── College-network-report.pdf
│
└── Screenshots/
    ├── ACL_test.png
    ├── DHCP_test1.png
    ├── DHCP_test2.png
    ├── DHCP_test3.png
    ├── DNS_HTTP_test.png
    ├── OSPF_neighbour1.png
    ├── OSPF_neighbour2.png
    ├── OSPF_routing-table_sample.png
    ├── Topology.png
    ├── Vlan_computer-lab.png
    ├── Vlan_config_CS.png
    ├── Vlan_config_Library.png
    ├── Vlan_config_Mngmt.png
    ├── Vlan_config_server.png
    └── Vlan_configuration_admin.png
```

##  How to Run?

1. Install **Cisco Packet Tracer**.
2. Clone or download this repository.
3. Open `college-network.pkt` in Cisco Packet Tracer.
4. Inspect the router and switch configurations.
5. Test DHCP, routing, DNS, HTTP, and ACL functionality.

## 👨‍💻 Project


**Project:** Design and Implementation of a College Network Using Cisco Packet Tracer

---

### 📚 Documentation

The complete project report is available in the College-network-report.pdf.
