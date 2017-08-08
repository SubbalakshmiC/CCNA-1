# CCNA Notes

All notes made here relate to ICND 1 or 2, and may be a little lacking or nonsensical. Sorry.

---
# ICND1
## General Notes

### Timeline
* 2 Weeks Training (Week 1 GPK, Week 2 BFL)
* 1 Week self study
* Exam at the end of W3

### Course Goals
* Describe network fundementals and implement a simple LAN
* Establish Network fundementals
* Expand a small network to a medium-sized routing-enmabled network
* Confifure, manage, secure and monitor Cisco devices
* Describe IPv6 basics

### Extra Content
* CEF: Cisco Express Forwarding

### Exercise Types:
* Challenge Exercises
* Discovery Extercises

### Certified Mock Exam Questions:
* MeasureUp
* Bolan.com (?)

## Exam Notes

* Exam pass is a requirment to continue the Apprenticeship Program
* ICND1 is marked out of 1000
* 300/1000 marks for participating
* 90 minutes for the exam
* ~ 825/1000 marks to pass
* Results immediately displayed upon exam completion
* Qualification is valid for 3 years, and completing the next exam in the series (e.g. CCNP) will re-validate any lower exams

## Module Notes

### Module 1: Building a Simple Network
#### What is a Network?
* Networks carry data in varying environments.
* Large networks may be multi-location, e.g. Home Office, Branchg Office, Main Office & Mobile all on a single network.

#### Physical Components of a Network
* Networks are composed of:
    * Endpoints - PCs, servers, printers etc.
    * Interconnections - NICs, Network Media (e.g. UTP or STP in varying categories) & Connectors (e.g. RJ-i45)
    * Switches - Endpoints connect to these, and they can share a common network
    * Routers - Select the best route for traffic from one network to another
    * WLAN Devices - Connect Wireless Devices to a network
    * APs - Allow wireless devices to communciate with a wired network
    * WLAN Controllers - Devices that network admins can use to manage APs in large quantities
    * Firewalls - Network security systems that control and monitor incoming and outgoing traffic based on provided rules

#### Characteristics of a Network
Network characteristics are as follows:
* Topology - Physcial (e.g. arrangment of cables, devices and end systems) or Logical (e.g. the path that the data follows within a network) 
* Speed - The data travel rate per second given in bits within a link in the network (bitrate)
* Cost - General expendature for purchasing, installing and maintiaining the elements in a network
* Security - How protected the network is, including the information transferred across the network
* Availability - Measure of probability that the netowork will be available for use when required
    * This can be calculated with the following formula:
    `((minutes in a year) - (number of minutes if down time in a year) / number of minutes in a year) x 100` 
* Scalability - How easily the network can accokoate more users and data transmission requirements
* Reliability - The dependability of components that the network is composed of

