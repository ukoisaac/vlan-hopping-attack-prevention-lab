# 🔐 VLAN Hopping Attack Prevention Lab

## 📌 Overview

This lab demonstrates how to prevent **VLAN Hopping attacks** in a Layer 2 network.

The network is segmented into multiple VLANs (HR, IT, ACC), and security configurations are applied to prevent unauthorized access between VLANs.

---

## 🎯 Objectives

* Understand how VLAN hopping attacks work
* Prevent **Switch Spoofing (DTP attacks)**
* Mitigate **Double Tagging attacks**
* Secure trunk ports and access ports
* Disable unnecessary protocols (CDP)

---

## 🧱 Network Topology

<img width="1344" height="599" alt="image" src="https://github.com/user-attachments/assets/16bb35eb-311a-47cf-b679-00d14c711da4" />


---

## ⚙️ Technologies Used

* Cisco Packet Tracer
* VLANs (10, 20, 30)
* Trunking (802.1Q)
* DTP (Dynamic Trunking Protocol)
* CDP (Cisco Discovery Protocol)

---

## 🔧 Key Configurations

### ✅ Disable DTP (Prevent Switch Spoofing)

```id="6if92u"
interface range fa0/1 - 24
switchport mode access
switchport nonegotiate
```

---

### ✅ Secure Trunk Ports

```id="0hq7n3"
interface fa0/24
switchport mode trunk
switchport trunk native vlan 999
```

---

### ✅ Disable CDP (Reduce Information Leakage)

```id="9l7r3p"
no cdp run
```

---

### ✅ VLAN Configuration

```id="x3v0xg"
vlan 10
name IT

vlan 20
name HR

vlan 30
name ACC
```

---

## 🧪 Test Scenarios

### 🔴 VLAN Hopping Attempt (Switch Spoofing)

* Attempted to negotiate trunk using DTP
* DTP disabled → trunk not formed → attack failed

---

### 🟡 Double Tagging Protection

* Changed native VLAN from default VLAN 1 to VLAN 999
* Prevented VLAN tag manipulation attacks

---

## 🧠 Key Learnings

* VLAN hopping exploits weak trunk configurations
* DTP should always be disabled on access ports
* Native VLAN should never remain as VLAN 1
* CDP can expose sensitive network information

---

## 🚨 Real-World Use Case

Attackers can exploit misconfigured switches to gain access to unauthorized VLANs.

This lab demonstrates how proper configuration:

* Prevents unauthorized trunk formation
* Protects VLAN segmentation
* Improves overall Layer 2 security

---

## 📁 Lab File

attached 
```

---

## 👨‍💻 Author

**Isaac Uko**
Aspiring Network Engineer

---

## ⭐ Notes

This lab is part of my hands-on practice in securing enterprise networks against Layer 2 attacks.
