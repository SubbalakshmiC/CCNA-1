# CCNA Revision Document
# Warriors of the net 
CCNA lasts 3 years - can take a higher exam to requalify for CCNA

Boot camp begins!

* 4 week course
* 2 weeks of ICND1
* 1 week to study
* Then there is the part 1 exam
* Then 2 weeks of ICND2

## ICND1
* 90 mins - 55 to 60 questions
* Exam is tight for time
* Cannot go back, answer right first time
* If you fail you wait a week before you pass
* 826 out of 1000 to pass - 300 for turning up
* 4 or 5 questions wrong to fail
* Get told straight or away pass or fail

### Goals - 2 weeks
* Describe network fundamentals and implement a simple LAN
* Establish Internet connectivity
* Expand a small network to a medium sized network with routing enabled (CEF - Cisco Express Forwarding)
* Configure, manage, secure and monitor Cisco devices
* Describe IPV6 basics

### Module 1 - Building a simple network

#### Exploring the functions of a network
A network allows a connection of one thing to another.
Could be a one person to another (bus network etc) or more examples.
Allows the connection of multiple sites (places).
Also allows the connection of mobile workers or working from home.
Networks could be private (such as in a home or office) or a public network (such as the ones supplied by BT etc.).
Use to connect a selection of end devices to other end devices (PC's, IP Phones Servers, Printers etc.) or network equipment (WAP, Router, Switch etc.).

##### Network Components
* Firewall - Monitor and control incoming and outgoing traffic
* Endpoints - PC's etc
* Interconnections - Used to connect devices together
	* NIC - Translate computer data into a format that can be sent over the network
	* Network Media - Transmits signals from one device to another
		* Cables - The physical wires 
			* UTP (Unsheilded Twisted Pair) - Used for short distances (100m Max)
				* Includes different CATegories
				* E.G. Cat 6
			* Fibre Optic - Immune to interference, Used for long distance
				* Single mode fibre
				* Multi mode fibre 
			* Coaxial
			* etc (All of the cables)
		* Wireless
	* Connectors for Network Media - The plugs on the end of cables
		* RJ-45 (Registered Jack)
		* Fibre Connectors (IDK what they are called)
		* etc (All of the plugs) 
* Switches - Devices that endpoints typically connect to
* Routers - Used to connect networks, does the 'routing' between networks
* WLAN Controller - Used to do administrattion on multiple AP's
* AP's (Access point's) - Allows wirelles devices to connect to a wired network 
* WLAN Devices - Connect wireless devices to a network, WLAN NIC converts wirless signals to PC language

##### Characteristics of a network
Characteristics:
* Topology - Design of the network
	* Physical - The arrangement of physical cables and devices
	* Logical - The path that the data actually travels upon
* Speed - Bits per second
* Cost - How much to install the network
* Security - How secure is the network
* Availability - The amount of time that the network is up - (minutes in a year - minutes of down time) / minutes in a year * 100
* Scalability - How easily can the network grow (new devices added)
* Reliability - How likely the devices on the netwokr are to break (SSD's are more reliable than HDD's)

##### Physical VS Logical Topologies

Physical topology is the cabling and devices that you can see.

Logical topology is the path that data takes within the network to get to the desired destination.

Primary physical topologies:

* Bus - Single back bone, single point of failure, many clashes (CSMA/CD)
* Ring - Can only speak to devices next to eachother, not very secure
* Star - Centralised network device to send/receive traffic, good but expensive
* Mesh - Usually used by router networks, lots of cabling needed however has fallbacks (one path breaks, new one can be used)

##### Interpreting a Network Diagram

A network digram is basically a drawing of the network.
There are specific symbols and details the specify certain aspects of the network.

Legend:

* Thick red line - Ethernet Link
	* Fibre
	* UTP
* Lightning red line - Serial Link
* IP Address - Tells you the IP address of the specific device or sets of devices
* Interface - Tells you the interface/port that a wire is plugged into on a device
	* Fa - Fast Ethernet (max - 100Mb/s)
	* Gi - Gigabit Ethernet (max - 1000Mb/s)
	* S - Serial (1-2 Mb/s) Used to manage network devives usually

##### Impact of User Applications on the Network

QoS - Quality of Service: A way of the network knowing how important traffic is

* Batch Applications - Applications that run in the background
	* FTP (File Transfer Protocol) TCP, TFTP (Trivial File Transfer Protocol) UDP, inventory updates
	* No direct human interaction
	* Bandwidth important but not critical
* Interactive Applications
	* Inventory inquiry
	* Human-to-machine interaction
	* Human waiting for response, not critical however annoying
* Real-time Applications
	* VoIP, video
	* Human-to-human interaction
	* End-to-end latency critical

#### Understanding the Host-to-Host Communication Model

##### OSI Model

