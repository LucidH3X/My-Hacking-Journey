## Contents <img src = "https://razvioverflow.github.io/images/tryhackme/logo_0.png" width = 332px> </h2>
* [Info / Topics](README.md)
* [Log - click here to see my progress](log.md)

#   What is Networking?
## A network is 2 or more devices connected together
### Networks can be made up of 2 different types
#### [[Private Networks]]
#### [[Public Networks]]
- Devices on a network need to be identifiable this is done through 
	- Ip address
	- [[MAC Addresses (Media Control Access)]]

## Ip addresses
- Are used to identify a device on a network for a period of time
![](https://i.imgur.com/HZuhI0Q.png)
- A IP address can change from device to device but it **Cannot** be active more then once on the same network
- _IP addresses can be on both a public and private network at the same time_
### IP addresses come in two types
1. IPv4 
2. IPv6 - This is the newest addition to the family it can house over 340 trillion devices 
![](https://i.imgur.com/C9ry8NG.png)

## MAC addresses
**When a device is made on the mother board at the factory a MAC address is assigned on the chip of the motherboard** 
- It uses a 12 digit hex decimal number to identify itself
![](https://i.imgur.com/v3jZIGX.png)
- The first 6 Numbers Identifies the company who made it
- The last 6 are unique to the device itself
**A MAC address can how ever be faked by a process called [[Spoofing]]**
##### Places like hotels and coffee shops use MAC addresses to register computers on Paid networks to control internet traffic but with [[Spoofing]] you can get around this by cloning your self on the network so It trusts your device without showing your true identity

# [[ping]] uses [[ICMP]] internet control message protocol
- Its used to test an see how reliable the connection is between the device and the server its trying to connect to
## To use ping we use `ping` in command window or terminal

# Intro to [[LAN]]
## **Local Area Network [[LAN]] Topologies**
_In networking we can see 3 styles of typologies that are commonly used_
1. Star 
	- In this topology we can see all devices connected individually to a center hub or server
	- It is the most common due to cost as well as reliability and scalability
	- The large issue with this system is if we take down the hub the network goes down with it
![](https://i.imgur.com/5sArMqj.png)
2. Bus
	- Main issue with the topology is that all traffic runs along one back bone
	- If the backbone was to fail the entire network will go down this can happen to due a line severed
	- You can also drop the network by simply storming it with to many packets which will plug up the back bone and cause the network to go down.
![](https://i.imgur.com/ByREgoH.png)
3. Ring
	- it works by connect ll devices together in a ring type set up. This works well because it uses less wires and also needs less hardware they issue is the system is prone to bottle necks
	- If you were to disrupt one device on this set up it could end the chain causing the network to crash this can be done by bottle necking, cut cable or broken device.
![](https://i.imgur.com/BDRcTwm.png)
_What is a switch_
**They are used to aggregate devices over a network,  other devices are plugged into the switch via a rj cable and the switch it self is connected to the main router.** 
_What is a router_
**Its the job of the router to connect network and pass data between them. It helps to route the traffic from different devices to other locations on the network.**

# A Primer on Subnetting
**Subnetting is the process of splitting up networks into smaller networks within itself**
## Subnetting 
- Is used by network admins to assign specific parts of network
- This is done by splitting up the number of hosts that we can fit on a network
#### [[Subnet mask]]
![](https://i.imgur.com/vvJq337.png)
- Is made up of four sections just a IP address 
- **Its represented as a number of four bytes (32 bits), ranging from 0 to 255 (0-255)**

##### Subnets use IP address in 3 ways 
1. identify a network address
2. identify a host address
3. identify a default gateway

#### A home network does need Subnetting because it uses less the 250 devices but a place like a business might use it 
**Subnetting** allows a place like a Cafe to split up a network so we can have 2 mini networks "Subnet" such as one for the registers and and employees another for gen public and hotpot.

# The [[ARP Protocol]]
- Allows a Device to to associate its [[MAC Addresses (Media Control Access)]] and [[IP Address]] on a network
- Each device on a network will keep a active log of [[MAC Addresses (Media Control Access)]] associated with a device 
### In order for [[ARP Protocol]] to work it uses two identifiers to to help map [[IP Address]] and [[MAC Addresses (Media Control Access)]] together
1. [[ARP Request]]
2. [[ARP Reply]]
- This works by [[ARP Request]] sending out a request to see if the [[MAC Addresses (Media Control Access)]] attached to a [[IP Address]] is on a network if it is, the Network replies back with a t [[ARP Reply]] to confirm that it located it on the network
- It then will sore the info on the Cache on the network under [[ARP Entry]]
![](https://i.imgur.com/EeeFUzj.png)

#  The DHCP Protocol
- [[DHCP(Dynamic Host Configuration Protocol)]]
When a device connects to a network it uses the [[DHCP(Dynamic Host Configuration Protocol)]] to to get a [[IP Address]] assigned to it. It goes there a process using the steps below
1. [[DHCP Discover]]
	- It uses this to see if any servers are on the network
1. [[DHCP Offer]]
	- If it does not reply back with a IP address it uses offer to give one
1. [[DHCP Request]]
	- It uses request to confirm that it wants the IP address 
1. [[DHCP ACK]]
	- Then uses ACK to acknowledge that it received the request for the IP address assignment 
![](https://i.imgur.com/HB0NMuW.png)

# What is the OSI Model?
- [[ OSI model (or Open Systems Interconnection Model)]]
![](https://i.imgur.com/NZ8UFkN.png)
- At every layer information is added to the data that is passing through the layer this is done through a process called [[Encapsulation]]
- The [[OSI model (or Open Systems Interconnection Model)]] Has 7 layers

# [[Layer 7 - Application]]
![](https://i.imgur.com/EkPrXxD.png)
- This layer is the one we use the most it is set with the protocols and the rules set in place that determine how we interact with data sent or received

# [[Layer 6 - Presentation]]
![](https://i.imgur.com/1cQxMDN.png)
- This later helps to standardize all info that is sent over the network
- An example would be a email sent from Gmail to thunder bird even though the client is different the email is the same cross platform and cross client. 
# [[Layer 5 - Session]]
![](https://i.imgur.com/AbPuO7Q.png)
- This layer synchronizes the data to make sure they are both on the same page prior to data being sent or received
- Once the data is received and sorted through it begins to sort the data into smaller chunks called [[Packets]] one at a time
- This is done to protect data loss so that if the the connection goes down only a part of the data was sent and lost rather then the full stream
# [[Layer 4  - Transport ]]
