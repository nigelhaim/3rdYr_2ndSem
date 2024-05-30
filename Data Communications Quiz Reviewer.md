
- **Module 9: Address Resolution**  
- **Module 10: Basic Router Configuration**  
- **Module 13: ICMP**  
- **Module 14: Transport Layer**
- **Module 15: Application Layer**
- **Module 16: Network Security Fundamentals**
- **Module 17: Build a Small Network**


## MAC and IP 
### Destination on Same Network

There are two primary addresses assigned to a device on an Ethernet LAN: 

**Layer 2 physical address (the MAC address)** - Used for NIC (Network Interface Card) to NIC communications on the same Ethernet network
**Layer 3 Logical address (the IP address) -** Used to send the packet fro mthe source device to the destination device 

Layer 2 addresses are used to deliver frames from one NIC to another NIC on the same network. If a destination IP address is on the same network, the destination MAC address will be that of the destination device 

>[!Note]- Layer 2 
>![[Pasted image 20240507105907.png]]

### Destination on Remote Network 

When the destiantion IP address is on a remote network, the destination MAC address is that of the default gateway

- **ARP (Address Resolution Protocol)** is used by IPv4 to associate the IPv4 address of a device with the MAC address of the device NIC
- **ICMPv6 (Internet Control Message Protocol version 6)** is used by IPv6 to associate the IPv6 address of a device with the MAC address of the device NIC. 

>[!Note]- ARP
>![[Pasted image 20240507110953.png]]
## ARP 

### ARP Overview

A device uses ARP to determine the destination MAC address of a local device when it knows its IPv4 address. 

ARP provides two basic functions:
- Resolving IPv4 addresses to MAC addresses 
- Maintaining an ARP table of IPv4 to MAC address mappings 

>[!Note]- How does ARP work 
>![[Pasted image 20240507111329.png]]

### ARP Functions

 To send a frame, a device will search its ARP table for a destination IPv4 address and a corresponding MAC address. 
 - If the packet's destination IPv4 address is on the same network, the device will search the ARP table for the destination IPv4 address. 
 - If the destination IPv4 address is on a different network, the device will search the ARP table for the IPv4 address of the default gateway 
 - If the device locates the IPv4 address, its corresponding MAC address is used as the destination MAC address in the frame. 
- If there is no ARP table entry is found, then the device sends and ARP request. 

### Removing Entries from an ARP Table 
- Entries in the ARP table are not permanent and are removed when an ARP cache timer expires after a specified period of time. 
- The duration of the ARP cache timer differes depending on the operating system. 
- ARP table entries can also be removed manually by the administrator. 

>[!Note]- Removing ARP Entries 
>![[Pasted image 20240507112009.png]]

### ARP Tables on Networking Devices 

**show ip arp** -  command displays the ARP table on a Cisco router.
**arp -a** - Command displays the ARP table on a Windows 10 PC

### ARP Issues - ARP Broadcasting and ARP Spoofing 
- ARP requests are received and processed by every device on the local network. 
- Excessive ARP broadcasts can cause some reduction in performance
- ARP replies can be spoofed by a threat actor to perform an ARP poisoning attack. 
- Enterprise level switches include mitigation techniques to protect against ARP attacks.

>[!Note]- ARP Issues 
>![[Pasted image 20240507112514.png]]


**Video:** https://www.youtube.com/watch?v=cn8Zxh9bPio

## IPv6 Neighbor Discovery 

### IPv6 Neighbor Discovery Messages

**IPv6 Neighbor Discovery (ND) protocol provides:**
- Address resolution 
- Router discovery 
- Redirection services 

ICMPv6 Neighbor Solicitation (NS) and Neighbor advertisement (NA) messages are used for device-to-device mesageing such as adress resolution. 
ICMTPv6 Router Solicitation (RS) and Router Advertisement (RA) messages are used for messaging between devices and routers for router discovery. 
ICMPv6 redirect messages are used by routers for better next-hop selection 

### IPv6 Neighbor Discovery - Address Resolution 

- IPv6 devices use ND to resolve the MAC address of a known IPv6 address. 
- ICMPv6 Neighbor Solicitation messages are sent using special Ethernet and IPv6 multicast addresses. 

>[!Note]- Neighbor Discovery
>![[Pasted image 20240507113356.png]]


**Video:** https://youtu.be/A3LFt7CHpgs?si=WSmn0kMfQUn9wgMz
## Basic Router Configuration 

### Basic Router Configuration Steps

| Code                                                                                                                                                                         | Meaning                                               |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- |
| Router (config) # **hostname** hostname                                                                                                                                      | Configure the device nameba                           |
| Router (config) # **enable secret** *password*                                                                                                                               | Secure privileged EXEC mode                           |
| Router (config) # **line console 0**<br>Router (config-line) # password *password*<br>Router (config-line) # login                                                           | Secure user EXEC mode                                 |
| Router (config) # **line vty 0 4**<br>Router (config-line) # password *password*<br>Router (config-line) # login<br>Router (config-line) # transport input { ssh \| telnet } | Encypt all plaintext passwords                        |
| Router (config) # **service password encryption**                                                                                                                            | Provide legal notification and save the configuration |
| Router (config) # **banner motd # message #** <br>Router (config) # end<br>Router# copy running-config startup-config                                                        | Provides a banner on the login page and during the op |

### Basic Router Configuration Example

```
R1 (config) # hostname R1
R1 (config) # enable secret class
R1 (config) # line console 0 
R1 (config-line) # password cisco
R1 (config-line) # login
R1 (config-line) # line vty 0 4 
R1 (config-line) # password cisco
R1 (config-line) # login
R1 (config-line) # transport input ssh telnet
R1 (config-line) # exit 
R1 (config) # service password encryption
R1 (config) # banner motd #
Enter TEXT message. End with a new line and the # *********************************************** 
WARNING: Unauthorized access is prohibited! **********************************************

R1 (config) # exit
R1 # copy running-config startup-config

```

**Commands for basic router configuration on R1**
**Configuration is saved to NVRAM**

### Configure Router Interfaces 

**Configuring a router interface includes issuing the following commands:**

```

Router (config) # interface type-and-number 
Router (config-if) # description description-text
Router (config-if) # ip address ipv4-address subnet-mask
Router (config-if) # ipv6 address ipv6-address/prefix-length 
Router (config-if) # no shutdown

```

- It is good practice to use the description command to add information about the network connected to the interface 
- The **no shutdown** command activates the interface

### Configure Router Interfaces Example 

**The commands to configure interface G0/0/0 on R1 are shown here:**

>[!Note]- Configured router 
>![[Pasted image 20240508172209.png]]

```

R1 (config) # interface gigabitEthernet 0/0/0
R1 (config-if) # description Link to LAN
R1 (config-if) # ip address 192.168.10.1 255.255.255.0
R1 (config-if) # ipv6 address 2001:db8:acad:10::1/64
R1 (config-if) # no shutdown
R1 (config-if) # exit 
R1 (config-if) #

*Aug 1 01:43:53.435: %LINK-3-UPDOWN: Interface GigabitEthernet0/0/0, changed state to down 
*Aug 1 01:43:56.447: %LINK-3-UPDOWN: Interface GigabitEthernet0/0/0, changed state to up 
*Aug 1 01:43:57.447: %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0/0

changed state to up
```


### Verify Interface Configuration 

**To verify interface configuration use the show ip interface brief and show ipv6 interface brief commands shown here:**

| Code                              | Meaning      |
| --------------------------------- | ------------ |
| R1# **show ip interface brief**   | for the ipv4 |
| R1# **show ipv6 interface brief** |              |
>[!Note]- Examples 
>![[Pasted image 20240508172613.png]]

The table summarizes show commands used to verify interface configuration 

| Commands                                             | Description                                                                                         |
| ---------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| show ip interafce brief<br>show ipv6 interface brief | Displays all interfaces, their IP addresses, and their current status                               |
| show ip router <br>show ipv6 router                  | Displays the contents of the IP routing tables stored in RAM                                        |
| show interfaces                                      | Displays statistics for all interfaces on the device. Only displays the IPv4 addressing information |
| show ip interfaces                                   | Displays the IPv4 statistics for all interfaces on a router                                         |
| show ipv6 interfaces                                 | displays the IPv6 statistics for all interface on a router.                                         |
**View status of all interfaces with the show ip interface brief and show ipv6 interface brief commands, shown here: **

>[!Note]- status of all interfaces
>![[Pasted image 20240508173314.png]]

**Display the contents of the IP routing tables with the show ip router and show ipv6 route commands as shown here:**

>[!Note]- Displaying the contents
>![[Pasted image 20240508173514.png]]

**Display statistics for all interfaces with the show interfaces command , as shown here:**

>[!Note]- Display statistics 
>![[Pasted image 20240508173619.png]]

**Display IPv4 statistics for router interfaces with the show ip interface command, as shown here:**

