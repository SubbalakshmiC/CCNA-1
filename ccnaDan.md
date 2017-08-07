# CCNA stuff 
> let's do this!!!
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
  
* Don't leave it to the last minute
* older apprentices will be more that happy to help you
* It's actually worth it, even if you go into sales
* you will have NO time if you leave it too late as when you start rotations you will have to drop something
* reach out to anyone if you need help, your co workers, other apprentices or any one really
* keep going, don't stop looking at the content for a month as you will forget it 

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
			* used for when over long distance (100m - km's)
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
  * AP's
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
* Scalability
	* how able is the network able to scale up to new users
* Reliability
	* [ (minutes in a year) - (Downtime) ] / 525600 * 100 = percentage up time
		* e.g. (525600 - 15) / 525600 * 100 = 99.9971% uptime
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
	


## Module 2 - Establishing internet connectivity 

## Module 3 - Summary challenge

## Module 4 - Building a Medium sized network

## Module 5 - Network device management and security 

## Module 6 - Summary challenge

## Module 7 - Introducing IPV6
