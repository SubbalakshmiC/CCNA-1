> what is the unique identifier of router 1?

**CISCO887VA-K9:FCZ1121C119**

The unique identifier that you would use for router 1 will consist of the PID (Product IDentifier) and the SN (Serial Number). This is because the PID is used to get the information of the actual device like what type of router or switch that you have, while the SN is used to get information on what the unique ID of the board and processor in the device actually are. 

> CORE 2 has been configured to send its configuration file to the TFTP server every five minutes. What is the ip address of this TFTP server?

The way that you would find this out would be to show the mac address table on the switch nearest the TFTP server then issue:
```
SW1>show mac address-table 
          Mac Address Table
-------------------------------------------

Vlan    Mac Address       Type        Ports
----    -----------       --------    -----
   1    aabb.cc00.7c00    DYNAMIC     Et0/1
Total Mac Addresses for this criterion: 1
```
this will then allow us to see what the mac address of the TFTP server is. we will then remember that mac address and switch to the terminal of the router where we would input:
```
R1>show ip arp
Protocol  Address          Age (min)  Hardware Addr   Type   Interface
Internet  10.10.1.1               -   aabb.cc00.7b00  ARPA   Ethernet0/0
Internet  10.10.1.2               0   aabb.cc80.7e00  ARPA   Ethernet0/0
Internet  10.10.1.3               0   aabb.cc80.7f00  ARPA   Ethernet0/0
Internet  10.10.1.10              0   aabb.cc00.7c00  ARPA   Ethernet0/0
```
from this command we will now know the ip addresses of all the devices connected in the network that the router will know how to route to. from this output you can see that the mac address of the server that we got from the switch it tied to the ip address of 10.10.1.30 and thats the answer.  

> What is the severity level for buffer logging on R1?

the way that you would find this out is that you would input the command:
```
R1#show logging
Syslog logging: enabled (0 messages dropped, 4 messages rate-limited, 0 flushes, 0 overruns, xml disabled, filtering disabled)

No Active Message Discriminator.



No Inactive Message Discriminator.


    Console logging: level debugging, 26 messages logged, xml disabled,
                     filtering disabled
    Monitor logging: level debugging, 0 messages logged, xml disabled,
                     filtering disabled
    Buffer logging:  level debugging, 27 messages logged, xml disabled,
                    filtering disabled
    Exception Logging: size (4096 bytes)
    Count and timestamp logging messages: disabled
    Persistent logging: disabled

No active filter modules.

    Trap logging: level informational, 30 message lines logged
        Logging Source-Interface:       VRF Name:

Log Buffer (4096 bytes):

<...Output Omitted...>
```
from here you would then see that it says buffer logging is at a level of "debugging". then you just need to know that debugging is lebel 7 in the stack and so you would use that value. 

> the correct command format for setting password encryption is:
```
server password-encryption
```
# help needed here
> Which configuration step is required to properly configure Switch Port Security on Core Switch A?

you will need to "Configure the proper client MAC addresses on access ports", however, i am not sure why this is the case because the MAC address should be learned automatically when the first frame comes in on that port

> There is no route to network 192.168.2.0 on Router0. What is causing this problem?

at first you may look to the "ip route" command on router0 and see that there is no entry for ip address of the network 192.168.2.0 and therefor assume that the ip address for that network is missing on that router. however you will need to look at why that is the case. if you look to the output you will see that some of the address in the table are learned by "R" which means that RIP is used in this network. From this you can then look to the rip configuration on router1 and I assume that it would show you that "The network command for 192.168.2.0 is missing on Router1". 

> When the question asks for two answers, actually put 2 down not just one.......

> You are the network administrator for your company. You decide to implement VLAN's with in your network architecture. You create the VLAN's as shown in the exhibit. You properly assigned interfaces Fa0/11 and Fa0/6 to the appropriate VLAN's on switch S1. You create and address the appropriate subinterfaces on router R1 as shown in the exhibit. You now need to enable interVLAN routing using the Router on a stick method to ensure that PC1 and PC2 are able to communicate with each other. Which three commands are still needed to be implemented to complete this configuration properly?