>[!Note]- Display statistics
>![[Pasted image 20240508231534.png]]

**Display IPv6 statistics for router interfaces with the show ipv6 interface command shown here:**

>[!Note]- Display Statistics
>![[Pasted image 20240508231611.png]]


## Configure the Default Gateway 

### Default Gateway on a Host 

- The default gateway is used when a host sends a packet to a device on another network.
-  The default gateway address is generally the router interface address attached to the local network of the host
- To reach PC3, PC1 addresses a packet with the IPv4 address of PC3, but forwrds the packet to its default gateway, the G0/0/0 interface of R1.

>[!Note]- The IP address of the host and the router interface must be in the same network 
>![[Pasted image 20240508231912.png]]

### Default Gateway on a switch 
- A switch must have a default gateway address configured to remotely manage the switch from another network 
- To configure an IPv4 default gateway on a switch, use the **ip default-gateway** *ip-address* global configuration command 

>[!Note]- Gateway on a switch 
>![[Pasted image 20240508232038.png]]

## ICMP (Internet Control Message Protocol)

### ICMPv4 and ICMPv6 Messages 

- Internet Control Message Protocol (ICMP) provides feedback about issues related to the processing of IP packets under certain conditions
- ICMPv4 is the messageing protocol for IPv4. ICMPv6 is the messaging protocol for IPv6 and includes additional functionality. 
- The ICMP messages common to both ICMPv4 and ICMPv6 include: 
	- Host reachability
	- Destination or Service Unreachable 
	- Time exceeded

**Note:** ICMPv4 messages are not required and are often not allowed within a network for security reasons.

### Host Reachability 

ICMP Echo Message can be used to test the reachability of a host on an IP network. 

>[!Note]- Example
> The local host sends an ICMP Echo Request to a host
> If the host is available, the destination host responds with an Echo Reply. 
>![[Pasted image 20240508233113.png]]

### Destination or Service Unreachable 

- An ICMP Destination Unreacahble message can be used to notify the source that a destination or service is unreachable 
- The ICMP message will inclulde a code indicating why the packet could not be delivered 

| #   | ICMPv4               | ICMPv6                                                                             |
| --- | -------------------- | ---------------------------------------------------------------------------------- |
| 0   | Net Unreachable      | No route to destination                                                            |
| 1   | Host unreachable     | Communication with the destination is administratively prohibited (e.g., firewall) |
| 2   | Protocol Unreachable | Beyond scope of the source address                                                 |
| 3   | Port Unreachable     | Address Unreachable                                                                |
| 4   |                      | Port Unra                                                                          |
### Time Exceeded
- When the Time to Live (TTL) field in a packet isd decremented to 0, an ICMPv4 Time Exceeded messge will be sent to the source host. 
- ICMPv6 also sends a Time Exceeded message. Instead of the IPv4 TTL field, IMCPv6 uses the IPv6 Hop Limited field to determine if the packet has expired. 

>[!Note]- Time Exceeded
>![[Pasted image 20240509000400.png]]

### ICMPv6 Messages

ICMPv6 has new features and improved functionality not found in ICMPv4, including four new protocols as part of the Neighbor Discovery Protocol (ND or NDP).

Messaging between an IPv6 router and an IPv6 device, including dynamic address allocation are as follows:
- Router Solicitation (RS) message 
- Router Advertisement (RA) message

Messaging between IPv6 devices, including duplicate address detection and address resolution are as follows"
- Neighbor solicitation (NS) message
- Neighbor Advertisement (NA) message 

RA messages are set IPv6-enabled routers every 200 seconds to provide addressing information to IPv6-enabled hosts. 
RA message can include addressing information for the host such as the prefix, prefix length, DNS address, and domain name. 
A host using Stateless Address Auto configuration (SLAAC) will set its default gateway to the link-local address of the router that sent the RA. 

>[!Note]- RA Message
>![[Pasted image 20240509002556.png]]

An IPv6-enabled routter weill also send out an RA message in response to an RS message 
In the figure, PC1 sends a RS message to determine how to receive its IPv6 address information dynamically.

- R1 replies to the RS with an RA message. 
- PC1 sends an RS message, “Hi, I just booted up. Is there an IPv6 router on the network? I need to know how to get my IPv6 address information dynamically.” 
- R1 replies with an RA message. “Hi all IPv6-enabled devices. I’m R1 and you can use SLAAC to create an IPv6 global unicast address. The prefix is 2001:db8:acad:1::/64. By the way, use my link-local address fe80::1 as your default gateway."

>[!Note]- Replies 
>![[Pasted image 20240509002921.png]]

A device assigned a glboal IPv6 unicast or link-local unicast address, may perform duplicate address detection (DAD) to ensure that the IPv6 address is unique.

To check the uniqness of an address, the device will send an NS message with its own IPv6 address as the targeted IPv6 address. 
If another device on the network has this address, it wil lrespond with an NA message notifying to the sending device taht the address is in use. 

>[!Note]- DAD
>![[Pasted image 20240509011131.png]]

To determine the MAC address for the destination, the device will send an NS message to the solicited node address. 

The message will include the known (targeted) IPv6 address. The device that has the targeted IPv6 address will repsond with an NA message containing its ethernet MAC address.

>[!Note]- NS message
>![[Pasted image 20240509011259.png]]

**Video:** https://www.youtube.com/watch?v=xTqtm7-k25o
## Ping and Traceroute Tests

### Ping - Test Connectivity 

**The ping command is an IPv4 and IPv6 testing utility that uses ICMP echo request and echo reply messages to test connectivity between hosts and provides a summary that includes the success rate and average round-trip time to the destination.**** 
**
If a reply is not received within the timeout, ping provides a message indicating that a response was not received. 

It is common for the first ping to timeout if address resolution (ARP or ND) needs to be performed before sending the ICMP Echo Request.

>[!Note]- Ping
>![[Pasted image 20240509012553.png]]

Ping can be used to test the internal configuration of IPv4 or IPv6 on the local host. To do this, ping the local loopback address of 127.0.0.1 for IPv4 (::1 for IPv6). 

A response from 127.0.0.1 for IPv4, or ::1 for IPv6, indicates that IP is properly installed on the host. 

An error message indicates that TCP/IP is not operational on the host.

>[!Note]- Ping example
>![[Pasted image 20240509013149.png]]

**The ping command can be used to test the ability of a host to communicate on the local network.**

The default gateway address is most often used because the router is normally always operational 
- A successful ping to the defualt gateway indicates that the host and the router interface serving as the default gateway are both operational on the local network. 
- If the default gateway address does not respond, a ping can be sent to the IPaddress of another host on the local network that is known to be operational 

### Ping a remote host

**Ping can also be used to test the ability of a local host to communicate across an internetwork.**

A local host can ping a host on a remote network. A successful ping accross the internetwork confirms communciation on the local network. 

**Note:** Many network administrators limit or prohibit the entry of ICMP messages therefore the lack of a ping response could be due to security reasons. 

>[!Note]- Remote host ping
>![[Pasted image 20240509083713.png]]

### Traceroute - Test the Path 

**Traceroute (tracert)** is a utiility that is used to test the path between two hosts and provide a list of hops that were successfully reached along that path 

Traceroute provides round-trip time for each hop along the path and indicates if a hop fails to respond. An asterisk is used to indeicate a lost or unreplied packet. 

This information can be used to locate a problematic router in the path or may indicate that the router is configured not to reply. 

**Note:** Traceroute makes use of a function of the TTL field in IPv4 and the Hop Limit field in IPv6 in the Layer 3 headers, along with the ICMP Time Exceed message. 

>[!Note]- Traceroute
>![[Pasted image 20240509085018.png]]

The first message sent from traceroute will have a TTL field value of 1. This causes the TTL to time out at the first router. This router then responds with a ICMPv4 Time Exceed message. 

Traceroute then progressively increments the TTL field (2,3,4...) for each sequence of messages. This provides the trace with the address of each hop as the packets time out further down the path. 

The TTL field continues to be increased until the destination is reached, or it is incremented to a predefined maximum. 

>[!Note]- Traceroute 
>![[Pasted image 20240509085234.png]]

**Video:** https://youtu.be/up3bcBLZS74?si=MB3GGtsbhE9rww1p
## Transportation of Data

### Role of the Transport Layer

The transport layer is: 
- responsible for logical communications between applications running on different hosts. 
- The link between the application layer and the lower layers that are responsible for network transmission

>[!Note]- Transport Layer
>![[Pasted image 20240509085650.png]]

### Transport Layer Responsibilities 

The transport layer has the following responsibilities 
- Tracking individual conversations
- Segmenting data and reassembling segmetns 
- Adds header information
- Identify, separate, and manage multiple conversatios
- Uses segmentation and multiplexing to enable different communication conversations to be interleaved on the sane network. 

>[!Note]- Responsibilities 
>![[Pasted image 20240509085818.png]]