Open Systems Interconnect

Used to stop duplication.
Without this all applications would have to manually connect to hardware.

Way to remember: Please Do Not Throw Sausage Pizza Away (PDNTSPA)

The model helps to troubleshoot and to create new protocols and applications.

###### 7 - Application - messages

Interface to enable applications that want network services to be able to talk to the network stack.

###### 6 - Presentation - messages

Presents the data into either the above or below layers. 
How the data is encoded (RLE etc.).
Also where encryption and decryption takes place.
Compression will also sbe handled here.
Information about the compression and encoding etc. needs to be sent with the data.
This is where file types are handled and they are used to show this.
Metadata will also be used to store this.

###### 5 - Session - messages

This layer in summary controls network session management.
This is used to manage for example: different tabs within an application.
Each session has a port number assosciated with it.
This allows incoming connections connections to be routed to the correct application and the correct session within that application.
This is an incoming port number.
This should not be confused with outgoing port numbers.
For example: all outgoing http sessions will be going to port 80, however, this is not the incoming port of the network.
This will be something completely different, and will be recorded so that the correct data will be sent back to the correct session.

###### 4 - Transport - segments

This layer defines how data will be transported across the network.
It runs end to end connectivity.
This is where the TCP (Transmittion Control Protocol - Reliable - Connectionfull - 3-way handshake - SYN SYN&ACK SYN) or UDP (User Datagram Protocol - Unreliable or Best Effort) is set up.
TCP is used when you need to ensure that all of the data gets there, e.g. file transfer.
UDP is used when the connection needs to be fast and not reliable, e.g. Live streams.

###### 3 - Network - packets

Responsible for network to network connectivity.
This is where addressing happens.
Main function is to get the data from your PC to the destination it needs to go.
A very common protocol of this layer is IP (internet protocol).
This is the protocol that manages all of the addresses of devices within a network.
This is the layer that routers work on.

###### 2 - Data Link - frames

Responsible for device to device connectivity.
This is where physical addressing happens (MAC addresses - Media Access Control).
Every device will have a NIC, and each of those will have a unique MAC address.
This is where switches work.
This layer also includes error detection.

###### 1 - Physical - bits

This layer is essentially the wire, or wires that the data travels along.
This does not necessarily mean on or off, but could be as different voltages.

#### Introducing LAN's

##### Local Area Networks

LAN's are very common.
They are the networks that you have iun your home, office or in shops.
LAN's provide much faster speeds.
LAN used to mean that it was a network within a singular building, each building would have it's own LAN.
LAN now comes to mean a set of buildings within a limited area (usually 1km).
LAN's are connected to eachother via a WAN (Wide Area Network).
Due to higher speed WAN's, LAN's can essentially be connected together to effectively make one large LAN. 
For example, the offices in Bedfont Lakes and in Green Park are now effectively on the same LAN.
This is called an intranet and it's you can connect to all of the Cisco webpages from any office in the world.

##### Components of a LAN

* Hosts
	* PC's
	* Servers
* Interconnections
	* NICs
	* Network Media
* Network Devices
	* Switches 
	* Routers 
* Protocols - Set of rules that are used to communicate
	* Ethernet - Layer 2 (Data Link)
	* IP (Internet Protocol) - Layer 3 (Network)
	* ARP (Address Resolution Protocol)
	* DHCP (Dynamic Host Cionfiguration Protocol)

##### Need for a switch

Switches replace the need for Bus networks and replace hubs.

Switches have the following functions:

* Operate at the link layer of the TCP/IP protocol suite
* Forward, Filter or Flood frames based on MAC table entries
* Have many full-duplex ports to segment a large LAN into many smaller segments
* Have high speeds and support for varoius port speeds

Switches essentially recieve frames and forward the frame through the required port based on destination address.
Due to the fact that the switch operates on layer 2, these addresses will be hardware (MAC) addresses.
To keep track of these addresses, the switch makes and maintains a MAC table.
The MAC address table is generated using the SA (Source Address) header and the incoming port/interface.
This is called 'learning by source' or 'dynamic learning'.
This means for incoming frames, the destination, found in the header, can be compared to the MAC table and then that can determine how the frame needs to be dealt with.
Administrators under certain circumstances will add or remove entries into the MAC table.

So, when a frame is sent to the switch, the first thing that is read is the SA (source address). 
It will then populate the MAC table with the SA and the port number/interface.
It will then look at the DA (Destination Address) and decide what to do with it.

There are 3 types of different addresses:

* Unicast - a singular point on a network, a singular device
* Multicast - a specific group of devices
* Broadcast - everyone on the network, all devices


