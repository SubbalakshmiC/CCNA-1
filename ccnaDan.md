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
  * Firewall

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
| Data Link  | Device to device connectivity. handles MAC addresses. Switches. only works on a local network this is how ARP is used
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



## Module 2 - Establishing internet connectivity 

## Module 3 - Summary challenge

## Module 4 - Building a Medium sized network

## Module 5 - Network device management and security 

## Module 6 - Summary challenge

## Module 7 - Introducing IPV6