### Transport Layer Protocols 

- IP does not specify how the delivery or transportation of the packets takes place.
- Transport layer protocols specify how to transfer messages between hosts, and are responsible for managing reliability requirements of a conversation. 
- The transport layer includes the TCP and UDP protocols 

>[!Note]- Transport Layer protocols 
>![[Pasted image 20240509090237.png]]

### Transmission Control Protocol 

TCP provides reliability and flow control. TCP basic operations: 
- Number and track data segments transmitted to a specific host from a specific application 
- Acknowledge received data 
- Retransmit any unacknowledged data after a certain amount of time 
- Sequence data that might arrive in wrong order
- Send data at an efficient rate that is acceptable by the receiver

>[!Note]- Transmission Control Protocol 
>![[Pasted image 20240509090501.png]]


### User Datagram Protocol (UDP)

UDP provides the basic functions for delivering datagrams between the appropriate applications, with very little overhead and data checking. 
- UDP is a connectionless protocol
- UDP is known as a best-effort delivery protocol because there is no acknowledgement that the data is received at the destination

>[!Note]- User Datagram Protocol
>![[Pasted image 20240509092535.png]]

### The Right Transport Layer Protocol for the Right Application 

UDP is also used by request-and-reply applications where the data is minimal, and retransmission can be done quickly. 

If it is important that all the data arrives and that it can be processed in its proper sequence, TCP is used as the transport protocol. 

>[!Note] UDP and TCP 
>![[Pasted image 20240509093400.png]]

### TCP Features 

**Establishes a Session** - TCP is a connection-oriented protocol that negotiates and establishes a permanent connection (or session) between source and destination devices prior to forwarding any traffic. 

**Ensures Reliable Delievery** - For many reasons, it is possible for a segment to become corrupted or lost completely, as it is transmitted over the network. TCP ensures that each segment that is send by the source arrives at the destination. 

**Provides Same-Order Delivery** - Because networks may provide multiple routes that can have different transmission rates, data can arrive in the wrong order. 

**Supports Flow Control**- Network hosts have limited resources (i.e. memory and processing power). When TCP is aware that these resources are overtaxed, it can request that the sending application reduce the rate of data flow.

### TCP Header

TCP is a stateful protocol which means it keeps track of the state of the communication session. 

TCP records which informaiton it has sent, and which infromation has been acknowledged 

>[!Note]- TCP Header
>![[Pasted image 20240509094652.png]]

### TCP Header Fields

>[!Note]- TCP Header Fields
>![[Pasted image 20240509094947.png]]

### Applications that use TCP 

TCP handles all tasks associated with diving the data stream into segments, providing reliability, controlling data flow, and reordering segments 

>[!Note]- TCP applications
>![[Pasted image 20240509095115.png]]


### UDP Overview 

UDP features include the following 
- Data is reconstructed in the order that is received
- Any segments that are lost are not resent 
- There is no session establishment 
- The sending is not informed about resource availability 

### UDP Header

The UDP header is far simpler than the TCP header because it only has four fields and requries 8 bytes (i.e. 64 bits) 

>[!Note]- UDP Header
>![[Pasted image 20240509095640.png]]

### UDP Header fields

>[!Note]- UDP Header Fields
>![[Pasted image 20240509095732.png]]

### Applications that use UDP 
- Live video and multimedia applications - These applications can tolerate some data loss but require little or no delay. Examples include VoIP and live streaming video. 
- Simple request and reply applications - Applications with simple transactions where a host sends a request and may or may not receive a reply. Examples include DNS and DHCP. 
- Applications that handle reliability themselves - Unidirectional communications where flow control error detection, acknowledgements, and error recovery is not required, or can be handled by the application, Examples include SNMP and TFTP. 

**Video:** https://youtu.be/uwoD5YsGACg?si=qdqqDIVMSYvDxZ2F
## Port Numbers

### Multiple Separate Communications

TCP and UDP transport layer protocols use port numbers to manage multiple, simultaneous conversations. 

The source port number is associated with the originating application on the local host whereas the destination port number is associated with the destination application on the remote host.

>[!Note]- Source Port and Destination port
>![[Pasted image 20240509100417.png]]

### Socket Pairs 

The source and destination ports are placed within the segment. 

The segments are then encapsulated within an IP packet. 

The combination of the source IP address and source port number, or the destination IP address and destination port number is known as a socket. 

Sockets enable multiple processes, running on a client, to distinguish themselves from each other, and multiple connections to a server process to be distinguished from each other.

>[!Note]- Socket pairs
>![[Pasted image 20240509100451.png]]

### Port Number Groups

| Port Group                   | Number Range     | Description                                                                                                                                                                                                                                                                                                                                                                                       |
| ---------------------------- | ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Well-known Ports             | 0 to 1,023       | •These port numbers are reserved for common or popular services and applications such as web browsers, email clients, and remote access clients. <br><br>•Defined well-known ports for common server applications enables clients to easily identify the associated service required.                                                                                                             |
| Registered ports             | 1,024 to 49,151  | •These port numbers are assigned by IANA to a requesting entity to use with specific processes or applications. <br><br>•These processes are primarily individual applications that a user has chosen to install, rather than common applications that would receive a well-known port number. <br><br>•For example, Cisco has registered port 1812 for its RADIUS server authentication process. |
| Private and/or Dynamic ports | 48,152 to 65,535 | These ports are also known as ephemeral ports. <br><br>•The client’s OS usually assign port numbers dynamically when a connection to a service is initiated. <br><br>•The dynamic port is then used to identify the client application during communication.                                                                                                                                      |

>[!Note]- Well-Known Port Numbers
>![[Pasted image 20240509100958.png]]

### Netstat Command

Unexplained TCP connections can pose a major security threat. Netstat is an important tool to verify connections.

>[!Note]- Netstat
>![[Pasted image 20240509101025.png]]

### TCP Server Processes 

Each application process running on a server is configured to use a port number. 
• An individual server cannot have two services assigned to the same port number within the same transport layer services. 

• An active server application assigned to a specific port is considered open, which means that the transport layer accepts, and processes segments addressed to that port. 

• Any incoming client request addressed to the correct socket is accepted, and the data is passed to the server application.

>[!Note]- TCP Server Processes 
>![[Pasted image 20240509101104.png]]

### TCP connection establishment

Step 1: The initiating client requests a client-to-server communication session with the server. 

Step 2: The server acknowledges the client-to-server communication session and requests a server-to-client communication session. 

Step 3: The initiating client acknowledges the server-to-client communication session

>[!Note]- Connection Establishment
>![[Pasted image 20240509101147.png]]

### Session termination

Step 1: When the client has no more data to send in the stream, it sends a segment with the FIN flag set. 

Step 2: The server sends an ACK to acknowledge the receipt of the FIN to terminate the session from client to server. 

Step 3: The server sends a FIN to the client to terminate the server-to-client session. 

Step 4: The client responds with an ACK to acknowledge the FIN from the server.

>[!Note]- Session Termination
>![[Pasted image 20240509101208.png]]

### TCP Three-Way Handshake Analysis 

Functions of the Three-Way Handshake: 

• It establishes that the destination device is present on the network. 
• It verifies that the destination device has an active service and is accepting requests on the destination port number that the initiating client intends to use. 
• It informs the destination device that the source client intends to establish a communication session on that port number. 

After the communication is completed the sessions are closed, and the connection is terminated. The connection and session mechanisms enable TCP reliability function.


The six control bit flags are as follows: 
• **URG** - Urgent pointer field significant 
• **ACK** - Acknowledgment flag used in connection establishment and session termination • **PSH** - Push function 
• **RST** - Reset the connection when an error or timeout occurs 
• **SYN** - Synchronize sequence numbers used in connection establishment 
• **FIN** - No more data from sender and used in session termination

>[!Note] 
>![[Pasted image 20240509101940.png]]


### TCP Reliability - Guaranteed and Ordered Delievery 

TCP can also help maintain the flow of packets so that devices do not become overloaded. 

• There may be times when TCP segments do not arrive at their destination or arrive out of order. 

• All the data must be received and the data in these segments must be reassembled into the original order.

• Sequence numbers are assigned in the header of each packet to achieve this goal.
>[!Note]- Different Segments on Different routes
>![[Pasted image 20240509102337.png]]

### TCP Reliability - Data Loss aand Retransmission

No matter how well designed a network is, data loss occasionally occurs. 

TCP provides methods of managing these segment losses. Among these is a mechanism to retransmit segments for unacknowledged data.

>[!Note]- Reliability 
>![[Pasted image 20240509102426.png]]

Host operating systems today typically employ an optional TCP feature called selective acknowledgment (SACK), negotiated during the three-way handshake. 

If both hosts support SACK, the receiver can explicitly acknowledge which segments (bytes) were received including any discontinuous segments.


>[!Note]- Retransmission
>![[Pasted image 20240509102522.png]]


