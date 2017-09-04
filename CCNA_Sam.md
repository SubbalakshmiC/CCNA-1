# CCNA Notes

All notes made here relate to ICND 1 or 2, and may be a little lacking or nonsensical. Sorry.

---
# General Notes
## Exercise Types:
* Challenge Exercises
* Discovery Exercises

## Certified Mock Exam Questions:
* MeasureUp
* Boson.com

# Exam Notes
* Exam pass is a requirement to continue the Apprenticeship Program.
* ICND1 is marked out of 1000.
* 300/1000 marks for participating.
* 90 minutes for the exam.
* ~ 825/1000 marks to pass.
* Results immediately displayed upon exam completion.
* Qualification is valid for 3 years, and completing the next exam in the series (e.g. CCNP) will re-validate any lower exams.

# ICND1 Admin Notes

## Timeline
* 2 Weeks Training (Week 1 GPK, Week 2 BFL).
* 1 Week self study.
* Exam at the end of W3.

## Course Goals
* Describe network fundamentals and implement a simple LAN.
* Establish Network fundamentals.
* Expand a small network to a medium-sized routing-enabled network.
* Configure, manage, secure and monitor Cisco devices.
* Describe IPv6 basics.

## Extra Content
* CEF: Cisco Express Forwarding

# ICND 1 Module Notes

## Module 1: Building a Simple Network
### What is a Network?
* Networks carry data in varying environments.
* Large networks may be multi-location, e.g. Home Office, Branch Office, Main Office & Mobile all on a single network.

### Physical Components of a Network
* Networks are composed of:
    * Endpoints - PCs, servers, printers etc.
    * Interconnections - NICs, Network Media (e.g. UTP or STP in varying categories) & Connectors (e.g. RJ-i45).
    * Switches - Endpoints connect to these, and they can share a common network.
    * Routers - Select the best route for traffic from one network to another.
    * WLAN Devices - Connect Wireless Devices to a network.
    * APs - Allow wireless devices to communicate with a wired network.
    * WLAN Controllers - Devices that network admins can use to manage APs in large quantities.
    * Firewalls - Network security systems that control and monitor incoming and outgoing traffic based on provided rules.

### Characteristics of a Network
Network characteristics are as follows:
* Topology - Physical (e.g. arrangement of cables, devices and end systems) or Logical (e.g. the path that the data follows within a network).
* Speed - The data travel rate per second given in bits within a link in the network (bitrate).
* Cost - General expenditure for purchasing, installing and maintaining the elements in a network.
* Security - How protected the network is, including the information transferred across the network.
* Availability - Measure of probability that the network will be available for use when required.
    * This can be calculated with the following formula:
    `((minutes in a year) - (number of minutes if down time in a year) / number of minutes in a year) x 100` 
* Scalability - How easily the network can accommodate more users and data transmission requirements.
* Reliability - The dependability of components that the network is composed of.