This is how a switch deals with unicast addresses (Unicast - 

|Step|Action|
|---|---|
|1|When a unicast frame is received on a port, the switch compares the destination MAC address to the MAC address that is listed in the table.|
|2|If the switch determines that the destination MAC address resides on the network, it only forwards the frame to the required port, and not any others. The proccess of not forwarding to any other ports is called filtering. By performing this process, switches can significantly reduce the amount of traffic going between network segments by eliminating the unnecessary frames.|
|3|If the switch determines that the MAC address of the frame is not in the same segment as the frames' source, it forwards the frame to the necessary segment.|
|4|If the switch does not have an entry in the MAC table for the destination address, it transmits the frame out of all ports except the port the frame was received on. This is called flooding |

In reality, the MAC table also contains lots of extra information regarding reliabilty and speeds.
This means that when there are multiple entires of the same MAC address, the switch can make a decision to send over either port, rather than both.

##### Characteristics of a switch

LAN Switch Characteristics:
* High port density
* Mixture of port speeds
* Large frame buffers
* Fast internal switching
* Low per-port cost

#### Operating IOS Software

IOS - Internetwork Operating System

##### Feature and functions

The following are features or functions of IOS:

* Features to carry the chosen network protocols and functions
* Connectivity for high-speed traffic between devices
* Security to control access and prohibit unautherized network usage
* Scalibility to add interfaces and capability as needed for network growth
* Reliability to ensure dependable access to network resources

IOS is a CLI.
Due to this it can be controlled through a console connection, modem connection or throught Telnet or SSH.

##### Software Modes

| Mode | Access Method | Prompt | Exit Method | About This Mode |
|---|---|---|---|---|
|User EXEC | Begin a session| Switch> |Enter 'logout' or 'quit'|Use this mode to change terminal settings, perform basic tests, or display system information - Read Only Mode|
|Priveleged EXEC| While in User EXEC, enter the 'enable' command| Switch# | Enter 'disable' or 'exit' |Use this mode to verify commands that you have entered. Use a password to preotect access to this mode - Read Only Mode|
|Global Configuration| While in Priveleged EXEC, enter the 'configure' command| Switch(config)#| Enter 'exit' or 'end', or press Ctrl-Z|Use this mode to configure parameters that apply to the entire switch|
|Interface Configuration| While in Global Configuration, enter the 'interface' command (with a specified interface)| Switch(config-if)# | Enter 'exit' or 'end'|Use this mode to configure paramaters for the Ethernet interfaces|
|VLAN Configuration|While in Global Configuration, enter the 'vlan' command (with specified interfaces)| Switch(config-vlan)#|Enter 'exit' or 'end'||
|Router Configuration|While in Global Configuration, enter the 'router' command (with specific options)| Switch(config-router)#|Enter 'exit' or 'end'||
|(n)ACL Configuration|

#### Starting a Switch

##### Switch Installation

* Before installing a switch, verify the power and cooling requirements 
* Physically install the switch:
	* Rack mount
	* Wall mount
	* Table or shelf mount
* Verify the network cabling
* Attach the power cable to start the switch
* System startup routines perfrom POST (Power On Self Test) and initiate the switch software
* Kernel loads and then IOS

##### Switch LED Indicators

|Name|Description|
|---|---|
|SYST| Implies the overall system status|
|RPS| Suggests the status of the extra (redundant) power supply|
|STAT| If on (green), each port LED implies the status of the port|
|DUPLX| If on (green), each port LED implies the duplex of this port (on is full duplex, off is half duplex)|
|SPEED| If on (green), each port LED implies the speed of this port, as follows: off means 10Mbps, solid green means 100Mbps, flashing green means 1Gbps|
|PoE| Some switches have PoE LED in the system status group of LEDs. This LED indicates the per-port and system PoE status|

##### Connecting to a switch

* Console Port
* Console Cable
* USB to Serial Port Adapter

#### Understanding Ethernet and Switch Operations

##### Ethernet LAN connection Media

* The mechanical properties of Ethernet depend on the type of physical medium
	* Coaxial (not used anymore)
	* Twisted copper pair
	* Fiber optics
	* Wireless

Types of UTP Cabling:

* Straight through cable
	* The cables run directly throught the cable (1-1, 2-2, 3-3 etc...)
	* This cable is for connecting different types of devices together
		* Switch to Router
		* Switch to Host
* Crossover cable
	* The cables cross in the cable (1-8, 2-6, 3-5 etc....)
	* This cable is used for connecting like to like devices
		* Switch to Switch
		* Router to Router
		* PC to Router ***** This is the only non like to like that uses crossover
	* This is to avoid clashes within the cable

LEARN THE FIBRE CONNECTION TYPE (PAGE 51) 🙃🙃

##### Ethernet Frame Structure

|Field Length (Bytes)| 8|6|6|2|46-1500|4|
|---|---|---|---|---|---|---|
|Typical Ethernet Frame|Preamble|Destination Address| Source Address| Type| Data| FCS|
|Description| Warning that a message is coming| Where the frame is going| Where the frame has come from| What is the frame carrying (IPv4/IPv6)| The actuall data| Essentially a value based on length of frame (checksum)|

##### MAC Addressess 

Different display formats:

* 000.0c46.2e08
* 00:00:0c:43:2e:08

First 24 bits - Vendor code (manufacturer)

Last 24 bits - ID 

In total there are 48 bits used, however, usually shown in Hex


### Module 2 - Establishing Internet Connectivity

#### Exploring the functions of a router

##### Role of a router

* Routers are required to reach a host that is not on the local network
* Routers use a routing table to route between networks

Routers need an address on a network to function.

You do this in IOS with:

* `ip addr "IP" "Subnet"`
* `no shutdown`

` sh ip route ` shows you the routing table

When sending information from one IP address to another, the data will be put into a frame that contains the MAC address of the sender host, and also the MAC address of the default gateway.

A host will use ARP (Address Resolution Protocol) to find the MAC address of the default gateway.


A router contains a routing table.
This is similar to a MAC table found in a switch, however, they are used in very different ways.
If the router knows the destination address, it will forward the packets through the required port.
If not, the packet will be sent along the default route or by discovering the network.

The routing table is populated in 3 ways.
One way is the router just reading the address of directly connected networks.
Another way is with statice routing.
This is where an admin directly tells the router an address and the port to send it from.
The other way is called dynamic routing.
This is where routers use a routing protocol to advertise remote networks to other routers.
This is basically routers sharing their routing tables.
This means if R1 is connected to R2, which is connected to R3.
Due to dynamic routing, R1 knows to connect to R3 by sending to R2, which it will know what port it is connected  on.
On R1s routing table, it will have an entry for R3, and the interface would be the interface that R2 is connected to.
This shows how routers only care about the next hop, as R1 only knows that it needs to send the traffic to R2.
It does not care how many routers are between R2 and R3 (in this case it is 0 but it could be thousands).

All routers need to know about is something called the 'next hop'.
This is basically the next router on the path.
It does not care what happens to the traffic after that, it just needs to send the traffic to the next router.

Routers only really have 2 functions:
* Forwarding the packets
* Path determination

There is a specific entry in a routing table called a default gateway, or a gateway of last resort.
This is basically where a router will send packet of addresses it does not know.
This is basically your ISP, and from there, they can forward the packets as required.


##### Memory of a router

* Flash - IOS
* NVRAM - Startup Config
* RAM - Running Config
* ROM - Power On self Test, Bootstrap, ROM monitor - backup OS

##### Distance Vector vs Link State

Distance vector routing is like having signposts for routers, and the number of hops away.
Examples of this are EIGRP and RIPv2.
Link state routing is like having a map with a you are here sign on it, and showing every possible route to the destination.
Examples of this are OSPF and IS-IS.

##### Routing protocols
A router will have different metrics to decide the best path:
* Bandwidth - The data capacity of a link
* Delay - The length of time that is required to move a packet along each link from the source to the destination.
* Cost - A value set by administrators to weight decicions (load balance, reliability etc.)
* Hop Count - Number of hops between the source and destination (shortest but not necessarily fastest)

Usually protocols use multiple metrics to decide the best route

##### Picking between routing protocols
Routers can have multiple routing protocols running at the same time.
The way a router picks between which route to take is a number called the administrative distance.
The lower this number the better the rating.

|Protocol|Administrative Rating|
|---|---|
|Directly connected|0|
|Static route|1|
|EIGRP|90|
|OSPF|110|
|RIP|120|


### Module 3 - Summary Challenge

### Module 4 - Building a Medium Sized Network

#### Introducing VLANS

The point of a vlan is to segment up a network.
This is so that the amount of traffic that goes accross the network is decreased.
The way that this works is by telling a switch that certain ports belong to different vlans.
For example, HR, Sales, Engineering and Research will all be on different vlans.
This proccess can be done over multiple switches.
To connect multiple vlans on multiple switches, you need a special kind of port called a trunk port.
This is 2 special configuration that can be done over any port and any cable.
At the poinnt that a frame is sent over a trunk cable, a special header is put between the SA and the type field.
This is called the VLAN tag.
This has the data size of 32 bits (or 4 bytes) however, only 12 bits of this header are used to represent the VLAN ID.
The number of VLANS you can make is 1,000, however, if using the extended range, the maximum is 4,094 so, in total thats 5,094
This is only used on a trunk cable, and is removed when it exits the trunk.
This is a recognised standard (ieee 802.IQ) or commonly known as 'dot iq'.

When you create a vlan, the switch creates a file in flash called vlan.dat



### Module 5 - Network Device management and Security

### Module 6 - Summary Challenge

### Module 7 - Introducing IPV6

## ICND2