### TCP Flow Control – Window Size and Acknowledgments

TCP also provides mechanisms for flow control as follows: 

• Flow control is the amount of data that the destination can receive and process reliably. • Flow control helps maintain the reliability of TCP transmission by adjusting the rate of data flow between source and destination for a given session.

>[!Note]- Window Size and Acknowledgments
>![[Pasted image 20240509102657.png]]

### TCP Flow Control – Maximum Segment Size

Maximum Segment Size (MSS) is the maximum amount of data that the destination device can receive. 

• A common MSS is 1,460 bytes when using IPv4. 
• A host determines the value of its MSS field by subtracting the IP and TCP headers from the Ethernet maximum transmission unit (MTU), which is 1500 bytes be default. 
• 1500 minus 40 (20 bytes for the IPv4 header and 20 bytes for the TCP header) leaves 1460 bytes.

>[!Note]- Maximum Segment Size 
>![[Pasted image 20240509103000.png]]

### TCP Flow Control – Congestion Avoidance

When congestion occurs on a network, it results in packets being discarded by the overloaded router. To avoid and control congestion, TCP employs several congestion handling mechanisms, timers, and algorithms.

>[!Note]- Congestion Avoidance 
>![[Pasted image 20240509103330.png]]

## UDP Communication

### UDP Low Overhead versus Reliability

UDP does not establish a connection. UDP provides low overhead data transport because it has a small datagram header and no network management traffic.
>[!Note]- Reliability 
>![[Pasted image 20240509103501.png]]

### UDP Datagram Reassembly

UDP does not track sequence numbers the way TCP does. 

• UDP has no way to reorder the datagrams into their transmission order. 

• UDP simply reassembles the data in the order that it was received and forwards it to the application.

>[!Note]- Datagram Reassembly 
>![[Pasted image 20240509103559.png]]

### UDP Server Processes and Requests

UDP-based server applications are assigned well-known or registered port numbers. UDP receives a datagram destined for one of these ports, it forwards the application data to the appropriate application based on its port number.

>[!Note]- Processes and Requests
>![[Pasted image 20240509103632.png]]

### UDP Client Processes

The UDP client process dynamically selects a port number from the range of port numbers and uses this as the source port for the conversation. 

• The destination port is usually the well-known or registered port number assigned to the server process. 

• After a client has selected the source and destination ports, the same pair of ports are used in the header of all datagrams in the transaction.
>[!Note]- Client Processes 
>![[Pasted image 20240509103714.png]]


## Application, Presentation, and Session

### Application layer

The presentation layer has three primary functions: 
- Formatting, or presenting, data at the source device into a compatible format for receipt by the destination device 
- Compressing data in a way that can be decompressed by the destination device
- Encrypting data for transmission and decrypting data upon receipt 
 
The session layer functions: 
- It creates and maintains dialogs between source and destination applications. 
- It handles the exchange of information to initiate dialogs, keep them active, and to restart sessions that are disrupted or idle for a long period of time.

### TCP/IP Application Layer Protocols 

- The TCP/IP application protocols specify the format and control information necessary for many common internet communication functions.
- Application layer protocols are used by both the source and destination devices during a communication session.
- For the communications to be successful, the application layer protocols that are implemented on the source and destination host must be compatible.

| Name System DNS - Domain Name System (or Service)              | Host Config DHCP - Dynamic Host Configuration Protocol               | Web HTTP - Hyper Text Transfer Protocol                                                                            |
| -------------------------------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| TCP, UDP client 53                                             | UDP client 68, server 67                                             | TCP 80, 8080                                                                                                       |
| Translates domain names, such as cisco.com, into IP addresses. | Dynamically assigns IP addresses to be re-used when no longer needed | A set of rules for exchanging text, graphic images, sound, video, and other multimedia files on the World Wide Web |

### Client-Server Model

- Client and server processes are considered to be in the application layer. 
- In the client/server model, the device requesting the information is called a client and the device responding to the request is called a server. 
- Application layer protocols describe the format of the requests and responses between clients and servers.

>[!Note]- Client Server Model 
>![[Pasted image 20240517092408.png]]

### Peer-to-Peer Networks

- In a peer-to-peer (P2P) network, two or more computers are connected via a network and can share resources (such as printers and files) without having a dedicated server. 
- Every connected end device (known as a peer) can function as both a server and a client. 
- One computer might assume the role of server for one transaction while simultaneously serving as a client for another. The roles of client and server are set on a per request basis.

>[!Note]- Peer to Peer
>![[Pasted image 20240517092717.png]]

### Peer-to-Peer Applications

- A P2P application allows a device to act as both a client and a server within the same communication. 
- Some P2P applications use a hybrid system where each peer accesses an index server to get the location of a resource stored on another peer.
>[!Note]- Peer to Peer Applications 
>![[Pasted image 20240517092804.png]]

### Common P2P Applications

Common P2P Applications With P2P applications, each computer in the network that is running the application can act as a client or a server for the other computers in the network that are also running the application. 

Common P2P networks include the following:
- BitTorrent 
- Direct Connect 
- eDonkey
- Freenet

>[!Note]- Torrent 
>![[Pasted image 20240517092916.png]]


### Hpyertext Transfer protocol and Hypertext Markup Language

When a web address or Uniform Resource Locator (URL) is typed into a web browser, the web browser establishes a connection to the web service. The web service is running on the server that is using the HTTP protocol. 

To better understand how the web browser and web server interact, examine how a web page is opened in a browser

**Step 1:**
The browser interprets the three parts of the URL: 
- http (the protocol or scheme) 
- www.cisco.com (the server name) • index.html (the specific filename requested)
>[!Note]- Step 1
>![[Pasted image 20240517093125.png]]

**Step 2:**

The browser then checks with a name server to convert www.cisco.com into a numeric IP address, which it uses to connect to the server. 

The client initiates an HTTP request to a server by sending a GET request to the server and asks for the index.html file.

>[!Note]- Step 2
>![[Pasted image 20240517093205.png]]

**Step 3:**

In response to the request, the server sends the HTML code for this web page to the browser.

>[!Note]- Step 3 
>![[Pasted image 20240517093228.png]]

**Step 4:**

The browser deciphers the HTML code and formats the page for the browser window.

>[!Note]- Step 4
>![[Pasted image 20240517093258.png]]

### HTTP and HTTPS

HTTP is a request/response protocol that specifies the message types used for that communication. 

The three common message types are GET, POST, and PUT:

- **GET** - This is a client request for data. A client (web browser) sends the GET message to the web server to request HTML pages. 
- **POST** - This uploads data files to the web server, such as form data. 
- **PUT** - This uploads resources or content to the web server, such as an image.

Note: HTTP is not a secure protocol. For secure communications sent across the internet, HTTPS should be used.

>[!Note]- HTTP
>![[Pasted image 20240517093557.png]]

### Email Protocols 

Email is a store-and-forward method of sending, storing, and retrieving electronic messages across a network. Email messages are stored in databases on mail servers. Email clients communicate with mail servers to send and receive email.

The email protocols used for operation are:
- Simple Mail Transfer Protocol (SMTP) – used to send mail. 
- Post Office Protocol (POP) & IMAP – used for clients to receive mail.

>[!Note]- Email Protocols
>![[Pasted image 20240517093655.png]]

### SMTP, POP and IMAP

- When a client sends email, the client SMTP process connects with a server SMTP process on well-known port 25. 
- After the connection is made, the client attempts to send the email to the server across the connection. 
- When the server receives the message, it either places the message in a local account, if the recipient is local, or forwards the message to another mail server for delivery. 
- The destination email server may not be online or may be busy. If so, SMTP spools messages to be sent at a later time.

**Note:** SMTP message formats require a message header (recipient email address & sender email address) and a message body.

>[!Note]- SMTP
>![[Pasted image 20240517093922.png]]

POP is used by an application to retrieve mail from a mail server. When mail is downloaded from the server to the client using POP the messages are then deleted on the server. 
- The server starts the POP service by passively listening on TCP port 110 for client connection requests. 
- When a client wants to make use of the service, it sends a request to establish a TCP connection with the server. 
- When the connection is established, the POP server sends a greeting. 
- The client and POP server then exchange commands and responses until the connection is closed or aborted
**Note:** Since POP does not store messages, it is not recommended for small businesses that need a centralized backup solution.

>[!Note] POP
>![[Pasted image 20240517094021.png]]

IMAP is another protocol that describes a method to retrieve email messages. 

- Unlike POP, when a user connects to an IMAP server, copies of the messages are downloaded to the client application. The original messages are kept on the server until manually deleted. 

- When a user decides to delete a message, the server synchronizes that action and deletes the message from the server.
>[!Note]- IMAP
>![[Pasted image 20240517094104.png]]

**Video:** https://youtu.be/SBaARws0hy4?si=JHCEDqgqBWJAWMUe
### Domain Name Service

