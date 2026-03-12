# Use The website Wikipedia.org or Example.com to solve this lab
# Layer 2(Data Link layer)
* First Ping the specific website
	* Using **ping** command
	* This way we will get the IP address of the website
	* We can use the IP address to filter it using wire shark
	* command: `ip.addr==103.102.166.224`
* Second:
	* ETHERNET-II represents the layer 2
	* Over here we can see two things:
		* Source MAC address
		* Destination MAC address
		*<img width="1448" height="137" alt="image" src="https://github.com/user-attachments/assets/43179138-7580-4742-8133-d61b09bd87a5" />
 

---

# Layer 3(Internet Protocol Layer)
*<img width="1139" height="464" alt="image" src="https://github.com/user-attachments/assets/22591e41-f0b8-41c0-948b-8154b14513c4" />
1. Version: This tells us the IP version either 4 or 6
2. Header Length: This is the total size of the IP Header 
3. DSCP/ECN: The quality of service
	1. DSCP
		1. Checks the priority of the packet
		2. Controlled by the sender
	2. ECN
		1. Congestion control
		2. Warns the sender to make sure the network is not overwhelmed with packet overflow
4. Don't fragment and Data Fragmentation:
	1. Don't fragment
		1. Whether the packet needs to be fragmented or not 
		2. 0 1 0
		3. First bit->Reserved bit which is always 0
		4. Second bit->Don't fragment 1(Cannot be fragmented) | 0(Can be fragmented)
		5. Third bit->More Fragmentation 1(More fragments are coming) | 0(No more fragments)
	2. Fragmentation
		1. Fragment offset : position in bytes where this fragment starts from in the original byte
		2. 0 = First Fragment(always starts from 0)
		3. any other number = middle | last position 
		4. Eg:  breaking down a 40 page book
			1. Fax 1: pages 1-15   (offset = page 0)
			2. Fax 2: pages 16-30  (offset = page 15)
			3. Fax 3: pages 31-40  (offset = page 30)
5. TTL : Max no of hops before the packet dies
6. Protocol: The payload that is being used
7. Source add & Dest add
---
# Layer 4(Transport Layer)
