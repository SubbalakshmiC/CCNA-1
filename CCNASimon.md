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





### Module 2 - Establishing Internet Connectivity

### Module 3 - Summary Challenge

### Module 4 - Building a Medium Sized Network

### Module 5 - Network Device management and Security

### Module 6 - Summary Challenge

### Module 7 - Introducing IPV6

## ICND2