Domain names were created to convert the numeric IP addresses into a simple, recognizable name. 

- Fully-qualified domain names (FQDNs), such as http://www.cisco.com, are much easier for people to remember than 198.133.219.25. 

- The DNS protocol defines an automated service that matches resource names with the required numeric network address. It includes the format for queries, responses, and data.

>[!Note]- Domain Name Service
>![[Pasted image 20240517094150.png]]


### DNS Message Format 

The DNS server stores different types of resource records that are used to resolve names. These records contain the name, address, and type of record.

Some of these record types are as follows: 
- A - An end device IPv4 address 
- NS - An authoritative name server 
- AAAA - An end device IPv6 address (pronounced quad-A) 
- MX - A mail exchange record

When a client makes a query, the server DNS process first looks at its own records to resolve the name. If it is unable to resolve the name by using its stored records, it contacts other servers to resolve the name. 

After a match is found and returned to the original requesting server, the server temporarily stores the numbered address in the event that the same name is requested again.

DNS uses the same message format between servers, consisting of a question, answer, authority, and additional information for all types of client queries and server responses, error messages, and transfer of resource record information.

![[Pasted image 20240517094319.png]]


### DNS Hierarchy 

DNS uses a hierarchical system to create a database to provide name resolution.
- Each DNS server maintains a specific database file and is only responsible for managing name-toIP mappings for that small portion of the entire DNS structure.
- When a DNS server receives a request for a name translation that is not within its DNS zone, the DNS server forwards the request to another DNS server within the proper zone for translation.

Examples of top-level domains:
- .com - a business or industry
- .org - a non-profit organization
- .au - Australia
>[!Note]- DNS Hierarchy 
>![[Pasted image 20240517094442.png]]

### The nsLookup Command

- Nslookup is a computer operating system utility that allows a user to manually query the DNS servers configured on the device to resolve a given host name. 
- This utility can also be used to troubleshoot name resolution issues and to verify the current status of the name servers. 
- When the nslookup command is issued, the default DNS server configured for your host is displayed. 
- The name of a host or domain can be entered at the nslookup prompt.

>[!Note]- nsLookup Command
>![[Pasted image 20240517094552.png]]

**Video:** https://youtu.be/mpQZVYPuDGU?si=46tSPp_uyOpNKqr2

### Dynamic Host Configuration Protocol 


- The Dynamic Host Configuration Protocol (DHCP) for IPv4 service automates the assignment of IPv4 addresses, subnet masks, gateways, and other IPv4 networking parameters. 
- DHCP is considered dynamic addressing compared to static addressing. Static addressing is manually entering IP address information. 
- When a host connects to the network, the DHCP server is contacted, and an address is requested. The DHCP server chooses an address from a configured range of addresses called a pool and assigns (leases) it to the host. 
- Many networks use both DHCP and static addressing. DHCP is used for general purpose hosts, such as end user devices. Static addressing is used for network devices, such as gateway routers, switches, servers, and printers.

**Note:** DHCP for IPv6 (DHCPv6) provides similar services for IPv6 clients. However, DHCPv6 does not provide a default gateway address. This can only be obtained dynamically from the Router Advertisement message of the router.

>[!Note]- DHCP 
>![[Pasted image 20240517094652.png]]

### DHCP Operation

The DHCP Process: 

- When an IPv4, DHCP-configured device boots up or connects to the network, the client broadcasts a DHCP discover (DHCPDISCOVER) message to identify any available DHCP servers on the network. 

- A DHCP server replies with a DHCP offer (DHCPOFFER) message, which offers a lease to the client. (If a client receives more than one offer due to multiple DHCP servers on the network, it must choose one.)

- The client sends a DHCP request (DHCPREQUEST) message that identifies the explicit server and lease offer that the client is accepting. 

- The server then returns a DHCP acknowledgment (DHCPACK) message that acknowledges to the client that the lease has been finalized. ▪ If the offer is no longer valid, then the selected server responds with a DHCP negative acknowledgment (DHCPNAK) message and the process must begin with a new DHCPDISCOVER message.

**Note:** DHCPv6 has a set of messages that is similar to those for DHCPv4. The DHCPv6 messages are SOLICIT, ADVERTISE, INFORMATION REQUEST, and REPLY.

>[!Note]- DHCP Operation
>![[Pasted image 20240517094756.png]]


**Video:** https://youtu.be/e6-TaH5bkjo?si=bsRkTxtVl4MCA0Iu
### File Transfer Protocol 

FTP was developed to allow for data transfers between a client and a server. An FTP client is an application which runs on a computer that is being used to push and pull data from an FTP server.


**Step 1** - The client establishes the first connection to the server for control traffic using TCP port 21. The traffic consists of client commands and server replies. 
**Step 2** - The client establishes the second connection to the server for the actual data transfer using TCP port 20. This connection is created every time there is data to be transferred. 
**Step 3** - The data transfer can happen in either direction. The client can download (pull) data from the server, or the client can upload (push) data to the server.

>[!Note]- FTP 
>![[Pasted image 20240517094921.png]]

**VIdeo:** https://youtu.be/tOj8MSEIbfA?si=nOU7ZtEvqFMx_ZUj
### Server Message Block 

The Server Message Block (SMB) is a client/server, request-response file sharing protocol. Servers can make their own resources available to clients on the network. 

Three functions of SMB messages: 

- Start, authenticate, and terminate sessions 

- Control file and printer access 

- Allow an application to send or receive messages to or from another device

Unlike the file sharing supported by FTP, clients establish a long-term connection to servers. After the connection is established, the user of the client can access the resources on the server as though the resource is local to the client host.

>[!Note]- Server Message Block 
>![[Pasted image 20240517095028.png]]


## Network Security Fundamentals

### Security Threats and Vulnerabilities 

### Types of Threats 

Attacks on a network can be devastating and can result in a loss of time and money due to damage, or theft of important information or assets. Intruders can gain access to a network through software vulnerabilities, hardware attacks, or through guessing someone's username and password. Intruders who gain access by modifying software or exploiting software vulnerabilities are called threat actors.

After the threat actor gains access to the network, four types of threats may arise: 
- Information Theft 
- Data Loss and manipulation 
- Identity Theft • Disruption of Service

Vulnerability is the degree of weakness in a network or a device. Some degree of vulnerability is inherent in routers, switches, desktops, servers, and even security devices. Typically, the network devices under attack are the endpoints, such as servers and desktop computers. There are three primary vulnerabilities or weaknesses: 

- Technological Vulnerabilities might include TCP/IP Protocol weaknesses, Operating System Weaknesses, and Network Equipment weaknesses. 

- Configuration Vulnerabilities might include unsecured user accounts, system accounts with easily guessed passwords, misconfigured internet services, unsecure default settings, and misconfigured network equipment. 

- Security Policy Vulnerabilities might include lack of a written security policy, politics, lack of authentication continuity, logical access controls not applied, software and hardware installation and changes not following policy, and a nonexistent disaster recovery plan.

All three of these sources of vulnerabilities can leave a network or device open to various attacks, including malicious code attacks and network attacks.

### Physical Security 

If network resources can be physically compromised, a threat actor can deny the use of network resources. The four classes of physical threats are as follows: 

- **Hardware threats** - This includes physical damage to servers, routers, switches, cabling plant, and workstations. 

- **Environmental threats** - This includes temperature extremes (too hot or too cold) or humidity extremes (too wet or too dry). 

- **Electrical threats** - This includes voltage spikes, insufficient supply voltage (brownouts), unconditioned power (noise), and total power loss. 

- **Maintenance threat**s - This includes poor handling of key electrical components (electrostatic discharge), lack of critical spare parts, poor cabling, and poor labeling. 

A good plan for physical security must be created and implemented to address these issues.

### Types of Malware 

Malware is short for malicious software. It is code or software specifically designed to damage, disrupt, steal, or inflict “bad” or illegitimate action on data, hosts, or networks. The following are types of malware: 

- Viruses - A computer virus is a type of malware that propagates by inserting a copy of itself into, and becoming part of, another program. It spreads from one computer to another, leaving infections as it travels. 

- Worms - Computer worms are similar to viruses in that they replicate functional copies of themselves and can cause the same type of damage. In contrast to viruses, which require the spreading of an infected host file, worms are standalone software and do not require a host program or human help to propagate. 

- Trojan Horses - It is a harmful piece of software that looks legitimate. Unlike viruses and worms, Trojan horses do not reproduce by infecting other files. They self-replicate. Trojan horses must spread through user interaction such as opening an email attachment or downloading and running a file from the internet.

### Reconnaissance Attacks 

In addition to malicious code attacks, it is also possible for networks to fall prey to various network attacks. Network attacks can be classified into three major categories: 

- Reconnaissance attacks - The discovery and mapping of systems, services, or vulnerabilities. 

- Access attacks - The unauthorized manipulation of data, system access, or user privileges. 

- Denial of service - The disabling or corruption of networks, systems, or services. 

