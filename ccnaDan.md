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
sales vlan|||||||||HR vlan

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

the trunk tagging is an industry standard and can be thought of as a sub-category of the Ethernet frame standard and is called IEEE 802.1q but is commonly known as "dot1q". the vlan tag is 4 bytes in size so its 32 bits in size. BUT NOT all of those bits are for the vlan tag and thats far too much so only 12 bits are for the number of the vlan tag. This means that there can be 2^12 vlans between connected switches. THE NORMAL VLAN RANGE IS UP TO 1000, but the extended range 4094. there are about 5 reserved vlan addresses. 

a frame bigger than 1518 bytes is called a giant (frame). but because the tagged frame is just over the limit its called a baby giant frame. 

there are 3 types of switches when vlans are used:
* access
	* what people are connected to 
* distribution
	* shares the load between switches
	* only connects to switches
* core
	* this will connect all of the switches and actually connect the network together

## Module 5 - Network device management and security 

## Module 6 - Summary challenge

## Module 7 - Introducing IPV6

ipv6 is 128 bit
* 64 bit for network
* 64 bits for device
