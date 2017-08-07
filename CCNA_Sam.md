# CCNA Notes
---
# ICND1
## General Notes

### Timeline
* 2 Weeks Training (Week 1 GPK, Week 2 BFL)

* 1 Week self study
* Exam at the end of W3

### Course Goals
* Describe network fundementals and implement a simple LAN
* Establish Network fundementals
* Expand a small network to a medium-sized routing-enmabled network
* Confifure, manage, secure and monitor Cisco devices
* Describe IPv6 basics

### Extra Content
* CEF: Cisco Express Forwarding

### Exercise Types:
* Challenge Exercises
* Discovery Extercises

### Certified Mock Exam Questions:
* MeasureUp
* Bolan.com (?)

## Module Notes

### Module 1: Building a Simple Network
#### What is a Network?
* Networks carry data in varying environments.
* Large networks may be multi-location, e.g. Home Office, Branchg Office, Main Office & Mobile all on a single network.

#### Physical Components of a Network
* Networks are composed of:
    * Endpoints - PCs, servers, printers etc.
    * Interconnections - NICs, Network Media (e.g. UTP or STP in varying categories) & Connectors (e.g. RJ-i45)
    * Switches - Endpoints connect to these, and they can share a common network
    * Routers - Select the best route for traffic from one network to another
    * WLAN Devices - Connect Wireless Devices to a network
    * APs - Allow wireless devices to communciate with a wired network
    * WLAN Controllers - Devices that network admins can use to manage APs in large quantities
    * Firewalls - Network security systems that control and monitor incoming and outgoing traffic based on provided rules

#### Characteristics of a Network
Network characteristics are as follows:
* Topology - Physcial (e.g. arrangment of cables, devices and end systems) or Logical (e.g. the path that the data follows within a network) 
* Speed - The data travel rate per second given in bits within a link in the network (bitrate)
* Cost - General expendature for purchasing, installing and maintiaining the elements in a network
* Security - How protected the network is, including the information transferred across the network
* Availability - Measure of probability that the netowork will be available for use when required
    * This can be calculated with the following formula:
    `((minutes in a year) - (number of minutes if down time in a year) / number of minutes in a year) x 100` 
* Scalability - How easily the network can accokoate more users and data transmission requirements
* Reliability - The dependability of components that the network is composed of

#### Physical vs. Logical Topology
* Physical Topologies
    * Bus - Every workstation is connected to the main network medium. Each device is directly connected to another
    ![Bus Topology](https://upload.wikimedia.org/wikipedia/commons/thumb/4/47/BusNetwork.svg/527px-BusNetwork.svg.png)
    * Ring - Each device is cabled together in a ring, so that the last device is connected to the first, etc.
    ![Ring Topology](https://upload.wikimedia.org/wikipedia/commons/thumb/7/75/RingNetwork.svg/440px-RingNetwork.svg.png)
    * Star - The most common type of topology. A central device is connected to all of the endpoints and other network devices
    ![Star Topology](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d0/StarNetwork.svg/440px-StarNetwork.svg.png)
    * Mesh - Every device is connected to one another, allowing higher redundancy tollerences
    ![Mesh Topology](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/NetworkTopology-FullyConnected.png/440px-NetworkTopology-FullyConnected.png)
    * Logical Topologies - The path that the data follows within a network

#### Interpreting a network diagram
* Various connection interfaces are used in a netowork. On a network diagram they are denoted as follows:
    * S0/0/0 - **S**erial
    * Gi0/0 - **Gi**gabit Ethernet
    * Fa0/0 - **Fa**st Ethernet
    * / -  Slash notation of subnet mask used

#### Impact of User Applications on the Network
* Applications can perfect network performace, and vice versa.
There are varying types of applications, such as:
    * Batch
        * No Direct Human Interactions
	* Bandwith non-critical
	* e.g. TFP, TFTP, inventory updates
    * Interactive
    	* Human-Machine interactions
        * Human waits for response, therefore the response time is important but not critical
	* e.g. Inventory enquiries
    * Real-Time Applications
	* End-to-end latency is critical
	* e.g. VoIP, Video calling
        * Human-Human interaction
* QoS (Quality of Service) is important. It allows for the granting of higher priority to different types of data e.g. VoIP Packets.

#### Host-to-Host Communications
* Varying types of host-to-host models exist:
    * Older Models e.g. Used by Proprietary Software
    * Standards-based Models e.g. Used by Multivendor Software (OSI, TCP/IP Models)
* OSI Model

| ↓| OSI Model   |
| -| :----------:|
| ↓| Application |
| ↓| Presentation|
| ↓| Session     |
| ↓| Transport   |
| ↓| Network     |
| ↓| Data Link   |
| ↓| Physical    |

    * The OSI Model is a layer-based reference model that provides functions and services that can occur at each layer.
    * It describes the interaction between each layer above and below it.
    * It is standards based, allowing vendors a set of standards that ensure compatability between various types of network technology worldwide.
    * The layer functions are as follows: 
        * Session - Port numbers are present in both sending and recieving capacities. e.g. Internet requests will be sent to port 80, but will be recieved on veryiong port numbers dependant on my Session ID
 
* TCP/IP Model

| ↓| TCP/IP Model|
| -| :----------:|
| ↓| Application |
| ↓| Transport   |
| ↓| Internet    |
| ↓| Data Link   |

    * The layer of the TCP/IP Model map onto the OSI model as follows:

| ↓| OSI Model                         | TCP/IP Model|
| -| :--------------------------------:| :----------:|
| ↓| Application, Presentation, Session| Application |
| ↓| Transport                         | Transport   |
| ↓| Network                           | Internet    |
| ↓| Data Link & Physical              | Link        |

    * The layer functions are as follows:

* Peer-to-Peer Communications
    * At each layer of communciation a different Protocol Data Unit (PDU) is used, for example:

| ↓| Sender     | PDU    | Reciever   |
| -| :---------:| :-----:| :---------:|
| ↓| Application| Data   | Application|
| ↓| Transport  | Segment| Transport  |
| ↓| Internet   | Packet | Internet   |
| ↓| Link       | Frame  | Link       |

### Module 2: Establishing internet connectivity

### Module 3: Summary Challenge

### Module 4: Building a Medium-Sized Network

### Module 5: Network Device Managment & Security

### Module 6: Summary Challenge

### Module 7: Introducing IPv6

---
