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

> Day 4

|192|168|0|1|
|-|-|-|-|
11000000|10101000|00000100|00000110|

### Classing system

|Class|fixed bits|start|secend|third|final|example|
|-|-|-|-|-|-|-|
| class A | first bit is fixed | 0xxxxxxx | .Host | .Host | .Host | 10.0.0.1 |
| Class B | 2 bits are fixed | 10xxxxxx | .Network | .Host | .Host | 172.16.0.1 |
| Class C | 3 bits are fixed | 110xxxxx | .Network | .Network | .Host | 192.168.1.1 |
| Class D (Multicast) | 4 bits are fixed | 1110xxxx | | | | |
| Class E (Reserved) | 4 bits are fixed | 1111xxxx | | | | |

|Class|binary range|decimal range|maximum number of hosts|Layout
|-|-|-|-|-|
|A|**0**0000001 - **0**1111110|1 - 126| 16,777,214|N.H.H.H
|B|**10**000000 - **10**111111|128 - 191| 65,534|N.N.H.H
|C|**110**00000 - **110**11111|192 - 223| 254|N.N.N.H
|D|**1110**0000 - **1110**1111|224 - 239| Multicast |
|E|**1111**0000 - **1111**1111|240 - 255| Reserved |
| |**01111111** | 127 | used for diagnostics

>*Please note that 127.0.0.0 to 127.255.255.255 is not used as it is for diagnostics and loopback and so on. hence why 127.0.0.1 is your local machine*

The assignment of ip address is done by

Internet Assigned Number Authority (IANA)
* Regional Internet . Europe (RIPE)

> IPV6 is 128 bit

 we will configure multicast with RIFv2 - 224.0.0.9

next week we will look at OSPF (open shortest past first) which is another - 224.0.0.5 / 224.0.0.6

hold music is sent on 239.0.0.1 

class full addressing is what we have just done, but its old so now we use classless addressing

#### classing test thing

200.210.18.34
* class C
* 200 is between 128 and 191
* N.N.H.H

10.255.17.254
* class A
* 10 is between 1 and 126
* N.H.H.H

172.54.3.2
* class B
* 172 is between 128 and 191

### subnetting 

think of the number of hosts that you want in the network then select the lowest power of 2 that is bigger than you want and can accommodate the number. 

number of usable hosts = (2^n) - 2

#### reserved addresses

There are always 2 less than the 2^x number due to one being the broadcast address and then the other being the network ID

* 0.0.0.0 is not valid
	* unspecified address
	* used to indicate "anything"
	* cannot assign as a host address

* 255.255.255.255
	* local network broadcast address
	* this will propagate in a network but will not leave it (a router will drop the packet)
	* one example is the use in DHCP

10.***0.0.0***
* the network ID
	* like setting your house name as the street name
* N.H.H.H
	* the host feild is all 0's
	* this means the whole network
	* hone to advertise the network to other people

10.255.255.255
* directed broadcast address
* ping of death
	* all devices in 10.*.*.* will try to respond
	* it will pass through routers

#### public IP addresses

|class|ip address section one| address section 2|
|-|-|-|
|A|1.0.0.0 to 9.255.255.255 | 11.0.0.0 to 126.255.255.255|
|B|128.0.0.0 to 172.15.255.255 | 172.32.0.0 to 191.255.255.255|
|C|192.0.0.0 to 192.167.255.255 | 192.169.0.0 to 223.255.255.255|

#### private IP addresses

|class|ip range|
|-|-|
|A|10.0.0.0 to 10.255.255.255|
|B|172.16.0.0 to 172.31.255.255|
|C|192.168.0.0 to 192.168.255.255|

#### NAT (Network Address Translation)

translates your private ip address 192.168.0.4 to a public ip address 23.43.65.145.

#### Domain Name Server

you type in the name of the website, then that data will go to a dns server who will send back the ip address that will actually connect you to the server that holds the website. 

on the endpoint you just need to say that you just want to use DHCP then the rest will work it out itself. 

if you set in manually then you need to say what ip address you want and the subnet mask that you want. 

### IP ADDRESSING AND SUBNETTING

if you are in a class A network then you could easily get many of the devices sending a broadcast at the same time that it would be far too slow. you take a whole layer 2 network (just switches) then then split it up with routers so that there are now many smaller netowrks and connect them together. 

small networks are easy to manage, have less traffic 

the subnet mask is 32 bits. it can be represented in dotted decimal notation or slash notation. 

a comparison is made between the bits in the ip address and the bits in the subnet mask. 

if you have a bit in the mask, then that bit is part of the network section and not the host section. 
* if the bit is 0 then it is part of the host section of the address 

10.1.1.1 - class A

N.H.H.H

the mask for that would be 255.0.0.0 as it shows the first byte is part of the network section. 

172.16.5.12 - class B

N.N.H.H

the mask for that would be 255.255.0.0 as it shows the first two bytes are part of the network section

200.210.18.32 - class C

N.N.N.H

the mask for this would be 255.255.255.0 as it shows the first 3 bytes are part of the network section 

then you have slash notation so for example 255.255.0.0 has a slash notation of /16 as there are 16 1's in a row at the start of the mask.

your machine needs to know what network it is on so that it knows that you are in the public section of that network so it knows if it needs to go through the router to do NAT and access the machine that it needs. 

* it needs to know where the default gateway is

|128|64|32|16|8|4|2|1|
|-|-|-|-|-|-|-|-|
|0|0|0|0|1|0|1|0|
|1|1|1|1|1|1|1|1
|0|0|0|0|1|0|1|0|

|128|64|32|16|8|4|2|1|
|-|-|-|-|-|-|-|-|
|0|0|0|0|1|1|1|1|
|1|1|1|1|1|1|1|1
|0|0|0|0|1|1|1|1|

one device on network 16.7.7.11 another on 15.7.7.11

15.7.7.11 & 255.0.0.0 = 15.0.0.0

16.7.7.11 & 255.0.0.0 = 16.0.0.0

These are not the same so they are on a different network and so need to go through a router to get the each other so therefor it has to go through the default gateway to access it. 

172.16.0.0 & 11111111.11111111.11111100.00000000

6 additional bits have been taken from the next byte and so there are 2^6=64 different subnets that are now available to be made. 

the value of the last 1 in the mask is the magic number this will tell you the steps that the subnets will go in 

200.210.18.0/24 - 11 switch networks - min 10 hosts on each

10 hosts fits in 4 bits

/24 means that can only be in the last byte

therefor the last byte would look like 11110000

therefor the slash notation would now be /28 due to there being 28 ones

the last bit of the subnet is a 16 value so there will be a step of 16 betweeen each subnet

the subnets will be

* 200.210.18.0
	* first address - 200.210.18.1
	* last address - 200.210.18.14
	* BC = 200.210.18.15
* 200.210.18.16
	* first address - 200.210.18.17
	* last address - 200.210.18.30
	* BC = 200.210.18.31
* 200.210.18.32
	* first address - 200.210.18.33
	* last address - 200.210.18.46
	* BC = 200.210.18.47
* 200.210.18.48
	* first address - 200.210.18.49
	* last address - 200.210.18.62
	* BC = 200.210.18.63
* 200.210.18.64
	* first address - 200.210.18.65
	* last address - 200.210.18.78
	* BC = 200.210.18.79
* 200.210.18.80
	* first address - 200.210.18.81
	* last address - 200.210.18.94
	* BC = 200.210.18.95
* 200.210.18.96
	* first address - 200.210.18.97
	* last address - 200.210.18.110
	* BC = 200.210.18.111
* 200.210.18.112
	* first address - 200.210.18.113
	* last address - 200.210.18.126
	* BC = 200.210.18.127
* 200.210.18.128
	* first address - 200.210.18.129
	* last address - 200.210.18.142
	* BC = 200.210.18.143
* 200.210.18.144
	* first address - 200.210.18.145
	* last address - 200.210.18.158
	* BC = 200.210.18.159
* 200.210.18.160
	* first address - 200.210.18.161
	* last address - 200.210.18.174
	* BC = 200.210.18.175
* 200.210.18.176
	* first address - 200.210.18.177
	* last address - 200.210.18.190
	* BC = 200.210.18.191
* 200.210.18.192
	* first address - 200.210.18.193
	* last address - 200.210.18.206
	* BC = 200.210.18.207
* 200.210.18.208
	* first address - 200.210.18.209
	* last address - 200.210.18.222
	* BC = 200.210.18.223
* 200.210.18.224
	* first address - 200.210.18.225
	* last address - 200.210.18.238
	* BC = 200.210.18.239
* 200.210.18.240
	* first address - 200.210.18.241
	* last address - 200.210.18.254
	* BC = 200.210.18.255

15.17.18.35 - 255.255.255.0

network ID = 15.17.18.0

the default class mask is what the class A, B and C will use by default (255.0.0.0, 255.255.0.0, 255.255.255.0)

### The connection between two routers will have to be its own network and it will probably have just two ip addresses for the two routers

### Understanding the TCP/IP transport layer

when you write a letter you would add in both the logical and the physical address, e.g. nan, and then her address.

"defines how data is going to be transported across the network"

one way of transferring data is reliable and the other is unreliable 

in an unreliable method you don't check that there is a connection and that the data all got sent and so on 

like passport control, if you check everyone then you will be really slow

UDP = unreliable

TCF = reliable

* session multiplexing - allowing multiple programs to run at once
 
* identification of different applications - port numbers
 
* segmentation - segmenting up the data into the packets so that they fit in the layer two protocol - MTU (Maximum transmitting unit)
	 * ethernet = 1500 bytes
 	* tcp is a header that takes up 20 bytes
 	* ip is a header that takes up 20 bytes
 	* MSS (maximum Segment Size)
 
* flow control - window size for reliability - TCP sliding windows

#### TCP

a handshake will happen

* c:Do you want to talk?
* s:yes I do, do you want to talk?
	* this is now a two way handshake
* c:yes i do

|Client|Server|
|--|--|
|SYN ↘| |
| | ↙ SYN - ACK |
|ACK ↘| |

the conversation has now been established!

* c:get me cisco.com
* s:yeah, sure i will send it over give me a sec
* s:here you go
* c:ah cool, thanks for the page
	* OR
	* c:erm, can i have the page please?

the ip address gets you there then the port number tells you what you want. 

* establish the connection
* conversate
* terminate the connection mutually

|Client|Server|
|--|--|
|FIN↘| |
| | ↙ FIN - ACK |
|ACK ↘| |

dns port 53 this will get the ip address for the domain name that you ask for. Then the information is cached so that next time the information is there. every response has a time to live that is not normally less than a day. 

window size shows how much bytes can be sent each time before and ack. it keeps going up and up until there is a mismatch then you will decrees until you are at the highest 

#### UDP

* can you send me this information please?
* if I get a response then i assume that the data got through all fine
* if i don't get a response then I send for the information again 

200 ok - 301 permanent redirection 

#### ADD IN TCP HEADER HERE

flags are ack, syn, fin and so on

UDP = "absolutely not very much"

DNS is recursice. 
* company DNS
	* Service provider DNS
		* THE BIG MAIN ONES

|ftp|ssh|telnet|http|https|dns|tftp|sntp|
|-|-|-|-|-|-|-|-|
21|22|23|80|443|53|69|161

# HOMEWORK THING TO DO

* lab 5
* lab 6
* lab 7

Challenge lab
* 1
* 2

### The role of a router

routers are required to reach hosts that are not on the same network. "Transmission of data from one network to another"  

a router WILL NOT flood the data if it does not know where to go. a router will instead DROP the packet, then send a message back. 

Routers need this knowledge to know where to send the information.

* to know about a network the router will need to have an address on the network 
* to get it to work you will need to
	* enable the port: no shutdown
	* set an ip address: ip address 10.1.1.1 255.255.255.0

