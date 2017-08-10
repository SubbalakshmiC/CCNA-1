# CCNA stuff 
> lets do this!!!
---
# Course introduction  

> 2 weeks for learning ICND1 - 
> one week personal learning- 
> exam

# ICND1

In ICND 1 we will do:
* Describe network fundamentals and implement a simple LAN
* Establish internet connectivity
* Expand a small network to a medium sized now with routing enabled
* Configure, manage, secure and monitor Cisco devices
* Describe IPV6 basics

> CEF Cisco express forwarding will be in the routing section maybe....

## Pointers from apprentices
  
* Dont leave it to the last minute
* older apprentices will be more that happy to help you
* Its actually worth it, even if you go into sales
* you will have NO time if you leave it too late as when you start rotations you will have to drop something
* reach out to anyone if you need help, your co workers, other apprentices or any one really
* keep going, dont stop looking at the content for a month as you will forget it 

## Exam notes

* MUST PASS EXAM IF YOU WANT TO CONTINUE
* 300 marks for turning up
* Exam is out of 1000
* 90 minutes
* 825 or something to pass
* Cannot go back to a previous question
* Instant results when the time it up
* Exam is valid for 3 years when you get it

## Module 1 - building a simple network

### Exploring the functions of a network

a network allows people access to information. for example allows you to access emails, internet and so on. allows you to connect multiple sights together, like all the Cisco offices. Supports mobile users and allows them to do their work when they are not actually in the workplace. Could be private or public, 

#### physical components of a network

  * Firewall
  	* filters the traffic to only allow what you want / what it good
	* filters from outside in, the outgoing is not normally filtered 
	* a firewall is basically a router
  * Endpoints
  	* The end user machines - IP phones - laptops - desktops and so on
	* can connect with either wire or wireless 
		* wireless must connect to the netowrk through a wireless access point
  * Interconnections
  	* Network media
		* ethernet cable
			* can be UTP (Unsheilded twisted pair)
			* different cat levels, cat 1 - 6 or so
		* or fibre optic
			* simple = small glass inside
			* multi mode = bigger
			* immune to interference 
			* used for when over long distance (100m - kms)
			* split in two, one for send one for reiceive 
		* or coaxial
			* sinple copper core, used for internet in street
	* connectors
		* ethernet 
			* (R)egistered (J)ack
			* RJ45 - the one that is used all of the time
			* RJ11 - the old phone one
		* fibre
			* subscriber - SC
			* lucid - LC
			* stright tip - ST(C)
	* NIC (Network interface card)
		* used to allow the computer to actually plug into and use the network and connecter
  * Switches
  	* allows local devices to talk to each other
	* has many NIC interface
	* allow different parts of the building to speak with each other as they connect a small geographical location
  * Routers
  * WLAN devices
  * APs
  * WLAN controller
  
#### Characteristics of a network