### Physical vs. Logical Topology
* Physical Topologies:
    * Ring - Each device is cabled together in a ring, so that the last device is connected to the first, etc.
    * Mesh - Every device is connected to one another, allowing higher redundancy tolerances.
    * Star - The most common type of topology. A central device is connected to all of the endpoints and other network devices.
    * Bus - Every workstation is connected to the main network medium. Each device is directly connected to another.
    ![Bus, Ring, Mesh and & Star Topologies](http://www.itgeared.com/images/content/1339-1.jpg)
    * Logical Topologies - The path that the data follows within a network.

### Interpreting a network diagram
* Various connection interfaces are used in a network. On a network diagram they are denoted as follows:
    * S0/0/0 - **S**erial (Speeds up to 2Mbps)
    * Fa0/0 - **Fa**st Ethernet (Speeds up to 100Mbps)
    * Gi0/0 - **Gi**gabit Ethernet (Speeds up to 1Gbps
    * /XY -  Slash notation of subnet mask used

### Impact of User Applications on the Network
* Applications can perfect network performance, and vice versa.
There are varying types of applications, such as:
    * Batch
       * No Direct Human Interactions
		* Bandwidth non-critical
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

### Host-to-Host Communications
* Varying types of host-to-host models exist:
    * Older Models e.g. Used by Proprietary Software
    * Standards-based Models e.g. Used by Multivendor Software (OSI, TCP/IP Models) 
    
### OSI Model
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
* It is standards based, allowing vendors a set of standards that ensure compatibility between various types of network technology worldwide.
* The layer functions are as follows: 

    #### Application
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
  
    #### Presentation
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

    #### Session
* Port numbers are present in both sending and receiving capacities. e.g. Internet requests will be sent to port 80, but will be received on varying port numbers dependant on my Session ID.
* Responsible for:
	* session establishment,
	* maintenance
	* and termination
* In the connection establishment phase, service rules are transmitted and must be accepted by both devices. Once these rules have been set, the transfer begins, the session is ended once the transmission is complete.
  
    #### Transport
* One of 2 things:
	* TCP (handshake like connection e.g. a phone)
		* The TCP Handshake goes as follows:
		* SYN → SYN-ACK → ACK
	* UDP (connection-less e.g. a radio)
* There is also a mechanism to ensure that a device running multiple applications simultaneously all receive their data.
* To make this work correctly, incoming data from various applications are multiplexed on the transport layer and pushed to the bottom layers. At the other end of the communication, that data is de-multiplexed at the Transport Layer.
  
    #### Network
* Responsible for:
	* Logical-physical address mapping: translates logical addresses, or names, into physical addresses.
	* Routing routes frames among networks.
* Routers direct the data packet from this layer using location information stored in a Routing Table. This is a list of destinations on the network.

    #### Data Link
* Responsible for establishing and terminating links.
* This layer provides error-free transfer of data frames from one node to another over the physical layer.
* This layer is separated into the Media Access Control (MAC) Sublayer and the Logical Link Control (LLC) Sublayer.
* The MAC layer determines the physical addressing of host devices. It maintains MAC addresses for communicating with other devices.
* Logical Link is responsible for synchronising frames, error checking, and flow control.

    #### Physical
* The physical layer handles how data is physically encoded and decoded. 
* Physical layers describe the electrical or optical signals used for communication.
	* For example, whether a voltage represents a 1 or a 0.
* This layer is concerned by the electrical or optical signalling techniques which includes the voltage of the electrical current used to transport the signal, the media type, impedance characteristics, physical shape of the connector, synchronisation method, etc. 
 
### TCP/IP Model
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
	
	#### Application
* This layer generates data dependant on what application is being used. This could be a web address in a web browser, for example.
* It also defines how host programs interface with Transport layer services to use the network.
* Protocols on this layer are:
	* HTTP (Hypertext transfer protocol)
	* FTP (File transfer protocol)
	* SMTP (Simple mail transfer protocol)
	* SNMP (Simple network management protocol) etc

	#### Transport
* This layer receives data from the application layer above it. 
* This layer permits devices on the source and destination hosts to continue their communication.
* There are many protocols that work at this layer but the two most commonly used protocols at transport layer are TCP and UDP.
	* TCP (handshake like connection e.g. a phone)
		* The TCP Handshake goes as follows:
		* SYN → SYN-ACK → ACK
	* UDP (connection-less e.g. a radio)
	* UDP (connection-less e.g. a radio)

	#### Internet
* The main purpose of this layer is to organise or handle the movement of data on network.
* It controls how data is physically transmitted, including how bits are electrically or optically signalled by hardware devices that interface directly with a network connection type, like coaxial cable, optical fibre, or twisted pair copper wire.

	#### Link
* This layer normally consists of device drivers in the OS and the network interface card attached to the system.
* The most popular protocol in use over LAN is ethernet. This uses a method known as CSMA/CD, this is Career Sense Multiple Access/Collision Detection. This is used to access media. Access methods determine how hosts place media on communication mediums.
* In the case of CSMA/CD every host has the same access to the medium and can place data on the wire when there is no traffic. If there is traffic it waits until there is not before placing the data. If this was not the case, the data would collide and be destroyed, and will need resubmitting.

### Peer-to-Peer Communications
* At each layer of communication a different Protocol Data Unit (PDU) is used, for example:

	|   |Sender     |PDU    |Receiver   |
	|---|:---------:|:-----:|:---------:|
	| ↓ |Application|Data   |Application|
	| ↓ |Transport  |Segment|Transport  |
	| ↓ |Internet   |Packet |Internet   |
	| ↓ |Link       |Frame  |Link       |
	
	> At the physical layer, the PDU used is 'bits'

### Encapsulation and De-Encapsulation
* Encapsulation is a process that occurs within the OSI and TCP/IP Models
* Within the OSI Model, it occurs as follows:
    * The application layer received the user data, and adds a header before sending it to the presentation layer
    * The presentation layer adds its own header before transmitting to the session layer
    * This process continues down the stack and at the data link layer, a trailer is added
    * At Layer 2 the trailer is usually the FCS - Used to check for errors in transmission
    * At the destination this is unpacked one layer at a time, and the data is then passed up to the PDU on the layer above

### Local Area Networks
* Ethernet became widespread in the 1990s
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
	
* Pre-switching ethernet networks used co-axial cables with many devices connected to them in a bus. This method offered up-to 10Mbps speeds
	* At points along the cable, marked dots denoted areas where the cable could be tapped into with vampire taps to attach devices to the bus.
	* Errors required Time Domain Reflectometers to show a rough region of the cable whereby the connection was lost
	* Data on the broadcast media is accessible to any devices on the network
	* This system was replaced with a central hub that contained the effective bus of the network, and each device had its own UTP cable to and from the hub
	* Physically that network may be described as a hub, but logically that forms a bus network
* CSMA/CD (Collision Sense Multiple Access/Collision Detection) is used to mitigate collisions along the media that may result in lost data. This forms part of the Ethernet Protocol and is used in Half-Duplex networks
* CSMA/CA (/Collision Avoidance) is used on wireless, and ensures 2 devices are not transmitting at the same time, as the frequency is shared across the devices
	* Collision Detection - to discover whether a device is currently transmitting on the media
	* The sending device listens to the signal they are transmitting. If the data heard differs from that sent, the system becomes aware of a collision
	* A jamming signal is sent to prevent other devices whilst another is, mitigating the chances of a collision occurring
	* Hubs became repeaters, Bridges became Switches
	* ASIC - Application Specific Integrated Circuits
	
### Need for Switches
* Traditionally devices had to compete for bandwidth on a network (or broadcast domain), using a bus topology. This meant that only one device could transmit at a time
* Switches can now be used to split up a network, and reduce the number of devices within a collision domain. There may be multiple collision domains within a broadcast domain (the immediate reach of a switch)
* The function of switches is as follows:
	* Operate at the link (L2) layer of the TCP/IP Model
	* Forward, Filter or Flood frames to hosts dependant on entries in the MAC Address tables on the device
	* Have many Full-Duplex ports to allow for the LAN to be segmented, reducing collision domain sizes
	* Support multiple port speeds.
* Switches build tables of the devices immediately connected to them and store their MAC (Physical) Addresses in a MAC address table
* The header of each incoming frame has a MAC address within it for the destination host, which is compared to addresses within the switch's MAC address table. They use this to decide whether to flood, forward or filter received frames
* 'Bridges' connect token ring to ethernet networks

	|Sender| → |Recipient|Type     |
	|:----:|---|:-------:|:-------:|
	|A     | → |B        |Unicast  |
	|A     | → |B & C    |Multicast|
	|A     | → |All      |Broadcast|
> Transport Types	

* When a unicast frame is received on a port, the destination MAC is compared with the addresses within the MAC address table, one of 3 things happen:
	* If the switch is aware of the MAC address to interface relationship, due to it being an entry within it's MAC Address Table, then the packet is **Forwarded** to that port. The other ports are now filtered out. 
	* If the MAC address listed is known, and is on the same interface, e.g.Hosts X & Y being on the same segment as they are attached to a hub, the packet is **Filtered** by the switch and not passed outwards to any other ports.
	* If the address matches no entry on the switch's MAC Address Table, the frame is transmitted on all ports except the one it was received on, with the hope that it can be passed on, this is **Flooding**.

		|Port|Host|
		|----|----|
		|1   |A   |
		|2   |B   |
		|3   |C   |
		|4   |D   |
> MAC Address Table. This is built from source addresses
	
### Switches
* Switches can be in two types:
	* Dedicated Bandwidth - a single station is connected to a given switch port, and so there is no competition for bandwidth
	* Full Duplex Operation - on a shared ethernet medium, this allows for devices to both send and receive at the same time. Half duplex allows for either sending or receiving at a given time
	* A L2 Switch makes decisions as to where to send packets based on data found in the Ethernet Frame, whereas a L3 Router uses the IP addresses within said packets
	* A 1Gbps port on a switch defaults to Full Duplex if not told to do otherwise, whereas a 100Mbps port will default to Half Duplex unless specified otherwise.
	* LAN Switches can have:
		* High port density - any number from less than 32 to hundreds of ports may be on a switch
		* Large frame buffers - allowing more frames to be stored before needing to drop them
		* Varying port speeds - Speeds of 100Mbps are expected, but other speeds such as 1 or 10Gbps are also common
		* Fast internal switching - fast internal bus, shared memory or integrated crossbar switch fabric may be used 
		* Lower per port cost - Less devices are required to allow a network of the same size when using switches
	* A switch offers a port (connection) to each device, removing the need for CSMA/CD. However this is still accepted, in the event that a hub may be connected to one of these ports to increase capacity

### Cisco IOS
* Cisco IOS is the proprietary operating system that operates on Switches, Routers, APs and other networking appliances that Cisco Manufacture
* The port used to directly connect to a router, switch etc. is called a console port
* A light blue patch cable is used here (likely with an RJ-45 connection)
* The Cisco CLI is used to enter commands
* Operations performed vary dependant on the device

* Modes within the CLI (Command Line Interface):
	* `switch >` - User EXEC Mode
		* A limited, read-only examination mode.
	* `switch #` - Privileged EXEC Mode
		* Allowing access to all system commands, though still read-only.
		* Accessed by typing `enable` from within User Mode.
		* Here the user can entirely examine the system, reload the system.
		* Offers access to the global configuration mode.
	* `switch (config)#` - Global Configuration Mode
		*  Here there are different types of config mode dependant on the function desired:
		*  These are `Interface`, `VLAN`, `Router`, `(N)ACL` etc.
		*  These modes are accessed via typing their names from within Global EXEC Mode.

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
	* `exit` - Return to Privileged EXEC Mode

* There are 3 main types of error messages:
	* `ambiguous command` - You did not enter enough characters for your device to recognise the command
	* `incomplete command` - You did not enter all the keywords or values that are required by this command
	* `invalid command` - You entered the command incorrectly. The ^ marks the point of the error

* Cisco switches use an 'Ageing Timer' which lasts 300 seconds (5 Minutes) to know when to remove an address from a MAC address table. If a cable is removed from a port, the time is set to 0
* CAM - Content Addressable Memory. MAC Addresses are stored here
* When making changes to the operation of a switch or router, saving and managing said changes are important.
* The following commands may be useful:
	* `show running-config` - Displays the current running configuration. You can also use filters. For example, you can use the show running-config interface GigabitEthernet0/1 command to display only the interface GigabitEthernet0/1 running configuration.
	* `show startup-config` - Displays the saved configuration in NVRAM.
	* `configure terminal` - Enters the configuration mode, where you can interactively create configurations in RAM from the console or remote terminal.
	* `copy running-config startup-config` - Saves the running configuration to NVRAM.
	* `copy startup-config running-config` - Startup configuration in NVRAM is merged into running configuration.
	* `erase startup-config` - Deletes the saved startup-config file in NVRAM.

* When displaying portions of a config it may help to filter out unwanted data.
* This can be done in the following ways:
	* `begin` - Shows all output lines, starting with the line that matches the filtering expression.
	* `exclude` - Excludes all output lines that match the filtering expression.
	* `include` - Includes all output lines that match the filtering expression.
	* `section` - Shows the entire section that starts with the filtering expression.
* e.g. `R1# show running-config | begin interface` will show only lines from within R1's running config that begin with 'interface'.

### Starting a Switch
* Switches can be configured in one of two ways:
	* Via Console Port - physically to the switch.
	* Via VTY (Virtual Teletype) - remotely to the switch.
* Both of these connection mediums enter the system at User EXEC Mode.
* When a switch boots up, it performs Power On Self Test (POST) and then initialises the system.
* Switches have LED indicators, which have differing meanings, these are:

	|Indicator Name|Description|
	|--------------|-----------|
	|SYST          |Overall system status (off meaning system is off, green meaning switch is on and operational, amber meaning switch is on but has failed POST)
	|RPS           |Status of a Redundant Power Supply
	|STAT          |If on (green), shows that port LEDs are implying to the status of each port
	|DUPLX         |If on (green), shows that port LEDs are implying the duplex status (on meaning full duplex, off meaning half duplex)
	|SPEED         |If on (green), shows that port LEDs are implying port speeds (off meaning 10Mbps, solid green meaning 100Mbps, flashing green meaning 1Gpbs)
	|PoE           |If on (green), shows that port LEDs are implying the Power over Ethernet status of each port
	
	* A MODE button is also present, allowing you to cycle the indicator LEDs on each switch to it's Status (on/off), Duplex Status and Speed.

### Understanding Ethernet and Switch Operation
* Ethernet can be used on varying mechanical standards, such as:
	* Co-Axial (this is no-longer used for ethernet communications)
	* Twisted Copper Pair
		* Unshielded Twisted Pair cables can come in varying categories:
			* Category 1: Used in telephone communications but not transmitting data
			* Category 2: Capable of data transmissions up to 4Mbps
			* Category 3: Used in 10BASE-T Networks and can transmit up to 10Mbps
			* Category 4: Used in token ring networks and can transmit up to 16Mbps
			* Category 5: Capable of transmitting data at up to 100Mbps
			* Category 5e: Capable of transmitting data at up to 1Gbps
			* Category 6: 4 Pairs of 24-gauge copper wires, and can transmit up to 10Gbps
			* Category 6a: Used in networks at speeds up to 10Gbps
			* Category 7: Used in networks at speeds up to 10Gbps
			
		* These UTP Cables are terminated with RJ-45 connections. They may be terminated in one of two ways: Straight-Through and Crossover cables.
			* Like to like devices connect via crossover cables (e.g. switch to switch)
			* Like to unlike devices connect via straight-through cables (e.g. switch to PC)
		* The pin layout at each end of the cables varies between the two types.
		* This is as follows:
	
		![Straight-Through vs. Crossover](http://www.incentre.net/wp-content/uploads/2015/02/ethcable03.gif)
		
	* Optical Fibres
		* These fibres come in two types, Single and Multi Mode
		* Unlike copper cables, which transmit data as electrical signals, fiber-optic cables transmit data as pulsesof light; in addition, fiber-optic cables are not susceptible to radio frequency interference (RFI) or electromagnetic interference (EMI).
		* Therefore, implementing fiber-optic cabling can be useful in buildings that contain sources of electrical or magnetic interference.
		* Fiber-optic cables are also useful for connecting buildings that are electrically incompatible.
		* Because fiber-optic cables support greater bandwidth and longer segment distances than UTP cables, fiber-optic cables are commonly used for network backbones and for high-speed data transfer.
		* Fiber-optic cables can be used to create Fiber Distributed Data Interface (FDDI) LANs, which are 100-Mbps dual-ring LANs.
		* However, Cisco switches and Cisco routers do not require fiber-optic cable connections in order to communicate with each other.
		* Although fiber-optic cables are useful in situations where there are problems or incompatibilities related to electrical issues, fiber-optic cables typically cost more than copper UTP, shielded twisted-pair (STP), or coaxial cables.
		* These cables can also be terminated with differing connectors:
			![Connectors](http://i.imgur.com/WLFysNY.png)
	* Wireless (This has no connection media)

* Ethernet frames have a fixed structure. This may be:

	|Field Length (bits)       |8       |6                  |6             |2   |46-1500|4  |
	|--------------------------|--------|-------------------|--------------|----|-------|---|
	|**Typical Frame Contents**|Preamble|Destination Address|Source Address|Type|Data   |FCS|
	
	* Preamble	- 8 Bytes of Binary digits used to synchronise the signals of the communicating hosts.
	* DA - The address of the NIC on the local network that the packet is being sent to.
	* SA - The address of the NIC on the sending host.
	* Type - Code identifying the network layer protocol.
	* Data & Padding - Data being sent to the host. If the data is less than 46 Bytes, padding is used to make up this space.
	* FCS - Checksum mechanism used to make sure the data is sent without corruption.
	
* MAC Addresses are 48-bit strings of binary characters.
* They are split in half, containing the Organisation Unique Identifier and the Vendor Assigned Portion.
* These are noted in Hexadecimal format, and may appear as: `0000.0c43.2e08`, `00:00:0c:43:2e:08` or `00-00-0C-43-2E-08`.

* Switches perform frame switching. This is aided by the MAC Address Table, informing the switch of the relationship between host MAC Addresses and Ports.
* This procedure is as follows:
	1. Switch receives a frame from PC A on Port A.
	2. Switch enters the Source MAC Address (the port the message is received on) of PC A into its MAC Address table.
	3. Switch checks its MAC Address table for the destination MAC Address, however because it is unknown the frame is flooded to all ports, except the port that the frame is received on.
	4. The device with a matching destination MAC Address replies to the unicast with a unicast frame addressed to PC A.
	5. The switch enters the source MAC Address of PC B and the port number of the switch port that received the frame into its MAC Address table.
	6. The switch can now forward frames between these addresses without flooding, as these addresses are now in its MAC Address table.
* VLSM is Variable length subnet masking, and is used to make the most efficient use of the subnet range.
* It came into effect as the remaining IPv4 addresses were depleted.
* e.g. A provider may offer an address of 150.1.0.0/16 to a router. There may be 5 networks connected to the router, all with varying numbers of hosts on each network. It would be inefficient to provide all networks with the same subnet, in order to match the largest size network, huge numbers of host addresses would be wasted.
* Therefore, varying the length of the subnet mask allows the mot efficient use of the address range available. 
	
### Troubleshooting
* Troubleshooting issues may happen in a couple of ways:
* The OSI Model may be used to troubleshoot an error, be that by starting at the top, bottom or from using the 'divide and conquer' method (starting in the middle and working from above and below.
* If `ping` works, layers 3 and below (at least) are functional, because it is a layer 3 protocol.
* Using `telnet`, the user can test layer 4 functionality.
* Copper media can suffer from issues via:
	* Wiring damage
	* New sources of EMI
	* Changes to traffic patterns
	* New equipment installation
* Fibre can suffer from issues via:
	* Micro & Macro-bend data loss (cable is bent too far, causing data loss during reflection of light)
	* Splice loss

## Module 2: Establishing internet connectivity 
### Understanding the TCP/IP Internet Layer
* The Internet Protocol:
	* Operated at the Internet layer in the TCP/IP Model
	* Is connectionless
	* Treats packets independently of one another
	* Hierarchically addresses
	* Uses best-effort delivery methods
	* Values speed over reliability
	* Has no data recovery techniques
	* Is independent of the media
	* Works with IPv4 and IPv6 using 2 different versions
* In a route from PC A in Reading to Server X in San Jose, different layer 2 protocols may be used.
	* e.g. Ethernet, HDLC and PPP.
* This path may be: `PC A` → `SW1` → Eth → `R1` → HDLC → `R3` → PPP → `R2` → Eth → `SW2` → `Server X`
* IP information is transferred across this connection.
	* The process is as follows:
		* PC A generates an IP Packet, and S1 encapsulates it into an Ethernet frame.
		* Once the frame gets to R1, the frame is de-encapsulated and the layer 3 information is read.
		* The frame is re-encapsulated by R1 into a HDLC frame and forwarded on.
		* Once the frame gets to R3, the frame is de-encapsulated and the layer 3 information is read.
		* The frame is re-encapsulated by R3 into a PPP frame and forwarded on.
		* Once the frame gets to R2, the frame is de-encapsulated and the layer 3 information is read.
		* The frame is re-encapsulated by R2 into a Ethernet frame and forwarded on.
		* SW2 Receives the frame and forwards it to Server X.
		* Server X de-encapsulates the frame entirely and processes the request.
		
		> No conversion ever takes place. Each time a frame is de-encapsulated, the L2 data is discarded and replaced.

* IPv4 Addresses are 32 bit numbers, split into 4 octets.
* It is composed of two parts:
	* The network ID address - this is unchanged for any devices on a network.
	* Host addresses - this changes for each host on a network.
	* The size of each of these two portions is fluid dependant on the class of the address.
![IPv4 Layer Address Fields](http://computing.dcu.ie/~humphrys/Notes/Networks/tanenbaum/5-53.jpg)
	* Version - IP version
	* IHL - Header length
	* Service Type - Provides information on the desires QoS
	* Total Length - Length of the packet, inc. header and data
	* ID - Used for unique fragment identification
	* Flag - Sets various control flags regarding identification
	* Fragment offset - Indicates where specific fragments begin
	* TTL - Time to Live, lifetime of a packet
	* Protocol - Indicates protocol in use
	* Header Checksum - Used for error detection
	* Source Address - 32 bit binary value of the sending endpoint
	* Destination Address - 32 bit binary value of the receiving endpoint
	* Options - Indicates optional parameters
	* Padding - Used to ensure that the header ends on a 32 bit boundary
	
* Binary is a base 2 number system
* An IPv4 uses 32 binary digits.
* An IPv4 address is traditionally displayed in dotted decimal format (e.g. 192.168.4.6)
* The left-most character in a binary octet is the Most Significant Bit and the right-most is the Least Significant Bit.

	|128    |64     |32     |16     |8      |4      |2      |1      |
	|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|
	|$$2^7$$|$$2^6$$|$$2^5$$|$$2^4$$|$$2^3$$|$$2^2$$|$$2^1$$|$$2^0$$|

* Using this system, the number `00101000` translates to `40`.

* IP Addresses have different classes:
	* Class A - First Bit Fixed at `0`, first byte reserved for the network portion - used in networks with more than 16 million hosts.
	* Class B - First 2 Bits Fixed at `10`, first 2 bytes reserved for the network portion - used in networks with more than 65,000 hosts.
	* Class C - First 3 Bits Fixed at `110`, first 3 bytes reserved for the network portion - used in networks with less than 254 hosts.
	* Class D - First 4 Bits Fixed at `1110`, this is used for multicast addresses, and unlike Classes A, B & C, this is always a destination address.
	* Class E - First 5 Bits Fixed at `1111`, this is a reserved experimental range.
* The IANA (Internet Assigned Number Authority) Initially developed these classes.
> Cisco IP Phones use the Class D address 239.0.0.1 to send hold music via multicast to save on bandwidth.

	|IP address Class            |First Octet Binary Range|First Octet Decimal Range|Maximum Number of Hosts/Subnet|
	|:--------------------------:|:----------------------:|:-----------------------:|:----------------------------:|
	|Class A                     |00000001 to 01111110    |1 to 126                 |16,777,214                    |
	|Class B                     |10000000 to 10111111    |128 to 191               |65,534                        |
	|Class C                     |11000000 to 11011111    |192 to 223               |254                           |
	|Class D                     |11000000 to 11101111    |224 to 239               |-                             |
	|Class E                     |11110000 to 11111111    |240 to 255               |-                             |

	> The Class A address range from 127.0.0.0 to 127.255.255.255 is reserved for loopback and diagnostics purposes.
	
* Some IPv4 addresses and ranges are reserved, and cannot be given to hosts. For example:
	* 0.0.0.0 - Unspecified, or Any Network
	* 255.255.255.255 - Local Network Broadcast
	* Any address with the host portion as 0s - Network address
		* e.g. an address of 172.16.0.0 cannot be given to a host as it is a network address.
	* 10.255.255.255 - Directed Broadcast address
 
* This method is called class-full addressing.
* Another method is classless inter domain routing (CIDR)

* Worked Examples:
	* 200.210.18.34
		* Class C Address (200 falls between 192 to 223)
	* 10.255.17.254
		* Class A Address (10 falls between 1 to 126)
	* 172.54.3.2
		* Class B Address (172 falls between 128 to 191)
		
* An IPv4 Class C Address, for example, could be:

	|192       |168       |4         |6         |
	|:--------:|:--------:|:--------:|:--------:|
	|`11000000`|`10100010`|`00000100`|`00000110`|

* The number of usable hosts within a subnet can be calculated with $$2^n-2$$ where $$n$$ = number of bits available for the address portion of the IP address.
	* e.g. $$2 bits \therefore m=2 \therefore 2^2 = 4$$

* IPv4 has private and public IP ranges:
	* Private
	
		|IP Address Class|Range                         |
		|:--------------:|------------------------------|
		|A               |10.0.0.0 to 10.255.255.255    |
		|B               |172.16.0.0 to 172.31.255.255  |
		|C               |192.168.0.0 to 192.168.255.255|
		
	* Public
	
		|IP Address Class|Range                                                          |
		|:--------------:|---------------------------------------------------------------|
		|A               |1.0.0.0 to 9.255.255.255                                       |
		|                |11.0.0.0 to 126.255.255.255                                    |
		|B               |128.0.0.0 to 172.15.255.255                                    |
		|                |172.32.0.0 to 191.255.255.255                                  |
		|C               |192.167.0.0 to 192.167.255.255                                 |
		|                |192.169.0.0 to 223.255.255.255                                 |

* IPv6 offers $$3.4 \times 10^{38}$$ Addresses.

* DNS is the Domain Name System. It translates IP addresses to domain names such as 'www.cisco.com'.

### Understanding IP addressing and Subnets
* By subnetworking a network:
	* Smaller networks can be more easily managed
	* Overall network traffic is reduced
	* Network security policies can be more easily introduced
* When IPv4 addresses are expressed, a slash notation is provided in order to display the number of bits in the address is used for the network portion of the address, for example:
	* 10/.1.1.1/8 - A Class A Address with the mask 255.0.0.0
	* 172.16.55.87/16 - A Class B Address with the mask 255.255.0.0
* A Subnet mask:
	* Defines the number of bits that represent the network and submit part of an address
	* Is used by end systems to identify the destination IP address as either local or remote
	* Is used by L3 devices to determine network path

* The table below can be used to assist with slash notations and subnetting:

	|Step                |128|64 |32 |16 |8  |4  |2  |1  |
	|--------------------|---|---|---|---|---|---|---|---|
	|Mask (.x)           |128|192|224|240|248|252|254|255|
	|A: /8 255.x         |/9 |/10|/11|/12|/13|/14|/15|/16|
	|B: /16 255.255.x    |/17|/18|/19|/20|/21|/22|/23|/24|
	|C: /24 255.255.255.x|/25|/26|/27|/28|/29|/30|/31|/32|
	
* To find a network from a host address and a subnet mask, perform the following:
	* Device Address: 15.17.1.12
	* Subnet Mask: 255.0.0.0

	|            |   |128|64 |32 |16 |8  |4  |2  |1  |
	|------------|---|---|---|---|---|---|---|---|---|
	|Host Address|15 |0  |0  |0  |0  |1  |1  |1  |1  |
	|Subnet Mask |255|1  |1  |1  |1  |1  |1  |1  |1  |
	|Network ID  |?  |0  |0  |0  |0  |1  |1  |1  |1  |

	> The same process should be completed with each octet
	
* A host needs to be aware of its subnet mask to know when to send messages intended for devices in other networks to the default gateway instead.

* Worked Example 1:
	* 200.210.18.0/28 → Class C Address (Mask 255.255.255.240)
	* The network features 14 collision domains, and thus needs a minimum of 14 subnets
	* At least 10 hosts required per subnet
	* Subnetting can occur only the last byte
	* In the last octet:
	
		|     |128  |64   |32   |16   |8    |4    |2    |1    |
		|-----|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
		|Mask |1    |1    |1    |1    |**0**|**0**|**0**|**0**|
		
		> **Bold** denotes the host portion of the octet  
		
	* Because the last available bit in the mask is in position 4, equalling 16, that will be the step used for each of the subnets.

	* Subnet 1: 200.210.18.0/28
		* First Host: 200.210.18.1
		* Last Host: 200.210.18.14
		* Broadcast Address: 200.210.18.15
	* Subnet 2: 200.210.18.16/28
		* First Host: 200.210.18.17
		* Last Host: 200.210.18.30
		* Broadcast Address: 200.210.18.31
	* Subnet 3: 200.210.18.32/28
		* First Host: 200.210.18.33
		* Last Host: 200.210.18.46
		* Broadcast Address: 200.210.18.47
	* Subnet 4: 200.210.18.48/28
		* First Host: 200.210.18.49
		* Last Host: 200.210.18.62
		* Broadcast Address: 200.210.18.63
	* Subnet 5: 200.210.18.64/28
		* First Host: 200.210.18.65
		* Last Host: 200.210.18.78
		* Broadcast Address: 200.210.18.79
	* Subnet 6: 200.210.18.80/28
		* First Host: 200.210.18.81
		* Last Host: 200.210.18.94
		* Broadcast Address: 200.210.18.95

* Worked Example 2:
	* 15.17.18.35/24 → Class A Host Address (Mask 255.255.255.0)
	* Here the network address would be 15.17.18.0 for the subnet this host falls into, calculated by ANDing the values of the provided host address with the subnet mask.
	* Usable hosts would be calculated as: $$2^8-2=254$$
	* Number of subnets within the network is calculated as: $$2^8=256$$

* Worked Example 3:
	* 200.210.18.51/28 → Class C Host Address (Mask 255.255.255.240)
	* Network address of subnet 1 would be: 200.210.18.?
		
		|    |128|64 |32 |16 |8  |4  |2  |1  |
		|:--:|---|---|---|---|---|---|---|---|
		|.51 |0  |0  |1  |1  |0  |0  |1  |1  |
		|.240|1  |1  |1  |1  |0  |0  |0  |0  |
		|=   |0  |0  |1  |1  |0  |0  |0  |0  |  
		= 48
		
	* The subnet ID for this host would be: 200.210.18.48
	
### Understanding the TCP/IP Transport Layer
* The Transport layer on the TCP/IP Model maps to the Transport layer on the OSI Model also.
* Its functions are as follows:
	* Session Multiplexing
	* Identification of differing applications
	* Segmentation*
	* Flow-Control*
	* Connection-Orientated
	* Reliability*

		> *When required

* TTL - Time To Live (the number of routers the traffic can pass through in order to reach its destination before it is destroyed)
* The two most commonly used protocols here are TCP and UDP:

#### TCP
* Multiple applications occur at the same time on a system, e.g. web browsing using HTTP and file sharing using FTP. 
* To start a TCP communication, a 3 way handshake takes place:
	* (Host A) SYN → (Host B) SYN-ACK → (Host A) ACK
	* SYN meaning Synchronise
	* ACK meaning Acknowledge of request
* To end a TCP Conversation, a seminal process happens:
	* (Host A) FIN → (Host B) ACK-FIN → (Host A) ACK
	* FIN meaning Finish or Terminate session
	* ACK meaning Acknowledge of request
* Session multiplexing is used to allow an IP host to communicate using multiple protocols simultaneously.
* Differing Ports are used here to allow for this. e.g. HTTP on port 80 & FTP on port 21.
* Every application process requires a port number to allow these multiple processes to not be confused with one another.
* In order to process multiple data streams at once (*never cross the streams*) the data must be segmented to fit the Maximum Transmission Unit (MTU) of the layers below. IP 1500 as the MTU for that protocol. This is the normal size for MTU.
* If a sender sends data faster than it can be received, some packets will be dropped, and TCP requires them to be retransmitted. 
* TCP Detects dropped packets and resends them.
* For flow control to work the receiver must send ACK responses to the sender after each chunk of data that is sent.
* Flow control is used to maximise the transfer rate whilst minimising the number of retransmissions needed.
* The Round Trip Time (RTT) value represents the time for data to get from sender to receiver and back. If this is too significant, then windowing may also be used. This allows the receiver to advertise the maximum amount of that can be received by the device prior to any being sent.
* TCP has 3 main objectives:
	* Detection and Transmission of dropped packets
	* Detection and Remediation of duplicate or out-of-order data
	* Avoidance of congestion in the network 

#### UDP
* UDP is a best effort protocol that favours speed over reliability.
* Offers applications access to the network layer without the reliability overheads of TCP.
* One-way datagrams are sent to the receiver without any type of advance notification from the device.
* Provides no way to resend or discover lost packets
* Offers a low over-head

![TCP & UDP Headers](https://skminhaj.files.wordpress.com/2016/02/92926-tcp_udp_headers.jpg)

* Common Application Layer Protocols and corresponding Ports

	|Protocol|Port           |
	|--------|---------------|
	|FTP     |21 - TCP       |
	|SSH     |22 -  TCP      |
	|Telnet  |23 -  TCP      |
	|HTTP    |80 -  TCP      |
	|HTTPS   |443 - TCP   |  |
	|DNS     |53 -  TCP & UDP|
	|TFTP    |69 -  UDP      |
	|SNMP    |161 -  UDP     |

* DNS takes place over both TCP and UDP. UDP to send the initial request from a host, and TCP to synchronise between DNS Servers.

* Possible Webpage Responses:
	* 404 - Page not found
	* 200 - OK
	* 301 - Permanent Redirect (e.g. HTTP to HTTPS) 

### Exploring the Functions of a Router
* Routers are required to reach hosts that are not within the same local network as the sender.
* To do this, they use routing tables.
* When a path to the destination hast cannot be found, a "Destination Unreachable" message is sent back to the sender to inform them of the error.
* The command `show ip route` will display the Routing Table.
* Any packets that are for a host not found on the local network that the router is attached to are sent via the default gateway to exit the local network.
* Packets intended to external hosts will feature the destination address as the routers default gateway.
* Address Resolution Protocol (ARP) is used to resolve the link between IP address and MAC Address.
* When a router receives a frame, it checks the destination address to see if the frame was intended for it, and if so strips the frame information. It then inspects the packet's destination address. The Routing Table is consulted, and if a match is found the packet is re-encapsulated into a frame with the destination address of the next hop, and a source address of the router. The packet remains unchanged.

### Configuring a Cisco Router
* To see the ARP table, type `show ip arp` or `show arp` (dependant on the device)
* Routers have 4 Types of memory:
	* RAM: Stores data during CPU processing, volatile storage medium, so data is lost once the system is turned off.
	* NVRAM: Non Volatile RAM, stores the running config of a system.
	* ROM: Read Only Memory on the motherboard, volatile memory type that is read only memory and cannot be changed, only added to. Sometimes contains a ROM Monitor to fallback on if IOS becomes corrupted. POST and Bootstrap is here.
	* Flash: Non-Volatile memory that can be erased and reprogrammed. This is where the IOS image is stored for the system.
* Static routing is whereby an administrator sets a fixed route for data travel to reach another network. Indirect connections will still need to be discovered. E.g. a fixed route to Network B from Network A may be set via port E0/1, as well as an entry that to get to Host B, the message will have to be sent via port E0/1, that Network B is connected to.
* Dynamic Routing uses a routing protocol to advertise remote network to other routers. This is routers sharing their routing table with other routers.
* Dynamic routing can be done in one of two ways:
	* Distance-vector routing protocol - Router informs it's neighbour of topology changes periodically, and the data is passed to the next neighbour. e.g. EIGRP.
	* Link-state protocol -  The router informs all nodes in a network of changes in topology e.g. OSPF.
* Each Router can inform the next one that it is directly connected to about the hosts that it has within it's broadcast domain, and this information is passed about other routers that are directly connected to the next etc. There are many routing protocols with unique properties, e.g. RIP, EIGRP and BGP.
* Routers have two main functions:
	* Path determining
	* Packet Forwarding, of which there are 3 main systems:
		* Process Switching - every received packet is compared to all entries in the routing table.
		* Fast Switching - Recent destinations are cached to improve lookup speeds, this is consulted before the routing table.
		* Cisco Express Forwarding - Fastest combination of the two previous technologies.
* In a routing table, abbreviations along the left hand side will show how the addresses were discovered, e.g. C - Connected, S - Static or D - EIGRP
* Common Metrics used in routing are as follows:
	* Bandwidth: the data capacity of a link (the higher the better).
	* Delay: The time required to move along a link, dependant on bandwidth, port queues, congestion etc. (the lower the better).
	* Cost: arbitrary value assigned by an administrator, based on bandwidth, technology preference etc. (the lower the better)
	* Hop Count: The number of routers a packet must travel through to reach its destination (the lower the better).
* Different protocols use different metrics in order to determine path. e.g. RIP uses Hop Count, OSPF uses Cost, EIGRP uses Bandwidth and Delay.
* Path Determination is used to populated routing tables.
* Admin Distances are used to determine how trustworthy paths are.
	* Directly connected devices have an admin distance of 0
	* Static routes have an admin distance of 1
	* Each protocol has its own admin distance, e.g. OSPF is 110, RIP is 120 and EIGRP is 90.
* Entries in a table may include a subnet, so more than one entry may exist for a single destination via differing subnets. e.g. in a routing table the address 10.1.1.1, the entries 10.1.1.0/24 and 10.1.1.0/16 will show because the subnet masks mean that only the first 1 or 2 octets will be considered. However, the match with the longest prefix is chosen over that of others.
* Routing tables only contain a best route, determined by the protocol in use.
* When building and maintaining a Cisco routing table, multiple methods may be used:
	* The routing processes, which run routing protocols.
	* The forwarding process
	* The routing table its self, accepting data from routing processes.
* CDP - Cisco routing protocol that allows devices to announce their capabilities. An industry standard version of this protocol is Link Layer Discovery Protocol (LDDP) This can be enabled (or disabled) with `(no) lldp run`.
* 4 troubleshooting methods for lack of internet connectivity:
	* Ping loopback to check if the IP stack is functioning.
	* Ping Localhost to check if the NIC is functioning.
	* Ping default gateway to check if the Host can communicate on the Local Network.
	* Ping a remote device to check if the DNS service is functioning.
* To be able to route data, a router must be able to:
	* Identify the destination address (This may be via pre-determined static routes set by an administrator, or by information collected via dynamic routing protocols)
	* Identify the source of the information 
	* Identify routes of data travel 
	* Select routes
	* Maintain and verify routing information

### Enabling Static Routing
* Static routes should be used when:
	* A network is small and simple
	* A network follows a star topology
	* A quick route needs to be created
* Do not use static routing when:
	* A network is likely to change
	* A network is large 
* A stub network is a one-way in one-way out type network.
* To configure a static route, type `ip route (destination address) (destination subnet mask) (next hop or interface)`
* To configure a default route, type `ip route 0.0.0.0 0.0.0.0 (next hop or interface)`

### Learning the basics of ACL
* ACL - Access Control Lists.
* ACL is:
	* A Protocol that sorts with IPs or MAC Addresses dependant on whether it is in use on a Router or a Switch.
	* An IOS tool used to identify particular traffic types.
	* A list of permit and deny statements.
	* Identifies traffic using data in the IP Packet.
	* Usable on both routers and switches.
	* Working from top down through a list of statements, as soon as a non-match is found to any statement the packet is denied.
* Once traffic has been identified, a next course of action can be decided.

	![ACL](https://dbgate.files.wordpress.com/2016/02/flowchartacl.jpg?w=752&h=566)
* To implement for filtering via standard source IP run: `access-list 1 (IP address) (Wild Card bit mask)`.
* To implement via source IP, destination IP or Protocol run: `access-list 100`.
* Wild Card bit masking is used to match IP Conditions using 1s or 0s. e.g. `access-list 1 deny 10.1.1.1 0.0.0.0`
	* Binary 0 meaning "must match"
	* Binary 1 meaning "ignore"
	* This would deny only an IP address that matches the one above *exactly*.
* Adding `access-list 1 deny 0.0.0.0 255.255.255.255` would block all traffic.
* To display access lists run `show access-list`
* ACL can be implemented in 3 types:

	|ACL Type         |Identifier or Range      |
	|-----------------|-------------------------|
	|Numbered Standard|0 to 99 & 1300 to 1999   |
	|Numbered Extended|100 to 199 & 2000 to 2699|
	|Named            |Name                     |

* Worked example:
	* Permitting addresses 172.30.16.0/24 through 172.30.31.0/24
	* The following wildcard mask would be used: 0.0.15.255, allowing only addresses that begin with 172.30.16-31.0
	* Using the address 172.30.16.0 and the wildcard mask, the binary value of the third octet:
	
		|0  |0  |0  |1  |0  |0  |0  |0  |IP address   |
		|---|---|---|---|---|---|---|---|-------------|
		|0  |0  |0  |0  |1  |1  |1  |1  |Wildcard Mask|
		
	* This shows that the first 3 bits in octet 3 must be 0s and the fourth must be a 1, forcing the value to be more than 15 but less than 32, thus denying or permitting this source address range.
* Abbreviations can be used, such as typing `access-list permit host 172.30.16.3` instead of `access-list permit 172.30.16.3 0.0.0.0` to permit only the host with an IP address matching the address provided. Likewise the `any` prefix will ignore all bits in an address, the equivalent of a wildcard mask of `255.255.255.255`.
* If the wildcard mask is unspecified, the default is always 0.0.0.0.
* adding `log` to the end of a access-list statement will produce a log of denied requests. 
* Differing ACLs can be set inbound and outbound on an interface, e.g. `access-group 1 out` when configuring an interface to apply ACL 1 to outbound connection.
* Named ACLs allow you to specify line numbers when adding lines.
* `access-list` - create/edit list
* `access-class` - apply to vty
* `access-group` - apply to packet filtering

### Enabling Internet Connectivity
* Dynamic Host Configuration Protocol (DHCP) is used to assign IPs to devices governed by a central domain.
* Private addresses cannot connect to the internet, and so require a router to send traffic intended to other networks in encapsulated packets.
* Network Address Translation (NAT) is used to translate a inside local to an inside global address.
* NAT removes the need to readdress hosts with global addresses. e.g 192.168.1.10 becomes 81.11.214.6 when communicating with the internet.
* Addresses are conserved using port-level multiplexing, by using Port Address Translation (PAT), multiple hosts can share a single public IP address.
* NAT provides a layer of security by allowing private networks to not advertise themselves on the internet.
* However NAT is process consuming on a router as addresses have to be translated.
* NAT can exist in 3 ways:
	* Static NAT, where each individual device has a inside global address of its own
	* Dynamic NAT, whereby a router has a pool of addresses (that is likely less than the number of hosts in a network) that can be leased to a host to use to communicate with the internet and retuned to the pool when the communication is complete.
	* PAT, using a single inside global address, but many ports to allow many internal users to communicate on the internet. This is achieved using port numbers to manage sessions.
* To configure NAT use `ip nat outside` to state that the interface being configured is the outside interface. `ip nat inside` is used to mark an internal interface.
* When configuring static NAT use `ip nat pool *NAME* (range start) (range end) netmask`, then configure a ACL for the internal network & finish with `ip nat inside source list 1 pool *NAME*`
* To troubleshoot NAT:
	* `show ip nat translation`
	* `show nat statistics`
	* `show access-lists`
	* `show ip route`
	* `debug *THING*` *BE CAREFUL. RESOURCE HEAVY.*

## Module 3: Building a Medium-Sized Network 
### Implementing VLANs and Trunks
* Virtual LANs (VLANs) can be used to:
	* Segment a network.
	* Allow a network to be more flexible.
	* Secure a network better.
* By segmenting a network into VLANs, the number of broadcast domains is increased, This can help to reduce network overheads.
* logical groups of addresses can be separated to act as if they are on their own LANs.
* As a network increases more switches may be added to a VLAN, it may even span over multiple sites. 
* 'normal' ports on a switch are called access ports, and may only be configured to work on a single VLAN.
* 'trunking' ports can be used to link switches and are able to be configured to work with multiple VLANs. These trunk ports are configured to pass any network traffic intended to go to VLANs found on other switches.
* The command `switchport mode (access/trunk)` can be used to change the mode of these ports.
* Trunking ports are non-physical and can be configured on any port.
* An extra field within an ethernet frame is inserted between Source Address and Type, called VLAN Tag. This is added as data leaves a switch through a trunk and is used to help with finding the correct destination at the other end of the trunk. This is IEEE standard 801.1Q or DOT1Q. This is a 32 bit field.
* The tag fields are:
	* Type (16 Bits) - This is set to 0x8100 to show an 801.1Q tagged frame.
	* Priority (3 Bits) - The priority level of the frame
	* Flag (1 Bit) - if this is 1 the MAC address format is non-canonical, if this is 0 then the MAC format is canonical.
	* VLAN ID (12 Bits) - Used to identify the VLAN that the frame is intended for.
* The Standard VLAN range is 1 to 1000, and the Extended Range is 1006 to 4094.
* the Hierarchical model for LANs is composed of:
	* Access Layer - providing endpoints and users with direct network access.
	* Distribution layer - Aggregates access layers and provides service connectivity.
	* Core layer - provides connectivity between distribution layers for large LAN Networks
* When VLANs are created, a file titled 'vlan.dat' is created and stored in flash memory.
* The maximum number of VLANs that can be operated on a network is dependant on the switch being used.
* VLAN 1 is the factory default Ethernet VLAN.
* A dedicated VLAN is for the Cisco switch management IP address.
* It is important to keep management traffic in a separate VLAN, and change the default to something other than VLAN 1.
* In a network that features switches organised in a loop, broadcasts may end up being endlessly forwarded. This is called a broadcast storm. A protocol called Spanning Tree is used to remedy this, whereby if a loop is detected a port is put into a blocking state. STP allows for networks with physical redundancy to function without the risk of broadcast storms getting out of control.

### Routing between VLANs
* Each VLAN requires a unique IP address to function.
* Inter-VLAN routing can be achieved in one of 3 ways:
	* Giving each VLAN an interface on a router, though this is not sustainable.
	* Configuring a physical port with virtual interfaces that allow many VLANs to operate on a single physical port.
	* A L3 Switch can be used, negating the need for a router.
* A logical interface can be set up by typing:
	* `int f0/0.1` (The part of the address after the period shows that the interface is non physical and functions via a logical interface
	* `encapsulation dot1q (VLAN number)`
	* `ip add (address) (subnet mask)`

|Command and Variable                  |Description                                                                      |
|--------------------------------------|---------------------------------------------------------------------------------|
|interface (interface)                 |Enters interface configuration mode                                              |
|encapsulation dot1Q (VLAN number)     |Defines the encapsulation format as IEEE 802.1Q and specifies the VLAN identifier|
|ip address (ip address) (network mask)|Assigns an IP address and network mask to an interface                           |


### Using a Cisco IOS Networking Device as a DHCP Network Server
* DHCP - Dynamic Host Configuration Protocol
* Manually configuring IP addresses can be:
	* Time consuming
	* Prone to error
	* Unfavourable to mobility
* The DHCP Process is as follows:
	1. New hosts broadcast to *Discover* a DHCP server (DHCP Discover Message)
	2. DHCP server responds to *Offer* new hosts IP addresses via unicast
	3. Host responds with a *Request* message to confirm that it accepts the address that it has been offered.
	4. DHCP server *Acknowledges* this via unicast, and offers a lease period.
* This is known as the DORA Process.
* By specifying `ip helper (address)`, any DHCP Discover messages can be converted from broadcast to directed broadcast (unicast) by the router to reach the DHCP server more efficiently.
* to configure DHCP:
	* `ip dhcp pool (name)`
	* `network (ip) (mask)`
	* `default-router (ip)`
	* `dns-server (ip)`
	* `domain-name (address)`
	* `lease (days) (hours) (minutes (seconds)`
	* `exit`

### Implementing RIPv2
* Routing protocols can determine:
	* How updates are conveyed
	* Which knowledge is conveyed
	* When to convey knowledge
	* How to locate recipients of updates
* Routing protocols can be used for:
	* Discovering remote networks
	* Maintaining up-to-date information
	* Choosing the best path to follow
	* Ability to find a new best path when the previous one is not available 
* The operations of a dynamic protocol are:
	* Sending and receiving messages on its interfaces
	* Sharing routing messages and information with other routers
	* exchanging routing information to learn about other remote networks
	* When detecting a change in topology, this can be advertised to other routers
* If all routes feature the same value in a given metric that a dynamic routing protocol may use, Equal Metric Load Balancing is used to spread out the load across the paths.
* Most interior gateway protocol routing conforms to one of the following:
	* Distance vector routing - determining the distance of the link between networks and uses the shortest path.
	* Link-state - creates a map of the entire network to determine best paths. Periodic keep-alive messages are sent to ensure the map remains updated and accurate.
	* Advanced Distance Vector - Combines Distance Vector and Link-State features, whereby a 'Hello' packet is sent, and partial updates occur after that.
* RIPv2 is an open standard protocol that uses Hop Count as it's metric.
* Load balancing of equal paths is used (4 equal paths max by default)
* bandwidth is not taken into account as a metric. E.g. a serial connection with 2 hops will be favoured over a Gigabit connection with 3 hops.
* RIPv1 does not work with VLSM or subnets of differing sizes. RIPv2 does.
* To configure RIP:
	* `router rip` - to configure RIP
	* `version 2` - to enable RIPv2
	* `network 0.0.0.0` - to enable RIP on all interfaces and advertise it
	* `passive-interface e0/0` - allowing an interface to be advertised via RIP, but not receive unnecessary RIP messages
* In an IP Routing table output on a IOS device, the two values in square brackets are: `[ admin distance / hop count ]`
* Automatic RIP Summarisation occurs when a RIP packet moves to a network with a different subnet mask. It does not offer the mask, but instead a class-full IP address. e.g. Router A → Router B → Router C. Routers A and C are discontiguous to one another and occur on different subnet masks. This creates a class-full network boundary, whereby the Network address s different. 
* Auto RIP Summarisation is where a router compresses it's entire route table to a single network address and advertises that address.
* This is performed by EIGRP, RIPv1 and RIPv2.

> Find useful posters at [PacketLife.net](http://packetlife.net/library/cheat-sheets/)

## Module 4: Network Device Management & Security 
### Securing Administrative Access
* To enable varying passwords perform the following commands:
	* Privileged EXEC password: `enable password (password)`
	* Encrypted Privileged EXEC password: `enable secret (password)`
	* Encrypt all plaintext passwords: `service password encryption`
	* Secure console passwords:
		* `line console 0`
		* `password (password)`
		* `login`
	* To set a mode timeout perform: `exec-timeout (minutes)`
	* Enabling Remote Access passwords:
		* `line vty 0 15`
		* `login`
		* `password (password)`
	* To configure SSH:
		* `hostname (name)`
		* `ip domain-name (domain)`
		* `username (name) secret (password)`
		* `crypto key generate rsa modulus 1024`
		* `line vty 0 15`
		* `login local`
		* `transport input ssh`
		* `exit`
		* `ip ssh version 2`

### Implementing Device Hardening
* Using range selection multiple interfaces can be simultaneously configured:
	* `interface range (interface) 0 - 2`
	* `switchport access vlan 999` - Assigning to an unused VLAN for contingency 
	* `shutdown`
* When data is traveling through trunk ports, frames intended for the native VLAN are not tagged.
* Several implementations port security exist:
	* Static Learning - MAC addresses that use a specific port can be configured, preventing access to those not permitted from sending frames through that port.
	* Dynamic Learning - A number of addresses can be added and permitted at one time. This does not allow you to specify *which* addresses are allowed, however.
	* Combination - Some specific addresses are allowed, but a range is specified of new addresses that can be learned. e.g. allow up to 4 addresses per port, but statically learn 2 addresses.
	* Sticky Learning - Dynamically learned addresses are converted to 'sticky learned addresses' and stored in running config as if they are statically learned. The admin must save the config to move these addresses to NVRAM.
* MAC Layer Flooding Attack - filling the MAC address table and resending frames so that the entries are not forgotten, in order to force all devices to have an Unknown Unicast Address, flooding all frames and allowing a device to intercept all network traffic.
* When security violations occur, a port can be configured to:
	* Protect - Drops packets with unknown SAs, until enough addresses are un-learned to drop below the maximum value.
	* Restrict - Performs Protect functions, but also reports on security violations.
	* Shutdown - Shuts down the port, logs the attack and forces the admin to re-open the port manually.
* To configure Port security:
 	* `int (interface)`
 	* `switchport mode access`
 	* `switchport port-security`
 	* `switchport port-security maximum 1`
* To allow the switch to re-open ports after a violation, run:
	* `errdisable recovery cause (cause)`
	* `errdisable recovery interval (seconds)`
* To disable Cisco Discovery Protocol (CDP): `no cdp run`
* To disable the http server: `no ip http server`
* Network Time Protocol (NTP) is used to synchronise all network devices to use a shared time. Cisco Devices can be used as NTP servers. Configure with `ntp master`. Any devices on the network can be told to synchronise with `ntp server (ip)`.
* Switches can are configured to use the router they are connected to in able to synchronise their times. As each devices becomes a layer further from the time source its Stratum Level increases by 1 as it becomes less accurate, starting from 1. 15 is the highest active level.
* `Clock timezone (code)` can set the device timezone.

### Configuring System Message Logging
* System logging allows event notifications to be sent over IP networks. By default these are sent to a logging program.
* These can be configured to be sent to 4 types of location:
	* A logging buffer
	* Console lines
	* Terminal Lines
	* Syslog Server
* e.g. to send syslog messages to a server, `run logging (ip)`

|Severity Level   |Explanation                     |
|-----------------|--------------------------------|
|0 - Emergency    |System is unusable              |
|1 - Alert        |Immediate action needed         |
|2 - Critical     |Critical condition              |
|3 - Error        |Error condition                 |
|4 - Warning      |Warning condition               |
|5 - Notification |Normal but significant condition|
|6 - Informational|Informational message           |
|7 - Debugging    |Debug message                   |

"**E**liminate **a** **c**risis, **e**ven **w**hen **n**obody **i**s **d**ying"

### Managing Cisco Devices
* On a Router or Switch, ROM contains:
	* Bootstrap - detailing the startup behaviour of a device
	* POST - Power on Self Test
	* ROM Monitor - A backup OS, used for recovery
* The process is:
	* Reads Bootstrap
	* Run POST
	* Load IOS
	* If IOS is corrupt or missing, run ROM Monitor
	* If IOS is acceptable, then load IOS
	* Read startup-config
	* Start running-config
* The config register is a 16 bit hex value that denotes how a router acts. Each of the config bits have different meanings:
	* 0 to 3 - boot field (Hex 0 to F)
	* 6 - causes system to ignore NVRAM contents
	* 7 - disables boot messages
	* 8 - break disabled
	* 9 - causes the system to use the secondary bootstrap (typically not used)
	* 10 - IP broadcast with all 0s
	* 05, 11, 12 - Console line speed
	* 13 - Boots default ROM software
	* 14 - IP broadcasts do not have net numbers
	* 15 - enables diagnostic messages and ignores NVRAM contents
* e.g. if the registry is 0x2102 (router default) then:
	* Bit 2, 8 and 13 are on.
	* Therefore, the system will load the 1st file in flash, break is disabled and the default ROM software is booted into.
* Loading Cisco IOS configuration files process:
	* Boot up router
	* Startup config in NVRAM? → If yes, load startup config → If no, look for TFTP server for config
	* If none, launch setup
* IOS file name key:
	* Cs900-universalk9-mz.SPA-152-4.M1.bin
	* Platform (Cisco 2900 Router) - Feature set (universal - File format (M: runs in RAM, Z: Zipped) . Digitally Signed - Version (15.2, release 4 . M1) . File type (Binary executable).
* Device config can be loaded from:
	* NVRAM
	* Terminal
	* TFTP Server 
* To enter password recovery, set the boot process to ignore NVRAM:
	1. Switch off router
	2. Press **break** (Ctrl-C) on launch to enter ROM Monitor
	3. Type `confreg 0x2142`
	4. Save running config and reboot to start setup

### Licensing
* `show license` command will display active licenses on the system.
* Routers ship with an evaluation licence for most packages and features that are supported on the router. In order to activate a package, you must purchase a new licence.
* PAK - Product Authorisation Key
* To permanently activate a a software package:
	1. Purchase the package, in order to obtain a PAK
	2. Obtain the license file via Cisco License Manager or Cisco license Registration Portal.
	3. Use the CLI to install the license.
* `show license udi` may need to be used to show the product ID and Serial number of the router.

	|Package               |Features                                    |
	|----------------------|--------------------------------------------|
	|IP Base               |Entry-level Cisco IOS functionality         |
	|DATA                  |MPLS, ATM & Multiprotocol Support           |
	|Unified Communications|VoIP an IP Telephony                        |
	|Security              |Cisco IOS Firewall, IPS, IPSec, 3DES and VPN|

* `show license feature` shows the licenses supported by the router.
* `license install` installs a license file. After this the router must be reloaded to apply changes.
* e.g. `license boot module c2900 technology-package uck9` would install package UCK9 
* Using `license save flash:all_licenses.lic` will backup all licenses to the flash memory of the router.
* 

## Module 5: Introducing IPv6 
### Introducing IPv6 Basics
* To circumvent IPv4 address shortages, the following methods are used:
	* CIDR
	* VLSM
	* NAT
	* DHCP
* These have issues however.
* IPv6 has benefits over IPv4:
	* Larger address volumes:
	* Simpler header format
	* Security and mobility
* The format is 8 x 16 bit hex fields
* Leading 0s are optionalv
* e.g 2001:0DB8:010F:0001:0000:0000:0000:0000:0ACD becomes 2001:DB8:10F:1:0:0:0:ACD
* Successive 0s can be suppressed to form 2001:DB8:10F:1::ACD
* The IPv6 loopback is ::1
* IPv6 is classless and has 3 address types:
	* Unicast
	* Multicast
	* Anycast
* There are 3 types of IPv6 Address:
	* Global
	* Unique Local
	* Link-Local
* The address format for a unicast address is split in half to form a Network ID and a Host ID portion, each 64 bits in size.
* There are very types of unicast:
	* Global Unicast:
	
		|Provider                  |Site  |Host        |
		|--------------------------|------|------------|
		|48 bit                    |16 bit|64 bit      |
		|001, Global Routing Prefix|SLA   |Interface ID|
		
		* Here the first three bits are set to 001, an identifying feature of Global Unicast Addresses.
		* Therefore these addresses always start with 2000::/3
		* The global routing prefix is set by the ISP
		* The Site-Level Aggregator, or Subnet ID is set by the organisation. This can support up to 65,535 different subnet addresses.
		* The interface ID is often the MAC address of the device, as it forms a unique identifier that can easily be used as it is too a 64 bit address.
	* Unique Local Unicast Address
		* These are used for local communication within a network.
		* This features a unique prefix, followed by a subnet prefix (48 bits long) and a subnet ID (16 bits) before the interface ID.
	* Link Local Unicast Address
		* These are auto configured on devices at manufacture.
		* They are formatted as a 10 bit link local prefix - FE80::/10
		* There is padding up to the 64th bit, whereby the device MAC address follows.
	* IPv6 Multicast Address
		
		|Prefix|Lifetime|Scope         |Padding|Interface ID|
		|------|--------|--------------|-------|------------|
		|FF FF |0 or 1  |1,2,5,8 or E  |0s     |MAC address |
		
		* In the lifetime portion, 0 means permanent address and 1 means temporary.
		* Scope can be to the Node (1), Link (2), Site (5), Organisation (8) or Global (E)
 	* IPv6 Anycast Address
 		* The nodes that an any cast address are assigned to have to be specifically configured to recognise it as an any cast address.
 		* The format is: Prefix, 0s, Interface ID.
 * Stateless Auto-configuration allows devices to neighbour discovery mechanisms to find routers.
 * Stateful Auto-configuration uses a DHCPv6 server to assign addresses and other parameters to hosts.
 * Devices can also have their addresses manually configured. 

### Understanding IPv6 Operation
 ![IPv4 Header vs IPv6 Header](https://i2.wp.com/www.ebrahma.com/wp-content/uploads/2013/12/ipv4-ipv6-header.gif)

 * Internet Control Message Protocol v6 is used for diagnostic services.
 	* Diagnostic Tests 
 	* Router Discovery
 	* Neighbour Discovery
 * These packets can be added to IPv6 Frames, and look like:
 
 ![ICMPv6 Frame](https://notes.shichao.io/tcpv1/figure_8-2.png)
 
	|ICMP Message|Description            |
	|------------|-----------------------|	
	|1           |Destination Unreachable|
	|128         |Echo request           |
	|129         |Echo reply             |
	|133         |Router Solicitation    |
	|134         |Router advertisement   |
	|135         |Neighbour solicitation |
	|136         |Neighbour advertisement|

* Neighbour discovery is used in IPv6 in the same way ARP is used in IPv4.
* It performs the following functions:
	* Determining the data link layer address of devices on the link.
	* Finding neighbour's on a link
	* Keeping track of said neighbours
	* Querying duplicate addresses
* A solicited-node address is composed of FF02:0:0:0:0:1:FF/104 as a prefix, combined with the final 24 bits of the corresponding unicast address.
* This type of address must have a link-local scope.
* These addresses are used for neighbour solicitation and are used when another node needs the data-link layer address off a neighbour device.
* This avoids the need for broadcasts, as seen on ARP.
* However, if an IPv6 address is known, the associated solicited-node multicast address must also be known.
* e.g. the IPv6 Address 2001:0DB8:1001:F:2C0:10FF:FE17:FC0F would be FF02::1:FF17:FC0F.
* The prefix used for multicast ethernet addresses is 33:33 and is added before the last 32 bits of the IPv6 Address.

### Configuring IPv6 Static Routes
* IPv6 features some routing protocols from IPv4 that had to be changed to function with IPv6 - such as:

	|Protocol      |Full Name          |RFC        |
	|--------------|-------------------|-----------|
	|RIPng         |RIP Next Gen       |2080       |
	|OSPFv3        |OSPF Version 3     |2740       |
	|MP-BGP4       |Multiprotocol BGP-4|2545/4760  |
	|EIGRP for IPv6|EIGRP for IPv6     |Proprietary|

* Most IPv6 Protocols are still Interior Gateway Protocols, however BGP is the only Exterior Gateway Protocol in use.
* Static routing is configured in the same way using IPv6 as it is with IPv4.
* e.g. `ipv6 route (IPv6 address of the outgoing interface) (IPv6 next hop)`
* Using `show ipv6 static`, static routes can be displayed.

---
# ICND2 Module Notes
## Module 1: Implementation of Scalable Medium-Sized Networks
### Troubleshooting VLAN Connectivity
* VLANs can be used to segment a network and reduce broadcast messages.
* Hardware used across a campus LAN may be:
	* Distribution Switches
	* Access Switches
	* WAPs
* Routers ignore broadcasts and do not forward them out of it's ports - however this is an expensive solution to a broadcast storm issue on a LAN.
* Fewer cable connections offer fewer points of failure - a L3 switch is a good solution here.
* To implement trunking on a network:
	* `switchport mode vlan`
	* `switchport trunk native vlan (number)`
	* `switchport trunk allowed vlan (numbers)`
* Verify connectivity with `show interfaces (interface) switchport)`
* By default, Cisco Catalyst switches have Dynamic Trunking Protocol enabled. It negotiates the trunking state of a port, which can be understood with the table below.

	|Switchport Mode ↓ →  |Dynamic Auto|Dynamic Desirable|Trunk  |Access |
	|---------------------|------------|-----------------|-------|-------|
	|**Dynamic Auto**     |Access      |Trunk            |Trunk  |Access |
	|**Dynamic Desirable**|Trunk       |Trunk            |Trunk  |Access |
	|**Trunk**            |Trunk       |Trunk            |Trunk  |Limited|
	|**Access**           |Access      |Access           |Limited|Access |

* To make a voice VLAN: `switchport voice vlan (number)`
* Cisco have a proprietary protocol called VLAN Trunking Protocol (VTP), which advertises the VLAN.dat file on a switch to other switches on the network. For this to operate, all devices must be on the same VTP domain.
* The version of the VLAN.dat file in use is advertised on trunk ports only. Devices can request and receive updated versions of the VLAN.
* VTP Pruning can be enabled so that the entire table isn't sent to all devices, however this can generate a lot of advert traffic.
* The process is:
	* VLAN is added or deleted at the VTP Server
	* Revision number incriments
	* Change propagated
	* Devices synchronise to changes
* VTP has 3 modes:
	* Server - Creates, Modifies and Deletes VLANs & Synchronises changes
	* Clients - Can only Synchronise changes
	* Transparent - Has a local database, which it does not synchronise

### Building redundant switched topologies
* Physical redundancy in a LAN is important to offer alternate routes for traffic.
* Redundant topologies eliminate single points of failure.
* This kind of topology does however cause: 
	* Broadcast storms
	* Frame copies arriving at a device at the same time, which may cause errors.
	* MAC address table instability - MAC addresses for ports may appear on other devices
* STP solves all of these issues.
* In the event of a broadcast storm, spanning tree will choose one or more interface to be logically blocked, blocking all traffic in and out of the port. This is in the 802.1D specification, which is now a legacy standard.
* STP is enabled by default on Cisco devices.
* The operation of STP is:
	1. Spanning tree elects a root bridge. There can only be one per network, and this device is chosen because it has the lowest Bridge ID.
		> Bridge Priority Number is a combination of BID and the MAC address of the deice, and can range from 0 to 65535, incrementing by 4096. The default is 32768.
	
	2. Elects a root port for each non-root switch
	3. Elects a designated port for each segment
	4. Ports transition to forwarding or blocking state

* Bridge Protocol Data Units (BPDUs) are Spanning Tree Hello packets and are exchanged between devices to discover who has the lowest BID, and should be the Root Bridge.
	> A BPDU contains Bridge ID and Root ID.
* These are compared by the switches to find out which BPDU is *superior* to the others. Once compared, if the switch finds it's self to be of a higher bridge ID, it proclaims the other switches claim to be root as true, no longer suggesting that it is the root device.
* Root ports are defined by ports closest to the root, by having the lowest root path cost.
* This can be calculated via the following table:

	|Data Rate|STP Cost (802.1D-1998)|STP Cost (802.1D-2004)|
	|---------|----------------------|----------------------|
	|4 Mbps   |250                   |5000000               |
	|10 Mbps  |100                   |2000000               |
	|16 Mbps  |62                    |1250000               |
	|100 Mbps |19                    |200000                |
	|1 Gbps   |4                     |20000                 |
	|2 Gbps   |3                     |10000                 |
	|10 Gbps  |2                     |2000                  |

* The RPC (Route Path Cost) is combined when the link travels across another switch
	* e.g. from A → (RPC 4) → B → (RPC 2) → C 
	* This has a RPC total of 6 across A to C.
	* The fastest route is marked as the Root Port on the switch, and is used to inform the network of topology changes within the network, in a TCMP PDU.
	* If two routes coming into the switch have the same RPC, the route with the lowest BID is marked as the root port into and out of the switch.
* Root ports are **never** blocked
* Designated ports propagate BPDUs onto the local network segment.
* Any port that isn't an RP is blocked for all traffic but BPDUs, in order to prevent the Layer 2 loops panning tree was created to solve. These BPDUs travel roughly every 2 seconds.
* Without this the root is assumed dead and the BPDU Root Bridge allocation starts again.
* IF a link goes down, the root device is no longer present, a blocked link opens and becomes a forwarding port, and the new root port.
* IEEE 802.1D is standard STP, the wait time is 30 second before a link is considered dead. This is because the port must transition to Listening, then to Learning. The default delay between state changes is 15 seconds, hence the 30s wait time.
* IEEE 802.1W is Rapid Spanning Tree Protocol, which has a 2 to 5 second wait before considering a link dead.
* Per VLAN Spanning Tree (PVST+) is a Cisco protocol that provides a 802.1D spanning tree instance per VLAN in a network. This is slow and resource intensive however, so Rapid PVST+ was developed to help solve the issue, which used a tree for multiple VLANs.
* By default:
	* PVST+ is enabled
	* PVST+ is active on all ports within VLAN 1
	* Slower convergence is present however, after changes in topology than that of RSTP
* A root bridge can be forced by doing the following:
	* `spanning-tree vlan root 1 root primary` making the given switch the root device.
	* `spanning-tree vlan root 1 root secondary` on an alternate device, forcing it as the secondary.
* PVST+ uses an extended bridge ID, meaning that the latter 12 bits of the 2 byte field traditionally reserved for bridge priority is now used for the extended system ID. This is why using PVST+ the Bridge Priority Number increments by 4096.
* PortFast jumps from blocking to forwarding without listening or learning prior. This can only be configured on access ports. PortFast should only be configured on ports leading to end devices.
* BPDU Guard shuts down a port when a BPDU is received on it. This is used in combination with PortFast.
* PortFast disables the functionality of spanning tree on a given switch port.
* Devices connected to PortFast Interfaces should not ever generate BPDUs, and so if the topology is changed to connect a switch to a link with PortFast enabled, by using BPDU block, the port will be shut down if a BPDU is received to prevent any loops occurring.
* When a voice VLAN is enabled, PortFast is also enabled by default.
* To configure PortFast and BPDU Guard:
	* `interface (interface)`
	* `spanning-tree portfast`
	* `spanning-tree bdpuguard enable`
* Or to enable globally on all non-trunk ports:
	* `spanning-tree portfast bpduguard default`
	* `spanning-tree portfast default`

### Improving Redundant Switched Topologies with EtherChannel
* Multiple links can be made between switches to improve bandwidth, however if spanning tree is enabled, all bar one of these links will be disabled to prevent a broadcast storm. This can be mitigated with EtherChannel.
* EtherChannel aggregates links between switches on a logical basis.
* It can be used to offer a more high-bandwidth connection
* It allows load sharing across links
* It allows for redundancy in a switched network.
* As far as spanning tree is aware, when EtherChannel is enabled, the EtherChannel link appears as a one-to-one connection, instead of a many-to-many.
* If STP decides to disable the link on an interface that the EtherChannel is enabled on, the entire EtherChannel link goes down.
* The cost is assessed by the combined speed of the links, e.g. 10 x 1Gbps links will be seen as 1 x 10Gbps link by STP when EtherChannel is enabled.
* Two protocols can be used to automatically configure EtherChannel on a switch:
	* PAgP - A Cisco Proprietary protocol (Port Aggregation Protocol)
	* LACP - An IEEE 802.ad standard (Link Aggregation Control Protocol)
	* These **CANNOT** be mixed - else an EtherChannel will not be created.
* PAgP has two modes: 'PAgP Desirable' (Actively desiring to be come an EtherChannel, requesting if the other side of the link can) and 'PAgP Auto' (willing to become an EtherChannel but will not seek to create one)
* LACP has two modes: 'LACP Active' (Actively desiring to be come an EtherChannel, requesting if the other side of the link can) and 'LACP Passive' (willing to become an EtherChannel but will not seek to create one)
* Static EtherChannels can also be configured without the need to use either of the protocols. These show as mode 'On'
* Both ends of an EtherChannel need to be the same in the following regards:
	* Speed
	* Mode (Trunk/Access)
	* Native and Allowed VLANs
	* Duplex
* To configure EtherChannel:
	* `interface range e0/0 - 3`
	* `channel-group (number) (mode)`
	* `exit`
	* `interface port-channel (number)`
	* `switchport trunk encapsulation dot1q`
	* `switchport mode trunk`
	* `switchport trunk allowed vlan (numbers)`

### Understanding Layer 3 Redundancy
* By making a network redundant at layer 3, there is a fail-safe in the event that a router goes offline.
* However, access devices can only have a single default gateway, which means that devices cannot access the network if their default gateway router goers offline, irregardless of whether there is a layer 3 redundancy within the network or not.
* To solve this, a First Hop Redundancy Protocol (FHRP) can be used.
* Cisco were first to market here with Hot Standby Routing Protocol, a proprietary protocol.
* Virtual Router Redundancy Protocol (VRRP) is an alternative available, which is an open standard. VRRP is defined within RFC 5798.
* Gateway Load Balancing Protocol (GLBP) is another Cisco protocol, which spreads traffic across the redundant routers in the network.
* When a route fails:
	1. The standby router stops seeing hello messages from the forwarding router.
	2. The standby router takes on the role of the forwarding router.
	3. There is no noticeable change in service because the router assumes the Virtual IP and Virtual MAC of the virtual router.
* When HS or VRRP is enabled, the virtual IP and is provided to the hosts that would otherwise by connected to the physical router in a non-redundant L3 Network. The routers used to produce the redundant network have the alias of the virtual router and can both act upon requests.

	> The Virtual MAC of a HSRPv1 virtual router follows the naming scheme 0000:0c07:ac0**x**, where **x** is the HSRP group number.
	
* With HSRP, client requests are always processed by the active router. When the active router fails, the standby router becomes the active router.
* The Virtual MAC will therefore only be known to be on the port of the active device, as it replies to and sends traffic to and from that address.
* VRRP sends Hello every second, with the dead time being 3 seconds.
* HSRP sends Hello every x seconds, with the dead time being 10 seconds.

**MAKE NOTES ON PAGE 25 to 44**

## Module 2: Troubleshoot Basic Connectivity
### Troubleshooting IPv4 Network Connectivity
* When end to end connectivity cannot be made, perform the following:
	* Verify physical connections - cable and interface.
	* Verify path decisions between source and destination.
	* Verify default gateway settings.
	* Verify resolution settings (DNS).
	* Verify ACLs to ensure traffic is not being blocked.
* By understanding the OSI model, the layer that the issue is occurring on can be discovered, and this will help to cut down the number of possible issues to increase the rate of fault mitigation.
* Three methods can be used:
	* Top-to-Bottom
	* Bottom-to-Top
	* Divide-and-Conquer
* ICMP is a layer 3/4 protocol that can be used to verify connection.
	* Ping is an ICMP type 8 (echo) and Type 0 (reply) message.
	* Traceroute is an ICMP type 11 message
* Ping procedure:
	* PC issues Ping command to IP
	* Router receives the request
	* Makes an ARP request to that address
	* If no reply is made, an ICMP Type 3 message is sent to the host with a code. 
		* 0 meaning detention network unreachable
		* 1 meaning destination host unreachable
		* 2 meaning destination protocol unreachable
		* 3 meaning destination application unreachable
		* 13 meaning administratively filtered
	* `UUUUU` is returned as there is some kind of unreachable error.
	* `.....` means that the router has forwarded the message, but an error occurred further downstream.
	* `.!.!.` meaning that a load-balancing system is in place, and one of the routers is not functioning correctly. `show ip route` should be sued next.
* On a network device, rebooting should be the last port of call, especially if protocols such as spanning tree are in place.
* Multiple ISPs can be used to produce a redundant L3 network. 
* Service Level Agreements (SLAs) can be used to perform actions autonomously on a network.
* e.g. SLA 100:
	* ping ISP 1
	* If fails, degrade HSRP 20
* ICMP redirect (type 5) messages can be sent in the event of failing a SLA to inform the switch to stop using that interface, as the ISP is unreachable.
* To configure this:
	* `ip sla (number)`
	* `icmp-echo (destination ip)`
	* `exit`
	* `ip sla schedule (number) life (seconds) start-time (hh:mm:ss day month)`
* Switch Port Analysis (SPAN) allows you to instruct a switch to send copies of packets to another port on the device. This is also called port mirroring.

### Troubleshooting IPv6 Network Security

|Address Type|Value            |Description                  |
|------------|-----------------|-----------------------------|
|Global      |2000::/3         |Public Networks              |
|Unique-Local|FC00::/7         |Private Networks             |
|Link Local  |FE80 to FEB0::/10|Auto-Configured, not routable|
|Reserved    |range            |Specific types of anycast    |
|Loopback    |::1              |Local testing                |
|Unspecified |::               |Unknown address              |

* IPv6 can be configured using DHCP for IPv6, with stateless auto configuration or statically.
* IPv6 can be configured statically by:
	* `interface (interface)`
	* `ipv6 address (host address)(/notation) OR (network address) eui-64`

* In IPv6, ACLs are called Traffic Filters. They are only available in a named variety and only an equivalent version of an Extended ACL.
* To configure an IPv6 ACL, use:
	* `ipv6 access-list (name)`
	* `(conditions)`
* To apply to an interface do:
	* `ipv6 traffic-filter (name)`

## Module 3: Implementation of an EIGRP-Based Solution
### Implementing EIGRP
* EIGRP is a dynamic routing protocol.
* Dynamic Routing Protocols can:
	* Discover remote networks by exchanging routing information between devices
	* Maintain up-to-date routing information
	* Choose the best path to destination networks
	* The ability to find a new best path if the currently used path is no longer available.
* All routing protocols are used to learn about remote networks and adapt to changes in network topologies.
* Different Routing Protocols use differing metrics to make these decisions.
* There are two types of routing protocols, Interior Gateway (maintained by a single administrative authority) and Exterior Gateway (e.g. via the internet).
* They may use either Distance Vector (e.g. RIP and EIGRP) or Link State (e.g. IS-IS and OSPF), and can be classfull or classless. Classfull routing protocols cannot handle VLSM.
* Every 30s, Distance Vector protocols share routing tables with one another, whereas link-state protocols use link state advertisements, which are flooded to the entire network using a reserve multicast address.`
* Multiple routing protocols and static routes can run simultaneously.
* Routers prefer sources with the lowest AD possible.
* Enhanced Interior Gateway Routing Protocol EIGRP) has the following properties
	* Rapid (2 to 5 second( convergence
	* Load balancing acr
	* Loop free classless routing
	* Reduced bandwidth usage
	* No broadcast address
	* Guarantee a loop free network.
* EIGRP uses the DUAL algorithm to ensure the network is loop free.
* EIGRP will send the route table to another divice initially and then only sends again when there is an update to that routing table.
* Two EIGRP routers exchange hello messages every 5 seconds to ensure the device saline
* An EIGRP Topology table shows all of the hosts and networks discovered by communication with neighbours.
* A Routing table is built from this table by selecting the best route to the connected networks, and the outbound interface used to access it.
* The feasible distance collected from the Topology Table is used as the Metric for that route.
	* Feasible distance = advertised distance + reported metric to neighbour.
* To avoid loops, it is only safe to use a neighbouring router as a next hop to another network if the FD is lower than your locally calculated FD. This prevents a router sending traffic to a next hop router that is further from the destination, only to have it sent back. This is called a Feasibility Condition (FC).
* The next hop router chosen is referred to as the successor.
* EIGRP Query messages are used when a link goes down, in order to request new successors.
* A topology Table will only ever show feasible routes.
* The criteria for metric calculation by EIGRP is with Bandwidth and Delay.
* $$Metric = (BW+Delay) \times 256$$
	* Where Bandwidth is Kbps and Time is in Microseconds (µsec)
* To enable EIGRP:
	* `router eigrp (autonomous system number)` - this number must be the same on all device you wish to share data.
	* `network (IP)` - enabled for any interface with the first octet matching the one inputted here. A wildcard mask can be added to overwrite this feature.
	* The network statement can be repeated to enable EIGRP on other interfaces also.
	* `show eigrp neighbors` will reveal adjacencies made.
	* `show ip eigrp interfaces` will reveal interfaces EIGRP is enabled on.	
* EIGRP calculates a successor for every next hop address where possible, which allows it to offer rapid convergence.
* The routing table is only shared upon table changes, and it only advertises said changes.
* EIGRP advertises on EIGRP 224.0.0.10.
* Feasible successors must also have advertised distances lower than the lowest feasible distance for that same route.
* The recorded bandwidth for calculation is always the slowest data travel rate value in the path. 
* The main downside to EIGRP is in the poor readability of the metric, without the formula, it is hard to understand it's meaning.
* AS numbers are Autonomous System Number, and must be the same along the network EIGRP is running on.
* `show eigrp neighbours` will reveal:
	* Handle - the order that the devices have been discovered in
	* The neighbours IP Address
	* The interface it is attached to
	* The Hold Time
	* The Uptime
* `show eigrp interfaces` will reveal:
	* Information about EIGRP interfaces within a given AS.
	* The number of peers on the interface specified.
	* etc.
* `show eigrp topology` will reveal the EIGRP topology table, which only shows feasible routes unless the `all-links` flag is supplied in addition.
* **Note:** on an EIGRP topology table, P means passive, but not in the passive interface sense. It simply means that a valid successor is being used instead of that interface.
* `show ip protocols` will, among other things, reveal the Metric Weight. This shows K1 through 5, where K1 is bandwidth and K3 is delay. The higher the number, the larger the impact the value will have on the metric calculation. These changes must match for all devices on the same AS.
* EIGRP uses Equal Cost Load balancing, whereby routes with the same metric will share load equally, also called round robin load sharing.
* Unequal Cost Load Balancing is also used when two routes to a network are of different metrics, whereby traffic will still be load balanced, though in accordance to the speeds of the link.

### Implementing EIGRP for IPv6
* EIGRP for IPv4 and IPv6 can run together on a single Cisco router.
* This protocol performs in the same way as EIGRP for IPv4, though it does use a link-local (FE80) address for adjacencies and next-hop attributes.
* To enable, run `ipv6 router eigrp (AS Number)` followed by `no shutdown` at the interface level, as opposed to running `router eigrp` followed by the network that the protocol will operate on.

### Troubleshooting EIGRP
* When suffering from loss of connectivity on an EIGRP network, it will be either a Neighbour Adjacency or Routing Issue.
* `show ip eigrp neighbours` will show as empty if no neighbours can be discovered.
* To prevent adjacency issues:
	* Ensure the interface is up.
	* Ensure the AS is the same.
	* Ensure EIGRP is enabled.
	* Ensure the interfaces are not passive interfaces.
* To prevent a routing table issue:
	* Ensure networks are being advertised
	* Ensure no ACL are preventing advertisement
	* Ensure Automatic Route Summarisation is not causing confusion in the network. Use `no auto-summarisation` to disable this.

## Module 5: Implementation of a Scalable OSPF-Based Solution
### Understanding OSPF
* OSPF is a link-state protocol.
* The benefits of these types of protocol over that of a DV protocol are:
	* Scalability is much better
	* Each router has an understanding of the full network topology.
	* Updates are only send as and when changes to the routing table occur.
	* Faster response times to changes in the network topology.
	* Greater breadth information communicated between routers.
* During Operation, OSPF:
	* Creates neighbour relationships by exchanging hello packets.
	* Propagates Link-state advertisements rather than entire routing tables.
		* These are composed of 'Links' (The router interface) and 'States' (The description of the interface and it's relationship to its neighbours)
	* Floods LSAs to all OSPF Routers
	* Pieces together received LSAs to form a database.
	* Uses SPF to calculate the shortest path to each destination within its routing table.
* The metric used by OSPF is Cost.
* This can be calculated with $$10^8 \times Bandwidth$$
* LSAs have a validity of 60mins. They use sequence numbers to ensure that if these messages are received in the wrong order, it isn't just always the last advert that is actioned upon.
* OSPF can be logically separated into areas. This must include a Backbone, other areas must be connected to this.
* In this however, the scope of routers becomes reduced, and so devices are only aware of what's within their area, unless the device borders 2 areas whereby it will have an understanding of both areas it falls under.
* Areas serve to reduce the size of routing tables and the impact of a change within the network topology.
* The contents of a hello message is:
	* Router ID
	* Hello/dead interval
	* Neighbours
	* Area ID
	* Router priority
	* DR IP Address
	* BDR IP Address
	* Authentication Data
	* Sub-Area flag
* In order to establish adjacency, the Hello/dead Interval, Area ID Authentication Data and Stub Area Flag must match.
* The OSPF routers go through different OSPF states:
	* Both devices are in a down state, a Hello is sent by R1.
	* A Hello is received by R2, who changes into an Init state and sends a Hello. This is received by R1 and it changes into an Init State
	* R2 sends a Hello again, this time with the R1s address in it as well as any other neighbours of R2 both devices are now in a Two-Way State.
	* Now both devices are in an Exstart state. Adjacencies are established with other routers in the network. A master-slave relationship is developed. The router with the highest ID becomes the master. This denotes who will start the process of exchanging information.
	* The master and slave router exchange Data Base Descriptions. The routers are now in the exchange state.
	* A router compares the DBD it receives within the LSAs it has. If the DBD is more up to date than the router it's self, an LSR is sent to the other router. This begins the loading state.
	* Once all devices have synchronised databases, they are in the full state.
* Each router advertises it's cost out of each of it's interfaces to connected networks. The router places it's self at the foot of an OSPF tree and calculates the total cost to each destination, based on the information it has been given by it's adjacencies.
* OSPF has different types of packets:
	
	|Type|Name |Description|
	|----|-----|-----------|
	|1   |Hello|Hello packet discovers and maintains neighbours                         |
	|2   |DBD  |Contains LSA headers that help to build the LSDB                        |
	|3   |LSR  |USed to request updated LSAs from neighbours                            |
	|4   |LSU  |List of LSAs that require updating                                      |
	|5   |LSAck|Ensure reliable transmission of LSAs, by sending Acknowledgment messages|

* Hello packets include a list of known neighbours.
* DBD Packets contain a summary of the LSDB.
* LSR packets contain the type of LSU needed and the router ID that needs it.
* LSU packets contain the complete LSA entries, multiple of which can fit in a single packet.
* LSAck packets are empty.

### Implementing Multiarea OSPF IPv4
* OSPF Areas allow the network to be segmented, as previously mentioned. 
* They feature the Backbone Area, and the Normal Areas.
* The Normal areas cannot by default directly communicate, all traffic must go via the Backbone.
* An OSPF router can be a:
	* Backbone Router
	* Internal Router
	* ABR
	* ASBR

### Implementing OSPFv3 for IPv6
### Troubleshooting Multiarea OSPF

## Module 6: Wide-Area Networks
## Module 7: Network Device Management

---
# A typing exercise
> I'm learning Dvorak, so here is some random story I am using to practice:

Once upon a time there was a dog and it had at least four legs, but maybe more. It often depended on which Saturday of the month it was. This dog had a favourite toy called Andreas, which was a (tatty looking) four dimensional rhomboid. Francine (the dog, if you could even call it that) love play with the toy and even buried him in the garden. This did however lead to time causality issues.