#### Routing table

|10.1.1.1/24|e0
|-|-|
100.172.16.4/24|e1

when you ping from one device to another then the pc will see that the device is not on the same network and so it will send it to the default gateway where the router is located and this will send the data to another network 

when you send information from one IP address to another, it will be put into a frame that contains the MAC address of the pc that send the information and the MAC address of the default gateway. this is because layer two is divide to device connections. 

* ARP ( Address Resolution Protocol )
	* used to get the MAC address when you have an IP address of a device on the network

* send ping
* ip is not on the same network
* gons to default gateway
* whats the mac address?
* uses ARP to get MAC address of default gateway
* data is encapsulated
* sent to router
* router reads ip address
* looks up data in routing table
* finds the correct interface for the network
* encapsulates the data with the mac address of the router port
* doesnt know mac address of destination
* sends arp request to find mac address of the device with the IP address
* encapsulates data with the mac address
* sends information across the next network on the other interface
* other machine gets the ping request

#### Routing

the router learns about directly connected network because it has an ip address with that network. The art of routing is about the routes leaning about indirectly connected networks

##### Static routing

an admin will configure the router on how to reach a network

basically the process of manually adding data to the routing table 

to get to network 12.1.1.10 you need to send the packet out of interface e1 via Router 2


|10.1.1.1/24|e0
|-|-|
100.172.16.4/24|e1
12.1.1.10/24|e1 via Router 2 (11.1.1.2)

this is known as the next hop address

so routers can see all of the networks within a one hop range e.g. via one router

##### dynamic routing

basically the router worming it out by itself. 

routers use a routing protocol to advertise remote networks to other routers. routers will share their routing table in a way. 

###### Distance vector routing

is like a router having a sings post, network x that way 3 hops and so on

will have to wait for help if there is a problem

###### Link state routing

like having a map with a you are here here that have every possible route to every destination 

can easily find a way around a problem like a down router

##### router memory

* flash - OS, kernel 
* nvram - startup config
* RAM - running config
* ROM - POST, bootstrap, ROM monitor

##### Router functions

* Path determination
* packet forwarding 

##### The network was learnt by....

* c = connected
* t = local
* r = RIP
* o = OSPF

gateway of last resort = if you dont know where to send it then send it to this as your final sort

dynamic routing will automatically choose the best path for the data to go, and many things will need to be taken into account:

* bandwidth
	* the data capasity
* delay
	* the time it takes for the data to get through the network
* cost
	* an arbitrary value that is assigned by a network admin to the network that factors in all of the things. 
* hop count
	* THIS IS ALL THAT RIP WILL CARE ABOUT
	* the number of hops that the connection will go through 
* ... and so on


* ospf = cost
* eigrp = delay andn speed
* rip = hops

different protocols will use different things to see what the best route is

the level of trust that you give to different protocols is called the administrative distance basically you would trust a complex protocol more that one that is super simple. 8 bit number. lower is better

* directly connected network
	* rating of 0
* admin done (manuall)
	* rating of 1

protocol|admin distance
|-|-|
direct | 0
static | 1
EIGRP|90
OSPF|110
RIP|120

Cisco decides what the ratings are on Cisco stuff

in the routing table you will only find the best route that the routes knows about

#### LLDP

LLDP (Link Layer Discovery Protocol)

basically a standard version of the CDP

* must be enabled on device and port
* only on physical ports
* can discover one device per port
* detect Linux server

##### ARP (address resolution protocol)

* broadcast: who has this IP
* unicast: I have that IP, here is my mac

### Routing Internet Protocol (Distance vector)

routing by rumour

ARP TTL is 4 hours to default

if something changes then the information that other people hold will be out of date, basically it does not auto magically update when information changes, only when the problem is found. 

### Enabling static routing

this can be done by an admin or by a dynamic routing protocol. 

to route a router must:

* identify destination
* identify routing information

comparing

static

* admin adds in table
* will have to manually update when a change occurs ( many administrative overhead )
* behaviour can be precisely controlled

dynamic

automatically does the thing
...

when to use static routing?
* hub and spoke
* small networks
* quick ad-hoc route

stub network = one way in, one way out

##### static route

```
ip route destination_network destination_mask next_hop 2
```

format

the 2 will tell the trust level to be lower 

```
ip route *.*.*.* 0.0.0.0 172.16.2.2
```

for any data that does not need to go to the local network then go out of 172.16.2.2

### implementing RIPv2

in the big company internet thing you would have to use dynamic routing due to the fact that it is far too complex to actually do manually. dynamic means that the network will automatically work out how the network should change when a problem occurs. but for a small off site part you could static routing as it is smaller. for site A, all data that is not internal you would static to the main network. you would then also have the site statically linked in the main part of the network. 

#### dynamic routing - metric

##### RIP

* distance vector based

rip uses hop count to determine the path, nothing else. its a very basic way to do the determination as it doesn't take into account speed, or so on. 

Equal cost path load balancing - round robin load sharing 
* this means that it will sent one packet will go one way, and one packet another way and so on for all the paths that have the same hop count. by default the max is 4 different paths at the same time. 

rip is legacy and not really used too much on big networks

OSPF goes off the cost of the connection. that is a combination of the bandwidth and the speed of the connections so the packets would not go through the.  

EIGRP - bw, delay, load, reliability
* usually just goes off the bw and delay

Routing protocols will have to:

* discovery of remote networks
* maintaining information
* choosing best path
* ability to wind new best path if one is no longer available

Routing protocols

* Dynamic routing protocols
	* Interior gateway protocols - under a network controlled by one organising body
		* Distance routing vector protocols
			* IGRP - not really used
				* EIGRP - advanced distance vector - modern version
			* RIP - not really used
				* RIPv2 - modern version
		* link state protocols
			* OSPF
			* IS-IS
	* Exterior gateway protocol - across the internet
		* BGP

### Understanding RIP2

* Hop count select the path
* allows load balancing of equal cost paths ( 4 by default )
* does not take into account other parameters like BW and so on
	* because of this RIP takes very simple decisions

|Network A|Router 1|Router 2|Router 3|Network B|
|-|-|-|-|-|
0|1|2|3|4

R1 will send all of the routing table to R2 - Network A is one hop away for you
* A is one hop away from you, via me, so your next hop is (ip)
R2 then sends its route table to R3
* A is two hops away from you, via me, so your next hop is (IP)

This process will carry on until 15 hops and after that then the router will say that it is not able to connect to the server. 

This means that a value of 16 will mean that it is infinite away and so the router will not try to connect. 

so far this is a one way process as it only describes how to get there

due to this the same thing happens in reverse

> This process happens every 30 seconds, this means that every 30 seconds the status of the network is cheeked

you get 3 attempts to prove that you are actually alive and still in the network. 

additionally another things happens so it will take 3 minutes for the connection to be re routed. 

#### RIP v1

route tables are sent on BC - 255.255.255.255

a classfull network protocol
* cannot do VLSM
	* in the routing message you send there is no compartment for the mask so it uses the routers one, so they all need to be the same

#### RIP v2

route tables are sent on unicast - 224.0.0.9

> RIP v2 - route tables - unicast - 224.0.0.9

a classless network protocol
* VLSM is supported

classfull means no vlsm - classless means yes vlsm

#### enable rip v2

```
R1(config)# router protocol
```

at this point you have only enabled RIPv1 and so you are classfull. to change to version 2 you would type:

```
R1(config-router)# version 2
```

this will just allow you to use it, but you need to set the networks that the router is connected to use rip

```
R1(config-router)# network 10.0.0.0
```

This will mean that all networks that are 10.*.*.* that the router is directly connected to will be sent the route tables every 30 seconds like the protocol states. 

how to enable a protocol

* step one: turn on the protocol 
	* R1(config)# router protocol
* stop two: tell the router what networks to use RIP on
	* R1(config-router)# network 10.0.0.0

RIP would have to be enabled on all the routers on the network in order for it to actually work. 

##### how to verify that RIP is working

```
R1# shop ip protocols 
```

[120/1] = [admin value/number of hops]

##### change values

```
router rip
timers basic 60 180 180 240
```

passive interface means that you dont send rip stuff to that part but it is still advertired. this would be used where a router is connected to a network that is stubbed.

```
passive-interface default
```

will set all interfaces as passive


things to clarify from discovery 20
* auto summary 
	* a problem that occers with classfull routing protocols 

Discontinuous subnets - subnets of one big network separated by networks of subnet works of another class of network

this means that there are class B networks that are connected together by some class A networks - the boundary between the routers of different classes will be a classfull network boundary.

in rip auto summary the protocol will change the network address of one of the classes to fit in with the class of the other network when it advertises it. 

a class B network is actually 172.16.5.0/24 and it is connected to a class A network with the address of 10.2.2.0/24. 

| 172.16.5.0/24 | R2 | 10.2.2.0/24 | R1 | 10.3.3.0/24 | R3 | 172.16.6.0/24 |
|-|-|-|-|-|-|-|
B||A||A||B
summ to 172.16.0.0/16||||||summ to 172.16.0.0/16

auto summary will mean that you would say that we are fy18 rather than saying all of our names. 

router 3 will not say 172.16.6.0 it will compress it and say 172.16.0.0. 

because the ip address of the device connected to the router will all have the same begining part of the ip address, then the parts after will change with the subnet mask. due to this the router will just have to advertise the first part of the ip address and then the router will sort out all of the specific stuff when the data gets to it. 

however, this could present a problem as you could then have two ip address that have the same begining on different parts of different networks, this would then lead to the data getting split between the two networks. 

in the example above you can see that both of the networks on the end have the same compressed form of the ip address that is advertised. 

if router 1 needed to ping 172.16.6.5 then it should go over to the right, but as you can see in the compressed form of the ig address, it sees both of the networks as the same address. so it will ping off to the right, and it will do throuth all OK. but then the router will load balance and send the next ping to the left router then the ping will be dropped and because its from the wrong network. this would lead to the ping pattern of:

> !.!.!

without compression then this would not happen. the command "no auto-summary" will ensure that this compression does not happen and therefor this problem will not exist.

### learning the basics of ACL (Access Control List)

an ACL is a way to identify a type of traffic and then do things according to that. can be as simple blocking all packets from simon to sam. can go up to allowing FTP but blocking telnet. can also be used for route summarisation. its a packet by packet check process where it will go through every single packet and check the contents. It will also make the router slower due to the fact that it has to check all of the packets. 

* cisco tool for traffic identification 
* list of permit or deny statements
* based on information that is in the ip packet
* after it has been identified then actions can be taken
* can be used on routers and switches. 

the acl is a sequential list and you have to create all of it

here is an example of how the process will work:

```
void process () {
	packet = getPacketNext();
	if ( packet = telnet ){
		block(packet);
	} elif ( packet = ssh ){
		block(packet);
	} elif ( packet = http ){
		allow(packet);

	 ...etc

	} else {
		block( packet ); // implicit block
	}
	 exit;
}
```

how to do this in IOS:

```
# access-list number
```

if number is 1
* you are configuring a standard ACL
	* this will limit the functionality of the if statements 
	* this can only access the source IP address 
if the number is 100
* you are configuring a extended ACL
	* you can look at
		* sourse address
		* destination address
	* you can filter on protocol 
		* is it IP
		* is it ospf
		* tcp?
			* ssh
			* ftp
			* web
		* udp?
		* and so on... 
	* port number

```
# accesss-list 1 deny 10.1.1.1 wildcardMask
```

the wildcardMask will match if there is a 0 bit. and a 1 means that it ignors it. 

basically where there is a 1 you are able to replace it with a \* to stand for a wild card in the address. 

> ITS THE OPPOSITE OF A SUBNET MASK 

> 0 = must match
> 1 = ignore

```
# accesss-list 1 deny 10.1.1.1 0.0.0.0
```

