# ICND1 config commands

## <div id="toc"></div> TOC
- [Securing switches and routers](#sec-sw)
    - [Banners](#banners)
    - [Applying ACLs to vty lines](#vty-ACLs)
- [Port security](#port-sec)
- [Configuring switch ports](#swports)
- [CDP](#cdp)
- [Interface information](#if-info)
- [Classful networks](#class-ntwk)
- [Router commands](#rt-cmd)
- [DHCP](#dhcp)
- [NAT](#nat)
  - [Static NAT](#snat)
  - [Dynamic NAT](#dnat)
  - [NAT overload](#onat)
- [Telnet/suspend](#telnet)
- [RIPv2](#ripv2)
- [Syslog](#syslog)

## <div id="sec-sw"></div> Securing switches and routers
To access a switch via telnet/ssh, configure an IP addr on an SVI.

    ip default-gateway <ip addr>

    service password-encryption
    enable secret <secret>
    line console 0
    password <pass>                    !-- line config
    username <user> password <pass>    !-- global config
    login                              !-- line config; req passwd
    line vty <first> <last>
    transport input ssh                !-- can do "telnet ssh"
    login local                        !-- req username and passwd
    exec-timeout 0 0                   !-- no limit
    logging synchronous                !-- wait for output before logging a msg

    ip domain-name test.com
    ip ssh version 2
    crypto key generate rsa

### <div id="banners"></div> Banners

    banner motd +msg+ !-- where + is the delimiter
    baanner login +msg+
    banner exec +msg+
    
### <div id="vty-ACLs"></div> Applying ACLs to VTY lines

    access-list 3 permit 10.1.1.0 0.0.0.255
    line vty 0 4
    access-class 3 in // instead of access-group


### Show commands

    show ip ssh !-- version
    show ssh    !-- clients connected

[Back to top](#toc)

## <div id="port-sec"></div>Configuring switch port security

    switchport port-security                          !-- enable with all defaults
    switchport port-security maximum <num>            !-- max num mac addr
    switchport port-security violation <mode>         !-- protect | restrict | shutdown
    switchport port-security mac-address <MAC addr>   !-- repeat as nec
    switchport port-security mac-address sticky       !-- for dynamic learning

### Port security show commands

    show port-security                                !-- table of all ports
    show port security interface <if>
    show running-config

[Back to top](#toc)

## <div id="swports"></div> Configuring switchports (access, trunk, routed)

    vlan 2
    name <name>
    shutdown

    !-- access and voice
    interface <if>
    switchport mode access
    switchport access vlan <num>
    switchport voice vlan <num>

    !-- trunk
    switchport trunk encapsulation dot1q
    switchport mode trunk
    switchport trunk native vlan <num>
    switchport trunk allowed vlan <num or range>
    switchport trunk allowed vlan add <num or range>
    switchport trunk allowed vlan remove <num or range>

    !-- DTP, if-config
    switchport mode dynamic {desirable | auto | trunk}
    switchport nonegotiate !-- no DTP

    !-- routed
    no switchport
    ip address <addr> <mask>

### Show commands

    show vlan brief
    show interface switchport
    show interface trunk
    show run interface <if>

[Back to top](#toc)

## <div id="cdp"></div> CDP

    cdp enable !-- if-config
    cdp run    !-- global

### CDP show commands

    !-- neighbors
    show cdp neighbors
    show cdp neighbors detail
    show cdp neighbors interface <if>
    show cdp entry <fqdn>

    !-- CDP protocol
    show cdp
    show cdp interface [<if>]
    show cdp traffic

[Back to top](#toc)

## <div id="if-info"></div> Interface information

### Counters and their descriptions
* __Runts:__ Frames below min frame size requirement of 64 bytes
    - Can be caused by collisions
* __Giants__: Frames bigger than the max frame size req of 1518 bytes
* __Input errors__: Total of many counters, including runts, giants, no buffer, CRC, frame overrun, and ignored counts
* __CRC__: Received frames that didn't pass the FCS math
    - Can be caused by collisions, bad cable, or bad SFP.
* __Frame__: Received frames with an illegal format, such as ending in partial byte
    - Can be caused by collisions
* __Packets output__: Total # of frames forwarded out the interface
* __Output errors__: Total # of frames the switch tried to transmit but a problem occurred
* __Collisions__: All collisions that occur when the interface is transmitting a frame.
* __Late collisions__: Collisions that occur after the 64th byte of the frame has been transmitted
    - Usually points to a duplex mismatch.

### Show commands

    show interfaces [<if>]
    show interfaces description
    show interfaces status

[Back to top](#toc)

## <div id="class-ntwk"></div> Classful networks based on the first octect

| Class | First octect | Purpose      |
|:-----:|-------------:|:-------------|
| A     | 1 - 126      | Unicast      |
| B     | 128 - 191    | Unicast      |
| C     | 191 - 223    | Unicast      |
| D     | 224 - 239    | Multicast    |
| E     | 240 - 255    | Experimental |

[Back to top](#toc)

## <div id="rt-cmd"></div> Router commands

    interface <if>
    no ip address
    interface <if>.20 encapsulation dot1q 20 !-- vlan 20
    ip address <addr> <mask>
    ip address <addr> <mask> secondary

    !-- serial interfaces
    clock rate <speed>                            !-- varies btw routers
    bandwidth <speed>

    !-- Routes
    ip route 0.0.0.0 0.0.0.0 <outgoing if>          !-- route of last resort
    ip route <subnet id> <mask> null0               !-- discard route (for BGP)
    ip route <ntwk> <mask> <next hop> <admin dist>  !-- fallback if rt protocol fails

    !-- DNS name resolution
    ip name-server <dns server addr>
    ip host name <addr>
    no ip domain-lookup                !-- disable the DNS resolver

### Router show commands

    show ip route
    show ip interface brief
    show vlans
    show protocols [<if>]
    show controllers [<if>]
    show ip protocols

[Back to top](#toc)

## <div id="dhcp"></div> DHCP

    !-- addresses to exclude form DHCP pool
    ip dhcp excluded-address <first> [<last>]

    ip dhcp pool <name>
    network <subnet ID> <mask>
    default-router <addr1> [<addr2>] ...
    dns-server <addr1> [<addr2>] ...
    least <days> <hrs> <min>
    domain-name <example.com>
    next-server <address>      !-- tftp server if needed

### DHCP show commands

    show ip dhcp bindings
    show ip dhcp pool <name>
    show ip dhcp server statistics
    show ip dhcp conflict

### Helper address

    ip helper-address <DHCP server addr>

[Back to top](#toc)

## <div id="nat"></div> NAT

### <div id="snat"></div> Static NAT
1. Configure interfaces to be in the inside part of the NAT design using the ip nat inside interface subcommand.
2. Configure interfaces to be in the outside part of the NAT design using the ip nat outside interface subcommand.
3. Configure the static mappings with the ip nat inside source static <inside local> <inside global> global configuration command.

__Example__

    !-- from inside interface
    ip address 192.168.1.1 255.255.255.0
    ip nat inside

    !-- from outside interface
    ip address 200.1.1.251 255.255.255.0
    ip nat outside

    !-- from global config
    ip nat inside source static 192.168.1.2 11.1.1.3
    ip nat inside source static 192.168.1.3 11.1.1.4
    ip nat inside source static 192.168.1.4 11.1.1.5

### <div id="dnat"></div> Dynamic NAT
1. Configure interfaces to be in the inside part of the NAT design using the ip nat inside interface subcommand.
2. Configure interfaces to be in the outside part of the NAT design using the ip nat outside interface subcommand.
3. Configure an ACL that matches the packets entering inside interfaces for which NAT should be performed.
4. Configure the pool of public registered IP addresses using the ip nat pool name first-address last-address netmask subnet-mask global configuration command.
5. Enable dynamic NAT by referencing the ACL (Step 3) and pool (Step 4) with the ip nat inside source list acl-number pool pool-name global configuration command.

__Example__

    interface et0/0
    ip address 10.1.1.3 255.255.255.0
    ip nat inside

    interface Serial0/0
    ip address 200.1.1.251 255.255.255.0
    ip nat outside

    !-- First/last IP addresses in the pool, plut subnet mask
    ip nat pool fred 200.1.1.1 200.1.1.2 netmask 255.255.255.252

    !-- ACL indicating inside IP addresses
    access-list 1 permit 10.1.1.0 0.0.0.255

    !-- Using the ACL to translate addresses
    ip nat inside source list 1 pool fred

### <div id="onat"></div> NAT overload (PAT)
1. Config inside interface with ip nat inside
2. Config outside interface with ip nat outside
3. Create an ACL permitting the inside addresses
4. Enter `ip nat inside source list <src ACL> interface <outside if> overload`

__Example__

    !-- inside interface (e0/0)
    ip nat inside

    !-- outside interface (e0/1)
    ip nat outside

    !-- global config
    access-list 1 permit 192.168.1.0 0.0.0.255
    ip nat inside source list 1 int e0/1 overload

### Show commands

    show ip nat translations
    show ip nat statistics

[Back to top](#toc)

## <div id="telnet"></div> Telnet and suspend

You can connect from a Cisco device to another via Telnet or SSH. You can suspend a Telnet/SSH session to leave it active while connecting to other devices and thereby having concurrent Telnet/SSH sessions you can switch between.

    Cindy# telnet Bronx
    
    Password:            !-- Access verification
    
    Bronx>               !-- press Ctrl + Shift + 6, x
    
    Cindy# telnet NewYork
    
    Password:            !-- Access verification
    
    NewYork>             !-- press Ctrl + Shift + 6, x
    
    !-- back at Cindy as a result

    Cindy# show sessions !-- suspended Telnet sessions
    
    Conn  Host      Address     Byte    Idle    Conn Name
      1   Bronx     10.1.4.252     0       0    Bronx
    * 2   NewYork   10.1.6.253     0       0    NewYork
    
    Cindy# where         !-- same as show sessions
    
    Conn  Host      Address     Byte    Idle    Conn Name
      1   Bronx     10.1.4.252     0       0    Bronx
    * 2   NewYork   10.1.6.253     0       0    NewYork
    
    Cindy# resume 1      !-- resume connection 1

    !-- OR ---
    
    Cindy# disconnect 1

[Back to top](#toc)

## <div id="ripv2"></div> RIPv2

    router rip
    version 2
    network <ntwk ID>
    passive-interface <if>
    maximum-paths <num>
    no auto-summary         !-- must include to disable

### RIP show commands

    show ip rip database
    show ip protocols

## <div id="syslog"></div> Syslog

IOS shows console users log messages in the terminal by default

    logging console            !-- default
    no logging console

VTY users don't see log messages in the terminal by default

    logging monitor
    terminal monitor           !-- after login

Storing messages for later review

    loggign buffered           !-- store in RAM; global config
    show logging

Syslog protocol to store log messages in a centralized syslog server via UDP

    logging <addr | fqdn>      !-- global command

Components of a syslog message:

    Dec 18 17:10:15.079: %LINEPROTO-5-UPDOWN: Line protocol on Interface
    FastEthernet0/0, changed state to down

- __A timestamp__
- __The facility on the router that generated the message:__ %LINEPROTO
- __The severity level:__ 5
- __A mnemonic for the message:__ UPDOWN
- __The description:__ Line protocol on Interface FastEthernet0/0, changed state to down

Toggle the timestamp (on by default) and sequence numbers (off by default)

   !-- global config
    no service timestamps
    service sequence-numbers

Log message severity levels

    logging console <lvl name | lvl num>
    logging monitor <lvl name | lvl num>
    logging buffered <lvl name | lvl num>
    logging trap <lvl name | lvl num>

0. Emergency
1. Alert
2. Critical
3. Error
4. Warning
5. Notification
6. Informational
7. Debug

Eliminate a crisis, even when no-one is dead

### Configuring and verifying logging

    logging console 7
    logging monitor debug
    logging buffered 4
    logging host 172.16.3.9
    logging trap warning       !-- syslog server

    show logging               !-- shows the logging levels set

[Back to top](#toc)