```
S1(config-subif)# encapsulation dot1q 10
```
[  ]
YOU SHOLD NOT DO THIS COMMAND. the reason is that you would only need to run the encapsulation commands on the router and not the switch. This is because the router will have the subinterfaces set up and ready to do this, the switch just needs to have the trunking port set up and that will deal with it all. *In this setup the router will do all of the smart things, the switch will just send all the data from the vlan's through the trunk port labeled.*  
```
R1(config-subif)# switchport mode trunk
```
[  ]
YOU SHOULD NOT DO THIS COMMAND. the reason is that there is no such thing as a trunk port on a router. a VLAN is a layer 2 thing not a layer 3, due to this trunk ports that function at layer 2 and so do not exist on routers. on the router you would have the subinterfaces that would be there to separate out the traffic on each VLAN. 
```
R1(config-subif)# encapsulation dot1q 30
...
R1(config-subif)# encapsulation dot1q 10
```
[x]
both of these commands should be run on the correct interfaces of the router. The reason that this is needed is so that the router will be able to know what subinterface is for what VLAN as well as how that data that goes out will need to be encapsulated so that it can be read.   
```
S1(config-subif)# switchport mode trunk
```
[x]
you will need to run this command in order to get the communication between the VLAN's all going through this port on the switch. The reason is that without this the port would only be able to access data from one VLAN and so only one VLAN could be routed to, and that doesn't make sense. Also, subinterfaces are not a thing that we have done on switches and so they need the trunk port so that the one port can send all of the data.  

> Your core router is also your DHCP server. Every time you reload the router, it clears any information it had on DHCP leases. Therefore, it serves IP addresses that are already in use. What is the best way to resolve this problem?

The best way to save the information not is not being saved when the system turns off is to literally save it. you would "Use the IP DHCP database command to store the DHCP bindings". what this would do is it would save anywhere you wanted, a list of all of the leased ip addresses and who they all belong to in non-volatile storage. Then, when the router turns on again, it will read this infomation to know what addresses are already in use and what ones it can actually assign. 

YOU WOULD NOT release and renew the addresses, as although this would work, it would cause a lot of overhead and some outages on the network. (more than the router being off anyway). 

> Which protocol is in use between a wireless LAN controllers and access points? 

**CAPWAP**

you would use CAPWAP because it stands for "Control And Provisioning of Wireless Access Points" and is designed to actually handle and deal with the access points that the question is referring to. Even if we diet learn about this protocol we still need to know about it. 

> You implemented VLANs on the network to logically group the hosts according to their respective functions. You set up a network and configure a trunk link between two 2960 switches. You configure Dynamic Trunking Protocol (DTP) in the defraud mode on both of the switches. After the configuration is complete, the trunk is not established. What is the most likely cause of the problem?

"Both ends are configured in dynamic auto mode", this will mean that both ends will try to set themselves to be the same type of port as the other end, but they cannot do that. Normally if one end was trunk ant the other was in auto then the auto port would set itself to trunk. you will also need to know that on 2950 switches the default mode is dynamic auto mode. 

> You manage a network with multiple Cisco routers and switches. You receive a new product activation key (PAK) for the routers. You need to install the licences on each router. What should you do. 

**"On each router run the following command:"**
```
licence call-home
```
what this command will do is it will will allow you to specify a product activation key that the device will then use to contact cisco.com to verify the features for that device. the reason for the "call-home" part of the command is that you are telling the router that it needs contact cisco to register. YOU WOULD NOT RUN licence install as that would not do anything as you just have the key, not the additional features that you want in an installable format. 

YOU CANNOT copy the PAK to or from the device as it is not a file, just a code so putting it in a file would do nothing. Like how you wouldn't copy a Windows licence key to file on your computer, you would instead input it in to the computer at a certain moment and then the computer would register that key to your machine by contacting Microsoft. Likewise the same will happen on a router, you will input the key when you run the command. then the router will contact cisco and register the key as will as verify the features that that device should have.   

> The port security feature is not working as expected on a switch. You run the "show port-security" command to troubleshoot and get the following output:
>
> <...Omitted output...>
>
> Port Security : Disabled
>
> <...Omitted output...>

From the output the first thing that you should actually look at is weather Port security is actually enabled on the interface that you want it to be. From this output you can see that this is not the case. In order to fix this, all that you need to do is run the command:
```
switchport port-security
```
on the relevant interface. This will then actually enable Port security on that interface and until that is done then all other configurations regarding switchport are invalid. 

YOU WOULD NOT use no shutdown because that would not enable port security, it would just allow the port to function as a port. You would also not change the violation mode to something different like protect, due to the fact that the question does not tell you how the port should be set up and so you dont know anything about the violation procedure. 

> Which two statements are true about this DHCP configuration? (Choose two.)
> 
> ip dhcp pool EastCoast
>
> network 192.168.1.0 255.255.255.0
>
> domain-name eastcoastwidgets.com
>
> dns-server 4.2.2.1 192.168.1.10
>
> default-router 192.168.1.1
>
> lease 4