this will mean that it will block "10.1.1.1" 

at the botttom of the ACL this is automatically defined 

```
access-list 1 deny 0.0.0.0 255.255.255.255
```

this will deny ANY traffic that comes in from any address, also note that the 0.0.0.0 is useless due to the fact that the 255.255.255.255 will ensure that all of the numbers in the address will be ignored. 

due to this if you want to allow all traffic apart from things that you have bloked then you would want to add in a global permit statement for all of the people on the subnet that you want to allow. this would look like:

```
access-list 1 permit 10.1.1.0 0.0.0.255
```

what this would do is that this would allow all of the people that are on the subnet that are trusted, but will still block all of the data from people on other networks. 

it works like an if statement if you have the allow before the block then it would be allowed before it would be blocked. 

if you want to see the list then you would do as you expect:

```
show access-list
```

cisco make this whole process a lot nicer, so instead of doing:

```
access-list 1 deny 10.1.1.1 0.0.0.0
```
you can instead put down:
```
access-list 1 deny host 10.1.1.1
```
in a similar way, you can re write:
```
access-list 1 deny 0.0.0.0 255.255.255.255
```
as:
```
access-list 1 deny any
```

for example if you wanted to allow all of the packets that go through then you would write in:
```
access-list 1 permit any
```

you can set the wildcard mask to any value that you want like you can with subnet mask. 

example: allow 172.30.16.0/24 through to 172.30.31.0/24

```
access-list 1 permit 172.30.16.0 0.0.15.255
```

this command will permit all of the values higher than 172.30.16.0 up to 172.30.31.0. this is because the last four bits of the 16 will be changeable and the first four bits will be locked and in this case the are locked to 16. This then means that the value will range from 16 to 31 and so all of those will be allowed. 

|172.30.|16|.0
|-|-|-|
|0.0.|15|255|
|changes|0000*1111*||
|stays|00010000||
||**0001**0000|16|
||...||
||**0001**1111|31|

there are a few shortcuts that cisco allow you to do:
* host will just do one ip 
* any will do anything

### ACP

* standard
	* only source address
* extended
	* source IP
	* destination IP
	* protocols
	* applications

you can also then give names

standard:
* 1-99 and 1300-1999
extended
* 100-199 and 2000-2699

these numbers are the acl profile numbers. this means that you could create many different profiles that all have different rules and then swap out the number of the profile that you are using. 

when you are using a standard ACL and dont add in the wildcard mask the router will add one in for you and this will be 0.0.0.0 which basically means that it will only do the address that you put in and not anything else. on most cases this will means that the address that you use will not work because you would put in a network address as it ends in 0so

when you want to show an acl you must specify the name of the acl that you want to edit.

### NAT (network address translation)

you need an ip address that is allowed, both for you as a device and the router that you are connecting through. the reason that home routers will just work is because the have a config. when you plug it in for the first time it asks for an ip address from the ISP routers, this is DHCP (dynamic host configuration protocol). first step is to get and address that comes from your service provider using dhcp. you can manually set the ip address. 

a public address is accessible/allowed from the internet, a private one is not. 

when you connect to your router you will make a dhcp request that will give you an ip address. 

devices on your private network need to be able to access the internet, but they cannot do that with the private address that they have. 

NAT will enable the devices on your private network to be able to talk to devices on the internet even though they have a private address. 

|Inside local address |->| inside global address. |
|-|-|-|
|static NAT|one to one process|old
192.168.1.10 (pc) |-> direct assignment | 81.113.214.6(unique address)|
192.168.1.11 (phone) |-> direct assignment | 81.113.214.7(unique address)|
192.168.1.12 (tablet) |-> direct assignment | 81.113.214.8(unique address)
dynamic NAT|many to many||
192.168.1.10 (pc) |-> taken from pool | 81.113.214.6(unique address)
192.168.1.11 (phone) |-> taken from pool | 81.113.214.7(unique address)
192.168.1.10 (tablet) |-> taken from pool | 81.113.214.6( old address from device that is no longer talking )
PAT | many to one | used now
192.168.1.11 (pc) |-> uses a port number (the PID) | 81.113.214.4:6349(router address)
192.168.1.11 (phone) |-> uses a port number (the PID) | 81.113.214.4:3043(router address)
192.168.1.11 (tablet) |-> uses a port number (the PID) | 81.113.214.4:8934(router address)

static NAT | 1:1
|-|-|
dynamic NAT | many:many
PAT | many:1

the outside global address is the destination ip. 

the NAT table is used to translate the local to the global ip address and also the port. 

#### static NAT

for a few devices is ok, but if you ask for 2000 public ip addresses then you cannot. 

#### dynamic NAT

i have 2000 people who want to speak to the internet, but only 100 who would speak at the same time. we create a pool of 100 addresses that then a router would then give to a device when it is going to the internet, then when the conversation ends then the address is returned into the pool for another device to take when it needs to communicate with the internet. 

when more that 100 devices need to connect to the internet then there is a problem

#### PAT (port address translation)

all the devices in your network will share the address of the router but the will use a unique port number that will then be used to handle what device is speaking. 

the pid of the networking process will go to be the outbound port number, this is then what the router will use to differentiate the inbound connections and then send it onto the correct device in the network. 

but if two of the devices select the same port, so they have the same networking pid, then the router will handle a change and deals with it all separately. 

the port selection is handled by the devices when they are going outbound, but if there is a clash then the router will handle the change seamlessly.   

Demarcation - is the point at where responsibility of the network changes - for example the cable in your wall is where the ISP will handle everything. 

fibre to the curb is where the fibre goes to the green box and then copper to the home. but fibre to the house is actually fibre to your house. 

2g covers 85% of the populated earth. 

when you set ip on a router you will need to also set the route. or you can do "ip address dhcp"

when setting NAT you have to tell the router the IP address of the ports.

on the outside port you set the ip and type "ip nat outside"

on the inside port you set the ip and type "ip nat outside"

you must define what is inside add what is outside. then you do 

```
ip nat inside source static insideIP outsideIP
```

to see all the nat:

```
show ip nat translations 
```

clear ip nat translation *

```
show ip nat translations
```
```
show ip nat statistics - what ports are set up what way - THEY MAY BE THE WRONG WAY AROUND
```
```
show access-list
```

```
debug ip nat
```
this is basically verbose mode. 

NEVER EVER TYPE "debug all"

Floating static route is when the best route that you have is not there so the next one down will float into the place. 

## Module 3 - Summary challenge

just a lab that we have done

## Module 4 - Building a Medium sized network

### VLANs and trunking

this is still true of bigger networks, they will just have more of them. its just that we are covering it now. 

VLAN is virtually segmenting a broadcast domain. in this room (bc domain) the boundary if the 4 walls, the process of the VLAN would be left half vs right half. would be bad for rob to teach one side something and then have mike teach the other half something else. there would be too much going on. to solve this you would put a wall in the room. VLAN is segmenting switches or a series of switches. 

|port 1|port 2|port 3|port 4|port 5|port 6|port 7|port 8
|-|-|-|-|-|-|-|-|
sales pc|sales printer|sales server|sales pc|HR|HR|HR|HR

the sales people are not interested in the HR stuff and vice versa. this would mean that only half of the data on the network is useless, so to cut that down we could segment it so that the sales and the HR people will not hear all of the bc of the other people that they do not need to hear. we would literally split the switch in half so that it acts as two switches with two MAC tables and so on. so the switch would look like this:

|port 1|port 2|port 3|port 4|\||port 5|port 6|port 7|port 8
|-|-|-|-|-|-|-|-|-|
sales pc|sales printer|sales server|sales pc|\||HR|HR|HR|HR
sales vlan||||||||HR vlan

