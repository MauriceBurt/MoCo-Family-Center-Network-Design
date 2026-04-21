<p align="center">
  <img src="https://raw.githubusercontent.com/MauriceBurt/Modular-Networks/main/Transparent_PNG.png" width="350"/>
</p>

# MoCo Family Center Network Design

## Overview
This design simulates a small medical practice network built with a focus on segmentation, controlled access, and physical port security.

The environment represents a real-world deployment where different departments require isolated access, while still maintaining controlled communication where appropriate.

---

## Network Segmentation
The network is divided into the following VLANs:

- VLAN 10 — Reception
- VLAN 20 — Doctors
- VLAN 30 — Nurses
- VLAN 40 — Exam Rooms
- VLAN 50 — Guest Wi-Fi

Each VLAN is logically separated to reduce broadcast domains and enforce security boundaries between departments.

---

## Security Focus
This design highlights two key security concepts:

### 1. VLAN Segmentation
Departments are isolated to prevent unnecessary communication between devices.

### 2. Port Security (Waiting Area Protection)
Unused wall ports in the waiting area are administratively disabled to prevent unauthorized access.

A rogue device attempting to connect will not gain network access due to the port being shut down.

---
## Repository Structure

- 📁 configs — Device configurations (router & switch)
- 📁 screenshots — Key validation and proof of behavior
- 📁 topology — Packet Tracer design file

---

## Network Behavior

### Internal Users (Staff VLANs)
- Can communicate within their own VLAN
- Inter-VLAN communication is controlled and limited
- Access to necessary internal resources is maintained

### Guest Users (VLAN 50)
- Can connect to wireless network
- Receive IP addressing via DHCP
- Can reach default gateway
- Can access external/public-facing resources

### Restrictions
- Guest VLAN is isolated from internal VLANs
- Direct access to internal devices is blocked

---

## Port Security Enforcement (Waiting Area)

- Unused wall ports are configured as **access ports**
- Ports are **administratively shut down**
- Prevents unauthorized physical access to the network

### Scenario:
A rogue device attempts to connect directly to a wall port.

**Result:**
- No link established
- No IP assignment
- No network access

---

## Outcome

This design demonstrates:

- Structured VLAN segmentation across departments  
- Controlled access between internal and guest networks  
- Physical layer security through port shutdown enforcement  

The network reflects a real-world approach where both logical and physical security are considered.

---

## Tools Used

- Cisco Packet Tracer  
- Cisco IOS CLI  

---

## Screenshots

Key validation points are included in the `screenshots` directory:

- Topology overview  
- Rogue device attempt  
- Guest WiFi connection  
- Guest access restrictions  
- Port shutdown verification  

---

## Topology

The full network design can be found in the `topology` directory.

---