For reconnaissance attacks, external threat actors can use internet tools, such as the nslookup and whois utilities, to easily determine the IP address space assigned to a given corporation or entity. After the IP address space is determined, a threat actor can then ping the publicly available IP addresses to identify the addresses that are active.

### Access Attacks

Access attacks exploit known vulnerabilities in authentication services, FTP services, and web services to gain entry to web accounts, confidential databases, and other sensitive information. 

Access attacks can be classified into four types: 
- Password attacks - Implemented using brute force, trojan horse, and packet sniffers 
- Trust exploitation - A threat actor uses unauthorized privileges to gain access to a system, possibly compromising the target. 
- Port redirection: - A threat actor uses a compromised system as a base for attacks against other targets. For example, a threat actor using SSH (port 22) to connect to a compromised host A. Host A is trusted by host B and, therefore, the threat actor can use Telnet (port 23) to access it. 
- Man-in-the middle - The threat actor is positioned in between two legitimate entities in order to read or modify the data that passes between the two parties.

### Denial of Service Attacks

Denial of service (DoS) attacks are the most publicized form of attack and among the most difficult to eliminate. However, because of their ease of implementation and potentially significant damage, DoS attacks deserve special attention from security administrators. 
- DoS attacks take many forms. Ultimately, they prevent authorized people from using a service by consuming system resources. To help prevent DoS attacks it is important to stay up to date with the latest security updes for operating systems and applications. 
- DoS attacks are a major risk because they interrupt communication and cause significant loss of time and money. These attacks are relatively simple to conduct, even by an unskilled threat actor. 
- A DDoS is similar to a DoS attack, but it originates from multiple, coordinated sources. For example, a threat actor builds a network of infected hosts, known as zombies. A network of zombies is called a botnet. The threat actor uses a command and control (CnC) program to instruct the botnet of zombies to carry out a DDoS attack.

### The Defense-in-Depth Approach 

To mitigate network attacks, you must first secure devices including routers, switches, servers, and hosts. Most organizations employ a defense-indepth approach (also known as a layered approach) to security. This requires a combination of networking devices and services working in tandem. 

Several security devices and services are implemented to protect an organization’s users and assets against TCP/IP threats: 
- VPN 
- ASA Firewall 
- IPS 
- ESA/WSA 
- AAA Server
>[!Note]- Defense-in-Depth Approach
>![[Pasted image 20240517102028.png]]

### Keep Backups

Backing up device configurations and data is one of the most effective ways of protecting against data loss. Backups should be performed on a regular basis as identified in the security policy. Data backups are usually stored offsite to protect the backup media if anything happens to the main facility. The table shows backup considerations and their descriptions.

>[!Note]- Keep Backups 
>![[Pasted image 20240517102100.png]]


### Upgrade, Update, and Patch 
As new malware is released, enterprises need to keep current with the latest versions of antivirus software. 
- The most effective way to mitigate a worm attack is to download security updates from the operating system vendor and patch all vulnerable systems. 
- One solution to the management of critical security patches is to make sure all end systems automatically download updates.

### Authentication, Authorization, and Accounting

Authentication, authorization, and accounting (AAA, or “triple A”) network security services provide the primary framework to set up access control on network devices. 
- AAA is a way to control who is permitted to access a network (authenticate), what actions they perform while accessing the network (authorize), and making a record of what was done while they are there (accounting). 
- The concept of AAA is similar to the use of a credit card. The credit card identifies who can use it, how much that user can spend, and keeps account of what items the user spent money on.
>[!Note]- AAA
>![[Pasted image 20240517102201.png]]

### Firewalls

Network firewalls reside between two or more networks, control the traffic between them, and help prevent unauthorized access. 

A firewall could allow outside users controlled access to specific services. For example, servers accessible to outside users are usually located on a special network referred to as the demilitarized zone (DMZ). The DMZ enables a network administrator to apply specific policies for hosts connected to that network.

>[!Note]- Firewalls
>![[Pasted image 20240517102458.png]]

### Types of Firewalls

Firewall products come packaged in various forms. These products use different techniques for determining what will be permitted or denied access to a network. They include the following: 
- Packet filtering - Prevents or allows access based on IP or MAC addresses 
- Application filtering - Prevents or allows access by specific application types based on port numbers 
- URL filtering - Prevents or allows access to websites based on specific URLs or keywords 
- Stateful packet inspection (SPI) - Incoming packets must be legitimate responses to requests from internal hosts. Unsolicited packets are blocked unless permitted specifically. SPI can also include the capability to recognize and filter out specific types of attacks, such as denial of service (DoS).

### Endpoint security 
An endpoint, or host, is an individual computer system or device that acts as a network client. Common endpoints are laptops, desktops, servers, smartphones, and tablets. 

Securing endpoint devices is one of the most challenging jobs of a network administrator because it involves human nature. A company must have well-documented policies in place and employees must be aware of these rules. 

Employees need to be trained on proper use of the network. Policies often include the use of antivirus software and host intrusion prevention. More comprehensive endpoint security solutions rely on network access control.

### Cisco AutoSecure 

The security settings are set to the default values when a new operating system is installed on a device. In most cases, this level of security is inadequate. For Cisco routers, the Cisco AutoSecure feature can be used to assist securing the system. 

In addition, there are some simple steps that should be taken that apply to most operating systems: 
- Default usernames and passwords should be changed immediately. 
- Access to system resources should be restricted to only the individuals that are authorized to use those resources. 
- Any unnecessary services and applications should be turned off and uninstalled when possible. 
- Often, devices shipped from the manufacturer have been sitting in a warehouse for a period of time and do not have the most up-to-date patches installed. It is important to update any software and install any security patches prior to implementation.

### Passwords 

To protect network devices, it is important to use strong passwords. Here are standard guidelines to follow: 
- Use a password length of at least eight characters, preferably 10 or more characters. 
- Make passwords complex. Include a mix of uppercase and lowercase letters, numbers, symbols, and spaces, if allowed. 
- Avoid passwords based on repetition, common dictionary words, letter or number sequences, usernames, relative or pet names, biographical information, such as birthdates, ID numbers, ancestor names, or other easily identifiable pieces of information. 
- Deliberately misspell a password. For example, Smith = Smyth = 5mYth or Security = 5ecur1ty. 
- Change passwords often. If a password is unknowingly compromised, the window of opportunity for the threat actor to use the password is limited. 
- Do not write passwords down and leave them in obvious places such as on the desk or monitor. 

On Cisco routers, leading spaces are ignored for passwords, but spaces after the first character are not. Therefore, one method to create a strong password is to use the space bar and create a phrase made of many words. This is called a passphrase. A passphrase is often easier to remember than a simple password.Itisalsolongerandhardertoguess.

### Additional Password Security

There are several steps that can be taken to help ensure that passwords remain secret on a Cisco router and switch including these:
- Encrypt all plaintext passwords with the service password-encryption command.
- Set a minimum acceptable password length with the security passwords minlength command.
- Deter brute-force password guessing attacks with the login blockfor # attempts # within # command.
- Disable an inactive privileged EXEC mode access after a specified amount of time with the exec-timeout command.
>[!Note]- Additional Password Security 
>![[Pasted image 20240517102841.png]]

### Enable SSH

It is possible to configure a Cisco device to support SSH using the following steps: 
1. Configure a unique device hostname. A device must have a unique hostname other than the default. 
2. Configure the IP domain name. Configure the IP domain name of the network by using the global configuration mode command ip-domain name. 
3. Generate a key to encrypt SSH traffic. SSH encrypts traffic between source and destination. However, to do so, a unique authentication key must be generated by using the global configuration command crypto key generate rsa general-keys modulus bits. The modulus bits determines the size of the key and can be configured from 360 bits to 2048 bits. The larger the bit value, the more secure the key. However, larger bit values also take longer to encrypt and decrypt information. The minimum recommended modulus length is 1024 bits. 
4. Verify or create a local database entry. Create a local database username entry using the username global configuration command. 
5. Authenticate against the local database. Use the login local line configuration command to authenticate the vty line against the local database. 
6. Enable vty inbound SSH sessions. By default, no input session is allowed on vty lines. You can specify multiple input protocols including Telnet and SSH using the transport input [ssh | telnet] command.

### Disable Unused Services

Cisco routers and switches start with a list of active services that may or may not be required in your network. Disable any unused services to preserve system resources, such as CPU cycles and RAM, and prevent threat actors from exploiting these services.
- The type of services that are on by default will vary depending on the IOS version. For example, IOS-XE typically will have only HTTPS and DHCP ports open. You can verify this with the show ip ports all command. 
- IOS versions prior to IOS-XE use the show control-plane host openports command.
### Small Network Topologies

- The majority of businesses are small most of the business networks are also small.

- A small network design is usually simple.

- Small networks typically have a single WAN connection provided by DSL, cable, or an Ethernet connection.