![image of the vlan](https://wiki.mikrotik.com/images/9/9a/Image12005.gif)

in this image you can see that we have three different vlans, each is a different network, with different network addresses, different bc domains and so on. 

you can configure it port by port so they dont have to be next to each other. so if a bc comes in on a certain vlan interface then it will come out of the interfaces with the same vlan. 

you can do this over multiple switch devices and still have the same vlans. to do this you will need to connect up the switches with a cable. to do this you would normally use the specific uplink ports, but you can actually use any port on the device. 

* normal port = access port
	* can only be accessed by one vlan

normal ports can only be associated to one vlan so the cable that is connected to the other swith will have to be a trunk port. a trunk port can be associated with many vlans. 

when a bc comes into a port the switch will send the bc out of the same ports in the vlan AND the trunk port. by default the bc will all go through the trunk port and the switch will have no knowledge of what vlans the other switch has, but by a process of vlan pruning you can set what vlans can be sent through a trunk port. 

ethrnet frame:

|DA|SA|Type|Data|fcs|
|-|-|-|-|-|

if you look you will see that there is no place for the storage of the vlan that the data is part of when it goes through the trunk port. in the old days you would encapsulate it again with additional information about what the vlan ID is this was only supported by cisco, but NOT USED ANY MORE. instead of encapsulating the data an extra field is inserted in the frame between the SA and the Type, and this is called the vlan tag

this would turn 

|DA|SA|Type|Data|fcs|
|-|-|-|-|-|

into this. 

|DA|SA|vlan tag|Type|Data|fcs|
|-|-|-|-|-|-|

what the vlan tag is made up of

|type|priority|flag|vlanID|
|-|-|-|-|

the trunk tagging is an industry standard and can be thought of as a sub-category of the Ethernet frame standard and is called IEEE 802.1q but is commonly known as "dot1q". the vlan tag is 4 bytes in size so its 32 bits in size. BUT NOT all of those bits are for the vlan tag and thats far too much so only 12 bits are for the number of the vlan tag. This means that there can be 2^12 vlans between connected switches. THE NORMAL VLAN RANGE IS UP TO 1000, but the extended range 4094. there are about 5 reserved vlan addresses. 

the tag is only added between the switches, it is read by the switch, removed and then sent out

a frame bigger than 1518 bytes is called a giant (frame). but because the tagged frame is just over the limit its called a baby giant frame. 

there are 3 types of switches when vlans are used:

![image of network design](http://ncs.fnal.gov/nvs/documents/architecture/Hierarchical-Topology.png)

* access
	* what people are connected to 
	* end points are here
* distribution
	* shares the load between switches
	* only connects to switches
	* where the access layer aggregates (meets)
* core
	* this will connect all of the switches and actually connect the network together
	* where the data centre lies so that everyone can access it
	* high performing switch
		* nexus in the core 
		* others are catalyst

access ports - clients plug in

trunk ports - switches plug in 

if you dont design it well:
* large broadcast domains
* security vunerability
 and so on.....

how to do it in IOS

```
# conf t
(config)# vlan 2
(config-vlan)# name Sales
```

> when you create any vlan you create a special file called vlan.dat, this is saved to flash with the OS rather than to the vram. THIS IS NOT SAVED IN THE RUNNING CONFIG 

```
show vlan 
```

```
show vlan id *number*
```

the number will show you the just the information for the certain vlan number. 

```
conf t
int e 0/3
switchport mode access
switchport access vlan 2
```

> when you see switchport think layer two. 


```
conf t
int e 0/3
switchport mode trunk
switchport trunk native vlan 99 	// this is the backup if the vlan fails due to being done configured on one side
```

#### VLAN design configuration

* the maximum number of VLANs is switch dependant
	* based on the number of ports that the switch has
* VLAN 1 is the factory-default Ethernet VLAN
	* the management VLAN will be in the same one by default and you should change that
	* most people change the management VLAN to be 99
* a use-dedicated VLAN is for the Cisco switch management IP address
* keep management traffic in a separate VLAN 
* change the native VLAN to something other that VLAN 1

DTP - dynamic trunking protocol
* two ports work out if they are trunk or access.

if you have a loop of switchs, this could be good as you will then have two different paths to get to where you want to go. BUT it will create a broadcast storm. This is where a BC will keep looping around the switches until the bw is all taken up and nothing that you want to get in actually can. this is stopped by the spanning tree protocol. 

#### routing between VLANs

##### one router and interface between VLANs

to communicate between the VLANs you will need to have a router in order to communicate between them. if there are 3 VLANs then the router will need to have 3 ports so that it can access all of the different networks and have a network address for each of them. This is one way for doing it, but its a really bad way to do it. 

##### router connected to the trunk port

this is where you connect the router to the trunk port and read the traffic for all the VLANs. but you can only assign one ip address to one interface. you can then take the interface on the router like Fa0/0 and then create virtual interfaces or sub ports. you can then assign the one physical port to act as and work with multiple network that have different addresses. this is know as router on a stick due to how the network diagram looks.  

```
conf t
int f0/0.1
```
the ".1" in this case will will the virtual interface into existence and then set it. you will set that number to be the VLAN number because that makes sense. 
```
encapsulation dot1q 1 	// setting the encapsulation for the extra frame section that is added
ip address 10.1.1.1 255.255.255.0 	// setting the ip address for the certain VLAN
int f0/0.2 	// creating a second Vinterface
encapsulation dot1q 2
ip address 10.1.2.1 255.255.255.0
```

##### level 3 switch

this is where you have a router and a switch in the same box. this means that all of the data goes through a system bus rather than a port and so you will get a higher data throughput. 

the management vlan is the vlan that the trunk port is on. 

> the management VLAN is the one that is used just for communicating between switches with information that they want to share with each other. This will be default be vlan 1 the same as all of the normal traffic on the network. for security reasons you should change the management VLAN so that it cannot be accesses easily. 

### using a cisco IOS device as a DHCP server

Dynamic Host Configuration Protocol

used to get ip address for devices on a network.

manual ip addressing:
* time consuming
* prone to errors
* unfavorable to employee mobility
 
a dhcp ip address assignment in a segmented LAN is as follows:
* (re)assigned on a per VLAN basis. 

|Host||server|
|-|-|-|
discover (broadcast)| -> ||
|| <- | offer(unicast) |
request (broadcast) | -> |
|| <- | acknowledge(unicast) |

Discover, Offer, Request, Acknowledge = DORA

#### Discover

bc sent out to whole network

#### Offer

unicast through unspecified address

#### Request

where you accept the 

#### Acknowledge

the DHCP will send your device the following:
* IP address
* Default gateway
* DNS server
* Domain name
* and maybe some more

server will have a pool of offer able addresses that it can assign to devices on the network. the pool is also called the scope. if you have a few devices in another network to the main dhcp server then all the requests will be dropped. to fix this you would use DHCP relay. 

to do this on a router you would do:

```
(config)# int fa0
(config-it)# ip helper 10.1.1.1 	// the ip address for the dhcp server
```

the router will then send a message to the dhcp server with the network ID so that the dhcp server will know what type of address to return to the device. basically the whole thing will happen in the background so that the host device will never know what happened. 

relaying over the networks will take too long and so on... to solve this all we do is make the router able to be a dhcp server in its own right. 

```
(config)# ip dhcp excluded-address 10.1.50.1 10.1.50.50 // this will prevent any addresses in the range of these from being assigned to a device on the network. 
(config)# ip dhcp pool guests
(dhcp-config)# network 10.1.50.0 /24
(dhcp-config)# default-router 10.1.50.1 	// the default gateway
(dhcp-config)# dns-server 10.1.50.1
(dhcp-config)# domain-name example.com 	// used for active directory 
(dhcp-config)# lease 0 12 	// 0 days, 12 hours
(dhcp-config)# exit
```

### Network device management and security

networks are prone to attacks:
* remote access
* local access
* physical
* theft
* environmental
* electrical
* maintain once 

The first thing that you NEED to do is secure enable mode. to set the plaintext password you will do:
```
enable password Cisco123
```
this will be visible when you look at the config files

but to set an encrypted password WHICH YOU SHOULD DO, you would type:
```
enable secret sanfran
```
this will be hashed and not able to see what the password actually is. 

when you set a secret password it will disable the plaintext password. 

if you want to encrypt the passwords again then run:

```
service password encryption 
```
but this is not too secure as it uses an old system. 

we just protected enable mode, here is how to protect the user mode. 

by default there is no password and so you should add one. 

```
line console 0 	// this will only work for the local connection, not for VTY
password Cisco123
login 	// when to request the password
```
the console port is what you are protecting 

login can be login local, AAA server authentication, authoritarian, accounting where the creds are stored so they can be pointed to. 

to set a timeout you will type:
```
exec-timeout 5
```

this will mean that if you dont send a message in 5 minutes then the connection will cut. 

to secure the vty lines then you would do:
```
line tvy 0 15 	// the range that you want to set the password for. 
login
password Cisco
```
vty is disabled until a password is actually set as a security measure.                                       

telnet is a clear text based protocol. dont do this as you know. Instead use SSH due to the fact that it is not in plaintext. SSH it not trend on by default. 

```
(config)# hostname SwitchX
(config)# ip domain-name cisco.com
(config)# username user1 secret Cisco12 	// creates a user on the switch that the ssh will apply to, also a fallback for AAA. 
(config)# crypto key generate rsa modulus 1024 	// when the key is generated the hostname and the domain name will be used 
the name for the keys will be: SwitchX.cisco.com
% The key modulus size will is 1024 bits
% Generating 1024 bit RSA keys, keys will be non-exportable...
[OK] (elapsed time was 1 seconds)
(config)# line vty 0 15
(config-line)# login local 		// use the local account on the device (the one we just set up ssh for)
(config-line)# transport intput ssh 	// allow ssh as an inbound transport (enables only ssh but you can do "ssh telnet" for both )
(config-line)# exit
(config)# ip ssh version 2 	// sets the version, 1 has issues so use 2 when you can. 
```

YOU MUST CHANGE the hostname on the device due to the fact that otherwise the key will be insecure. 

AAA uses protocol radius or tacacs. 


## Module 5 - Network device management and security 

### implementing device hardening

unsecured ports on switches. shutdown the ports that you done use on the switch. 

in ios there is an interface range command. this will allow you to put a configuration on a grout of ports. this will only work on ethernet ports. 

```
(config)# interface range FastEthernet0/1 - 2 		// this is a range of ports set
(config-if-range)# switchport access vlan 999
(config-if-range)# shutdown
```
this will set the config for all of the ports but cannot be used for anything specific like ip addresses. 

for ports that you dont use you will shut then down AS WELL AS putting them in an unused VLAN so that if they come up you they wont have any information with you 

default vlan is vlan 1 that is set by default and that all traffic will go through if you don't change it. 

The native vlan is the one that is used by the trunk cables and this will have no tag value in the Ethernet frame. this is used by ip phones when there is a pc connected to the internet through the phone, the phone will understand the vlan and the tag but the pc will not, due to this the vlan tag cannot be used to communicate to the pc. but the tag is dealt with by the phone. 

#### port security

mainly this will stop mac layer flooding attack. this is a passive attack that can allow people to see things that they can not normally see. 

mac layer flooding works on the flooding layer of the switch. 

in port 1 is in the CEO, in port 3 is the financial director, in port 2 is someone else... person X

CEO mac address 1, FD 2, person X 4.

person X sends something to the switch and so the mac table now knows that the mac address of 4 is in port 2. then they use macchanger to set their mac address to 5 and in the mac table there is the link to address 5 and port 2. this keeps happening over and over again going filling up all of the table with different mac addresses that will all be sent to them. so when a packet goes in to the switch for the CEO with the mac address of 1 then the switch will see that the mac table is full and so the switch cannot learn the address and does not know where to send it. this will then act as an unknown unicast and will be flooded to all devices on the network. 

* fill the mac address table with random addresses
* the switch cannot store where the data needs to go as its table is full
* the incoming packet will then be flooded and seen by the attacker

to fix this you would make a vlan between these people and therefor they are in different networks. but that will not fully work

if you think about it when there is an access switch there can only be one mac address for each port as that represents only one user. the admin will then set port security. 

port security will then:
* allow at max one mac address per port
* but if there is a change to the mac address then the port can be shutdown. 

there are 3 different ways that the port can react

protect
* drops unauthorised but doesn't tell you 
restrict
* drops but sends syslog
shutdown
* shut-down the port

```
(config)# interface FastEthernet0/5
(config-if)# switchport mode access 		// must statically set the port mode
(config-if)# switchport port-security 	// switchport means layer two
(config-if)# switchport port-security maximum 1 	// port-security will auto set up the max of 1 address and so on
(config-if)# switchport port-security mac-address sticky 	// this would copy the secure mac addresses into running config in nvram
(config-if)# switchport port-security mac-address violation shutdown 	// here is the protected or restricted thing
```
the MAC address table is stored in the RAM, and that would delete the secure port assignment if it was power cycled. 

if you have a service on your device that you dont need or use then disable it so that it cant be exploited. 

* disable http is a good idea. 
* disable CDP where it is not needed so that other devices cannot read the information
	* this can be done globally or on a specific port. 

```
no cdp run
no ip http server
```

### NTP (Network Time Protocol)

this will share time within a network to any devices that request it. it will allow all devices to sync their times. 

a cisco router can be an NTP source. to set this up do:

```
ntp server ipAddress
```

this will sync the clock on the router with that of the server. 

to set up a server you wold assign the ip address to the one of the device. 

```
ntp server 10.1.1.1
```

stratum level - the steps taken from the original clock and therefor the time inaccuracy.  max is 15, so 16 is not syncd

to show ntp associations just do:

```
show ntp associations
```

to see the status of ntp run:

```
show ntp status
```

### configuring syslog 

syslog is a protocol that 

the format of syslogs is:

```
seq no:timestamp: %facility-severity-MNEMONIC:description
```

severity = 0 REALLY BAD, 7 debug

|level|explanation|
|-|-|
emergency| system is unusable
critical| immediate action needed
error| critical condition
warning| error condition
notification| normal but significant condition
informational| informational message
debugging| debugging information

Eliminate, A, Crisis, Even, When, No one, Is, Dead

the syslog messages can be sent to any place but by default they are sent to the console port. the logging buffer is there to keep a small about of buffer for the syslog information. or you could send it to the syslog server where it is stored permanently. we can also send them to the vty lines for when you are remote accessing the system.  

you can nest the sessions by going into one device and then use that to create another session to a device that only that device could access. 

when you ssh to a device you can run "debug ip rip" now the router will display all the information about rip. but this will be displayed to the console port NOT the vty so you will need to change this. to do this run:

```
# terminal monitor 
```

to switch it off you would do:

```
terminal no monitor
```
this is slightly different to normal but its still the same thing as what you would expect.

to send syslog to a server you would do:

```
logging 10.1.10.100
logging trap informational 	// this will send only information from severity level 1 to 6
```

### managing Cisco devices 

In ROM we have:
* bootstrap
	* how to start up the device and run the kernel and OS
	* part of this will call the POST
* POST
	* power on self test
	* will test all of the hardware to ensures that it is actually working 
* ROM monitor
	* a backup operating system in case the main OS fails so that there is basic functions. 
	* basically a recovery mode that can do only basic functions
	* used if you wanted to upgrade the OS then you would download it to your server and then to the router, but if the new version didn't work then it would boot to ROM monitor so that the device will still work.  

a router can boot from:
* flash
* usb
* server

configuration register = 0x2102
* the least significant four bits (second 2) are known as the boot field
* case boot field = 0x0
	* load ROM monitor
* 0x1
	* boot normally
* 0x2 - 0xf // normal operation 
	* check for boot commands then boot normally

the other bits will change basic dip switch functions

```
show file systems
```

you can backup and load your current image. ALWAYS BACKUP YOUR OS

device type|image type|file format m~ram z~compresses|digital sighed image|version|extension
|-|-|-|-|-|-|-|

how to back up OS:
* verify connection to server
	* ping
* check that there is enough space on the server
	* show flash:
* copy the file over
	* copy flash0: tftp:

how to upgrade:
* download the new image to server
* make sure router can connect to server
* check that you have enough space
* copy the file over
* set the boot command to the new os
* save config
* reload the device

config from:
* nvram
* terminal
* tftp server

### password recovery

you can only do this when you are plugged into the device physically by the console port. 

> quote "the welcome to slough sign, what has it been stolen?"

* switch off the router
* switch on the router and press control+break to enter ROM monitor mode
* when in ROMmon mode check the configuration register

```
rommon 1> confreg 0x2142
```

setting bit six to 1 will ignore the NVRAM which contains the passwords

2142 means that bit 6 will be set to 1. 

> 2101 is default

when you do this all the interfaces will be down due to the fact that the blank configuration merged and that had all interfaces down. you will also need to reset the bits back to the default value so that it will load the config like normal. 

# do the licencing homework stuff

## Module 6 - Summary challenge

## Module 7 - Introducing IPV6

### VLSM (variable length subnet mask)

efficient use of address space, the idea came about because we ran out of IP addresses. if you had subnets with 100 hosts and some with only 2 then it would be wasteful to ure 9 bits for the subnets. 

you have been given the address of 150.1.0.0/16 and you have 3 networks of 250 hosts and then 2 with only 20 hosts. you would set the subnet mask then you could have 256 hosts per notwork, this is wastefull for the networks with only 20 hosts. having /24 everywhere would be a HUGE waste and this is why we use VLSM. for the networks with only 20 users you would only need 5 bits for the subnet ro that would be a /27. then for the routers where there are only 2 hosts you would only need 2 hosts and so that would be a /30. 

example

ip address of 200.1.1.0/24

we will need:
* 6 networks with 30 hosts per network
* 6 network with 2 hosts per networks 
	* this is for the routers that get to the branch offices

6 branch offices with 30 users each, 6 connections for users. 

this totals to 12 networks, so you need to borrow 4 bits, one for each network. this will leave 4 bits for the hosts. 

basically you will take an unused network that you have subnetted and then break that down to more networks. basically you will then have many different slash notations in the same network. 

### ipv6

this will just be an introduction for the moment. 

we have exhausted the ip address space for ipv4 and so we need a new way to actually connect everything that we need. ipv4 was made in the mid 1950s. 

several mechanisms were made to help with this:
* CIDR
* VLSM
* NAT
	* breaks the end to end model of ip
	* breaks security
	* some things are not nat friendly
	* a lot of load on the router
* DHCP

move to ipv6, its not new because it has been around for a long time. 

the benefits:
* larger address space
* simpler header
* security and mobility
* transition richness

ipv4 is 32 bits long while ipv6 is 128 bits long

RFC (request for comments) ~ where people suggest how to make it easier to actually use

and ipv6 address is represented by a 16 bit hex number. leading zeros are optional. additionally, a range that it just zeros it can be reduced to just :: but only once in the address

2001:0db8:010f:0001:0000:0000:0000:0acd - main example

2001:db8:10f:1:0:0:0:acd - suppressing leading zero

2001:db8:10f:1::acd - suppressing consecutive zero 

ipv4 loopback - 127.0.0.1

ipv6 loopback - ::1

ipv4 unspecified - 0.0.0.0

ipv6 unspecified - ::

ipv6 address types:
* unicast
* multicast
	* used for dhcp by using a reserved address
	* only ipv6dhcp servers listen for that specific request
* anycast
	* instead of one to anybody, you go to the nearest device
* NO BROADCAST

you cat have ipv6 addresses in different scopes
* global (global unicast address)
	* like public addresses
* site (unique local unicast address)
	* like private addresses
* link local (Link local unicast addresses)
	* allows device to communicate with each other 

ipv6 is 128 bit
* 64 bit for network
* 64 bits for device
* built in 16 bits for JUST subnetting 
THIS IS FIXED

global unicast address is always 2000::/3 = 001

|002|global routing prefix|SLA|interface ID|
|-|-|-|-|

fc00::/7 to identify a local unicast address = 1111 110

link local address always begin fe80::/10 = 1111 1110 10

then the other 54 bits for the network ID will be zero

this will be acquired auto magically 

because the interface section is soo big you can fit in a mac address but its still not big enough, so in-between the OEM and the device section on the mac address we put in FF FE to make it the correct size. ONLY FOR LINK LOCAL ADDRESSES. this is called EUI-64 bit interface ID

when you change the 7th bit of the host ID to a one it will tell that you have changed the value and that it is only locally unique (local address) rather than globally unique (public address)

you can set the address manually, or automatically or...:

stateless auto configuration
* this is done automatically by the device
* when you set a router with an ipv6 address, it will send out a new icmp message called the router advertisement. this will send out the networkID, the default route and to on 
* the host device will then take the advertised networkID and add in its padded mac address to give it a unique and reachable ID all over the internet. this removes the need for NAT. 
* arp is no longer needed, due to this because the neighbour's all know each other
stateful auto configuration
* you used a dhcp v6 server to assign the ip addresses. 

neighbour solicitation and advertisment

FF02::1 is the all nodes multicast address (basically a broadcast)

source address is :: because it doesnt have an address, destination is ff02::2 as that goes to all devices. 

to set the router to automatically get the ipv6 address, you would do

```
ipv6 address autoconfig
```

```
ipv6 unicast-routing 	// this will make it actually act like a router rather then a generic devcice
```
You must remember this command otherwise many bad things will happen. 

### configuring ipv6 static routes

they have tried to keep it the same as the ipv4 static routes. 

RFC - request for comment - basically the way that a standard is defined by many suggested.

you now have many different protocols for routing with an ipv6 network
* RIPng - 2080
* OSPFv3 - 2740
* MP-BGP4 - 2545/4760
* EIGRP for IPV6 - proprietary

for static routing you will use basically the same commands, in the same format just ipv6

```
ipv6 route networkThatYouWantToReach nextHop
```

for a branch router you would do:
```
ipv6 route ::/0 nextHop
```
this is because you would send any data that you have to the HQ router due to the fact that it is a stub network. 

to verify that you have the static route:
```
show ipv6 route static
```

> THATS IT, ALL OF ICND 1!!!!!! whoo

access-
* list
	* applies to list
* class
	* vty lines
* group
	* in going and outgoing


# ICND 2 

lets go and do this again, hopefully better this time. But apparently this one is easier so there is no problem. 

## Implementing scalable medium sized networks

> "you will be tested in the exam" - Rob

you set up and use vlans so that you have less broadcasts going around and more broadcast domains to reduce the traffic that is on the network. the end devices will have to process the information that they get and so if you reduce the broadcasts then you will save processing time on the devices. we used to use routers for all of the broadcast domain, but that was expensive, so VLANs were used instead. but you still need a router to connect data and information between the VLANs. you would want to have a layer 3 switch as you will have high data throughput and will only have to manage one box. 

* create a vlan
* then assign the port to vlan otherwise it might break

```
switchport trunk allowed vlan 2 - 4
```
this command will only allow VLANs 2 to 4 to pass through the cable.  

in a switch thing with 3 clans, then you would have 4 broadcast domains due to the fact that VLAN 1 is always there. 

The native VLAN will be used for when data is not tagged for a VLAN. 

an access port can only access one vlan, apart from if you have an ip phone, then the phone and the connected PC will be in different vlans. this will do layer 2 and 3 prioritisation. 

* Native VLAN mismatch
* management VLAN mismatch
* vlan access mismatch on each side

.

* the native is for untagged traffic
* management is for management traffic like CDP messages. 

### troubleshooting VLAN connectivity

```
conf t
vlan 3
name telephone
switchport voice vlan 3
```
some useful commands
```
show interface status
shof interface trunk
```

the default mode for all ports on switches is that they have DTP turned on. (Dynamic Trunking Protocol). this negotiates the trunking state with the other end of the link. 

> auto is a passive state

due to the fact that the ports will be in a passive state (auto) by default, and so a trunk will not be made and it will be in access mode not trunk. this will then default to the native VLAN. 

due to this fact, all broadcasts will then be sent to one device and so there may be a security problem. 

#### VTP (Vlan Trunking Protocol)

a Cisco proprietary protocol. 

this will advertise the VLAN.dat to all of the other switches. 

if you have 100 vlans then you would need to create the VLANS on all of the switches and that will take a lot of work. so you will just create the vlans on one switch and then VTP will send out all of the data to the other switches. the switch that this comes from is the VTP server. Whenever you change the VLAN.dat on the VTP server the revision number will go up by one, this will then let devices know if they are out of date through the advertising. for this to work, all of the devices will have to be in the same domain. This will send information through TRUNK LINKS only. you can then get it to do pruning by setting it up on the individual device, this is callid VTP pruning. VTP is commonly banned due to the fact that it generates traffic and can mean that a rouge vlan.dat can propagate through a network. 

* server mode
	* the default
	* creates and deletes VLANS
* client mode
	* can only read the stuff
* transparent mode
	* will not take changes, but will forward them

> if you add in a switch to a network, then you should set it to transparent so that it will not mess up the network. 

some useful commands. 

```
vtp domain name
vtp mode transparent
vtp password
show vtp status
```

### Building redundant switched topologies

#### Spanning tree protocol / algorithm (STP or STA)

if you wanted to have redundancy in a layer 2 network then you would have to have two or more routes from one host to another. if you only had one connection between the devices then so many things could go wrong that would bring down the network. But, if you have switches that form a loop then you could create a switch storm when an unknown broadcast goes into one of the switches. 

spanning tree will discover the looping in a network and it will then logically block some interfaces on other or its device. Anything that comes through that port, apart from one thing will be discarded, and nothing can be sent out of the port. 

you want to eliminate single points of failure. but this causes 3 specific problems:
* broadcast storms
	* when a frame gets flooded out of each switch it will keep going in a loop over and over again taking up network bandwidth. 
* multiple frame copies
	* if a frame in the network has the correct mac address then the packet could go one way through the network and get there, but then the same frame could go through a slower part of the network and get there later. on a router this would mean that it could drop the packet as the router will see that there is a problem with the tcp/ip numbers. 
	* basically the same frame gets to its destination twice as two different routes will get there at different times. 
* MAC table instability 
	* when due to the loop a switch will associate the incorrect port to a host device. 

Spanning tree will stop all of these problems from happening. the way that spanning tree works means that you have basically disconnected the two switches but in a way that can quickly that can come back up. 

> IEEE 802.1D

spanning tree will do the following things:
* elect a route bridge
* elects a route port for each non-root switch
* elects a designated port for each segment
* ports transition to forwarding or blocking state. 

spanning tree will work in a broadcast domain of a layer two network. 

* elect a route bridge
	* you will need to have a start, reference point. that switch is called the route bridge. 
	* there is only ever ONE in the spanning tree. 
	* everything is calculated from the perspective of that route bridge. 
	* the switches will do this auto matically work this out in the background, but they dont always make a good decision when deciding. 
		* normally you would have to make the route bridge selection. 
* elects a route port for each non-root switch
	* this is used so that non-root switches can send stuff to the route bridge. 
* elects a designated port for each segment
	* TBE
	* if the interface is not a route port or a designated port then it is blocked. 
* ports transition to forwarding or blocking state. 

The route bridge has the lowest bridge ID within the broadcast domain. 

#### Elects a route bridge

The bridge ID is made of the bridge priority and a MAC address. 

This bridge priority can be a range between 0 and 65535, due to this the default value would be 32768 as that is half of the range. 

The MAC is the base Ethernet address, this is the address of the whole switch rather than that of a specific port. the address of the ports is made from the MAC address, plus the number of the port. e.g. Fa0/1 will have a MAC address of the base MAC +1 and then Fa0/2 will have a MAC address of the base MAC +2 and so on...

| Bridge Priority | MAC address |
|-|-|
Range: 0-65536, Default: 32768 | Unique for every device
16 bits of value |

```
connections + (MAC address)
A(1) -> C, B
B(2) -> A, C, D
C(3) -> A, B, D
D(4) -> B, C

ID:
A - 327681  
B - 327682  
C - 327683  
D - 327684  
```
In this example switch A would be the route with due to the fact that it has the lowest ID out of all the devices on the network. 

The way that these switches send the ID that they have is through the use of Bridge Protocol Data Units (BPDU). the switches exchange the ID numbers by the BPDU's 

BPDU contents:
* Bridge ID
* Root ID

the Root ID is the lowest value that the switch knows about. At the start the switch only knows that it has the lowest value so they are the same. 

all of this is made into a table and compared so that the switch can see if anyone else has a lower number on the network. 

For example, B would see that A has a lower ID and so the root ID that will be sent out is that from A. 

as you know, the time that it will take for all of the ID's to get to the smallest value will vary depending on the size of the network. Due to this you will have a MAX age timer for the protocol. 

the default for the Max age is 20 seconds.

when you start up all of the switches then the BPDU's would take up all the bandwidth on the network and it would become unusable. to solve this, all of the ports will be put into a blocked state so that they will not forward all of the information around. BUT the exception to the blocking of the ports is that BPDU's are allowed and are read by the switch.  

#### elect a route port

the route port is the port that is used to communicate to the root switch about any changes to the network topology. 

The root port is the port that has the lowest route cost to the root switch. 

the cost is generated from the speed of the interfaces. 

```
This is the 1998 standard
RPC value
10Mbps link - cost = 100
100mbps link - cost = 19
1Gi - cost = 4
10Gi - cost = 2
```

| | A | B | C | D |
|-|-|-|-|-|
| A |  | Gi | Gi| |
| B | Gi |  | Gi | Gi |
| C | Gi | Gi | | Gi |
| D | | Gi | Gi |  |

 The hello interval means that every 2 seconds the root switch will send out the RPC. 

 When switch B gets the hello from A it will get data on the path cost to A, and that will be 4 due to the fact that the Gi connection is worth 4. Then B will forward the BPDU with the RPC to switch D, but it will then add on 4 to the RPC due to the fact that it goes off on a Gi connection. 

 Basically the cost to get to the route switch it sent through the network and then all of the switches will select the lowest value that they get to work out the lowest cost to get to the root switch. 

 This then means that all switches will get ONE port on them that has access to the path that has the lowest cost. 

 BUT if a switch will get multiple BPDU's that say the same lowest score, then the switch will select the port that has the lowest sender ID. Basically the connected switch that has the lowest MAC address value. 

#### elect a designated port for each segment

the way that you chose the designated port is that you choose the port that has the lowest route cost to the root switch. So basically a segment is a connection between two switches, so there are two options to select from. You will then choose the port that is closest to the root switch in terms of the cost for the path. 

> DESIGNATED PORTS ARE NEVER BLOCKED

if two ports have the same value then then device with the lowest bridge ID will be chosen. 

Designated ports are assigned to propagate the BPDU's onto that segment

if a non-root switch doesn't hear from the root switch for 21 seconds then the process will start again and that switch that detected the dead root switch will start sending out its own BPDU's.  

when a blocked port becomes a root port then it will take 30 seconds. 

the default that is used on Cisco devices is IEEE 802.1D think (D)efault for cisco devices. 

IEEE 802.1w = RSPT (Raping spanning tree) - newer version (Wapid spanning tree) will only take 2 - 5 seconds. 

the reason it takes time to transition between the states is because the port has to go through 2 stages:
* Listning
* Learning

and these processes are set to a timer of 15 seconds. 

IEEE 802.1D

Normal spanning tree is not really used in Cisco stuff, instead you would have one spanning tree per VLAN. but this would mean that you would then have many instances of other spanning tree protocol on the same router for the same network and this will mean that.  

802.1s is where you assess the spanning tree for multiple vlans. 

default:
* PVST+
* enabled on all ports in VLAN 1
* slow convergence. 

for the intervlan spanning tree, Cisco need 12 bits for the VLAN ID so it takes them from the 16 bits for priority. But this then means that you have to make jumps of 4096 due to the fact that you are changing the 13th bit.

to set one switch as the primary or root switch you will run the command 
```
spanning-tree vlan 1 root primary
```
then to set one as the secondary you would run the command
```
spanning-tree vlan 1 root secondary
```
|Blocking 20s|
|-|
Listning 15s|
learning 15s|

* PortFast
	* immediate transition to forwarding state
	* can only be on access ports
* BPDU guard
	* if BPDU is received, the port will shut down
	* usually used with PortFast

PortFast will basically disable spanning tree on that port. You would only do this on access ports as that is where the clients of the network will lie, and these will not create loops as they are terminators. 

PortFastTrunk is for use on trunk ports like you could find on a vm server which is still an end dvice. 

BPDU's will never come from end devices as they are not switches. due to this anything plugged into a PortFast port will not send any BPDU. so if you plug a switch into itself then two PortFast ports will be connected and so they will send BPDU's into the switch. BPDU guard will then error disable the ports so that they will not create a loop and will stop the broadcast storm going to the rest of the network. 

to set this for all of the interfaces that you want it on. 

```
int e 0/1 - 20
spanning-tree portfast
spanning-tree bpduguard enable 		// REMEMBER THIS ONE
```
and to automatically apply it to all access ports. 
```
spanning-tree point bpduguard default
spanning-tree portfast default
```

### Improving Redundant Switched Topologies with EtherChannel

when you have two switches connected together then you would want to to have high bandwidth. this would mean that you would want to put in two cable to double the bandwidth, but that would create a loop and so EtherChannel will make the switch think that both of the cables are one. This will work with up to 8 interfaces. 

spanning tree will see the connection as an addition of the individual bandwidth. 

sometimes called link aggregation, so EtherChannel is just the Cisco name for it. It will allow us to create a higher bandwidth cable and will also load balance between the cables. If one cable goes down, then all the data is just put through the rest of the cables. this will mean that spanning tree will still see the connection there, its just that it will see the speed go down.  

when you create an EtherChannel port you will create a new virtual interfaces on the switch. 

there are two protocols that are in place to allow the creation of EtherChannel auto magically:
* PAgP Port Aggregation Protocol
	* Cisco proprietary
* LACP Link Aggregation Control Protocol
	* IEEE 802.3ad standard

YOU CANNOT MIX AUTO AND STATIC CONFIGURATION

#### PAgP

can be:
* desirable
	* active
* auto 
	* passive
* ON
	* basically static

x|On|Desirable|Auto
|-|-|-|-|
On| y|n|n
Desirable | n|y|y|
Auto|n|y|n

#### LACP

can be:
* Active
* passive
* On

THESE MUST MATCH for EtherChannel to work
* speed and duplex
* made
	* access or trunk
* Native and allowed VLANs on trunk port
* Access VLAN on access ports

if any of these things to not the same then the offending port will be kicked out of the EtherChannel. Otherwise the EtherChannel could be down compliantly. 

mode active = LACP
mode auto = PAgP

the channel group does not NEED to be the same but you should have them the same to make it easier.

``` 
show EtherChannel summary
show EtherChannel port-channel
```

```
int range e0/0 - 3
channel~group 1 mode active/passive
int port-channel 1
```

## Understanding Layer 3 Redundancy

First Hop Redundancy

This will be the first hop that you see / get to from the host device. THIS WOULD NOT BE A SWITCH. but the first router. 

Basically you would have two default gateways for the network so that if one was to go down then you would still be able to get the internet. two independent network links from one network to another, with each having two routers leading to the internet. 

> The default gateways needs to be ONE of the branch routers. 

First Hop Redundancy Protocol (FHRP)

HSRP - Hot Standby Routing Protocol
* proprietary and made by Cisco

there is version 1 and 2. basically version 2 supports ipv6. 

there is also:
* VRRP
	* Virtual Router Redundancy Protocol
	* an industry standard
* GLBP
	* Gateway Load Balancing Protocol
	* Cisco only
	* advantage is that you get redundancy and load balancing

The way that this works is that you will have two physical routers, you actually have 3 or more routers. This third one is virtual. This virtual router has its own IP address and MAC address. THe mac address will look like: "0000:0C07:AX0x" in this case the X will equal the HSRP group number. 

you will tell the routers about this virtual router. 

if a request for the virtual router comes through the network, then the router that gets the request will act upon it on the virtual routers behalf, this then becomes the active router. 

on the client, you would set the default gateway to be the ip address of the virtual router. 

the reason that you would have more than one virtual router is so that you have one for each VLAN as they will all have different default gateways. 

every 3 seconds the two routers will send a hello message to each other. The first one to start will become the active router. Then the second one to be turned on will see the hello messages and set itself to be the standby router. 

if the first router fails, then the second one will stop seeing the hello messages and will then becomes the active router. The new router will then send out the hello messages.o

It will wait for 3 of the hello messages before becoming the active router. So there will be a 10 second delay before it sorts itself out.

VRRP has a dead time of a second, so it will take 3 seconds total to sort out the problem. 

you can force an election so that the router with the Gi connection to the internet will be the active one all of the time rather that the other router that could have only 10mbps. 

* HSRP defines a group of routers, one active, one standby
* Virtual IP and MAC are shared between the routers
* `show standby` will tell you the state. 

```
standby [groupNumber] ip [ipAddress] 		// set ip address and MAC address
standby [groupNumber] priority [priority]
standby [groupNumber] preempt 		// will redo election of active router 
standby version [1/2]
```

HSRP v2 uses a different multicast address. 

> MST = Multi spanning tree - used for when you need to use STP on multiple VLAN's so that you dont need to run many instances of the protocol. 
> mst 1 1-500
> mst 2 501-1000
> this way, only 2 STP are running on the switches. 

### Extended ACL

to tell that there is an ACL on an certain interface run:
```
show ip interface [interface]

inbound access list is 101

```

standard access list checks source IP only. extended access list checks source IP AND destination IP and more like protocol and port. 

to permit all HTTP traffic on the network: 

```
access-list 100 permit tcp any any eq 80
```

you can block by protocol, and you can have many additional options like equal to, and not, and range and so on. 

a firewall will automatically write the rules for the ACL that will allow response packet. 

224-239 are reserved multicast addresses

224.0.0.2 is the multicast address for all routers in a network. 

## Troubleshooting IPv4 network connectivity

SLA, switch port analysis, access list

in reality, only SPAn will actually be used in troubleshooting. 

to troubleshoot you will need to follow some kind of logic. One of your best tools is knowledge of the OSI model. one of the reasons for having the OSI model is to simplify how a device connects to the network. 

one troubleshooting the mothed is called "follow the path", this is where you will go hop by hop along the network to see where the problem will be. 

ping is an icmp type 8 message and a type 0 message. 8 is the echo, 0 is the reply. when you ping you will generate a icmp packet. traceroute is also an icmp packet, with the tty set to 1 initially. when the packet gets to the first router the ttl will get set to 0, then the router will drop the packet and then send back a message to the sender telling you that the packet was dropped by that router. Then the sender will send out the same packet but with a ttl of 2 and so on...

the type is the message telling the reason and the code is to say specifically why 

when you get a ping of U.U.U its because the router could not route the packet and so it told you that it couldn't. its an icmp Type 3 message to say that it is unreachable and a code as follows:
* 0 = destination network unreachable
* 1 = destination host unreachable
* 2 = destination protocol unreachable
* 3 = application unreachable
in this case the host is not there, and so you would get the code of 1 because the host is unreachable. 

code 13 will mean it is administratively filtered. 

icmp is a messaging protocol used by network devices to communicate basic information. these are FUNDAMENTAL to troubleshooting a network problem. 

you may also get ".....", this will mean that you sent the message all ok, but a response could not get back to your machine for some reason. so when you get a "....." then you know to look at unbound connections, but when you get a "UUUUU" then you will need to look at your connection to the device. 

"....." the two most common reasons are that a firewall has blocked the packet and that 

you should try to do a ping twice so that you KNOW for sure that the ARP tables are populated and that all the conversations have happened. 

rebooting a networking device should be the LAST THING that you do, think of spanning tree, non-saved running configs and so on, this can also happing with routing protocols. icmp will also contain the first 8 bytes of the original packet that was sent so that you can get an idea for what it was. 

the process of name resolution starts with your local device, this contains two devices, the localhost file and the cache. if QA changed their servers provider then the new ip address could not have filtered through to the local storage. 

on a router you can set up an SLA that will perform automatic testing, like testing that you can always contact an ISP or branch office and that your connection is good. you would need to ensure that the connection doesn't drop packets or has low speed. 

a multihomed solution is where with HSRP one router will contact one service provider and the other will use the other. if the serial port on one router becomes shutdown then the router will not change over and the connection to the internet will not be reachable. so the router may have to then redirect all the traffic that it gets to the other router and then out to the internet, but that will not be efficient. 

what you could then do is set up an SLA so that it will ping the ISP. then when it cannot ping then you would degrade the hsrp value so that eventually when you cant reach the ISP then the other router will have a higher rating and so the other router will become the active one and the normal router will go into standby. 

how to create an SLA:

```
ip sla [operation number]
(confip-ip-sla)# icmp-echo [destination ip address]
(config)# ip sla schedule [operation number] life [life time] start-time [start time]
```

the life can be forever. 

```
ip sla 1
icmp-echo 10.10.3.30
frequency 300
```

### SPAN / port mirroring

duplicating frames through a switch to a receiving station. 

by default the you will capture B/C, multicast and unknown unicast by just being in the switch. 

normally the switch will send the data out of only the relevant ports. but if you turn on SPAN (switch port analysis) then it will send a copy of every frame from certain interfaces in or out to a certain other port. 

RSPAN (remote span) is used for when you want to listen for information on different subnets. 

this is called baseline testing and is what wireshark is actually supposed to be used for

to set up:

```
monitor session 1 source interface Fa0/3 both
monitor session 1 destination interface Fa0/1
```

### extended access list

you can add in a remark so that you know where you are. like a printf(); for when you are debugging.  

### Troubleshooting IPV6 Network Connecting

link local: FE80
* not globally routable 
	* not even routable
* used for discovering neighbours and the router
* FF02::1 is the messages for ipv6
* routers have a specific address ~ all routers address = ff02::2
* leading zero compression :0201: = :201:
* zero compression :2038:0000:0000:0031: = :2038::0031:

unicast addresses   

* global address : 2000::/3
* Unique-local : FC00::/7
* link local : FE80::/10 - FEB0::/10
* Loopback : ::1
* Unspecified : ::

in ipv6 you ONLY HAVE named and extended access lists. in ipv6 its called a "traffic-filter". 

```
show ipv6 neighbours
```

### recap on distance vector based routing

distance vector based routing is where you have a map of the network. 

link state is where you have a signpost. 

* Distance - hop count
* vector - direction. 

when you are using RIP the hop count is the metric and any directly connected network will have a hop count of 0 and this will be called the seed metric when you are talking about it as a reference point for the hop count. when R1 will send its routing table to R2 then it will send the information that its directly connected networks can be accessed by this router ant the hop count will increment by one

the holdtime timer for RIP means that for that network the messages will be ignored for that time. if a port kept going up and down then it would make sure that other devices on the network will not have too much traffic about the 

one problem that can arise from distance vector is that a network can be advertised to its own router. this would not be a problem due to the fact that you would use the directly connected network. but if that were to go down then the router would send all the data to router 2 due to the fact that thats all the information is has about that network. this could then mean that R1 will send all the data to R2 and then R2 will send all the data to R1 and this is a routing loop. 

distance vector will use a thing called split horizon, this will ensure that a network learned by a port will not be sent out back to that port. 

when a network is disconnected then the router will send out a flash update to rip that will let the others know the network is 16 hops away. called route poisoning. 

a poison reverse message will make R2 send the poisoning message back to R1 so that no loops could EVER occur. 

## Implementing an EIGRP based solution

this is a distance vector based protocol. so you will have a signpost telling you where to send information rather than having a map of the network. 

dynamic routing protocols do the following things:
* discover remote networks
	* this is done by offering information or requesting for it
* maintaining up to date routing information
* choosing the best path to destination network
	* this is where the metric will come into play
* find a new best path if the current path is no longer available. 
	* when you are using RIP then the time to find a new path is 3 minutes
	* for EIGRP the time is 2 to 5 seconds. 

an IGP ir a group of routers that are under the control of one authority this is also called an "autonomous system". basically all the stuff that you own and maintain you can use IGP, but when you need to work with someone elses routers then you would have to use an EGP so that it will be compatible and so you cant steal information and so on. "there are rules and regulations that you have to follow"

within IGP you get Distance vector and link state. 
* distance vector is simple and you would send over the whole route table to other routers. 
* link state routers never send route tables to each other, they instead stand link state adverts and these will flood through the network.  

there are then also classless and classfull protocols. 
* classless protocols allows you to use VLRM networks and there are no problems. 
* classfull protocols needs the masks to be consistent in the same major networks. basically they don't have space to store information about the subnet masks and so it will have to use its own. 

Admin distance

this is an assigned value that all routing protocols carry and this will indicate what route to use based on what protocol is more trustworthy. 

### EIGRP (Enhanced Interior Gateway Protocol)

here are the features:
* Rapid convergence
	* takes only about 2 to 5 seconds to converge
* Load balancing
	* can load balance against paths that have different metric costs. 
	* non equal cost path load balancing 
* loop-free, classless routing
	* this will actually stop loops from happening, rather than dampening the effects of one. 
* Reduced bandwidth usage
	* Bounded updates 
	* No broadcasts 

EIGRP was made Cisco proprietary but is now available to all vendors if they want, but most, if not all, choose not to. 

Underneath, EIGRP uses DUAL (diffusing update algorithm) and thats why its called "D" in the ip routes. 

RIP would tell the routing table every 30 seconds, that makes no sense if nothing actually changes, so EIGRP does not do that. 

EIGRP will send the whole routing table once at the beginning and ONLY then. but will then only send updates when a change is made and will then only send the changes of the table. EIGRP will then not know when a router dies, so every 5 seconds they will send a hello message to ensure that they are still alive. This communicatin will happen on a reserved multicast address: **224.0.0.10** 

the first thing to say is that EIGRP does not send all its route table, 

hello are sent every 5, but are pronounced dead after 15 seconds, so you get 3 tries. 

tables:
* neighbour 
	* what routers by what interfaces
* topology 
	* all the networks that it has learned
* routing
	* the best of the topology table for each network only once. 

Distances:
* feasible
	* the distance from your router to the network
* advertised 
	* the distance from the advertised router to the network

basically you know your distance to the network and the next routers distance to the network. 
 
the DUAL algorithm enforces the feasibility condition. to avoid a loop, you can only use the neighbouring router for a certain network if its advertised distance is lower than yours, but if your value is lower then you don't use the neighbouring router. Basically, you will just use the best path that you know of. 

> only use a neighbouring router if it is closer than you are 

the next hop router is called the successor. 

then all the other routes that have a value that will be feasible to actually use then there will be called feasible successor. 

a router that is the same distance away to the network will not be a feasible successor, because why would you go that way when i am the same distance away. 

#### metric

the metrics that are used are:
* b/w
* delay

but you can also use:
* reliability
* load

b/w is calculated by:
```
10^7 / the minimum of (the advertisedB/w or the linkB/w) 
```
delay is calculated by:
```
the sum of (advertisedDelay and linkDelay)
```
this is then combined by:
```
( B/W + delay ) * 256
```


```
router eigrp [autonomous network value]
network 10.0.0.0 		// enable EIGRP on all interfaces that have the first byte of the network address as 10
netowrk 192.168.1.0 	// you can also use a wildcard mask for more control, so its optional. 
```
the autonomous netowrk value needs to be the same as this is used to send the routing into macho to the correct routers. the routers will only communicate EIGRP information if the autonomous network value is the same. 

the main reason that EIGRP is so fast is due to the fact that it has already calculated other paths and so it can just switch instantly. 

you will get a feasible successor if to get to the network the distance that another router has is less than your current way to get there. This will only happen if the feasible distance from your current router is less that your current route, or it will switch to the better one.  

if there is an issue with EIGRP then normally its a problem with the metric. Another things is that the AS numbers must be the same. 

to see neighbor information. 

```
show ip eigrp neighbors
```

the "H" that you see here is the handle number which is the order that they were learnt in. 

to see all the interfaces that you have applied EIGRP to then you would run:

```
show ip eigrp interfaces
```

so see the topology table you would run:

```
show ip eigrp topology 
show ip eigrp topology all-links 	// this will show all of the routes, not lust the feasable ones like normal
```

the "P" that you may see at the beginning means that there is a feasible valid successor. Passive because you wouldn't send anything out of that interface because you already have a path. Simply means that there is a valid successor. 

"A" for active will mean that it is trying to ask around for a new successor due to its normal one being down. 

"passive interface default" will mean that all of the interfaces will be passive, THIS COULD EASILY BE A QUESTION IN THE EXAM. 

### K numbers

1| bandwidth
|-|-|
2 |load
3 |delay
4 |reliability 
5 |MTU

if the K numbers are different then the routing protocols will not work. but you 

### load balencing

EIGRP uses equal cost load balancing, this is where if multiple paths have the same metric cost then data will be split equally between the two. 

there is also another version called unequal cost load balancing, this is where data is sent in proportion to the metrics of multiple paths to get to the destination. 

### Implementing EIGRP for ipv6 

EIGRP has a module that allows it to work for ipv6, this means that EIGRP and ipv6 can run at the same time. 

FF02::A is the multicast address for ipv6 EIGRP. 

you can shutdown an ipv6 EIGRP process by just running:
```
no shutdown 	// when you are in router mode "ipv6 router eigrp"
```

when you are looking at ip route the numbers in the brackets will be FD and AD. (FD/AD)

### troubleshooting EIGRP

when you have an issue you should first check if EIGRP is working and then over to the router. but FIRST FIRST you should chesk the routers are actually on, and you can ping, show cdp neighbors. 

first run commands like:
```
show ip neighbors
show ip interface brief
shof ip eigrp interfaces
show ip protocols
```

then after that you would run:
```
show ip interfaces
show ip router
show ip protocols
show ip access-list
```

you would also check:
* does the AS number match the rest of the network. 
* are the interfaces set up for EIGRP
* are the interfaces passive


Discontinuous networks is where one there is a classfull network boundary, so a network advertisement will have to be summarised because the advert when through a different network class. 

auto summary will be shown in "show ip protocol"

you can find the AS numbers with the command "show ip protocols", this will also show if an interface is passive. 

## Implementing a scalable OSPF based solution

Open Shortest Path First = OSPF

> The first Link State routing protocol.  WHOOO

The first thing that happens when you start OSPF, is a hello mechanism so that it advertises its existence. OSPF has an identity so that it can be recognised, this is normally the ip address of the network. 

in the hello packet the identity of the router is sent out, this is normally the IP address. the ip address is used because OSPF needs to route ip traffic. 

### router ID

the way that the router ID is assigned follows this method. 

* manually set
* loop back address
* highest active IP address. 

the reason that the loop back address is preferred is due to the fact that the loop back address will never go down or get reassigned. 

in the hello packet that is sent out tells the other devices, hello I am "\NetworkID"

this will start the neighbour relationship. 

the hello messages are then spread all throughout the network so that all of the devices will become aware of all other devices on the network. This is NOT THE SAME as EIGRP as there the devices will only know about directly connected devices. 

a router will advertise all of the routers that they know about during this initial stage. 

> Step one: build the neighbour table. 

from here the routers will then start to advertise what networks they are connected to. Each router will need to do this. Link State Adverts (LSA) are used to advertise the network. YOU ALSO ADVERTISE YOU LINK TO THAT NETWORK. 

from this, you can then see all of the ip address that all of the routers and work out what routers are connected to what other routers, this will then allow you to get a complete map of the network. Since all of the routers will have the same information then all of the routers will have a complete map of the network. 

in order for this to work, this map MUST be the same on all of the routers. 

> Step two: Build topology (LSDB = Link State DataBase) table 

> Step three: choose the best routes = the routing table

the LSDB will contain information on EVERY connection and path in the network. 

the best routes are then calculated by looking at the path with the lowest metric. 

OSPF metric = cost
cost = 10^8 / BW of interface in bits per second

each router will calculate the shortest path that it will use to get to any network and it will do this first and put this in the routing table. 

YOU CAN MANUALLY CHANGE REFERENCE BANDWIDTH. 

once a link goes down, the whole route will need to be re calculated and that can take 2 - 5 seconds to sort out, but that will depend on the size. 

you can take a network and break it into areas so that a change in a different area will not force a computation in another area.  

OSPF is the largest used internal gateway protocol. 

110 AD 

hello messages are sent every 10 seconds. Dead interval is 40 seconds. so 4 times with this protocol because reasons. 

updates are sent when there is a change

BUT the adverts have a ttl of 60 minutes, but half way though the routers will retransmit their link state adverts. 

all of the adverts will have a sequence number with them that will let the receiving device know what the newest version is.  

* Discover neighbours
* Form adjacencies
* flood LSDB
* compute shortest path
* install routes 

### areas

you can chop up a network into areas so that if a topology change happens in one area, then only the routers in that area will have to recompute the path. 

The default is area 0, and in a multiarea network the backbone area will be 0, all areas will have to connect to area 0. 

Area Border Router (ABR) is the name of the router that will allow routing between the areas basically. 

"summarize network changes between routers in different areas"

routers between areas will basically have two tables, one for each. 

"reduce the table size and the impact of a change" this is all you need to know about why we use areas

### hello message 

for a relationship to happen between two routers the following must be the same:
* Area ID
* Hello/Dead interval
* Authentication data
* Stub Area Flag

the wull data that is in a hello message is as follows:
* Router ID
* Hello/Dead Interval
* Neighbours
* Area ID
* Router priority
* DR IP address
* BDR IP adders 
* Authentication data
* Stub Area Flag

the hello message and SLA's are send out of address "224.0.0.5"

### 7 steps to form a router relation

#### 1 - DOWN

to start with, both of the routers are in the down state

this means that they are sending hellos

if they then reiceive an hello back, they jo into an INIT state

#### 2 - INIT (fam)

reiceiving a hello 

#### 3 - TWO WAY

Receive a hello message containing my router ID, I now know that the other router will know about  

#### 4 - Exstart

The routers are in an exchange state 

The start of the exchange. 

They will then decide who will be the master and who will be the slave. and who will take charge of the relationship.

the highest router ID will become the master. 

#### 5 - exchange

where data is actually exchanged

the master will share DB first, then slave second

summary databases (DBD [DataBase Descriptor]) packets are exchanged

#### 6 - loading

further information requested 

this is where you get the additional information that you need 

#### 7 - full (in sync)

this is where both of the routers have the same information 

#### finally - run Dijkstra's algorithm 

this is where the best routes are found and calculated and this leads to the routing table. 

the costs of the network path is done by the routers adding the values to the ones that they receive to what they know the connection to be. 

some of the downsides of OSPF is that it needs a lot of processing power and storage. 

OSPF has its own method of reliable communicating so it does not rely on TCP.  

### OSPF packet

hello
DBD
LSU
LSAck

OSPF uses protocol number 89 

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

### OSPF header

version number| type| packet length| router ID| area ID| checksum| authentication type| authentication| data
|-|-|-|-|-|-|-|-|-|

ICMP, OSPF, EIGRP are maybe layer 3 protocols. 

to active OSPF you would run:
```
router ospf [process number]
```

the process number is a locally significant (only on this one router) number. 

you can also just go into an interface to turn on OSPF rather that specifying the networks that you want to add 

### multiarea design

you have areas in a network to reduce the bandwidth usage, reduce the table size and reduce the impact of a topology change. 

ABR = Area Border Router

this is the routes that will be on the boundary between two areas and in most cases will be in the backbone area. 

routers in a normal area are called internal routers. 

 get an internet connection. this router that connects to the outside world (that uses BGP) is called an ASBR (Autonomous system boundary router)

the tables in OSPFv3 are:
* neighbour 
* topology
* routing 

version 2 is for ipv4, version 3 is for ipv6. 

```
router ospf [process id]
```

you can have multiple OSPF processes on a router.  

if more data is needed then you will send an LSRequest, and then this is completed by a LSUpdate and an LSAck

every 10 seconds hello messages are sent, the dead interval time is 40 seconds. Except when a change to the network occurs an LSA will be sent out to update the information. A

when a change comes in the database is changed and then the route table is recalculated. 

a router will reflush its routes every 30 minutes. 

The LSA's are routers LSAdvertisment. 

this router LSA is a type 1 LSA, these are flooded everywhere. 

a point to point network is where the routers are all in a line. when all the routers are connected to the same switch then it is a broadcast network as all of the routers would get the updates in a broadcast. 

in a broadcast network all of the multicast LSA's will be broadcast all over the network and all of the bandwidth will be taken up. 

to solve this OSPF will put someone in charge and that is the Designated router. BUT THIS WILL ONLY HAPPEN IN A BROADCAST NETWORK. 

in case the Designated Router goes down then we have a Backup Designated Router. All of the other routers are called the DRother

changes are now sent to the DR and BDR where they are sent out. 

in this case the multicast address used is: 224.0.0.6

the Priority feild can be used to select the DR, and in this case the highest is the best. if you dont want the router to the a DR or a BDR then you would set the priority to 0. 

the LSA that are sent to the DR are type 2 LSA's, this means that it will be sent to the DR rather then flooded. This is a network LSA. 

type | name | description
|-|-|-|
1 | router | flooded across the network
2 | network | sent only to the Designated Router
3 | summary | sent out by ABR, type 1 and 2 are put into this to sent information across areas. 
5 | external | used when you connect to the ISP or a completely different area, external of OSPF. 

these are flooded within an area. They dont go beyond an area. They are stopped by an Area Border Router. 

all the routers in the backbone area are called backbone routers. 

type 1 and 2 cannot get out of an area

an ABR will sent its own LSA type 3 thats called a summary LSA. 

the type 1 and 2 LSA will get put into a type 3 LSA

### area types

area 0 is the backbone area, this is where all other areas must connect to 

all other areas are normal areas. 

if you want to limit the adverts sent to an area then you would set it to be a stub area. this is where the stub area flag its sent. You will need to tell both the routers that connect the area to the backbone that they are a stub area as the flag needs to match. 

when you make a stub area it will not get adverts for external areas which are type 5 LSA's. 

A totally stubby area means to type 3 or 5 SLA's. 

we know 3 areas: backbone, normal, stub. 

> "its pretty much the same, but slightly different" - Rob

### Implementing OSPFv3 for IPV6

OSPFv3 will support ipv4 as well as ipv6. 

v3 is an implementation that allow OSPF to use ipv6. 

you still have all of the tables that you would do anyway

the address will obviously have to change due to the fact that you are using ipv6. these addresses in OSPFv3 are:

* FF02::5
* FFO2::6

the router ID's still use 32 bit router ID. it will still go through seeing if there is any manual setting, and loopback and so on. 

YOU WILL NEED TO HAVE AN IPV4 INTERFACE SO THAT IT CAN AUTOMATICALLY GET A ROUTER ID THAT IS 32 BITS IN LENGTH. if it cannot get a router ID then OSPF will not be able to start, and so you will set it manually or set up an ipv4 interface. 

OSPF is enabled on a link basis, not a network basis. so you would have to apply it to an interface, and therefor you would not apply it by the network address. 

### troubleshooting

there are 3 main things that you would want to check if there is a problem:

* OSPF neighbour adjacencies
	* **different areas**
	* do all of the things that need to match, actually match. 
		* look at running config
		* show ip protocols / other commands
		* debug
	* ACL
	* passive interface
	* show ip OSPF neighbors
	* show ip interface brief
	* show ip OSPF interface
	* show ip protocols
* OSPF routing tables
	* show ip route
	* show ip protocols
	* show ip OSPF interface
	* show ip route [address]
	* is there another routing protocol running with a lower AD running. 
	* distance 85 - will set the AD of a protocol
* OSPF path selection 
	* show ip route
	* show ip OSPF

## Wide-Area networks



### Configuring single homed EBGP

all the routing protocols that we have covered so far are interior gateway protocols, that is that they run under one AS. 

AS - a series of networks under one administrative control. 

to connect networks that have different AS you would have to use BGP. 

BGP will establish a neighbour relationship. Two routers that are connected with BGP are called BGP neighbours. YOU WILL HAVE TO MANUALLY SET THIS UP.  

all of the AS will have a AS number that is assigned to them. 

BGP routers will connect with TCP and use port 179. 

```
(conf)# router bgp [AS number of this router] 

(conf-router)# neighbor [neighbor ip address] romote-as [neighbor AS number]
```

a router can only be in one AS. 

a service provider can then provide interconnectivity between their own customers and BGP is used to connect those customers to those of other ISP's. to do this you would need to set up a BGP peer relationship between two routers for the different ISP's. 

some service provides will provide a service to other providers. for example, Telefonica provide a service to connect other ISP's networks and this is called a Transit autonomous system because they allow traffic to flow through them . 

when two ISP communicate a lot of data then they will have to pay transit costs for the ISP that they go through, they then may want to set up a direct link so that they dont have to pay the cost. this is called an internet exchange point. 

* 1 turn on routing protocol
* 2 find neighbours
* 3 advertise network

```
network [network address] mask [subnet mask]
network 20.0.0.0 mask 255.0.0.0
```
normally no networks with moose that /24 bits will be advertised.  

you will connect to tier 3 ISP's - small and consumer, then these will connect to tier 2 - businesses, then finally there are teir 1. 

There are only 17 teir 1 service provider and they must all connect together in a mesh. 

BGP is the MOST scalable protocol but the SLOWEST protocol by design. 

### IBGP

relationships are formed manually, you need to specify neighbours manually as well. 

BGP will also advertise the all the networks that they are connected to. 

when a network is advertised the ip address of the network is sent and this is called the prefix. the subnet mask is then also sent and this is called the prefix length. Finally, the AS number is also advertised. All of this data is known as "Network Layer Reachability Information" (NLRI)

an AS will then advertise out what networks it is connected to, but it will also sent out networks that it has learned through another AS. When this information is sent out then the AS number of this second AS is added onto the end of the othser one. So the AS numbers will make a chain of what AS the advert has been to. this is called the AS PATH

if the advert is then sent to the destination through a different AS then the numbers will be different and then BGP will use the shortest path based on the number of AS numbers that are tagged onto the end of the advert. 

if you have a transit AS that you need to carry BGP information through then you would need to use IBGP inside the AS. this is because the other protocols don't understand the information that BGP will use. 

BGP will NOT load balance. 

BGP will go through like 13 processes to figure out the best path for data to take as it has to work out one. 

not used to route data in an AS but instead to pass BGP data through the AS. 

## Network device management and security 
