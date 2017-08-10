# CCNA Notes

All notes made here relate to ICND 1 or 2, and may be a little lacking or nonsensical. Sorry.

---
# ICND1
# General Notes

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

# Module Notes

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
		* They have the following properties:
			* **PROPERTIES**
		* These cables can also be terminated with differing connectors:
			* **CONNECTORS**
	* Wireless (This has no connection media)

* Ethernet frames have a fixed structure. This may be:

	|Field Length (bits)   |8       |6                  |6             |2   |46-1500|4  |
	|----------------------|--------|-------------------|--------------|----|-------|---|
	|Typical Frame Contents|Preamble|Destination Address|Source Address|Type|Data   |FCS|
	
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

* Worked Example:
	* 200.210.18.0/24 → Class C Address (Mask 255.255.255.0)
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
		* First Host: 200.210.18.17
		* Last Host: 200.210.18.30
		* Broadcast Address: 200.210.18.31
	* Subnet 4:
		* First Host: 200.210.18.17
		* Last Host: 200.210.18.30
		* Broadcast Address: 200.210.18.31
	* Subnet 5:
		* First Host: 200.210.18.17
		* Last Host: 200.210.18.30
		* Broadcast Address: 200.210.18.31
	* Subnet 6:
		* First Host: 200.210.18.17
		* Last Host: 200.210.18.30
		* Broadcast Address: 200.210.18.31

## Module 3: Summary Challenge 

## Module 4: Building a Medium-Sized Network 

## Module 5: Network Device Management & Security 

## Module 6: Summary Challenge 

## Module 7: Introducing IPv6 

---
# ICND2