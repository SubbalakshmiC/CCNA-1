# CCNA Notes

All notes made here relate to ICND 1 or 2, and may 🅱️e a little lacking or nonsensical. Sorry.

---
# ICND1
# General Notes

## Timeline
* 2 Weeks Training (Week 1 GPK, Week 2 🅱️FL).
* 1 Week self study.
* Exam at the end of W3.

## Course Goals
* Descri🅱️e network fundamentals and implement a simple LAN.
* Esta🅱️lish Network fundamentals.
* Expand a small network to a medium-sized routing-ena🅱️led network.
* Configure, manage, secure and monitor Cisco devices.
* Descri🅱️e IPv6 🅱️asics.

## Extra Content
* CEF: Cisco Express Forwarding

## Exercise Types:
* Challenge Exercises
* Discovery Exercises

## Certified Mock Exam Questions:
* MeasureUp
* 🅱️oson.com

# Exam Notes

* Exam pass is a requirement to continue the Apprenticeship Program.
* ICND1 is marked out of 1000.
* 300/1000 marks for participating.
* 90 minutes for the exam.
* ~ 825/1000 marks to pass.
* Results immediately displayed upon exam completion.
* Qualification is valid for 3 years, and completing the next exam in the series (e.g. CCNP) will re-validate any lower exams.

# Module Notes

## Module 1: 🅱️uilding a Simple Network
### What is a Network?
* Networks carry data in varying environments.
* Large networks may 🅱️e multi-location, e.g. Home Office, 🅱️ranch Office, Main Office & Mo🅱️ile all on a single network.

### Physical Components of a Network
* Networks are composed of:
    * Endpoints - PCs, servers, printers etc.
    * Interconnections - NICs, Network Media (e.g. UTP or STP in varying categories) & Connectors (e.g. RJ-i45).
    * Switches - Endpoints connect to these, and they can share a common network.
    * Routers - Select the 🅱️est route for traffic from one network to another.
    * WLAN Devices - Connect Wireless Devices to a network.
    * APs - Allow wireless devices to communicate with a wired network.
    * WLAN Controllers - Devices that network admins can use to manage APs in large quantities.
    * Firewalls - Network security systems that control and monitor incoming and outgoing traffic 🅱️ased on provided rules.

### Characteristics of a Network
Network characteristics are as follows:
* Topology - Physical (e.g. arrangement of ca🅱️les, devices and end systems) or Logical (e.g. the path that the data follows within a network).
* Speed - The data travel rate per second given in 🅱️its within a link in the network (🅱️itrate).
* Cost - General expenditure for purchasing, installing and maintaining the elements in a network.
* Security - How protected the network is, including the information transferred across the network.
* Availa🅱️ility - Measure of pro🅱️a🅱️ility that the network will 🅱️e availa🅱️le for use when required.
    * This can 🅱️e calculated with the following formula:
    `((minutes in a year) - (num🅱️er of minutes if down time in a year) / num🅱️er of minutes in a year) x 100` 
* Scala🅱️ility - How easily the network can accommodate more users and data transmission requirements.
* Relia🅱️ility - The dependa🅱️ility of components that the network is composed of.

