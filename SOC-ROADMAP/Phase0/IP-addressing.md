# IP Addressing Fundamentals

## IPv4 Addressing

### Structure

- **Total Size:** 32-bit address
- **Composition:** 4 bytes = 4 octets
- **Format:** Dotted decimal notation (e.g., 192.168.10.0)
- **Range per Octet:** 0-255

### What is an Octet?

- An octet is **8 bits**
- Each octet can represent values from 0 to 255
- 4 octets × 8 bits = 32 bits total

### Example Breakdown:

```
IP Address: 192.168.10.0

192     .    168    .     10     .      0
 ↓            ↓            ↓             ↓
Octet 1    Octet 2    Octet 3      Octet 4
(8 bits)   (8 bits)   (8 bits)     (8 bits)
```

---

## IPv6 Addressing

### Structure

- **Total Size:** 128-bit address
- **Composition:** 16 bytes (128 bits ÷ 8 = 16 bytes)
- **Representation:** 8 groups of hexadecimal digits
- **Format:** Each group contains 4 hexadecimal digits separated by colons

### Hexadecimal Notation

- Uses digits 0-9 and letters A-F
- Each hexadecimal digit represents 4 bits
- 4 hex digits = 16 bits = 2 bytes per group

### Example IPv6 Address:

```
2001:0DB8:85A3:0000:0000:8A2E:0370:7334

Group 1: 2001
Group 2: 0DB8
Group 3: 85A3
Group 4: 0000
Group 5: 0000
Group 6: 8A2E
Group 7: 0370
Group 8: 7334

Total: 8 groups × 16 bits per group = 128 bits
```

### IPv6 Shorthand Rules:

- **Leading zeros** can be omitted: `0DB8` → `DB8`
- **Consecutive groups of zeros** can be replaced with `::` (only once per address)
    - Example: `2001:0DB8:0000:0000:0000:0000:0370:7334`
    - Shortened: `2001:DB8::370:7334`

---

## IPv4 Address Classes

IP addresses are divided into classes based on the first octet value:

### Class A

- **Range:** 1 - 126
- **First Bit Pattern:** 0xxxxxxx
- **Default Subnet Mask:** 255.0.0.0
- **Network/Host Split:** 8 bits network, 24 bits host
- **Use Case:** Very large networks
- **Example:** 10.0.0.0

**Note:** 127.x.x.x is reserved for loopback (localhost)

### Class B

- **Range:** 128 - 191
- **First Bit Pattern:** 10xxxxxx
- **Default Subnet Mask:** 255.255.0.0
- **Network/Host Split:** 16 bits network, 16 bits host
- **Use Case:** Medium to large networks
- **Example:** 172.16.0.0

### Class C

- **Range:** 192 - 223
- **First Bit Pattern:** 110xxxxx
- **Default Subnet Mask:** 255.255.255.0
- **Network/Host Split:** 24 bits network, 8 bits host
- **Use Case:** Small networks
- **Example:** 192.168.1.0

### Class D (Multicast)

- **Range:** 224 - 239
- **First Bit Pattern:** 1110xxxx
- **Purpose:** Multicast groups (one-to-many communication)
- **Example:** 224.0.0.0
- **Note:** Not used for regular host addressing

### Class E (Experimental/Reserved)

- **Range:** 240 - 255
- **First Bit Pattern:** 1111xxxx
- **Purpose:** Reserved for experimental use and future purposes
- **Note:** Not available for general use

---

## Class Summary Table

|Class|Range|Default Subnet Mask|Network Bits|Host Bits|Typical Use|
|---|---|---|---|---|---|
|A|1-126|255.0.0.0|8|24|Very large orgs|
|B|128-191|255.255.0.0|16|16|Medium-large orgs|
|C|192-223|255.255.255.0|24|8|Small networks|
|D|224-239|N/A (Multicast)|N/A|N/A|Multicast|
|E|240-255|N/A (Reserved)|N/A|N/A|Experimental|

---

## Subnet Masks

A subnet mask separates the network portion from the host portion of an IP address.

### Common Subnet Masks:

- **Class A:** 255.0.0.0 (written as /8 in CIDR notation)
- **Class B:** 255.255.0.0 (written as /16 in CIDR notation)
- **Class C:** 255.255.255.0 (written as /24 in CIDR notation)

### How Subnet Masks Work:

```
IP Address:    192.168.10.5
Subnet Mask:   255.255.255.0
               ─────────── ─
               Network     Host
               Part        Part

Network Address: 192.168.10.0
Host Address: 0.0.0.5
```

---
# Private vs Public
1. Public:
	1. Anyone can access the internet without any restriction 
	2. Eg: Accessing the airport network or shopping without any unique password
2. Private:
	1. Only specific people can access the internet
	2. Eg: Home network only people with correct password can enter anyone outside the home will not be able to connect it. 
	3. It is used to make sure the network we are using is protected from any attacks
---

## Key Concepts to Remember

### Binary Representation

- Each octet in IPv4 is 8 bits
- Example: 192 in binary = 11000000
- Understanding binary is crucial for subnetting

### Network vs Host Portion

- **Network Portion:** Identifies the network
- **Host Portion:** Identifies the specific device on that network
- Subnet mask determines the split between network and host bits

### Special Addresses

- **Network Address:** All host bits set to 0 (e.g., 192.168.1.0)
- **Broadcast Address:** All host bits set to 1 (e.g., 192.168.1.255)
- **Loopback:** 127.0.0.1 (localhost for testing)

---

## Quick Reference

### IPv4 vs IPv6 Comparison:

|Feature|IPv4|IPv6|
|---|---|---|
|Address Size|32-bit|128-bit|
|Total Bytes|4 bytes|16 bytes|
|Notation|Decimal (dotted)|Hexadecimal (colon-separated)|
|Address Groups|4 octets|8 groups|
|Example|192.168.1.1|2001:DB8::1|
|Total Addresses|~4.3 billion|340 undecillion|

---

# COMMANDS: 
1. To look up the **IP address** we can use the command **ifconfig or ipconfig** 