#### Physical vs. Logical Topology
* Physical Topologies
    * Ring - Each device is cabled together in a ring, so that the last device is connected to the first, etc.
    * Mesh - Every device is connected to one another, allowing higher redundancy tollerences
    * Star - The most common type of topology. A central device is connected to all of the endpoints and other network devices
    * Bus - Every workstation is connected to the main network medium. Each device is directly connected to another
    ![Bus, Ring, Mesh and & Star Toplogies](http://www.itgeared.com/images/content/1339-1.jpg)
    * Logical Topologies - The path that the data follows within a network

#### Interpreting a network diagram
* Various connection interfaces are used in a netowork. On a network diagram they are denoted as follows:
    * S0/0/0 - **S**erial (Speeds up to 2Mbps)
    * Fa0/0 - **Fa**st Ethernet (Speeds up to 100Mbps)
    * Gi0/0 - **Gi**gabit Ethernet (Speeds up to 1Gbps
    * /XY -  Slash notation of subnet mask used

#### Impact of User Applications on the Network
* Applications can perfect network performace, and vice versa.
There are varying types of applications, such as:
    * Batch
       * No Direct Human Interactions
		* Bandwith non-critical
		* e.g. TFP, TFTP, inventory updates
    * Interactive
    	* Human-Machine interactions
    	* Human waits for response, therefore the response time is important but not critical
		* e.g. Inventory enquiries
    * Real-Time Applications
		* End-to-end latency is critical
		* e.g. VoIP, Video calling
		* Human-Human interaction
* QoS (Quality of Service) is important. It allows for the granting of higher priority to different types of data e.g. VoIP Packets.

#### Host-to-Host Communications
* Varying types of host-to-host models exist:
    * Older Models e.g. Used by Proprietary Software
    * Standards-based Models e.g. Used by Multivendor Software (OSI, TCP/IP Models) 
    
#### OSI Model
* The layers of the OSI model are as follows:

	|   |OSI Model   |
	|---|:----------:|
	| ↓ |Application |
	| ↓ |Presentation|
	| ↓ |Session     |
	| ↓ |Transport   |
	| ↓ |Network     |
	| ↓ |Data Link   |
	| ↓ |Physical    |

* The OSI Model is a layer-based reference model that provides functions and services that can occur at each layer.
* It describes the interaction between each layer above and below it. 
* It is standards based, allowing vendors a set of standards that ensure compatability between various types of network technology worldwide.
* The layer functions are as follows: 

    ##### Application
* Function of application layer changes dependant on application.
	* Some of these things include:
	* resource sharing,
	* remote file access,
	* remote printer access,
	* network management,
	* and electronic messaging (email). 
* Common Protocols include: 
	* File Transfer Protocol (FTP), 
	* Domain Name Service (DNS), 
	* Hypertext Transfer Protocol (HTTP) 
	* and Simple Mail Transfer Protocol (SMTP).
* Real traffic data is generated at this layer. It may be a web request from HTTP to a command from TelNet, to a file download from FTP.
  
    ##### Presentation
* Responsible for: 
	* character code translation (i.e. ASCII vs. EBCDIC vs. Unicode), 
	* data conversion, 
	* compression, 
	* and encryption. 
* Some common examples include: 
	* Multipurpose Internet Mail Extensions (MIME), 
	* Transport Layer Security (TLS) 
	* and Secure Sockets Layer (SSL).
* When the presentation layer receives data, it checks the data format is correct and if not converts it.
* This layer is also responsible for compression, encryption, and ensuring that the character code set can be interpreted on the other side of the connection.

    ##### Session
* Port numbers are present in both sending and recieving capacities. e.g. Internet requests will be sent to port 80, but will be recieved on veryiong port numbers dependant on my Session ID
* Responsible for:
	* session establishment,
	* maintenance
	* and termination
* In the connection establishment phase, service rules are transmitted and must be accepted by both devices. Once these rules have been set, the transfer begins, the session is ended once the transmission is complete.
  
    ##### Transport
* One of 2 things:
	* TCP (handshake like connection e.g. a phone)
		* The TCP Handshake goes as follows:
		* SYN → SYN-ACK → ACK
	* UDP (connection-less e.g. a radio)
* There is also a mechanism to ensure that a device running multiple applications simultaneously all receive their data.
* To make this work correctly, incoming data from various applications are multiplexed on the transport layer and pushed to the bottom layers. At the other end of the communication, that data is de-multiplexed at the Transport Layer.
  
    ##### Network
* Responsible for:
	* Logical-physical address mapping: translates logical addresses, or names, into physical addresses.
	* Routing routes frames among networks.
* Routers direct the data packet from this layer using location information stored in a Routing Table. This is a list of destinations on the network.

    ##### Data Link
* Responsible for establishing and terminating links.
* This layer provides error-free transfer of data frames from one node to another over the physical layer.
* This layer is separated into the Media Access Control (MAC) Sublayer and the Logical Link Control (LLC) Sublayer.
* The MAC layer determines the physical addressing of host devices. It maintains MAC addresses for communicating with other devices.
* Logical Link is responsible for synchronising frames, error checking, and flow control.

    ##### Physical
* The physical layer handles how data is physically encoded and decoded. 
* Physical layers describe the electrical or optical signals used for communication.
	* For example, whether a voltage represents a 1 or a 0.
* This layer is concerned by the electrical or optical signalling techniques which includes the voltage of the electrical current used to transport the signal, the media type, impedance characteristics, physical shape of the connector, synchronisation method, etc. 
 
#### TCP/IP Model
* The layers of the TCP/IP Model are as follows:

	|   |TCP/IP Model|
	|---|:----------:|
	| ↓ |Application |
	| ↓ |Transport   |
	| ↓ |Internet    |
	| ↓ |Data Link   |
	
* The layers of the TCP/IP Model map onto the OSI model as follows:

	|   |OSI Model                         |TCP/IP Model|
	|---|:--------------------------------:|:----------:|
	| ↓ |Application, Presentation, Session|Application |
	| ↓ |Transport                         |Transport   |
	| ↓ |Network                           |Internet    |
	| ↓ |Data Link & Physical              |Link        |

* The layer functions are as follows:
	
	##### Application
* This layer generates data dependant on what application is being used. This could be a web address in a web browser, for example.
* It also defines how host programs interface with Transport layer services to use the network.
* Protocols on this layer are:
	* HTTP (Hypertext transfer protocol)
	* FTP (File transfer protocol)
	* SMTP (Simple mail transfer protocol)
	* SNMP (Simple network management protocol) etc

	##### Transport
* This layer receives data from the application layer above it. 
* This layer permits devices on the source and destination hosts to continue their communication.
* There are many protocols that work at this layer but the two most commonly used protocols at transport layer are TCP and UDP.
	* TCP (handshake like connection e.g. a phone)
	* UDP (connection-less e.g. a radio)

	##### Internet
* The main purpose of this layer is to organise or handle the movement of data on network.
* It controls how data is physically transmitted, including how bits are electrically or optically signalled by hardware devices that interface directly with a network connection type, like coaxial cable, optical fibre, or twisted pair copper wire.

	##### Link
* This layer normally consists of device drivers in the OS and the network interface card attached to the system.
* The most popular protocol in use over LAN is ethernet. This uses a method known as CSMA/CD, this is Career Sense Multiple Access/Collision Detection. This is used to access media. Access methods determine how hosts place media on communication mediums.
* In the case of CSMA/CD every host has the same access to the medium and can place data on the wire when there is no traffic. If there is traffic it waits until there is not before placing the data. If this was not the case, the data would collide and be destroyed, and will need resubmitting.

#### Peer-to-Peer Communications
* At each layer of communciation a different Protocol Data Unit (PDU) is used, for example:

	|   |Sender     |PDU    |Reciever   |
	|---|:---------:|:-----:|:---------:|
	| ↓ |Application|Data   |Application|
	| ↓ |Transport  |Segment|Transport  |
	| ↓ |Internet   |Packet |Internet   |
	| ↓ |Link       |Frame  |Link       |
	
	> At the physical layer, the PDU used is 'bits'

#### Encapsulation and De-Encapsulation
* Encapsulation is a process that occurs within the OSI and TCP/IP Models
* Within the OSI Model, it occurs as follows:
    * The application layer recieved the user data, and adds a header before sending it to the presentation layer
    * The presentation layer adds its own header before transmissing to the session layer
    * This process continues down the stack and at the data link layer, a trailer is added
    * At Layer 2 the trailer is ususally the FCS - Used to check for errors in transmission
    * At the destination this is unpacked one layer at a time, and the data is then passed up to the PDU on the layer above

#### Local Area Networks
* Ethernet became widespead in the 1990s
* A LAN requires the following necessary components for operation:
	* Hosts
		* PCs
		* Servers
	* Interconnections
		* NICS - translating data into electrical signals
		* Network Media - Fibre optics or Copper (usually)
	* Network Devices
		* Routers
		* Switches
	* Protocols
		* Ethernet
		* Token Ring
		* HDLC (High Level Data Link Control) Protocol - used by Serial type connections
		* PPP (point to Point Protocol)
		* ATM (Asynchronous Transfer Mode)
		* PPPoE (PPP over Ethernet)
	
	> As explained above
	
* Pre-switching ethernet networks used co-axial cables with many devices connected to them in a bus. This method offered upto 10Mbps speeds
	* At points along the cable, marked dots denoted areas where the cable could be tapped into with vampire taps to attach devices to the bus.
	* Errors required Time Domain Reflexometers to show a rough region of the cable whereby the connection was lost
	* Data on the broadcast media is accessable to any devices on the network
	* This system was relaced with a central hub that contained the effective bus of the networ, and each device had its own UTP cable to and from the hub
	* Phyically that network may be described as a hub, but logically that forms a bus network
* CSMA/CD (Collision Sense Multiple Access/Collision Detection) is used to mitigate collisions along the media that may result in lost data. This forms part of the Ethernet Protocol and is used in Half-Duplex networks
* CSMA/CA (/Collision Avoidance) is used on wireless, and ensures 2 devices are not transmitting at the same time, as the frequency is shared across the devices
	* Collision Detection - to discover whether a device is currently transmitting on the media
	* The sending device listens to the signal they are transmitting. If the data heard differs from that sent, the system becomes aware of a collision
	* A jamming signal is sent to prevent other devices whilst another is, mitigating the chances of a collision occuring
	* Hubs became repeaters, Bridges became Switches
	* ASIC - Application Specific Integrated Circuits
	
#### Need for Switches
* Traditionally devices had to compete for bandwidth on a network (or broadcast domain), using a bus topology. This meant that only one device could transmit at a time
* Switches can now be used to split up a network, and reduce the number of devices within a collision domain. There may be multiple collision domains within a broadcast domain (the immediate reach of a switch)
* The function of switches is as follows:
	* Operate at the link (L2) layer of the TCP/IP Model
	* Forward, Filter or Flood frames to hosts dependant on entries in the MAC Address tables on the device
	* Have many Full-Duplex ports to allow for the LAN to be segmented, reducing collison domain sizes
	* Support multiple port speeds.
* Switches build tables of the devices immediately connected to them and store their MAC (Physical) Addresses in a MAC address table
* The header of each incomming frame has a MAC address within it for the destination host, which is compared to addresses within the switch's MAC address table. They use this to decide whether to flood, forward or filter recieved frames
* 'Bridges' connect token ring to ethernet networks

	|Sender| → |Recipient|Type     |
	|:----:|---|:-------:|:-------:|
	|A     | → |B        |Unicast  |
	|A     | → |B & C    |Multicast|
	|A     | → |All      |Broadcast|
> Transport Types	

* When a unicast frame is recieved on a port, the destination MAC is compared with the addresses within the MAC address table, one of 3 things happen:
	* If the switch is aware of the MAC address to interface relationship, due to it being an entry within it's MAC Address Table, then the packet is **Forwarded** to that port. The other ports are now filtered out. 
	* If the MAC address listed is known, and is on the same interface, e.g.Hosts X & Y being on teh same segment as they are attached to a hub, the packet is **Filtered** by the switch and not passed outwards to any other ports.
	* If the address matches no entry on the switch's MAC Address Table, the frame is transmitted on all ports except the one it was recieved on, with the hope that it can be passed on, this is **Flooding**.

		|Port|Host|
		|----|----|
		|1   |A   |
		|2   |B   |
		|3   |C   |
		|4   |D   |
> MAC Address Table. This is built from source addresses
	
#### Switches
* Switches can be in two types:
	* Dedicated Bandwidth - a single station is connected to a given switch port, and so there is no competiton for bandwidth
	* Full Duplex Operation - on a shared ethernet medium, this allows for devices to both sendand recieve at the same time. Half duplex allows for either sending or recieving at a given time
	* A L2 Switch makes decisions as to where to send packets based on data found in the Ethernet Frame, whereas a L3 Router uses the IP addresses within said packets
	* LAN Switches can have:
		* High port density - any number from less than 32 to hundreds of ports may be on a switch
		* Large frame buffers - allowing more frames to be storred before needing to drop them
		* Varying port speeds - Speeds of 100Mbps are expected, but other speeds such as 1 or 10Gbps are also common
		* Fast internal switching - fast internal bus, shared memory or integrated crossbar switch fabric may be used 
		* Lower per port cost - Less devices are required to allow a network of the same size when using switches
	* A switch offers a port (connection) to each device, removing the need for CSMA/CD. However this is still accepted, in the event that a hub may be connected to one of these ports to increase capacity

#### Cisco IOS
* Cisco IOS is the proprietory operating system that operates on Switches, Routers, APs and other networking appliances that Cisco Manufacture
* The port used to directly connect to a router, switch etc. is called a console port
* A light blue patch cable is used here (likely with an RJ-45 connection)
* The Cisco CLI is used to enter commands
* Operations performed vary dependant on the device

* Modes within the CLI (Command Line Interface):
	* `switch >` - User EXEC Mode
		* A limited, read-only examination mode
	* `switch #` - Priveleged EXEC Mode
		* Allowing access to all system commands, though still read-only
		* Accessed by typing `enable` from within User Mode
		* Here the user can entirely examine the system, reload the system
		* Offers access to the global configuration mode
	* `switch (config)#` - Global Configuration Mode

> `switch` is a placeholder hostname used here

* Useful key combinations:
	* `Ctrl-A` - Moves the cursor to the beginning of the command line
	* `Ctrl-C`	- Aborts the current command and exits the configuration mode
	* `Ctrl-E`	- Moves the cursor to the end of the command line
	* `Esc-B`	- Moves the cursor back one word
	* `Esc-F`	- Moves the cursor forward one word
	* `Ctrl-B`	- Moves the cursor back one character
	* `Ctrl-F`	- Moves the cursor forward one character
	* `Ctrl-D`	- Deletes a single character at the cursor
	* `Backspace`	- Removes one character to the left of the cursor
	* `Ctrl-P` - Redisplays the current command line
	* `Ctrl-U`	- Erases a line
	* `Ctrl-W`	- Erases a word to the left of the cursor
	* `Ctrl-Z` - Ends configuration mode and returns to the EXEC prompt
	* `Tab`	- Completes a partially entered command if enough characters have been entered to make it unambiguous
	* `Ctrl-Shift-6` - Allows the user to interrupt a Cisco IOS process such as ping or traceroute
	* `Ctrl-P` or `Up Arrow` - Recalls last (previous) commands
	* `Ctrl-N` or `Down Arrow`	- Recalls more recent commands

* Useful commands:
	* `show` - Show running system information, could be suffixed with an interface name for example
	* `disable` - Returns to User EXEC Mode
	* `exit` - Return to Priveledged EXEC Mode

* There are 3 main types of error messages:
	* `ambiguous command` - You did not enter enough characters for your device to recognize the command
	* `incomplete command` - You did not enter all the keywords or values that are required by this command
	* `invalid command` - You entered the command incorrectly. The ^ marks the point of the error

### Module 2: Establishing internet connectivity 

### Module 3: Summary Challenge 

### Module 4: Building a Medium-Sized Network 

### Module 5: Network Device Managment & Security 

### Module 6: Summary Challenge 

### Module 7: Introducing IPv6 

---