"The pool is active and ready to start allocating IP addresses from the 192.168.1.0/24 network".  The reason that this is true is because the network command tells the dhcp server to allocaste ip addresses from the network address 192.168.1.0 and then with a subnet mask of 255.255.255.0. this will then mean that all addresses from the 192.168.1.\* will be allocated from the server. 

"the lease time is set to 4 days" is another true statement due to the fact that the command "least 4" will do that. The format of the lease command is that thee the numbers will be in the format of:
```
lease days hours.minutes
```
from the config above you can see that the lease command will actually set the lease time on the ip addresses to be 4 days. 

THE CONFIG WILL allow the ip address of 192.168.1.10 to be assigned by the dhcp server. One important thing to note is the dhcp server will actually allocate its ip address if it is in the range that it is told to allocate its ip address from, this is because the dhcp serving and the reachable ip address of the device are two different processes. The way that you would fix this would be to set the ip address of the server with an ip exclude command as that will mean that it wont allocate that address:
```
ip dhcp excluded-address 192.168.1.10
```

> A web server named Web Server 1 is sending a web page to a web browser on a computer name Web1 using three separate messages. Each message has a TCP header and HTTP information in addition to the actual data. Each message has a sequence number. As shown in the exhibit, the web server sends three messages with their respective sequence numbers to Web1. Two messages with sequence number 1 and 3 reach their destination, but the message with sequence number 2 fails to reach the destination. Which action occurs so that web1 receives message number 2?

the way that this would be handled is that "Web1 sends a TCP Acknowledgement to the web server for the missing segment". the reason that this would work is that Web1 will send the Acknowledgement which means that the server will have to send back the segment that the missing message was in. One thing to note here is that the individual message cannot be resent, instead the server will have to send the whole segment again. The segment is different to the message as the segment is the window of information that will be sent before the end has to confirm that all of the data has been received. So to get the missing message the server will have to send the 1000 or so packets that came along with the missing one as they were all in the same window or segment.

YOU WOULD NOT discard the message and then get the web server to send that and only that message again due to the fact that you cannot only send across one message, you need to send across the whole window or segment.  

> Which command should you run to verfy that RIPv2 is running and to verify that RIPv2 update and hold down timers?

the command that you would use would be:
```
show ip protocols
```
the reason that you would do this is that this will display the RIP process running as well as the settings for the hold down timers and update timers. Additionally, this command will show other information like filter lists, version and other protocols that are running on the device.  

YOU WOULD NOT RUN THE "show ip rip timers" command as that does not exist. what you would need to do is that you would run the "show rip timers basic" command, but it would not show that RIP is actually working, just how it is configured. 

> You are the network administrator for your company. You configure your network using the subnet 172.16.10.0/24. You are unable to access a remote host with the IP address 62.168.10.20. You check the connectivity using the ping command on the network router. The exhibit shows the output of the ping command. "U.U.U" what conclusion can be drawn from the output?

from the output of the ping command you can see that there is no route to the host, this is known by the fact that instead of "!!!!!" meaning all packets went through, or even "....." for none of the packets made it though we instead got "U.U.U" so the packets didn't even make it out of the network. From this we can assume that the packets would have not been able to find their way to their destination. The only conclusion that we can then make is that the router didnt know where to send the packets and therefor dropped them, and that is the answer. 

THE PACKETS COULD NOT HAVE BEEN blocked by an ACP as then the output would be "....." as none of them made it through, but the fact that there was not a route to the host means that its a problem with the router. 

> Which command should you use to verify the interfaces that have been configured on a router and are included in the RIP routing process?

to verify that certain interfaces and so on are actually running the RIP process then you would have to run the:
```
show ip protocols 
```
command. This is because you want to know if the **interfaces** are involved in the RIP process and so that command will show you that information. Additionally, if you wanted to know that RIP was actually running then you would want to know if it is in the running config and actually loaded in the system. The way that you would do this is that you would run the command:
```
show running-cofig
```
This will then show that RIP is loaded and currently active on the device. 

YOU WOULD NOT run the "shop ip rip database" as this would only show you the routing entries and not the interfaces and weather it is running. Additionally, you would not run the "show ip route" command as this would not actually show you the interfaces that have been discovered by the routing process just the ways that you can reach other networks.

> Which three statements are true about enabling port-security? 

When setting up port security "the default violation mode is shutdown". This is an important fact to remember because if the default mode was not shutdown then attacks could be allowed to  happen on the network due to the fact that after the timeout the attacker will have another attempt. To make sure things are the most secure the default mode should be to shutdown the port to keep everything safe. 

In addition to this you can use the command:
```
switchport port-security
```
to enable port security 
