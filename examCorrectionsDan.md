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

 
