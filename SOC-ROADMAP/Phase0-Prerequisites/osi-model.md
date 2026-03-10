# OSI Model — Networking Fundamentals

> **OSI** — Open Systems Interconnection  
> A guideline that describes how data is moved through a network.  
> Allows communication between different devices using protocols.

---

## The 7 Layers

### Layer 1 — Physical
- Uses signals for communication
- Uses a physical medium for connection between devices
- **3 main transmission types:**
  - Copper cable → Electric signals
  - Fiber optic cable → Light pulses
  - Wireless → WiFi, Bluetooth

---

### Layer 2 — Data Link
- Handles data transfer between devices on the **same network**
- Uses **MAC (Media Access Control)** addresses to identify devices
- MAC is a 6-byte address engraved on every NIC (Network Interface Card)
- Represented as 2 hexadecimal digits per byte, separated by colons
- Data units at this layer are called **Frames**
- Uses **ARP (Address Resolution Protocol)** to map IP addresses to MAC addresses

**Example from Wireshark:**
```
Destination: TendaTechnol_bd:08:40 (58:d9:d5:bd:08:40) → Router's MAC
Source:      FNLINKTECHNO_d2:54:50 (80:9d:65:d2:54:50) → My device's MAC
```
- `TendaTechnol` = Tenda router (manufacturer identified from MAC)
- `FNLINKTECHNO` = My network card manufacturer
- Remaining bytes = the actual data being transmitted

---

### Layer 3 — Network
- Allows communication between devices on **different networks**
- Breaks frames down into smaller **packets**
- Uses a **routing table** to determine the next hop for each packet

**Two IP versions:**
| Version | Bits | Example |
|---------|------|---------|
| IPv4 | 32-bit | `192.168.10.5` |
| IPv6 | 128-bit | `F654::48A4:985d:484a:484b:C04s` |

**Routing example:**
```
PC → Router → Another Router → Destination PC
```

---

### Layer 4 — Transport
- Ensures data from the source is delivered to the correct destination
- Provides **end-to-end communication**

**4 main functions:**

| Function | Description |
|----------|-------------|
| **Segmentation** | Breaks large data into segments, each indexed for reassembly |
| **Flow Control** | Balances how much data is sent/received at once |
| **Error Control** | Confirms all packets arrived — resends missing or damaged ones |
| **Multiplexing** | Multiple apps communicate simultaneously using different port numbers |

**TCP vs UDP:**

| | TCP | UDP |
|-|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Guaranteed | No guarantee |
| Speed | Slower | Faster |
| Order | Maintained | Not maintained |
| Use cases | Web, email, file transfer | Streaming, gaming, DNS |

**TCP Three-Way Handshake:**
```
Client → Server : SYN
Server → Client : SYN-ACK
Client → Server : ACK
✓ Connection established
```

**Common Ports:**

| Port | Protocol |
|------|----------|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |
| 3389 | RDP |

---

### Layer 5 — Session
- Responsible for **opening, managing, and closing sessions** between devices

| Function | Description |
|----------|-------------|
| **Session Establishment** | Connection set up before any data transfer |
| **Session Management** | Keeps session alive, adds checkpoints for recovery |
| **Session Termination** | Cleanly closes session when communication ends |

**Example:** When WhatsApp disconnects mid-call, it reconnects from the last checkpoint rather than restarting the session entirely.

---

### Layer 6 — Presentation
- Acts as a **translator** — ensures data is in a format both sender and receiver understand

| Function | Description |
|----------|-------------|
| **Translation** | Converts data between different formats |
| **Compression** | Reduces data size to speed up transmission |
| **Encryption/Decryption** | Encrypts data before sending, decrypts on arrival |

**Examples:**
- Video: MP4, AVI
- Images: PNG, JPEG, GIF
- Encryption: SSL/TLS (HTTPS)

---

### Layer 7 — Application
- Provides **network services directly to the user's applications**
- Not the app itself (e.g. Chrome) but the protocols that allow it to communicate

**Common protocols:**

| Protocol | Purpose |
|----------|---------|
| HTTP/HTTPS | Web browsing |
| FTP | File transfer |
| SMTP | Sending email |
| POP3/IMAP | Receiving email |
| DNS | Domain name to IP resolution |
| DHCP | Automatic IP assignment |
| SSH | Secure remote access |
| Telnet | Remote access (unencrypted) |

---

## OSI vs TCP/IP

```
OSI Model          TCP/IP Model
─────────────────────────────────
Layer 7 Application  ↘
Layer 6 Presentation → Application Layer
Layer 5 Session      ↗
Layer 4 Transport  →   Transport Layer
Layer 3 Network    →   Internet Layer
Layer 2 Data Link  ↘
Layer 1 Physical   ↗   Network Access Layer
```

> OSI = theoretical model used for learning and troubleshooting  
> TCP/IP = practical model that actually runs the internet

---

## Quick Reference — All 7 Layers

| Layer | Name | Data Unit | Key Protocol/Concept |
|-------|------|-----------|---------------------|
| 7 | Application | Data | HTTP, DNS, FTP, SSH |
| 6 | Presentation | Data | SSL/TLS, JPEG, MP4 |
| 5 | Session | Data | NetBIOS, RPC |
| 4 | Transport | Segment | TCP, UDP, Ports |
| 3 | Network | Packet | IP, ICMP, Routing |
| 2 | Data Link | Frame | MAC, ARP, Switches |
| 1 | Physical | Bits | Cables, Signals, WiFi |

---

*Notes by Taha Asim | SOC Analyst Roadmap — Phase 0*
