# OSI
- Open source intercommunication
- A guideline that describes how the data is moved through the network
- Allows communication between deferent devices using protocols.


# Layers
1. Physical 
	1. It uses signals for communication 
	2. Cables, connectors and fiber optic cables are used for communication between devices, it uses a physical medium for physical connection.
	3. 3 Main wires
		1. Copper cable(Electric signals)
		2. Fiber optic cable(Light pulses)
		3. Wireless(WIFI- Bluetooth)
2. Data link
	1. The foundation layer that tells us how data is transferred between devices on the same network using MAC(Media Access Control) address.
	2. MAC is a six byte address that is engraved on every NIC(Network interface card).
	3. It is represented in 2 HEXADECIMAL digits representing one byte, and it is separated using a colon.
	4. It calls data "Frames"
	5. It uses an ARP table(Address resolution protocol) using for mapping IP address to its MAC address.
	6. Eg:
		1. Destination:`Tenda (15:85:10:15:55:20)`
		2. `Tenda` = the manufacturer (Tenda — a router brand)
		3.  This is your **router's MAC address**
		4. **Source:** `FNLINK (24:45:P8:15:16:85)`
		5.  `FNLINK` = the manufacturer of your network card
		6. This is **your device's MAC address**
		7. You are the source sending the traffic
		8. Remaining bits are the data that is being sent   
3. Network 
	1. Allows communication between different devices on different networks
	2. Breaks down the frames into smaller packets
	3. Uses routing table where all the IP address are stored, and to let them know which is the next IP they need to go to.
	4. Two IPS:
		1. IPV4(32 bit address): 192.128.10.5
		2. IPV6(128 bit address): F654::48S4:985d:484s:484s:po4s
	5. Eg:
		1. PC->ROUTER->Another ROUTER->DESTINATION PC
4. Transport 
	1. It makes sure the data that is taken from the source is delivered to correct destination.
	2. Provides end to end communication.
	3. It does 4 main things 
		1. Segmentation:
			1. Breaking down of large data into segments so it can easily travel across the network, and get reassembled using indexing as each segment is indexed.
		2. Flow Control:
			1. It controls how much data can be sent from the source at once, and how much data the receiver can get at once. Makes sure everything is balanced in the network system.
		3. Error control:
			1. Making sure the packets have been delivered successfully to its correct destination. If any packets are damaged or missing it resends them.
		4. Multiplexing:
			1. Multiple applications can send and received data at the same time using different port numbers. 
			2. That's why you tube or Spotify can work without mixing the data as it uses different port numbers. 
	4. Protocols:
			1. TCP(Transmission Control Protocol):
					1. Connection oriented: Connection needs to be established before hand for communication to take place.
					2. Guaranteed reliability makes sure all the packets have arrived and send confirmation
					3. Speed its slower as it needs to check each and every packet
					4. Makes sure the packet arrive in the same order as it was sent
					5. Web, email, file transfer 
					6. Three way handshake:
						1. Client->server: synchronization 
						2. sever->client: SYN-ACK
						3. Client->server: ACK
			2. UDP(User datagram protocol):
					1. Not connection oriented
					2. Faster 
					3. No guarantee
					4. No order is needed
					5. Video streaming, gaming, DNS
	6. Ports:
		1. Ports - Protocol
		2. 21 - FTP
		3. 22 - SSH
		4. 23 - TELNET
		5. 25 - SMTP
		6. 53 - DNS
		7. 80 - HTTP
		8. 443 - HTTPS
		9. 3389 - RDP
5. Session 
	1. Opening, managing, and closing a session between devices
	2. Session Establishment: Connection needs to be established before any data is transferred.
	3. Session Management: Keeps the session alive during data transfer. Adds **checkpoints** incase the data transfer fails midway it restores from where it failed.
		1. Eg: when WhatsApp gets disconnected it reconnects using the checkpoints 
	4. Session Termination: Closing the session once its completed
6. Presentation 
	1. A way to make sure that the data is translated for both the sender and receiver to make communication between them and easier to understand.
	2. Translation: Converting data from one format to another so both can understand each other
	3. Compression: Making sure the data is compressed so that it can speed up the process.
	4. Encapsulation decapsulation: Making sure the data is encrypted while it is being sent and decrypted to its original form once the data has been received. 
	5. Eg
		1. Video formats: MP4
		2. image: PNG,JPEG,GIF
7. Application layer
	1. Providing network service application to the users.
	2. It uses protocols so that it can communicate over the network.
