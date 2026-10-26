# 🌐 Cisco Packet Tracer - DHCP & Static IP Lab

A practical networking lab demonstrating dynamic IP allocation via DHCP alongside static IP configuration for network peripherals (Printer) to prevent IP conflicts.

---

## 📁 Repository Structure

* **`assets/`** - Contains network topology diagrams, configuration screenshots, and ping verification tests.
* **`labs/`** - Contains the executable Packet Tracer file (`DHCP2.pkt`).

---

##  Network Topology

![Network Topology](assets/topology.png)

* **Sv-DHCP:** Central DHCP Server
* **Switch0:** Cisco 2960 Switch connecting all network devices
* **Clients:** 7 PCs (`PC0` to `PC6`) set to dynamic IP allocation (DHCP)
* **Printer1:** Assigned a Static IP (`192.168.50.7`)

---

## ⚙️ Configuration Details

### 1. DHCP Server Settings (`Sv-DHCP`)
- **Pool Name:** `HR`
- **Default Gateway:** `192.168.50.1`
- **Start IP Address:** `192.168.50.20` (Excluding `.1` to `.19` for static assignments)

![DHCP Pool Setup](assets/dhcp-config.png)

---

### 2. Switch Port Status & VLAN Setup
- Verified active FastEthernet interfaces connecting the server, PCs, and Printer.

![Switch Configuration](assets/dhcp-switch.png)

---

### 3. Static IP Setup (Printer)
- **IPv4 Address:** `192.168.50.7`
- **Subnet Mask:** `255.255.255.0`

![Printer IP Setup](assets/printer-IP.png)

---

### 4. Client IP Lease Verification

- **PC0 Lease:** Successfully obtained IP `192.168.50.20` via DHCP.

![PC0 Config](assets/pc0-dhcp.png)

- **PC6 Lease:** Successfully obtained IP `192.168.50.26` via DHCP.

![PC6 Config](assets/pc6-dhcp.png)

---

## ✅ Connectivity Verification (Ping Tests)

1. **Ping Test to PC4:** End-to-end connectivity verified with **0% packet loss**.

![Ping PC4](assets/ping-pc4.png)

2. **Ping Test to Static Printer (`192.168.50.7`):** Communication verified with **0% packet loss**.

![Ping Printer](assets/ping-printer.png)
