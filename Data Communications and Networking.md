
# Data Communications and Networking 


![[Pasted image 20240117144403.png]]



## Network affects our lives 

#### Networking Connect US
- Communication as a need 


>[!Note]- Cisco's approach on networking 
>https://www.youtube.com/watch?v=NiZWvLqGL3s&ab_channel=Cisco


#### No Boundaries
- World without boundaries
- The internet is an escape from reality 
- Different communities around the world are accessible 

## Network Components 
### Host 
- Also called as end device 

### Server 
- Responds to the request of a client 
- provide information to end devices
	- email servers
	- web servers 
	- file servers

## Peer-to-Peer
- It is possible to have a device be a client and a server in a Peer-to-Peer Network. 
- Recommended for very small network 

>[!Note]- Peer to Peer
>![[Pasted image 20240117145336.png]]


| Advantages | Disadvantages |
| ---- | ---- |
| Easy to setup | No centralized administration |
| Less complex | Not as Secure |
| Lower cost | Not Scalable |
| Used for simple tasks: transfering files and sharing printers | Slower performance |


## End Devices
- **Processes the request**
- Originates from or where it is received.
- Data originates with an end device, flows through the network, and arrives at an end device.
- Internetwork has different branches from the Host to the endpoint 


>[!Note]- Setup (End devices)
>![[Pasted image 20240117145755.png]]


## Intermediary Network Devices
- **Where the traffic flows**
- The middle network 
- Interconnects end devices
- Management of data flows through a network. 

>[!Note]- Intermediary Devices 
>![[Pasted image 20240117145907.png]]

## Network Media
- **The hardware medium**
- Communication accross a network is carried through a medium
- POE  (Power Over Ethernet) - Mostly implemented on CCTVs
	- 12V
	- 25V
	- 30V

![[Pasted image 20240117150059.png]]



## Network Representations 
- Overview of a network 
- Also called topology diagram
- Information about the network 

#### Terms
**Network Interface Card** - Connects the port to the computer even in wifi 
**Physical Port** - The port where the port is located in the pc
**Interface**- Virtual versions of ports

>[!Note]- Network Representations 
>![[Pasted image 20240117150319.png]]

>[!Note]- Wireless Nic card 
>Interface SATA 
>![[Pasted image 20240117150513.png]]

## Topology Diagrams 
- Physical topology diagrams illustrate the physical location of intermediary devices 
- 
>[!Note]- Physical Network 
>![[Pasted image 20240117150939.png]]

- Logical Topology illustrates the ports, port number, and the addressing scheme of the network 
>[!Note]- Logical network
>![[Pasted image 20240117150957.png]]

## Common Types of Networks

### Networks of Many Sizes 

**Small Home Networks** - Only a few computers 
**Small Office/Home office** - There is connectivity of computers but only a few (Lessthan 20 computers)
**Medium to Large networks** - Hundreds of Thousands of computers (Universities)
**World Wide Network** - Scattered throughout the world. Different branches

### LAN and WANs

#### LAN
- Small geographical Area 

#### WAN
- One network but a larger geographical Area 
![[Pasted image 20240117152130.png]]


### The Internet 
- Connects the networks of the world 
- Different internet service providers to form the internet 
- Worldwide collection of interconnected LANs and WANs
- Not owned by any individual 


### The Intranet and Extranet
**Intranet**
- Internal 
- Exclusive only for the organization members or only people with authorization 
**Extranet**
- Wider range for the organization or other connections 

>[!Note]- Intranet and Extranets 
>![[Pasted image 20240117152817.png]]

## Internet Connections 
- Different ways to connect to the internet 

### Home and Small Office Internet Connections 
- Can be shared
**DSL**
- Digital subscriber Line 
- For small offices or home users 
- Boradbands 
**Cable**


>[!Note]- Home and Small Office Internet Connections
>![[Pasted image 20240117153117.png]]

### Business Internet Connections 
- Exclusive only for businesses 
- Expensive
>[!Note]- Business Internet Connections 
>![[Pasted image 20240117153341.png]]

### The Converging Network 
- Data, voice, and Video all in one 
- Multiple servicesa in one link 

>[!Note]- Converging network 
>![[Pasted image 20240117153637.png]]

### Network Architecture
- 4 Goals
- The reliability of a network 
- **Fault tolerance** - If a router is broken, all users should not be affected 
	- Can be achieved through redundant links where routes can be chaned 