- Large networks require an IT department to maintain, secure, and troubleshoot network devices and to protect organizational data. Small networks are managed by a local IT technician or by a contracted professional.

### Device selection for small network

Like large networks, small networks require planning and design to meet user requirements. Planning ensures that all requirements, cost factors, and deployment options are given due consideration. One of the first design considerations is the type of intermediary devices to use to support the network. 

Factors that must be considered when selecting network devices include: 
- cost 
- speed and types of ports/interfaces 
- expandability 
- operating system features and services

### IP Addressing for a Small Network 

When implementing a network, create an IP addressing scheme and use it. All hosts and devices within an internetwork must have a unique address. Devices that will factor into the IP addressing scheme include the following: 
- End user devices - The number and type of connections (i.e., wired, wireless, remote access) 
- Servers and peripherals devices (e.g., printers and security cameras) 
- Intermediary devices including switches and access points.

It is recommended that you plan, document, and maintain an IP addressing scheme based on device type. The use of a planned IP addressing scheme makes it easier to identify a type of device and to troubleshoot problems.


### Redundancy in a Small Network 

In order to maintain a high degree of reliability, redundancy is required in the network design. Redundancy helps to eliminate single points of failure. 

Redundancy can be accomplished by installing duplicate equipment. It can also be accomplished by supplying duplicate network links for critical areas.

>[!Note]- Redundancy in a Small Network 
>![[Pasted image 20240517110845.png]]

### Traffic Management 
The goal for a good network design is to enhance the productivity of the employees and minimize network downtime. 
- The routers and switches in a small network should be configured to support real-time traffic, such as voice and video, in an appropriate manner relative to other data traffic. A good network design will implement quality of service (QoS). 
- Priority queuing has four queues. The highpriority queue is always emptied first.
>[!Note]- Traffic management
>![[Pasted image 20240517111029.png]]


### Small Network Applications and Protocols

### Common Applications

After you have set it up, your network still needs certain types of applications and protocols in order to work. The network is only as useful as the applications that are on it. 

There are two forms of software programs or processes that provide access to the network: 

- Network Applications: Applications that implement application layer protocols and are able to communicate directly with the lower layers of the protocol stack. 

- Application Layer Services: For applications that are not network-aware, the programs that interface with the network and prepare the data for transfer.

### Common Protocols

Network protocols support the applications and services used by employees in a small network. 

- Network administrators commonly require access to network devices and servers. The two most common remote access solutions are Telnet and Secure Shell (SSH). 

- Hypertext Transfer Protocol (HTTP) and Hypertext Transfer Protocol Secure (HTTP) are used between web clients and web servers. 

- Simple Mail Transfer Protocol (SMTP) is used to send email, Post Office Protocol (POP3) or Internet Mail Access Protocol (IMAP) are used by clients to retrieve email. 

- File Transfer Protocol (FTP) and Security File Transfer Protocol (SFTP) are used to download and upload files between a client and an FTP server. 

- Dynamic Host Configuration Protocol (DHCP) is used by clients to acquire an IP configuration from a DHCP Server. • The Domain Name Service (DNS) resolves domain names to IP addresses. 

Note: A server could provide multiple network services. For instance, a server could be an email, FTP and SSH server.

These network protocols comprise the fundamental toolset of a network professional, defining: 
- Processes on either end of a communication session. 
- Types of messages. 
- Syntax of the messages. 
- Meaning of informational fields. 
- How messages are sent and the expected response. 
- Interaction with the next lower layer. 

Many companies have established a policy of using secure versions (e.g., SSH, SFTP, and HTTPS) of these protocols whenever possible.

### Voice and Video Applications

- Businesses today are increasingly using IP telephony and streaming media to communicate with customers and business partners, as well as enabling their employees to work remotely.
- The network administrator must ensure the proper equipment is installed in the network and that the network devices are configured to ensure priority delivery.
- The factors that a small network administrator must consider when supporting real-time applications:
	- Infrastructure - Does it have the capacity and capability to supporreal-time applications? 
	- VoIP - VoIP is typically less expensive than IP Telephony, but at thcost of quality and features. 
	- IP Telephony - This employs dedicated servers form call control ansignaling. 
	- Real-Time Applications - The network must support Quality of Service (QoS) mechanisms to minimize latency issues. Real-Time Transport Protocol (RTP) and RealTime Transport Control Protocol (RTCP) and two protocols that support real-time applications

### Scale to Larger Networks

### Small Network Growth

Growth is a natural process for many small businesses, and their networks must grow accordingly. Ideally, the network administrator has enough lead-time to make intelligent decisions about growing the network in alignment with the growth of the company. 

To scale a network, several elements are required: 
- Network documentation - Physical and logical topology 
- Device inventory - List of devices that use or comprise the network 
- Budget - Itemized IT budget, including fiscal year equipment purchasing budget 
- Traffic analysis - Protocols, applications, and services and their respective traffic requirements should be documented 
These elements are used to inform the decision-making that accompanies the scaling of a small network.

### Protocol Analysis

It is important to understand the type of traffic that is crossing the network as well as the current traffic flow. There are several network management tools that can be used for this purpose. 

To determine traffic flow patterns, it is important to do the following: 
- Capture traffic during peak utilization times to get a good representation of the different traffic types. 
- Perform the capture on different network segments and devices as some traffic will be local to a particular segment. 
- Information gathered by the protocol analyzer is evaluated based on the source and destination of the traffic, as well as the type of traffic being sent. • This analysis can be used to make decisions on how to manage the traffic more efficiently.

### Employee Network Utilization

Many operating systems provide built-in tools to display such network utilization information. These tools can be used to capture a “snapshot” of information such as the following: 
- OS and OS Version 
- CPU utilization • RAM utilization 
- Drive utilization
- Non-Network applications 
- Network applications 

Documenting snapshots for employees in a small network over a period of time is very useful to identify evolving protocol requirements and associated traffic flows.

### Verify Connectivity with Ping 

Whether your network is small and new, or you are scaling an existing network, you will always want to be able to verify that your components are properly connected to each other and to the internet. 

- The ping command, available on most operating systems, is the most effective way to quickly test Layer 3 connectivity between a source and destination IP address. 

- The ping command uses the Internet Control Message Protocol (ICMP) echo (ICMP Type 8) and echo reply (ICMP Type 0) messages.

>[!Note]- Verify Connectivity with Ping 
>![[Pasted image 20240517224953.png]]

On a Windows 10 host, the ping command sends four consecutive ICMP echo messages and expects four consecutive ICMP echo replies from the destination. The IOS ping sends five ICMP echo messages and displays an indicator for each ICMP echo reply received.

IOS Ping Indicators are as follows:

>[!Note]- IOS Ping Indicators
>![[Pasted image 20240517225235.png]]

### Extended Ping 

The Cisco IOS offers an "extended" mode of the ping command. 

Extended ping is entered in privileged EXEC mode by typing ping without a destination IP address. You will then be given several prompts to customize the extended ping. 

Note: Pressing Enter accepts the indicated default values. The ping ipv6 command is used for IPv6 extended pings.

>[!Note]- Extended Ping
>![[Pasted image 20240517225504.png]]

### Verify Connectivity with Traceroute

The ping command is useful to quickly determine if there is a Layer 3 connectivity problem. However, it does not identify where the problem is located along the path. 
- Traceroute can help locate Layer 3 problem areas in a network. A trace returns a list of hops as a packet is routed through a network. 
- The syntax of the trace command varies between operating systems.

>[!Note]- Verify Connectivity with Traceroute
>![[Pasted image 20240517225547.png]]

- The following is a sample output of tracert command on a Windows 10 host. Note: Use Ctrl-C to interrupt a tracert in Windows. 
- The only successful response was from the gateway on R1. Trace requests to the next hop timed out as indicated by the asterisk, meaning that the next hop router did not respond or there is a failure in the network path. In this example there appears to be a problem between R1 and R2.
>[!Note]- Tracert
>![[Pasted image 20240517225630.png]]

>[!Note]- The following are sample outputs of traceroute command from R1:
>![[Pasted image 20240517225708.png]]
>On the left, the trace validated that it could successfully reach PC B. 
>On the right, the 10.1.1.10 host was not available, and the output shows asterisks where replies timed out. Timeouts indicate a potential network problem.
> Use Ctrl-Shift-6 to interrupt a traceroute in Cisco IOS.

### Extended Traceroute

Like the extended ping command, there is also an extended traceroute command. It allows the administrator to adjust parameters related to the command operation. 

The Windows tracert command allows the input of several parameters through options in the command line. However, it is not guided like the extended traceroute IOS command. The following output displays the available options for the Windows tracert command:

>[!Note]- Extended Traceroute
>![[Pasted image 20240517225803.png]]


The Cisco IOS extended traceroute option enables the user to create a special type of trace by adjusting parameters related to the command operation. 