### Physical vs. Logical Topology
* Physical Topologies:
    * Ring - Each device is ca🅱️led together in a ring, so that the last device is connected to the first, etc.
    * Mesh - Every device is connected to one another, allowing higher redundancy tolerances.
    * Star - The most common type of topology. A central device is connected to all of the endpoints and other network devices.
    * 🅱️us - Every workstation is connected to the main network medium. Each device is directly connected to another.
    ![🅱️us, Ring, Mesh and & Star Topologies](http://www.itgeared.com/images/content/1339-1.jpg)
    * Logical Topologies - The path that the data follows within a network.

### Interpreting a network diagram
* Various connection interfaces are used in a network. On a network diagram they are denoted as follows:
    * S0/0/0 - **S**erial (Speeds up to 2M🅱️ps)
    * Fa0/0 - **Fa**st Ethernet (Speeds up to 100M🅱️ps)
    * Gi0/0 - **Gi**ga🅱️it Ethernet (Speeds up to 1G🅱️ps
    * /XY -  Slash notation of su🅱️net mask used

### Impact of User Applications on the Network
* Applications can perfect network performance, and vice versa.
There are varying types of applications, such as:
    * 🅱️atch
       * No Direct Human Interactions
		* 🅱️andwidth non-critical
		* e.g. TFP, TFTP, inventory updates
    * Interactive
    	* Human-Machine interactions
    	* Human waits for response, therefore the response time is important 🅱️ut not critical
		* e.g. Inventory enquiries
    * Real-Time Applications
		* End-to-end latency is critical
		* e.g. VoIP, Video calling
		* Human-Human interaction
* QoS (Quality of Service) is important. It allows for the granting of higher priority to different types of data e.g. VoIP Packets.

### Host-to-Host Communications
* Varying types of host-to-host models exist:
    * Older Models e.g. Used 🅱️y Proprietary Software
    * Standards-🅱️ased Models e.g. Used 🅱️y Multivendor Software (OSI, TCP/IP Models) 
    
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

* The OSI Model is a layer-🅱️ased reference model that provides functions and services that can occur at each layer.
* It descri🅱️es the interaction 🅱️etween each layer a🅱️ove and 🅱️elow it. 
* It is standards 🅱️ased, allowing vendors a set of standards that ensure compati🅱️ility 🅱️etween various types of network technology worldwide.
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
* Real traffic data is generated at this layer. It may 🅱️e a we🅱️ request from HTTP to a command from TelNet, to a file download from FTP.
  
    #### Presentation
* Responsi🅱️le for: 
	* character code translation (i.e. ASCII vs. E🅱️CDIC vs. Unicode), 
	* data conversion, 
	* compression, 
	* and encryption. 
* Some common examples include: 
	* Multipurpose Internet Mail Extensions (MIME), 
	* Transport Layer Security (TLS) 
	* and Secure Sockets Layer (SSL).
* When the presentation layer receives data, it checks the data format is correct and if not converts it.
* This layer is also responsi🅱️le for compression, encryption, and ensuring that the character code set can 🅱️e interpreted on the other side of the connection.

    #### Session
* Port num🅱️ers are present in 🅱️oth sending and receiving capacities. e.g. Internet requests will 🅱️e sent to port 80, 🅱️ut will 🅱️e received on varying port num🅱️ers dependant on my Session ID.
* Responsi🅱️le for:
	* session esta🅱️lishment,
	* maintenance
	* and termination
* In the connection esta🅱️lishment phase, service rules are transmitted and must 🅱️e accepted 🅱️y 🅱️oth devices. Once these rules have 🅱️een set, the transfer 🅱️egins, the session is ended once the transmission is complete.
  
    #### Transport
* One of 2 things:
	* TCP (handshake like connection e.g. a phone)
		* The TCP Handshake goes as follows:
		* SYN → SYN-ACK → ACK
	* UDP (connection-less e.g. a radio)
* There is also a mechanism to ensure that a device running multiple applications simultaneously all receive their data.
* To make this work correctly, incoming data from various applications are multiplexed on the transport layer and pushed to the 🅱️ottom layers. At the other end of the communication, that data is de-multiplexed at the Transport Layer.
  
    #### Network
* Responsi🅱️le for:
	* Logical-physical address mapping: translates logical addresses, or names, into physical addresses.
	* Routing routes frames among networks.
* Routers direct the data packet from this layer using location information stored in a Routing Ta🅱️le. This is a list of destinations on the network.

    #### Data Link
* Responsi🅱️le for esta🅱️lishing and terminating links.
* This layer provides error-free transfer of data frames from one node to another over the physical layer.
* This layer is separated into the Media Access Control (MAC) Su🅱️layer and the Logical Link Control (LLC) Su🅱️layer.
* The MAC layer determines the physical addressing of host devices. It maintains MAC addresses for communicating with other devices.
* Logical Link is responsi🅱️le for synchronising frames, error checking, and flow control.

    #### Physical
* The physical layer handles how data is physically encoded and decoded. 
* Physical layers descri🅱️e the electrical or optical signals used for communication.
	* For example, whether a voltage represents a 1 or a 0.
* This layer is concerned 🅱️y the electrical or optical signalling techniques which includes the voltage of the electrical current used to transport the signal, the media type, impedance characteristics, physical shape of the connector, synchronisation method, etc. 
 
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
* This layer generates data dependant on what application is 🅱️eing used. This could 🅱️e a we🅱️ address in a we🅱️ 🅱️rowser, for example.
* It also defines how host programs interface with Transport layer services to use the network.
* Protocols on this layer are:
	* HTTP (Hypertext transfer protocol)
	* FTP (File transfer protocol)
	* SMTP (Simple mail transfer protocol)
	* SNMP (Simple network management protocol) etc

	#### Transport
* This layer receives data from the application layer a🅱️ove it. 
* This layer permits devices on the source and destination hosts to continue their communication.
* There are many protocols that work at this layer 🅱️ut the two most commonly used protocols at transport layer are TCP and UDP.
	* TCP (handshake like connection e.g. a phone)
	* UDP (connection-less e.g. a radio)

	#### Internet
* The main purpose of this layer is to organise or handle the movement of data on network.
* It controls how data is physically transmitted, including how 🅱️its are electrically or optically signalled 🅱️y hardware devices that interface directly with a network connection type, like coaxial ca🅱️le, optical fi🅱️re, or twisted pair copper wire.

	#### Link
* This layer normally consists of device drivers in the OS and the network interface card attached to the system.
* The most popular protocol in use over LAN is ethernet. This uses a method known as CSMA/CD, this is Career Sense Multiple Access/Collision Detection. This is used to access media. Access methods determine how hosts place media on communication mediums.
* In the case of CSMA/CD every host has the same access to the medium and can place data on the wire when there is no traffic. If there is traffic it waits until there is not 🅱️efore placing the data. If this was not the case, the data would collide and 🅱️e destroyed, and will need resu🅱️mitting.

### Peer-to-Peer Communications
* At each layer of communication a different Protocol Data Unit (PDU) is used, for example:

	|   |Sender     |PDU    |Receiver   |
	|---|:---------:|:-----:|:---------:|
	| ↓ |Application|Data   |Application|
	| ↓ |Transport  |Segment|Transport  |
	| ↓ |Internet   |Packet |Internet   |
	| ↓ |Link       |Frame  |Link       |
	
	> At the physical layer, the PDU used is '🅱️its'

### Encapsulation and De-Encapsulation
* Encapsulation is a process that occurs within the OSI and TCP/IP Models
* Within the OSI Model, it occurs as follows:
    * The application layer received the user data, and adds a header 🅱️efore sending it to the presentation layer
    * The presentation layer adds its own header 🅱️efore transmitting to the session layer
    * This process continues down the stack and at the data link layer, a trailer is added
    * At Layer 2 the trailer is usually the FCS - Used to check for errors in transmission
    * At the destination this is unpacked one layer at a time, and the data is then passed up to the PDU on the layer a🅱️ove

### Local Area Networks
* Ethernet 🅱️ecame widespread in the 1990s
* A LAN requires the following necessary components for operation:
	* Hosts
		* PCs
		* Servers
	* Interconnections
		* NICS - translating data into electrical signals
		* Network Media - Fi🅱️re optics or Copper (usually)
	* Network Devices
		* Routers
		* Switches
	* Protocols
		* Ethernet
		* Token Ring
		* HDLC (High Level Data Link Control) Protocol - used 🅱️y Serial type connections
		* PPP (point to Point Protocol)
		* ATM (Asynchronous Transfer Mode)
		* PPPoE (PPP over Ethernet)
	
	> As explained a🅱️ove
	
* Pre-switching ethernet networks used co-axial ca🅱️les with many devices connected to them in a 🅱️us. This method offered up-to 10M🅱️ps speeds
	* At points along the ca🅱️le, marked dots denoted areas where the ca🅱️le could 🅱️e tapped into with vampire taps to attach devices to the 🅱️us.
	* Errors required Time Domain Reflectometers to show a rough region of the ca🅱️le where🅱️y the connection was lost
	* Data on the 🅱️roadcast media is accessi🅱️le to any devices on the network
	* This system was replaced with a central hu🅱️ that contained the effective 🅱️us of the network, and each device had its own UTP ca🅱️le to and from the hu🅱️
	* Physically that network may 🅱️e descri🅱️ed as a hu🅱️, 🅱️ut logically that forms a 🅱️us network
* CSMA/CD (Collision Sense Multiple Access/Collision Detection) is used to mitigate collisions along the media that may result in lost data. This forms part of the Ethernet Protocol and is used in Half-Duplex networks
* CSMA/CA (/Collision Avoidance) is used on wireless, and ensures 2 devices are not transmitting at the same time, as the frequency is shared across the devices
	* Collision Detection - to discover whether a device is currently transmitting on the media
	* The sending device listens to the signal they are transmitting. If the data heard differs from that sent, the system 🅱️ecomes aware of a collision
	* A jamming signal is sent to prevent other devices whilst another is, mitigating the chances of a collision occurring
	* Hu🅱️s 🅱️ecame repeaters, 🅱️ridges 🅱️ecame Switches
	* ASIC - Application Specific Integrated Circuits
	
### Need for Switches
* Traditionally devices had to compete for 🅱️andwidth on a network (or 🅱️roadcast domain), using a 🅱️us topology. This meant that only one device could transmit at a time
* Switches can now 🅱️e used to split up a network, and reduce the num🅱️er of devices within a collision domain. There may 🅱️e multiple collision domains within a 🅱️roadcast domain (the immediate reach of a switch)
* The function of switches is as follows:
	* Operate at the link (L2) layer of the TCP/IP Model
	* Forward, Filter or Flood frames to hosts dependant on entries in the MAC Address ta🅱️les on the device
	* Have many Full-Duplex ports to allow for the LAN to 🅱️e segmented, reducing collision domain sizes
	* Support multiple port speeds.
* Switches 🅱️uild ta🅱️les of the devices immediately connected to them and store their MAC (Physical) Addresses in a MAC address ta🅱️le
* The header of each incoming frame has a MAC address within it for the destination host, which is compared to addresses within the switch's MAC address ta🅱️le. They use this to decide whether to flood, forward or filter received frames
* '🅱️ridges' connect token ring to ethernet networks

	|Sender| → |Recipient|Type     |
	|:----:|---|:-------:|:-------:|
	|A     | → |🅱️        |Unicast  |
	|A     | → |🅱️ & C    |Multicast|
	|A     | → |All      |🅱️roadcast|
> Transport Types	

* When a unicast frame is received on a port, the destination MAC is compared with the addresses within the MAC address ta🅱️le, one of 3 things happen:
	* If the switch is aware of the MAC address to interface relationship, due to it 🅱️eing an entry within it's MAC Address Ta🅱️le, then the packet is **Forwarded** to that port. The other ports are now filtered out. 
	* If the MAC address listed is known, and is on the same interface, e.g.Hosts X & Y 🅱️eing on the same segment as they are attached to a hu🅱️, the packet is **Filtered** 🅱️y the switch and not passed outwards to any other ports.
	* If the address matches no entry on the switch's MAC Address Ta🅱️le, the frame is transmitted on all ports except the one it was received on, with the hope that it can 🅱️e passed on, this is **Flooding**.

		|Port|Host|
		|----|----|
		|1   |A   |
		|2   |🅱️   |
		|3   |C   |
		|4   |D   |
> MAC Address Ta🅱️le. This is 🅱️uilt from source addresses
	
### Switches
* Switches can 🅱️e in two types:
	* Dedicated 🅱️andwidth - a single station is connected to a given switch port, and so there is no competition for 🅱️andwidth
	* Full Duplex Operation - on a shared ethernet medium, this allows for devices to 🅱️oth send and receive at the same time. Half duplex allows for either sending or receiving at a given time
	* A L2 Switch makes decisions as to where to send packets 🅱️ased on data found in the Ethernet Frame, whereas a L3 Router uses the IP addresses within said packets
	* A 1G🅱️ps port on a switch defaults to Full Duplex if not told to do otherwise, whereas a 100M🅱️ps port will default to Half Duplex unless specified otherwise.
	* LAN Switches can have:
		* High port density - any num🅱️er from less than 32 to hundreds of ports may 🅱️e on a switch
		* Large frame 🅱️uffers - allowing more frames to 🅱️e stored 🅱️efore needing to drop them
		* Varying port speeds - Speeds of 100M🅱️ps are expected, 🅱️ut other speeds such as 1 or 10G🅱️ps are also common
		* Fast internal switching - fast internal 🅱️us, shared memory or integrated cross🅱️ar switch fa🅱️ric may 🅱️e used 
		* Lower per port cost - Less devices are required to allow a network of the same size when using switches
	* A switch offers a port (connection) to each device, removing the need for CSMA/CD. However this is still accepted, in the event that a hu🅱️ may 🅱️e connected to one of these ports to increase capacity

### Cisco IOS
* Cisco IOS is the proprietary operating system that operates on Switches, Routers, APs and other networking appliances that Cisco Manufacture
* The port used to directly connect to a router, switch etc. is called a console port
* A light 🅱️lue patch ca🅱️le is used here (likely with an RJ-45 connection)
* The Cisco CLI is used to enter commands
* Operations performed vary dependant on the device

* Modes within the CLI (Command Line Interface):
	* `switch >` - User EXEC Mode
		* A limited, read-only examination mode.
	* `switch #` - Privileged EXEC Mode
		* Allowing access to all system commands, though still read-only.
		* Accessed 🅱️y typing `ena🅱️le` from within User Mode.
		* Here the user can entirely examine the system, reload the system.
		* Offers access to the glo🅱️al configuration mode.
	* `switch (config)#` - Glo🅱️al Configuration Mode
		*  Here there are different types of config mode dependant on the function desired:
		*  These are `Interface`, `VLAN`, `Router`, `(N)ACL` etc.
		*  These modes are accessed via typing their names from within Glo🅱️al EXEC Mode.

	> `switch` is a placeholder hostname used here

* Useful key com🅱️inations:
	* `Ctrl-A` - Moves the cursor to the 🅱️eginning of the command line
	* `Ctrl-C`	- A🅱️orts the current command and exits the configuration mode
	* `Ctrl-E`	- Moves the cursor to the end of the command line
	* `Esc-🅱️`	- Moves the cursor 🅱️ack one word
	* `Esc-F`	- Moves the cursor forward one word
	* `Ctrl-🅱️`	- Moves the cursor 🅱️ack one character
	* `Ctrl-F`	- Moves the cursor forward one character
	* `Ctrl-D`	- Deletes a single character at the cursor
	* `🅱️ackspace`	- Removes one character to the left of the cursor
	* `Ctrl-P` - Redisplays the current command line
	* `Ctrl-U`	- Erases a line
	* `Ctrl-W`	- Erases a word to the left of the cursor
	* `Ctrl-Z` - Ends configuration mode and returns to the EXEC prompt
	* `Ta🅱️`	- Completes a partially entered command if enough characters have 🅱️een entered to make it unam🅱️iguous
	* `Ctrl-Shift-6` - Allows the user to interrupt a Cisco IOS process such as ping or traceroute
	* `Ctrl-P` or `Up Arrow` - Recalls last (previous) commands
	* `Ctrl-N` or `Down Arrow`	- Recalls more recent commands

* Useful commands:
	* `show` - Show running system information, could 🅱️e suffixed with an interface name for example
	* `disa🅱️le` - Returns to User EXEC Mode
	* `exit` - Return to Privileged EXEC Mode

* There are 3 main types of error messages:
	* `am🅱️iguous command` - You did not enter enough characters for your device to recognise the command
	* `incomplete command` - You did not enter all the keywords or values that are required 🅱️y this command
	* `invalid command` - You entered the command incorrectly. The ^ marks the point of the error

* Cisco switches use an 'Ageing Timer' which lasts 300 seconds (5 Minutes) to know when to remove an address from a MAC address ta🅱️le. If a ca🅱️le is removed from a port, the time is set to 0
* CAM - Content Addressa🅱️le Memory. MAC Addresses are stored here
* When making changes to the operation of a switch or router, saving and managing said changes are important.
* The following commands may 🅱️e useful:
	* `show running-config` - Displays the current running configuration. You can also use filters. For example, you can use the show running-config interface Giga🅱️itEthernet0/1 command to display only the interface Giga🅱️itEthernet0/1 running configuration.
	* `show startup-config` - Displays the saved configuration in NVRAM.
	* `configure terminal` - Enters the configuration mode, where you can interactively create configurations in RAM from the console or remote terminal.
	* `copy running-config startup-config` - Saves the running configuration to NVRAM.
	* `copy startup-config running-config` - Startup configuration in NVRAM is merged into running configuration.
	* `erase startup-config` - Deletes the saved startup-config file in NVRAM.

* When displaying portions of a config it may help to filter out unwanted data.
* This can 🅱️e done in the following ways:
	* `🅱️egin` - Shows all output lines, starting with the line that matches the filtering expression.
	* `exclude` - Excludes all output lines that match the filtering expression.
	* `include` - Includes all output lines that match the filtering expression.
	* `section` - Shows the entire section that starts with the filtering expression.
* e.g. `R1# show running-config | 🅱️egin interface` will show only lines from within R1's running config that 🅱️egin with 'interface'.

### Starting a Switch
* Switches can 🅱️e configured in one of two ways:
	* Via Console Port - physically to the switch.
	* Via VTY (Virtual Teletype) - remotely to the switch.
* 🅱️oth of these connection mediums enter the system at User EXEC Mode.
* When a switch 🅱️oots up, it performs Power On Self Test (POST) and then initialises the system.
* Switches have LED indicators, which have differing meanings, these are:

	|Indicator Name|Description|
	|--------------|-----------|
	|SYST          |Overall system status (off meaning system is off, green meaning switch is on and operational, am🅱️er meaning switch is on 🅱️ut has failed POST)
	|RPS           |Status of a Redundant Power Supply
	|STAT          |If on (green), shows that port LEDs are implying to the status of each port
	|DUPLX         |If on (green), shows that port LEDs are implying the duplex status (on meaning full duplex, off meaning half duplex)
	|SPEED         |If on (green), shows that port LEDs are implying port speeds (off meaning 10M🅱️ps, solid green meaning 100M🅱️ps, flashing green meaning 1Gp🅱️s)
	|PoE           |If on (green), shows that port LEDs are implying the Power over Ethernet status of each port
	
	* A MODE 🅱️utton is also present, allowing you to cycle the indicator LEDs on each switch to it's Status (on/off), Duplex Status and Speed.

### Understanding Ethernet and Switch Operation
* Ethernet can 🅱️e used on varying mechanical standards, such as:
	* Co-Axial (this is no-longer used for ethernet communications)
	* Twisted Copper Pair
		* Unshielded Twisted Pair ca🅱️les can come in varying categories:
			* Category 1: Used in telephone communications 🅱️ut not transmitting data
			* Category 2: Capa🅱️le of data transmissions up to 4M🅱️ps
			* Category 3: Used in 10🅱️ASE-T Networks and can transmit up to 10M🅱️ps
			* Category 4: Used in token ring networks and can transmit up to 16M🅱️ps
			* Category 5: Capa🅱️le of transmitting data at up to 100M🅱️ps
			* Category 5e: Capa🅱️le of transmitting data at up to 1G🅱️ps
			* Category 6: 4 Pairs of 24-gauge copper wires, and can transmit up to 10G🅱️ps
			* Category 6a: Used in networks at speeds up to 10G🅱️ps
			* Category 7: Used in networks at speeds up to 10G🅱️ps
			
		* These UTP Ca🅱️les are terminated with RJ-45 connections. They may 🅱️e terminated in one of two ways: Straight-Through and Crossover ca🅱️les.
			* Like to like devices connect via crossover ca🅱️les (e.g. switch to switch)
			* Like to unlike devices connect via straight-through ca🅱️les (e.g. switch to PC)
		* The pin layout at each end of the ca🅱️les varies 🅱️etween the two types.
		* This is as follows:
	
		![Straight-Through vs. Crossover](http://www.incentre.net/wp-content/uploads/2015/02/ethcable03.gif)
		
	* Optical Fi🅱️res
		* These fi🅱️res come in two types, Single and Multi Mode
		* They have the following properties:
			* **PROPERTIES**
		* These ca🅱️les can also 🅱️e terminated with differing connectors:
			* **CONNECTORS**
	* Wireless (This has no connection media)

* Ethernet frames have a fixed structure. This may 🅱️e:

	|Field Length (🅱️its)   |8       |6                  |6             |2   |46-1500|4  |
	|----------------------|--------|-------------------|--------------|----|-------|---|
	|Typical Frame Contents|Pream🅱️le|Destination Address|Source Address|Type|Data   |FCS|
	
	* Pream🅱️le	- 8 🅱️ytes of 🅱️inary digits used to synchronise the signals of the communicating hosts.
	* DA - The address of the NIC on the local network that the packet is 🅱️eing sent to.
	* SA - The address of the NIC on the sending host.
	* Type - Code identifying the network layer protocol.
	* Data & Padding - Data 🅱️eing sent to the host. If the data is less than 46 🅱️ytes, padding is used to make up this space.
	* FCS - Checksum mechanism used to make sure the data is sent without corruption.
	
* MAC Addresses are 48-🅱️it strings of 🅱️inary characters.
* They are split in half, containing the Organisation Unique Identifier and the Vendor Assigned Portion.
* These are noted in Hexadecimal format, and may appear as: `0000.0c43.2e08`, `00:00:0c:43:2e:08` or `00-00-0C-43-2E-08`.

* Switches perform frame switching. This is aided 🅱️y the MAC Address Ta🅱️le, informing the switch of the relationship 🅱️etween host MAC Addresses and Ports.
* This procedure is as follows:
	1. Switch receives a frame from PC A on Port A.
	2. Switch enters the Source MAC Address (the port the message is received on) of PC A into its MAC Address ta🅱️le.
	3. Switch checks its MAC Address ta🅱️le for the destination MAC Address, however 🅱️ecause it is unknown the frame is flooded to all ports, except the port that the frame is received on.
	4. The device with a matching destination MAC Address replies to the unicast with a unicast frame addressed to PC A.
	5. The switch enters the source MAC Address of PC 🅱️ and the port num🅱️er of the switch port that received the frame into its MAC Address ta🅱️le.
	6. The switch can now forward frames 🅱️etween these addresses without flooding, as these addresses are now in its MAC Address ta🅱️le.
	
### Trou🅱️leshooting
* Trou🅱️leshooting issues may happen in a couple of ways:
* The OSI Model may 🅱️e used to trou🅱️leshoot an error, 🅱️e that 🅱️y starting at the top, 🅱️ottom or from using the 'divide and conquer' method (starting in the middle and working from a🅱️ove and 🅱️elow.
* If `ping` works, layers 3 and 🅱️elow (at least) are functional, 🅱️ecause it is a layer 3 protocol.
* Using `telnet`, the user can test layer 4 functionality.
* Copper media can suffer from issues via:
	* Wiring damage
	* New sources of EMI
	* Changes to traffic patterns
	* New equipment installation
* Fi🅱️re can suffer from issues via:
	* Micro & Macro-🅱️end data loss (ca🅱️le is 🅱️ent too far, causing data loss during reflection of light)
	* Splice loss

## Module 2: Esta🅱️lishing internet connectivity 
### Understanding the TCP/IP Internet Layer
* The Internet Protocol:
	* Operated at the Internet layer in the TCP/IP Model
	* Is connectionless
	* Treats packets independently of one another
	* Hierarchically addresses
	* Uses 🅱️est-effort delivery methods
	* Values speed over relia🅱️ility
	* Has no data recovery techniques
	* Is independent of the media
	* Works with IPv4 and IPv6 using 2 different versions
* In a route from PC A in Reading to Server X in San Jose, different layer 2 protocols may 🅱️e used.
	* e.g. Ethernet, HDLC and PPP.
* This path may 🅱️e: `PC A` → `SW1` → Eth → `R1` → HDLC → `R3` → PPP → `R2` → Eth → `SW2` → `Server X`
* IP information is transferred across this connection.
	* The process is as follows:
		* PC A generates an IP Packet, and S1 encapsulates it into an Ethernet frame.
		* Once the frame gets to R1, the frame is de-encapsulated and the layer 3 information is read.
		* The frame is re-encapsulated 🅱️y R1 into a HDLC frame and forwarded on.
		* Once the frame gets to R3, the frame is de-encapsulated and the layer 3 information is read.
		* The frame is re-encapsulated 🅱️y R3 into a PPP frame and forwarded on.
		* Once the frame gets to R2, the frame is de-encapsulated and the layer 3 information is read.
		* The frame is re-encapsulated 🅱️y R2 into a Ethernet frame and forwarded on.
		* SW2 Receives the frame and forwards it to Server X.
		* Server X de-encapsulates the frame entirely and processes the request.
		
		> No conversion ever takes place. Each time a frame is de-encapsulated, the L2 data is discarded and replaced.

* IPv4 Addresses are 32 🅱️it num🅱️ers, split into 4 octets.
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
	* Fragment offset - Indicates where specific fragments 🅱️egin
	* TTL - Time to Live, lifetime of a packet
	* Protocol - Indicates protocol in use
	* Header Checksum - Used for error detection
	* Source Address - 32 🅱️it 🅱️inary value of the sending endpoint
	* Destination Address - 32 🅱️it 🅱️inary value of the receiving endpoint
	* Options - Indicates optional parameters
	* Padding - Used to ensure that the header ends on a 32 🅱️it 🅱️oundary
	
* 🅱️inary is a 🅱️ase 2 num🅱️er system
* An IPv4 uses 32 🅱️inary digits.
* An IPv4 address is traditionally displayed in dotted decimal format (e.g. 192.168.4.6)
* The left-most character in a 🅱️inary octet is the Most Significant 🅱️it and the right-most is the Least Significant 🅱️it.

	|128    |64     |32     |16     |8      |4      |2      |1      |
	|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|
	|$$2^7$$|$$2^6$$|$$2^5$$|$$2^4$$|$$2^3$$|$$2^2$$|$$2^1$$|$$2^0$$|

* Using this system, the num🅱️er `00101000` translates to `40`.

* IP Addresses have different classes:
	* Class A - First 🅱️it Fixed at `0`, first 🅱️yte reserved for the network portion - used in networks with more than 16 million hosts.
	* Class 🅱️ - First 2 🅱️its Fixed at `10`, first 2 🅱️ytes reserved for the network portion - used in networks with more than 65,000 hosts.
	* Class C - First 3 🅱️its Fixed at `110`, first 3 🅱️ytes reserved for the network portion - used in networks with less than 254 hosts.
	* Class D - First 4 🅱️its Fixed at `1110`, this is used for multicast addresses, and unlike Classes A, 🅱️ & C, this is always a destination address.
	* Class E - First 5 🅱️its Fixed at `1111`, this is a reserved experimental range.
* The IANA (Internet Assigned Num🅱️er Authority) Initially developed these classes.
> Cisco IP Phones use the Class D address 239.0.0.1 to send hold music via multicast to save on 🅱️andwidth.

	|IP address Class            |First Octet 🅱️inary Range|First Octet Decimal Range|Maximum Num🅱️er of Hosts/Su🅱️net|
	|:--------------------------:|:----------------------:|:-----------------------:|:----------------------------:|
	|Class A                     |00000001 to 01111110    |1 to 126                 |16,777,214                    |
	|Class 🅱️                     |10000000 to 10111111    |128 to 191               |65,534                        |
	|Class C                     |11000000 to 11011111    |192 to 223               |254                           |
	|Class D                     |11000000 to 11101111    |224 to 239               |-                             |
	|Class E                     |11110000 to 11111111    |240 to 255               |-                             |

	> The Class A address range from 127.0.0.0 to 127.255.255.255 is reserved for loop🅱️ack and diagnostics purposes.
	
* Some IPv4 addresses and ranges are reserved, and cannot 🅱️e given to hosts. For example:
	* 0.0.0.0 - Unspecified, or Any Network
	* 255.255.255.255 - Local Network 🅱️roadcast
	* Any address with the host portion as 0s - Network address
		* e.g. an address of 172.16.0.0 cannot 🅱️e given to a host as it is a network address.
	* 10.255.255.255 - Directed 🅱️roadcast address
 
* This method is called class-full addressing.
* Another method is classless inter domain routing (CIDR)

* Worked Examples:
	* 200.210.18.34
		* Class C Address (200 falls 🅱️etween 192 to 223)
	* 10.255.17.254
		* Class A Address (10 falls 🅱️etween 1 to 126)
	* 172.54.3.2
		* Class 🅱️ Address (172 falls 🅱️etween 128 to 191)
		
* An IPv4 Class C Address, for example, could 🅱️e:

	|192       |168       |4         |6         |
	|:--------:|:--------:|:--------:|:--------:|
	|`11000000`|`10100010`|`00000100`|`00000110`|

* The num🅱️er of usa🅱️le hosts within a su🅱️net can 🅱️e calculated with $$2^n-2$$ where $$n$$ = num🅱️er of 🅱️its availa🅱️le for the address portion of the IP address.
	* e.g. $$2 🅱️its \therefore m=2 \therefore 2^2 = 4$$

* IPv4 has private and pu🅱️lic IP ranges:
	* Private
	
		|IP Address Class|Range                         |
		|:--------------:|------------------------------|
		|A               |10.0.0.0 to 10.255.255.255    |
		|🅱️               |172.16.0.0 to 172.31.255.255  |
		|C               |192.168.0.0 to 192.168.255.255|
		
	* Pu🅱️lic
	
		|IP Address Class|Range                                                          |
		|:--------------:|---------------------------------------------------------------|
		|A               |1.0.0.0 to 9.255.255.255                                       |
		|                |11.0.0.0 to 126.255.255.255                                    |
		|🅱️               |128.0.0.0 to 172.15.255.255                                    |
		|                |172.32.0.0 to 191.255.255.255                                  |
		|C               |192.167.0.0 to 192.167.255.255                                 |
		|                |192.169.0.0 to 223.255.255.255                                 |

* IPv6 offers $$3.4 \times 10^{38}$$ Addresses.

* DNS is the Domain Name System. It translates IP addresses to domain names such as 'www.cisco.com'.

### Understanding IP addressing and Su🅱️nets
* 🅱️y su🅱️networking a network:
	* Smaller networks can 🅱️e more easily managed
	* Overall network traffic is reduced
	* Network security policies can 🅱️e more easily introduced
* When IPv4 addresses are expressed, a slash notation is provided in order to display the num🅱️er of 🅱️its in the address is used for the network portion of the address, for example:
	* 10/.1.1.1/8 - A Class A Address with the mask 255.0.0.0
	* 172.16.55.87/16 - A Class 🅱️ Address with the mask 255.255.0.0
* A Su🅱️net mask:
	* Defines the num🅱️er of 🅱️its that represent the network and su🅱️mit part of an address
	* Is used 🅱️y end systems to identify the destination IP address as either local or remote
	* Is used 🅱️y L3 devices to determine network path

* The ta🅱️le 🅱️elow can 🅱️e used to assist with slash notations and su🅱️netting:

	|Step                |128|64 |32 |16 |8  |4  |2  |1  |
	|--------------------|---|---|---|---|---|---|---|---|
	|Mask (.x)           |128|192|224|240|248|252|254|255|
	|A: /8 255.x         |/9 |/10|/11|/12|/13|/14|/15|/16|
	|🅱️: /16 255.255.x    |/17|/18|/19|/20|/21|/22|/23|/24|
	|C: /24 255.255.255.x|/25|/26|/27|/28|/29|/30|/31|/32|
	
* To find a network from a host address and a su🅱️net mask, perform the following:
	* Device Address: 15.17.1.12
	* Su🅱️net Mask: 255.0.0.0

	|            |   |128|64 |32 |16 |8  |4  |2  |1  |
	|------------|---|---|---|---|---|---|---|---|---|
	|Host Address|15 |0  |0  |0  |0  |1  |1  |1  |1  |
	|Su🅱️net Mask |255|1  |1  |1  |1  |1  |1  |1  |1  |
	|Network ID  |?  |0  |0  |0  |0  |1  |1  |1  |1  |

	> The same process should 🅱️e completed with each octet
	
* A host needs to 🅱️e aware of its su🅱️net mask to know when to send messages intended for devices in other networks to the default gateway instead.

## Module 3: Summary Challenge 

## Module 4: 🅱️uilding a Medium-Sized Network 

## Module 5: Network Device Management & Security 

## Module 6: Summary Challenge 

## Module 7: Introducing IPv6 

---
# ICND2