- **Scalability** - If a new feature is added. the network does need to be restructured
- **Quality of Service** - Ensures Critical Data is prioritized 
- **Network Security** - The confidientiality of a network
	- **Confidientialilty** - indented reciepeinces can read the data 
	- **Integrity** - How it sent is equal the same way it was recieved.
	- **Availability** - reliable access
>[!Note]- 4 Goals 
>![[Pasted image 20240117154445.png]]

### Network Trends 
- Networks are adaptable in the current trends 
- Bring your own devices (BYOD)
- Online Collaborations 
- Video Communicati9ons 
- Cloud computing 


### Cloud Computing 
- Allows us to store personal files or backup our data on servers over the internet 
- "Cloud is somebody else computer"
- IF anything happens cloud can act as a backup 


### Powerline Networking 
- Signal passes through a powerline 
- Not standard in the Philippines 
- Outlets can act as a network device

### Wireless Broadband 
- Cellular data 
- 4G, LTE, 5G

## Network Security 

### Security Threats 
- Risk for Hackers

**External threats**
- Viruses, worms, and Trojan horses
**Internal Threats**
- Loss of data
- Accidental misuse by employees 

### Security Solutions 
- Firewall 
- AntiVirus 
- Anti spyware 


## The IT professional 
- Level of specialization of an Employee 




## Protocols

### Network Protocol Functions




# Module 2: Basic Switch and End Device Configuration 

**CISCO IOS device - CISCO Internet Operating System** 




# Basic Network Communication 

1. Create a network topology which consists of the following devices:
	a. 1x 2960 Switch 
	b. 1x PC
	c. 1x Server 

>[!Note]- Connct the end devices to the switch
>![[Pasted image 20240208225653.png]]

2. Configure the following to the 2960 switch 
	a. Hostname (the format of the hostname should be your last name + initials of your first name/ s + _sw)
		Examples: lunia_sw
		
>[!Note]- Change the hostname 
>![[Pasted image 20240208230717.png]]

b. configure password encrypted fro line console and vty. Use your lastname +123 as password
Example: luna123

>[!Note]- Change the password for console
>![[Pasted image 20240208231733.png]]
>![[Pasted image 20240208234306.png]]


>[!Note]- Change the password for VTY
>![[Pasted image 20240208232110.png]]

>[!Note]- service password encryption
>![[Pasted image 20240208232220.png]]
>

c. configure a banner for the device login. Use this format "WARNING!" <your lastname's> propery. Authorized personel only!

Example: "WARNING! Sebastian's property. Authorized personnel only!"

>[!Note]- Banner
>![[Pasted image 20240208234556.png]]
>![[Pasted image 20240208234604.png]]

d. Assign the IP address of interface vlan 1 to 172.16.0.1 255.255.255.0. Enable the interface by issuing the command “no shutdown”

>[!Note]- Assign of IP address
>![[Pasted image 20240208234800.png]]


Configure the IP address of the PC: 
a. IPv4 address: 172.16.0.2 

b. Subnet Mask: 255.255.255.0 

c. Default Gateway: 172.16.0.1

>[!Note]- IP config of pc
>![[Pasted image 20240208235204.png]]

Configure the IP address of the Server: 

a. IPv4 address: 172.16.0.3 

b. Subnet Mask: 255.255.255.0 

c. Default Gateway: 172.16.0.1

>[!Note]- IP config of server
>![[Pasted image 20240208235310.png]]

On a new document, put the screenshots of the following: 
a. Ping from PC to Switch 

>[!Note]- Ping to Switch
>![[Pasted image 20240209000156.png]]



b. Ping from PC to Server 

>[!Note]- Ping to Server
>![[Pasted image 20240208235908.png]]


c. Login of console access on switch showing the banner that you have created. 

>[!Note]- Login
>![[Pasted image 20240208235755.png]]
>![[Pasted image 20240208235835.png]]

d. Connect to the switch from the PC using telnet via command line. 

>[!Note]- PC to switch
>![[Pasted image 20240209000323.png]]


e. Copy the running configuration then paste it (not screenshot) on the document. 

>[!Note]- Show running config 
>![[Pasted image 20240209000523.png]]


f. Submit the document as PDF to Canvas with a file name of “Lastname_Firstname_ACT_1”.