Extended traceroute is entered in privileged EXEC mode by typing traceroute without a destination IP address. IOS will guide you through the command options by presenting a number of prompts related to the setting of all the different parameters. 

Note: Pressing Enter accepts the indicated default values

>[!Note]- Extended Traceroute
>![[Pasted image 20240517230642.png]]

### Network Baseline 

- One of the most effective tools for monitoring and troubleshooting network performance is to establish a network baseline. 

- One method for starting a baseline is to copy and paste the results from an executed ping, trace, or other relevant commands into a text file. These text files can be time stamped with the date and saved into an archive for later retrieval and comparison. 

- Among items to consider are error messages and the response times from host to host. 

- Corporate networks should have extensive baselines; more extensive than we can describe in this course. Professional-grade software tools are available for storing and maintaining baseline information

### IP Configuration on a Windows Host 

In Windows 10, you can access the IP address details from the Network and Sharing Center to quickly view the four important settings: address, mask, router, and DNS. Or you can issue the ipconfig command at the command line of a Windows computer.

- Use the ipconfig /all command to view the MAC address, as well as a number of details regarding the Layer 3 addressing of the device. 

- If a host is configured as a DHCP client, the IP address configuration can be renewed using the ipconfig /release and ipconfig /renew commands. 

- The DNS Client service on Windows PCs also optimizes the performance of DNS name resolution by storing previously resolved names in memory. The ipconfig /displaydns command displays all of the cached DNS entries on a Windows computer system.
>[!Note]- IP Config on a Windows Host 
>![[Pasted image 20240517230828.png]]

### IP configuration on a Linux Host 

- Verifying IP settings using the GUI on a Linux machine will differ depending on the Linux distribution and desktop interface. 

- On the command line, use the ifconfig command to display the status of the currently active interfaces and their IP configuration. 

- The Linux ip address command is used to display addresses and their properties. It can also be used to add or delete IP addresses. 

Note: The output displayed may vary depending on the Linux distribution.

>[!Note]- IP Configuration on a Linux Host 
>![[Pasted image 20240517231327.png]]

### IP Configuration on a macOS Host

- In the GUI of a Mac host, open Network Preferences > Advanced to get the IP addressing information. 

- The ifconfig command can also be used to verify the interface IP configuration at the command line. 

- Other useful macOS commands to verify the host IP settings include networksetup -listallnetworkservices and the networksetup -getinfo.
>[!Note]- IP Confiugration on a MacOS Host
>![[Pasted image 20240517231507.png]]

### The arp Command 

The arp command is executed from the Windows, Linux, or Mac command prompt. The command lists all devices currently in the ARP cache of the host. 
- The arp -a command displays the known IP address and MAC address binding. The ARP cache only displays information from devices that have been recently accessed. 
- To ensure that the ARP cache is populated, ping a device so that it will have an entry in the ARP table. 
- The cache can be cleared by using the netsh interface ip delete arpcache command in the event the network administrator wants to repopulate the cache with updated information. 

Note: You may need administrator access on the host to be able to use the netsh interface ip delete arpcache command.

### Common show Commands Revisited

![[Pasted image 20240517231634.png]]
### The show cdp neighbors Command

CDP provides the following information about each CDP neighbor device:
- Device identifiers - The configured host name of a switch, router, or other device
- Address list - Up to one network layer address for each protocol supported
- Port identifier - The name of the local and remote port in the form of an ASCII character string, such as FastEthernet 0/0
- Capabilities list - Whether a specific device is a Layer 2 switch or a Layer 3 switch
- Platform - The hardware platform of the device. 

The show cdp neighbors detail command reveals the IP address of a neighboring device.

>[!Note]- show cdp neightbors Command
>![[Pasted image 20240517231754.png]]

### The show ip interface brief Command

One of the most frequently used commands is the show ip interface brief command. This command provides a more abbreviated output than the show ip interface command. It provides a summary of the key information for all the network interfaces on a router.

>[!Note]- show ip interface brief command
>![[Pasted image 20240517232025.png]]


### Basic Troubleshooting Approaches 

![[Pasted image 20240517232208.png]]


### Resolve or Escalate? 

- In some situations, it may not be possible to resolve the problem immediately. A problem should be escalated when it requires a manager decision, some specific expertise, or network access level unavailable to the troubleshooting technician.
- A company policy should clearly state when and how a technician should escalate a problem.

### The debug Command 

The IOS debug command allows the administrator to display OS process, protocol, mechanism and event messages in real-time for analysis. 
- All debug commands are entered in privileged EXEC mode. The Cisco IOS allows for narrowing the output of debug to include only the relevant feature or subfeature. Use debug commands only to troubleshoot specific problems. 
- To list a brief description of all the debugging command options, use the debug ? command in privileged EXEC mode at the command line. 
- To turn off a specific debugging feature, add the no keyword in front of the debug command 
- Alternatively, you can enter the undebug form of the command in privileged EXEC mode.
- To turn off all active debug commands at once, use the undebug all command. 
- Be cautious using some debug commands, as they may generate a substantial amount of output and use a large portion of system resources. The router could get so busy displaying debug messages that it would not have enough processing power to perform its network functions, or even listen to commands to turn off debugging.

### The terminal monitor Command
- debug and certain other IOS message output is not automatically displayed on remote connections. This is because log messages are prevented from being displayed on vty lines. 
- To display log messages on a terminal (virtual console), use the terminal monitor privileged EXEC command. To stop logging messages on a terminal, use the terminal no monitor privileged EXEC command

>[!Note]- The terminal monitor command
>![[Pasted image 20240517232529.png]]


### Duplex Operation and mismatch issues

- Interconnecting Ethernet interfaces must operate in the same duplex mode for best communication performance and to avoid inefficiency and latency on the link. 

- The Ethernet autonegotiation feature facilitates configuration, minimizes problems and maximizes link performance between two interconnecting Ethernet links. The connected devices first announce their supported capabilities and then choose the highest performance mode supported by both ends. 

- If one of the two connected devices is operating in full-duplex and the other is operating in half-duplex, a duplex mismatch occurs. While data communication will occur through a link with a duplex mismatch, link performance will be very poor. 

- Duplex mismatches are typically caused by a misconfigured interface or in rare instances by a failed autonegotiation. Duplex mismatches may be difficult to troubleshoot as the communication between devices still occurs.

### IP Addressing Issues on IOS Devices 

- Two common causes of incorrect IPv4 assignment are manual assignment mistakes or DHCPrelated issues. 

- Network administrators often have to manually assign IP addresses to devices such as servers and routers. If a mistake is made during the assignment, then communications issues with the device are very likely to occur. 

- On an IOS device, use the show ip interface or show ip interface brief commands to verify what IPv4 addresses are assigned to the network interfaces. For example, issuing the show ip interface brief command as shown would validate the interface status on R1.

>[!Note]- IP Addressing Issues on IOS Devices 
>![[Pasted image 20240517232724.png]]

### IP Addressing Issues on End Devices 

- On Windows-based machines, when the device cannot contact a DHCP server, Windows will automatically assign an address belonging to the 169.254.0.0/16 range. This feature is called Automatic Private IP Addressing (APIPA). 

- A computer with an APIPA address will not be able to communicate with other devices in the network because those devices will most likely not belong to the 169.254.0.0/16 network. 

- Note: Other operating systems, such Linux and OS X, do not use APIPA. 

- If the device is unable to communicate with the DHCP server, then the server cannot assign an IPv4 address for the specific network and the device will not be able to communicate. 

- To verify the IP addresses assigned to a Windows-based computer, use the ipconfig command.

### Default Gateway Issues 

- The default gateway for an end device is the closest networking device, belonging to the same network as the end device, that can forward traffic to other networks. If a device has an incorrect or nonexistent default gateway address, it will not be able to communicate with devices in remote networks. 

- Similar to IPv4 addressing issues, default gateway problems can be related to misconfiguration (in the case of manual assignment) or DHCP problems (if automatic assignment is in use). 

- To verify the default gateway on Windows-based computers, use the ipconfig command. 

- On a router, use the show ip route command to list the routing table and verify that the default gateway, known as a default route, has been set. This route is used when the destination address of the packet does not match any other routes in its routing table.

### Troubleshooting DNS Issues 

- It is common for users to mistakenly relate the operation of an internet link to the availability of the DNS. 

- DNS server addresses can be manually or automatically assigned via DHCP. 

- Although it is common for companies and organizations to manage their own DNS servers, any reachable DNS server can be used to resolve names. 

- Cisco offers OpenDNS which provides secure DNS service by filtering phishing and some malware sites. OpenDNS addresses are 208.67.222.222 and 208.67.220.220. Advanced features such as web content filtering and security are available to families and businesses. 

- Use the ipconfig /all as shown to verify which DNS server is in use by the Windows computer. 

- The nslookup command is another useful DNS troubleshooting tool for PCs. With nslookup a user can manually place DNS queries and analyze the DNS response.