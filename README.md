<p align="center">
  <img src="https://raw.githubusercontent.com/MauriceBurt/Modular-Networks/main/Transparent_PNG.png" width="350"/>
</p>

# MoCo Family Center Network Design

## 📘 Overview
This design represents a small medical practice network built with a focus on:

- VLAN segmentation  
- Controlled inter-VLAN communication  
- Guest network isolation  
- Physical port security  

The environment reflects how a real-world organization separates departments while maintaining controlled access across the network.

---

## 🧭 Repository Structure

🔧 **[Configs](./configs)**  
🗺️ **[Topology](./topology)**  
📸 **[Screenshots](./screenshots)**  
🏢 **[Floor Plan](./floor_plan)**  

---

## 🧩 Network Segmentation

The network is divided into the following VLANs:

- **VLAN 10 — Reception**
- **VLAN 20 — Doctors**
- **VLAN 30 — Nurses**
- **VLAN 40 — Exam Rooms**
- **VLAN 50 — Guest Wi-Fi**

Each VLAN is isolated to reduce broadcast domains and enforce separation between departments.

---

## 🔐 Security Implementation

### VLAN Segmentation
Departments are logically separated to prevent unnecessary lateral movement across the network.

### ACL Enforcement (Guest Isolation)
Guest traffic is controlled using extended ACLs:

- ❌ Guest → Internal VLANs = **Denied**
- ✅ Internal VLANs → Guest = **Allowed**
- ✅ Guest → External/Public = **Allowed**

This ensures internal resources remain protected while still providing usable guest access.

---

### Physical Port Security (Waiting Area)

Unused wall ports are secured to prevent unauthorized access:

- Configured as **access ports**
- **Administratively shut down**

#### Scenario:
A device attempts to connect directly to a wall port.

**Result:**
- No link established  
- No IP assignment  
- No network access  

---

## 🌐 Network Behavior

### Internal Users (Staff VLANs)
- Communicate within their VLAN  
- Controlled inter-VLAN communication  
- Access to required internal resources  

### Guest Users (VLAN 50)
- Connect via wireless network  
- Receive IP addressing via DHCP  
- Reach default gateway  
- Access public-facing resources  

### 🚫 Restrictions
- Guest VLAN is isolated from all internal VLANs  
- No direct access to internal systems  

---

## 🧪 Validation

Network behavior was validated through:

- ICMP testing (ping)  
- Cross-VLAN communication checks  
- ACL enforcement verification (allowed vs denied traffic)  

---

## 🛠️ Configurations

👉 **[View Configs](./configs)**  

Includes:
- Router-on-a-stick configuration (802.1Q)  
- VLAN assignments  
- Trunk configuration  
- ACL rules controlling traffic flow  

---

## 🖼️ Screenshots

👉 **[View Screenshots](./screenshots)**  

Includes:
- Topology layout  
- VLAN segmentation  
- Guest Wi-Fi connectivity  
- ACL enforcement (allowed vs blocked traffic)  
- Port security behavior  

---

## 🗺️ Topology File

👉 **[Download Packet Tracer File](./topology/MoCo_Family_Center_Network_Design.pkt)**  

---

## 🏢 Floor Plan

👉 **[View Floor Plan](./floor_plan)**  

Maps the logical design to a physical environment.

---

## 🎯 Outcome

This design demonstrates:

- Structured VLAN segmentation across departments  
- Controlled access between internal and guest networks  
- ACL-based traffic enforcement  
- Physical security at the access layer  

It reflects a practical approach to network design where both logical and physical controls are applied.

---

## 🧰 Tools Used

- Cisco Packet Tracer (Network Simulation & Validation)  
- Cisco IOS CLI (Configuration & Troubleshooting)  
- Canva (Visual Design & Presentation Layout)
---

## 📦 Modular Networks

Part of the  
👉 [Modular Networks Design Library](https://github.com/MauriceBurt/Modular-Networks)
