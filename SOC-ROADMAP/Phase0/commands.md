# IPCONFIG
`ipconfig` is used for displaying the overall network configuration of your device.

## Output
| Field           | Example          | Description        |
|-----------------|------------------|--------------------|
| IPv4 Address    | 192.168.1.10     | Your device's IP   |
| Subnet Mask     | 255.255.255.0    | Your network range |
| Default Gateway | 192.168.1.1      | Your router's IP   |

## Key Commands
| Command  | Purpose       |
| -------- | ------------- |
| ipconfig | Basic IP info |

---

# Telnet
Used for connecting to specific services using specific port numbers.

## Common Ports
| Service  | Port |
|----------|------|
| HTTP     | 80   |
| Daytime  | 13   |
| Echo     | 7    |

## Important Notes
- Telnet is unencrypted — all data sent is plain text
- SSH (port 22) is the secure modern replacement
- Seeing Telnet traffic on a network is a red flag in SOC

---
# nslookup

Used for querying DNS to find the IP address of a domain 
or the domain name of an IP address.

## Basic Commands

| Command | Purpose |
|---------|---------|
| `nslookup google.com` | Find IP address of a domain |
| `nslookup 8.8.8.8` | Find domain name of an IP address |
| `nslookup google.com 8.8.8.8` | Query a specific DNS server |

## Example Output
```
Server:  dns.google
Address: 8.8.8.8

Non-authoritative answer:
Name:    google.com
Address: 142.250.180.46
```

## Key Terms

| Term | Meaning |
|------|---------|
| Server | DNS server that answered your query |
| Non-authoritative answer | Answer came from cache, not the original DNS server |
| Address | The IP address of the domain |