* Topology
	* bus

		![bus topology image](https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/BusNetwork.svg/220px-BusNetwork.svg.png)
		* anyone can acess anyone elses data
	* ring

		![ring topology image](https://upload.wikimedia.org/wikipedia/commons/thumb/7/75/RingNetwork.svg/220px-RingNetwork.svg.png)
	* star

		![star topology image](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/StarNetwork.svg/220px-StarNetwork.svg.png)
		* This is how a switch works internally 
	* mesh

		![mesh topology image](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/NetworkTopology-FullyConnected.png/220px-NetworkTopology-FullyConnected.png)
		* This is how a router works internally to find the best way 
	* physical topology
		* This is how the cables and the devices are actually laid out physically aroud the building 
		* basically what you can see with the cables
	* logical topology 
		* Inside the devices you get the logical topolopy
		* its how the infomation flows between devices
* Speed
	* in a building the speed if fast
	* outside of a building it is generally slower
* Cost
	* when you get the cisco stuff in a network there is only a one off cost, not an ongoing one
* Security
	* if its all alone then there is no real need for security
	* if its public then you need security
* Availability
	* how well people can actually access it
	* can you access the network when you are away from the office
		* mobile users
		* VPN
	* [ (minutes in a year) - (Downtime) ] / 525600 * 100 = percentage up time
		* e.g. (525600 - 15) / 525600 * 100 = 99.9971% uptime
* Scalability
	* how able is the network able to scale up to new users
* Reliability
	* the dependability of the network devices
		* cheap stuff will break so dont use them
		* e.g. SSDs will last longer and wont fail as much as hard drives
#### Interoperating a network diagram

* thick red lines = a physical Ethernet connection 
	* can be Ethernet or fibre
* IP address 
	* 32 bit binary number
	* made of network and host sections
		* basically street name and house number
* interface
	* This is the where you plug the devices in to the networking component
	* FA = (Fa)st Ethernet
		* max speed is 100 Mbp/s
	* Gi = (Gi)gabit
		* max speed is 1,000 Mbp/s
	* S = (S)erial
		* its old, but still around and you still need to know about it
		* very slow
		* speed is up to 2 Mbp/s
		* generally used to power just a command line interface and not to do much networking
			* used to manage devices
	* the ports will be labelled by the port type and then number
		* for example a port could be called:
			* Fa0/12 - the 13th ethernet port
			* Fa0/7 - the 8th ethernet port
			* Gi0/1 - the 2nd Gigabit port
			* S0/0/0 - the 1st serial port
	
#### Impact of user applications on the network

* batch applications
	* Computer to computer communication
	* these are done one after another with a conclusive start and finish
	* No direct human interaction
		* just two machines talking to eachother
	* Bandwidth is important but not critical
		* the machines can just work in the backgroud when the network is slow
	* examples include
		* FTP - File Transfer Protocol
		* TFTP - Trivial File Transfer Protocol
		* inventory updates
		* SCP
* Interactive applications
	* Human to Computer communication
	* Inventory inquiry
	* Human waiting time is important but they can wait a bit for the computer as long as they dont have to wait too long
* Real time applications
	* Human to Human communication
	* 100ms
	* VoIP, video and so on
	* Needs a lot of bandwidth and priority
* QOS (Quality Of Service)
	* how well the network can actually prioritise the different applications types

### Understanding the Host-to-Host communications model
	
OSI standard model

At the top there is the software that you are using, e.g. Word, firefox and so on

|| Layer name | Layer Number | purpose | PDU
|-|------|-|-|-|
|↓| Application | 7 | Used to enable the software that wants to talk to the network stack and enables it to do so. The user interface for the network stack | Messages
|↓| Presentation | 6 | defines how the data is encoded and represented and contains information on the file type. Also things like encryption and compression. This additional information is stored as metadata | Messages
|↓| Session | 5 | network session management. Keeps the connection going to the right location. Outgoing is the normal port, but incoming is randomised to the session a then translated to the correct machine by the router. | Messages
|↓| Transport | 4 | defines how the data is to be transported across the network, implements TCP and UDP | Segments
|↓| Network | 3 | Network to network connectivity. handles ip addresses. Routers | Packets
|↓| Data Link | 2 | Device to device connectivity. handles MAC addresses. Switches. only works on a local network this is how ARP is used | Frames
|↓| Physical | 1 | How the data is represented on the raw media. e.g. ±5 volts, LED on for x miliseconds (encoding, need a clock to know when a signal ends) | Bits

##### Application
* allows the software to access the network stack

##### Presentation
* tell you how information has been encoded
* tells you about how the file has been encrypted so that it can be unencrypted
* compression so that the file is smaller and faster
	* must compress video as it is SO big when not compressed

##### Session
* keeps the session of the network connection alive ensures that you will still have access to it correctly
* when you have multiple tabs open this will send it to the correct tab that requested that information 
* e.g. when you request information from chrome the data will be sent to chrome on the machine
* every connection that you have will come in through a unique port number but it will go out through the normal one
* Outgoing will always be port 80 for example, but incoming will be a unique port number for a certain session like 23424 but this is then mapped to your internal ip address by the router

##### Transport
* defines how the data is to be transported across the network
* TCP = reliably 
	* TCP Transmission Control Protocol
	
	###### three way handshake
	|Client|Server|
	|--|--|
	|SYN ↘| |
	| | ↙ SYN - ACK |
	|ACK ↘| |
	
	* are you ready to get the data
	* yes I am
	* I am sending the data
	* go ahead
	* are you getting the data
	* I am
	* did you get all the data
	* yes
* UDP = unreliably
	* HERE IS THE DATA TAKE IT
	* AHHHHHHH OK

##### Network
* Network to network connectivity 
* mainly deals with addressing
* get the data from your computer on the network that you are on to the network that you want to get the data to
		* get the data from one logical address to another
##### data link
* Device to device connectivity 
* MAC addresses
* physical addressing
* to access by MAC you need to be on the same local network (on a switch)
	* ARP will take IP and convert to MAC
##### physical
* the actual cable 
* copper vs fibre vs wireless
* take the data and represent it in on and off signals
	* copper = electric signal high (+5V) -> 1
	* fibre = light on for x microseconds

* data is encapsulated with headers at the front and then trailer at the end

When you send information the data goes down the stack on your machine side, then at its destination it goes back up the stack.

##### TCP IP model

| Layer name | layer Number | purpose | PDU |
|-|-|-|-|
|Application | 4 | Application, presentation and session| Data
|Transport | 3 | Transport | Segment
|Internet | 2 | network | Packet
|Link | 1 | data link and physical | Frame
##### OSI summary
| Layer name | purpose 
|------|-|
| Application  | Used to enable the software that wants to talk to the network stack and enables it to do so. The user interface for the network stack 
| Presentation  | defines how the data is encoded and represented and contains information on the file type. Also things like encryption and compression. This additional information is stored as metadata 
| Session | network session management. Keeps the connection going to the right location. Outgoing is the normal port, but incoming is randomised to the session and then translated to the correct machine by the router. 
| Transport  | defines how the data is to be transported across the network, implements TCP and UDP 
| Network  | Network to network connectivity. handles ip addresses. Routers 
| Data Link  | Device to device connectivity. handles MAC addresses. Switches. only works on a local network this is how ARP is used. Tells you how to interoperate the binary
| Physical  | How the data is represented on the raw media. e.g. ±5 volts, LED on for x miliseconds (encoding, need a clock to know when a signal ends) 



##### OSI vs TCP IP model

<table>
	<tr>
	<th colspan="3"> OSI </th>
	<th colspan="3"> TCP/IP </th>
  </tr>
  <tr>
    <th>Layer Number</th>
    <th>PDU</th>
    <th>Layer Name</th>
    <th>Layer Name</th>
    <th>PDU</th>
    <th>Layer Number</th>
  </tr>
  <tr>
    <td>7</td>
    <td rowspan="3">Messages</td>
    <td>Application</td>
    <td rowspan="3">Application</td>
    <td rowspan="3">Data</td>
    <td rowspan="3">4</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Presentation</td>
  </tr>
  <tr>
    <td>5</td>
  	<td>Session</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Segment</td>
  	<td>Transport</td>
  	<td>Transport</td>
    <td>Segment</td>
    <td>3</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Packet</t>
  	<td>Network</td>
  	<td>Internet</td>
    <td>Packet</t>
    <td>2</t>
  </tr>
  <tr>
    <td>2</td>
    <td>Frame</td>
  	<td>Data Link</td>
    <td rowspan="2">Link</td>
    <td rowspan="2">Frame</td>
    <td rowspan="2">1</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Bit</td>
  	<td>Physical</td>
  </tr>
</table>

> Day 2

##### Encapsulation

<table>
<tr>
	<td >Application</td>		
	<td colspan="4" ></td>		
	<td>User data</td>		
	<td rowspan="3"> </td>
</tr>
<tr>
	<td> Transport </td>
	<td colspan="2"> </td>
	<td> L4 header </td>
	<td> Other Header</td>
	<td> User data </td>

</tr>
<tr>
	<td> Internet </td>
	<td></td>
	<td> L3 Header
	<td> L4 header </td>
	<td> Other Header</td>
	<td> User data </td>
</tr>
<tr>
	<td> Link </td>
	<td> L2 Header
	<td> L3 Header
	<td> L4 header </td>
	<td> Other Header</td>
	<td> User data </td>
	<td> Trailer </td>
</tr>
</table>

### Introducing LANs

A LAN is a network of computers that are in a small geographical location. Before LAN you would have had speeds of:

* 9.6 kb
* 19.2 kb
* 64 kb
* 2 Mb

e.g. There is a LAN at green park and a LAN at Bedfont 

Green park LAN <-> WAN <-> Bedfont LAN

| | GP LAN | WAN | BF LAN|
|-|-|-|-|
Old | 10 Mbps | 2 Mbps | 10 Mbps |
New | Gi | 100 Mbps / Gi | Gi |

Due to the new increse in speed you could now call both the LANS a Single UK LAN for Cisco. Basically just an Intranet. 

Due to this LANs can range in size from really small to inside a house all the way up to huge offices. For example an 8 port switch could cater for a small company perfectly fine. 

#### LAN Components

* Hosts
	* PC
	* Server
* Interconnections
	* NIC
	* Network Media
* Network Devices
	* Switches
	* Routers
* Protocols
	* Ethernet
		* Acts at the Data link layer (layer 2)
	* IP
	* ARP (Address Resolution Protocol)
	* DHCP (Dynamic Host Configuration Protocol)
	* a protocol is a way to do things that have been set up and act like a standard so that all devices know how to use it 

0100111010011 means what?

|bits|0100|1110|10011|
|-|-|-|-|
|Layer 2 frame|Destination address|source address| data|

In this example the layer 2 protocol defines where the DA, SA and data are in the binary numbers. 

Ethernet takes the binary on the cable and compartmentalises them into relevant information. 

Ethernet is just a layer 2 protocol, not a cable. Token ring is another layer 2 protocol. Due to this, they are not compatible with each other, if you did need to communicate between them then you would have to use a bridge. 


##### Layer 2 protocols

* Routers are good at taking data in one frame format and putting in another. 
* Ethernet
* Token ring
* HDLC
	* High level Data Link Control protocol
	* used in serial connections
* PPP
	* Point to Point Protocol
	* PPPoA(TM)
		* PPP A-syncsones Transpher Mode
	* PPPoE
		* PPP Over Ethernet

##### *Thicc* Ethernet  

Basically a coax cable, single copper core that would run in the floor or ceiling. every 2.5M along the cable you would attach a device to, you basically drill a hole in the cable and then attach the device to the copper core. Vampire taps. Maximum speed of 10Mbps which was REALLY fast for the day. Called a broadcast media because when you broadcast information all devices can read and see the information. 

Broadcast medium 

* CSMA/CD
	* Carrier sense multiple access with collision detect 
	* Controls who gets to go first when you are on a broadcast media like a single coax cable where all devices want to send information. 
	* before you transmit you would need to listen to the cable to see if someone else is transmitting, if they are then you must wait. 
	* the collision detection will loop back some data to know if there has been a collision 
	* if there has then they will send a jamming signal so that no data will interfere with the collision and will give time to let it pass
	* Random exponential back off algorithm is then used to see who will transmit first again
* when you add more devices to the network there will be MANY more collisions
* In reality you would get about 3-4 Mbps

This was a REALLY bad system. so it was replaced with UTP. it was nice as you had proper connectors and cables and so on. 

We moved to hubs after this due to the fact that you could then just plug in UTP cables to the magic box. It only charged the physical cabling. So it still used CSMA/CD so it was all broadcasting all around. A hub still has the single wire in it basically so no changes to network speed or collision. Physically its a star but logically its a bus. Also known as a repeater. The hub is a layer one device

##### Hub

* a coax cable in a box with fancy connectors
* Only changed the cables that you used, was still the same underneath
* also known as a repeater
* logically a bus but physically a star
* a layer 1 device
* this lead to a bridge

##### bridge

* ASIC (Application Specific Integrated Circuit)
* SW based
* Layer 2 device
* This lead to switches as they were hardware based and so they were faster. 

##### CSMA/CA
 
* Carrier Sense Multiple Access with Collision Avoidance
* really complicated but the modern version 
* wifi

###### random notes
* 2.4 Ghz 82.11 b/g/
	* 14 wireless frequencies 
	* DSS
* 5Hgz 82.11 n/AC
	* 48 frequencies
	* OFDM

### Switching in a network

why did we start switching

* speed
* reduce collisions
* improve security

#### Switches

* layer 2 devices
	* they actually read the frame data and send the information to where it needs to go. 

Layer 2 switch icon:

| | ---> |
|-|-
<---||
||--->|
<---||

in this example we have a four port switch

* device A is connected to port 1
* device B is connected to port 3
* device C is connected to port 2
* device D is connected to port 4
* Tx is send to switch
* Rx is send to device (receive)
	* Tx and Rx is full duplex
		* full duplex is faster as you can send and reiceice at the same time
	* only one is half duplex
		* this is where you can only send or reiceive at the same time
	* no need for CSMA/CD because separate wires are used
* auto negotiation is used to get to the correct duplex for the connection 

the switch maintains an internal table called the MAC address table. 

#### MAC address table

a table in the switch that is made by the switch in runtime. At the start the MAC address table is blank. 

|MAC table|
|-|
||

Device A sends information to device B. 

|A|->|B|
|-|-|-|
|Source address | | Destination address
|Port 1 | | |

Add to the MAC table "device A is available through port 1"

|MAC table|
|-|
|A=1|

Where is device B located???? I dont know where to send this information, I will therefore send this information through every other port. (unknown unicast flooding)
> called this because you dont know where B is (unknown), to one device (unicast), sending on all ports (flooding)

when device C and D get the message, they see that it is not for them and they ignore the message. Destination address is not MAC address, drop the frame

B gets the message takes it and then sends a response back

|B|->|A|
|-|-|-|
Source address||destination address
Port 3 ||

Device B is located on port 3, I will add that to the MAC table. But where is device A? lets look at the MAC table

|MAC table|
|-|
A=1|
B=3|

Ahh, A is on port one, i will send the frame to only port 1 then. 

|B|->|A|
|-|-|-|
Source address||destination address
Port 3 ||Port 1

Now i can send messages directly from these two devices

* This process is called forwarding as you forward the data to the correct known port

* This then means that you filter the data from the other ports

* This means that filtering is the opposite of forwarding and that forwarding is the process looking up the MAC table to get the correct port. 

* This also means that filtering does not happen when flooding

C -> D

|C|->|D|
|-|-|-|
|Source address | | Destination address
|Port 2 | | |

C is on port 2, lets add that to the MAC table, but where is D, lets check the MAC table 

|MAC table|
|-|
A=1|
B=3|
C=2|

I dont know where D is..... I have to flood the data to all ports

A and B see the data is not for them, they drop the packets

D gets the data and sees that it is for it so its gets the data, and sends back a responce

D -> C

|D|->|C|
|-|-|-|
|Source address | | Destination address
|Port 4| | |

D is on port 4, lets add that to the MAC table, but where do I send the data to get to C, lets check the MAC table

|MAC table|
|-|
A=1|
B=3|
C=2|
D=4|

ah, C is on port 2 I will send it there

|D|->|C|
|-|-|-|
|Source address | | Destination address
|Port 4| |Port 2 |

This is called Learning by source or dynamic learning

##### broadcast address

MAC address only contains source address information due to this you cannot assign the broadcast address in the MAC table. 

B sends in a broadcast frame, this is not in the MAC table so it floods the frame. 

Broadcast ends at the router where device then gets assigned an ip address by the router this is then sent back to the 

##### buffering

100mbps -> Gi is ok

Gi -> 100mbps is not ok
* needs to buffer the frames.... its a frame buffer
	* this additional information is stored on the switch and is buffered to the 100 port at 100 speed 
	* a large frame buffer is needed

#### Different types of casting

There are 3 different ways to send messages on a network based on who you want to receive them:

* Unicast
	* when you want to send the message to ONE device on the network
	* A -> B
* Multicast
	* when you want to send the message to MULTIPLE devices on the network
	* you get a multicast address that the switch will forward all data sent to that address to the intended devices
	* A -> B & D
* Broadcast
	* when you want to send the message to EVERYONE on the network
	* the highest available IP within the subnet will cast the data to all devices
	* all subnetting is done on the switch side, so broadcast is an alias to send to all active addresses
	* A -> B & C & D & ......
		* A -> ALL

##### unicast

When the switch receives a unicast frame the following process will occur:

* filter
* forward
* flood

### Operating Cisco IOS software

|User mode| -> | Privilege mode | - > | Global Configuration mode |
|-|-|-|-|-|
|$Hostname>|enable|$Hostname#| configure terminal / conf t|$Hostname(config)#
|<-|disable|<-|exit / end |<-|

switch is normally a plug and go device as it will do basic functions by just plugging in. but you may want to add security, remote management and so on.... 

Internetwork Operating System is the OS on cisco things. 

IOS is and End-to-End operating system as it covers all of the devices from switches to AP's

You plugin via the console port

You start in user mode, can read but not edit you know how this do

you cannot man, help or even tab complete flags..... *sigh*

* 'show' will as you guess, show you things
* '?' contextual help 
* '\<tab>' auto complete you know this
* '\<up>' or '\<C-P>' previous command
* '\<down>' or '\<C-N>' next command
* '\<C-A>' beginning of line
* '\<C-E>' end of line
* '?'

#### User mode | $Hostname> 

by default 
Read only mode

#### Privilege mode | $Hostname#

* "enable" will take you to privilege mode
* you cannot change but you can reload
* you can copy and save configuration
	* good for making a template 
* do a full examination 
	* full access to configuration
	* have access to config files that may have passwords
* configuration mode access

#### Global Configuration Mode

show running-config (sh run)
* shows your running config that is actually in place

show startup-cohfig
* the one that is used when you start up the device

show interface Ethernet0/3 (sh int e0/3)

hostname Temp
* changes the hostname to 'Temp'

##### CAM table

* aging time is normally 5 mintues
after that time the MAC address is removed from the table 

* When a cable is removed then the MAC table for that port is erased

* if the MAC address changes port then the MAC is changed the assigned port

### Starting a switch

when you connect to a switch you can do so via the two methods

|User mode| -> | Privilege mode | - > | Global Configuration mode |
|-|-|-|-|-|
|$Hostname>|enable|$Hostname#| configure terminal / conf t|$Hostname(config)#
|<-|disable|<-|exit / end |<-|
|||||V   ^
|||^||V exit
|||end||V 
/------<-------|----<---|--------<-------|-------------<------------|-------------->-------------\|
|interface | VLAN | Router|(n)ACL|...etc
|$Hostname(config-if)#|$Hostname(config-vlan)#|$Hostname(config-router)#|$Hostname(config-nacl)#|
|interface x|vlan x| router x | access-list|

#### switch installation

when you get it first you do the standard set-up stuff

* mount to location
* plug in power
* plug in network cables
* system does POST (Power On Self Test)
* kernel loads and bootstrap and so on

##### mode button

* will change what the LED lights show
	* syst
		* shows the system status
			* Off means switch is off
			* On (green) means fully operational
			* On (amber) means POST failed
	* RPS
		* Redundant Power Supply status
	* stat 
		* shows used ports
			* On means active port
			* Off means inactive connection
	* duplx
		* shows the duplex setting of the ports
			* on is full
			* off is half
	* speed
		* will show what speed the ports are running at
			* off is 10 Mbps
			* on is 100 Mbps
			* flashing is Gi
	* PoE
		* shows the ports that support Power Over Ethernet
			* on shows supported
			* off shows not supported

#### Connecting to the console port

* Console port (DB9)
* Console cable
* usb to console adaptor

#### Discovery 2: Perform basic switch function 

To reverse any command just put no before the command

things that can be wrong with the switch is that the duplex or the speed could be wrong

"do" basically sudo but for doing non-sudo commands from sudo
* running user commands in non-user mode

collision is normal
* late collision means that duplex is set up badly 
	* one end full duplex one end half

if the duplex is unknown then it sets to half
* but if it is Gi then it will set default to full duplex

set both speed and duplex in a network to a defined state for static devices
* so laptops that move around should be set to auto 

CDP - Cisco Detection Protocol
* will only work when both are Cir

LLDP - Link Layer Discovery Protocol

## Understanding Ethernet and switch operation

switch problem?
* is the cable ok
	* port down
* is the duplex wrong
	* will get duplex error in terminal
	* port up
* is the is the speed wrong

### Ethernet LAN connection media

* coax
* twisted copper pair (UTC)
	* 4 pairs of wires
	* 10 mbps to 10 Gbps
	* RJ 45 connector
	* Normally 100m range
	* 2 types
		* stright through
			|1|2|3|4|5|6|7|8|
			|-|-|-|-|-|-|-|-|
			|1|2|3|4|5|6|7|8|
			* used for like to unlike device
			* PC to switch
		* crossover cable
			|1|2|3|4|5|6|7|8|
			|-|-|-|-|-|-|-|-|
			|3|6|1|4|5|2|7|8|
			* Used for like to like device
			* PC to PC
			* PC to Router (Dont do this!)
* fibre-optic
	* main part is the glass core that is flexible
	* *FEST*
	* different types
		* Multi mode - 2 different frequencies on the glass
		* single mode - only one signal
		* connector types
			* thereaded 
			* bayonet
			* push pull
		* connector material 
			* Metal
			* Plastic sleve
		* ST - patch panels
		* FC - service providers
		* SC - enterprise
		* LC - sfp
	* see page 51
	
* wireless

### Ethernet frame structure

Byte size|8|6|6|2|46-1500|4|
|-|-|-|-|-|-|-|
Name|Preamble|Destination|source|type|data|FCS|
Description|A message is coming through|where the data is going to|where the data came from| what type of network this frame is intended for. (ipv4 or ipv6)|the actual data that you want| Frame check sequence - a checksum|

#### FCS

if it is bad then the packed is thrown away then requested again 

#### addresses

these are the MAC addresses. 

48bits in lenght (6 bytes)

first 24 bits are manufacturer

last 24 bits are the uuid

##### MAC address
	
* Unicast
	* one to one
* Broadcast
	* one to all
* Multicast
	* one to many

### troubleshooting problems

* define problem
* gather information
* analyse information
* eliminate potential causes
* Propose hypothesis
* test hypothesis
* solve and document

#### methods to troubleshoot

##### OSI model

Top-Down

Bottom-up

divide and conquer
* if ping works then layers 1, 2 and 3 MUST work

##### other

comparison of another machine

Follow the path of the issue
* do you have wifi 	
* does the router work?
* ... and so on, follow the path

swapping components
* router has died :(
	* get a new one

##### tools

	ping 10.10.50.2

	ping 10.10.50.2 source ethernet 0/0

> cisco ping will always send 5 requests

	traceroute 10.10.50.2

##### common trouble causes

###### Layer 1

New device adds EMI interference

Damage to wiring

Traffic patterns change

New stuff is installed that is not accommodated for in other devices

* fibre
	* bent and snapped core

###### Layer 2

duplex mismatch

speed mismatch
* if this is in effect then no coms at all

solution
* look at both devices to see about the issues

## Module 2 - Establishing internet connectivity 

### Understanding the TCP/IP internet layer

* The internet protocol (UDP)
	* layer two of the TCP/IT
	* layer three of the OSI
	* IP protocol
		* connectionless protocol
			* doesnt have to create a connection before you send information
		* packets treated indepently
		* Best-effort delivery
		* No data-recovery stuff
			* made to be fast
			* no reliability use transport layer for that stuff
		* media independant (not on layer 1 or 2)
		* IPv4 and 6 are here 
	
#### Protocols

* PC - SW = layer 2 ethnernet
* SV - SW = layer 2 ethernet

|PC||||||||SRV|
|-|-|-|-|-|-|-|-|-|
|V|ETH||HDLC||PPP||ETH|^|
|SW|->|R1|->|R3|->|R2|->|SW|
|||||||||
|<|-|-|-|IP|-|-|-|>

When the frame reaches R1 the router will de-encapsulate the data to layer 3, then make a decision about where to forward it. It sees that the next connection needs a HDLC frame to send the data so when the router re-encapsulates the data it will put it in a HDLC frame to send it across the connection. 

basically it decodes the data, decides where to send the data based on IP then re-encodes all the information in the correct format for the next connection keeping the destination and source MAC address and data between the two. 

example, when you upload a word document resume containing data, your name (source) and the company name (destination) to their website. the website would convert it to a pdf, but all the information contained will stay the same. then when the person gets it at the other end they will convert it back to the word document. Then it will contain all the same information inside but in the original format. 

### IPv4 address representation 

an IP address is a 32 bit binary number. we take this complicated value into 4 sections of 8 bits (4 octets). we then represent this in dotted decimal location 

an IP address is split into 2 sections, the Network ID and the Host ID. 

|32|bits|
|-|-|
|Network|Host|

[10].0.0.0 is like the street name and represents it. This is the network number and the length can change. all of the devices in the same network share the network name. 

router = 10.0.0.[1] because it is the first address that is reached

switch = 10.0.0.[2] - PC1 = 10.0.0.[3] - PC2 = 10.0.0.[4]

This 1,2 and 3 represents street number as they all have the same street name, but are located on different locations on the network. 

### IP header PUT MORE INFORMATION HERE

protocol = TCP or UDP

Time to live = hop count maximum

ask for two sheets of not paper

### decimal and binary

in an IP address you have a byte (8 bits), the full ip address is 4 bytes long.

|most significant bit|||||||least significant bit|
|-|-|-|-|-|-|-|-|

|2^7|2^6|2^5|2^4|2^3|2^2|2^1|2^0|
|-|-|-|-|-|-|-|-|
|128|64|32|16|8|4|2|1|
|0|0|1|0|1|0|0|0|
|0|0|32|0|8|0|0|0|
32+8 = 40

## Module 3 - Summary challenge

## Module 4 - Building a Medium sized network

## Module 5 - Network device management and security 

## Module 6 - Summary challenge

## Module 7 - Introducing IPV6
