- Process of adding data headers to your data
- Every layer adds its own specific header
---
# Application Layer 
- Data is created(raw data)
- Nothing is added to the header
---
# Transport Layer
- It takes the data
- Add its header to the data(TCP header) or (UDP header)
- This header includes: **source port, destination port, sequence number** 
- Its called a **Segment(TCP header added) or Datagram(UDP header)**
- Example:
	- [TCP-Header | Data] -> segment
---
# Network Layer
* It takes the segment
* Add its header to the segment(IP header)
* This header includes: **source IP address, destination IP address**
* its called a **Packet**
* Example:
	* [IP | TCP| Data]-> packet
---
# Data link layer
* It takes the packet
* Add its header to the packet(Header & tail)
* Header contains the **MAC Header** 
* Tail contains the **Frame check sequence**
* Example:
	* [MAC | IP | TCP | DATA | FRAME]->Frame 
---
# Physical Layer
* It takes the frame and converts into bits which are then transmitted into light signals.
