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
![](https://i.imgur.com/67Apaoi.png)
## When data is sent between devices it depends on two types of protocols
1. [[TCP (Transmission control protocol)]]
2. [[UDP (User datagram protocol)]]
### [[TCP (Transmission control protocol)]]
#### uses a error checking system to ensure data is intact the reason behind this is because TCP is most commonly used such as email clients, file sharing as well as web browsing were data needs to be complete and cant risk being broken up. The error checking system verifies that all data is received prior to viewing it so that the data wont come in broken.
![](https://i.imgur.com/LTlL2Dq.png)
### [[UDP (User datagram protocol)]]
#### uses less data and does not check if the data is complete this is good for small chunks of data being sent over a network the issue is even if the data is corrupt or incomplete it will still send over the network to the the user. The pro to UDP over TCP is speed the down side is completion of data as stated before for larger files we risk data being lost as we can see in the picture below. This works well with video streaming as a skip in frame is OK in most cases.
![](https://i.imgur.com/PjcBPMm.png)
# [[Layer 3 - Network]]
![](https://i.imgur.com/MRCmASq.png)
### This layer deals with the routing of information and data, It uses two types or protocols to determine the fastest route to get data from the host to the device with little time. It uses:
1. [[OSPF (Open shortest path first)]]
2. [[RIP (Routing information protocol)]]
#### Everything on this layer is dealt with via [[IP Address]]
# [[Layer 2 - Data Link]]
![](https://i.imgur.com/xS4fLX4.png)
### This layer is uses the [[IP Address]] and [[MAC Addresses (Media Control Access)]] to assign it self to the [[NIC (Network interface card)]]
#### this later takes the IP and MAC addresses and assigns it to the NIC so that that it can be recognized on a network it litterly links the foot print to the card
# [[Layer 1 - Physical]]
![](https://i.imgur.com/MHkHmij.png)
### This is the hardware layer in this layer you can find things like cables
![](https://i.imgur.com/yHBr8CA.png)

---
# Packets and frames
## Are small pieces of data that are formed together. 
### **Frames** are located on the data link layer and do not contain a IP address They are are the host for the packets used to travel a network.
#### **Packets** are data that does not contain a IP address 
### **Packets** are tiny segments of data that get sent over a network 
#### **Packets** are good when sending small bits of data because they are broken up into smaller sections and sent over the network rather then in one large frame this causes less a chance of bottle necking a system. 
![](https://i.imgur.com/veNfAXY.png)

# TCP/IP (The Three-Way Handshake)
## [[Three-way-handshake]] **Syn, Syn/Ack, Ack**
### _TCP opening a connection_ 
- This is done threw a series of packets sent two and from two devices to help establish a connection this is done by method seen below
#### **SYN**
- This is the first step the devices sends out a packet to initiate the process 
#### **SYN/ACK**
- This packet is then sent to acknowledge that the packet was received and that the request for synchronization was received 
#### **ACK**
- This packet is the acknowledgment packet form the server or client that shows that the series of data or messages have been sent and received properly  
#### **DATA**
- Once the connection is made data is sent via this route 
#### **FIN**
- This is used once the connection is done to "Cleanly close" the connection
#### **RST**
- This only happens if the connection fails or has issues is a emergency closure of the connection happens if a connection was lost or there was data corrupted
![](https://i.imgur.com/Xglylno.png)

### _TCP closing a connection_
#### **FIN**
- It starts with a closure packet being sent 
#### **ACK**
- The receiving  devices then has to acknowledge that it was revived 
#### **FIN**
-  The receiving device then sends it own closure packet
#### **ACK**
- Then the main deceives ackowldges it receives it and the closure happens 
![](https://i.imgur.com/6Yy1WBc.png)

# UDP/IP
- User datagram protocol is like **tcp** Biggest difference is that its stateless and does not need a constant connection between the two devices 
- The three way handshake does not occur in UDP nor do the devices sync

# Ports 101
#### A few of the most common ports in cyber-security are 
## 21
- [[FTP]] **File transfer protocol**
## 22
- [[SSH]] **Secure shell**
## 80
- [[HTTP]] **Hyper text transfer protocol**
## 443
- [[HTTPS]] **Hyper text transfer protocol secure**
## 445
- [[SMB]] **Server message block**
## 3389
- [[RDP]] **Remote desktop protocol**

---

# Introduction to Port Forwarding
## [[Port Forwarding]]
- Opens up ports on a network to route traffic to different areas 
- A router is used / needed to Port forward 
# Firewalls 101
- Firewall is used to help determine what data can enter and leave a network 
- Firewalls come in two flavors
## Stateful
-  A Stateful firewall requires a full connection and uses a lot of resources to do its job. If the connection from a host is bad it will deny the full host from connecting
## Stateless
- A stateless Firewall checks individual packets and and will block those that are fragmented or corrupt they also use less resources and they issue is these type are not that smart they are rule based and if a rule is not meant it will not let the packet pass through. These work best with DOS attacks 
# VPN Basics
#### VPN is used to connect multiple devices on a network under one network to mask there identity and prevent data form being scraped 
##### This is done through different technologies such as:
1. [[PPP]]
2. [[PPTP]]
3. [[IPSec]]

---

# What is DNS?
### DNS or (Domain Name System)
#### is a way of viewing the IP of a website in a simple form such as 123.124.12.34 = tryhackme.com**Which is a lot more reasonable to remember then the full IP **
![](https://i.imgur.com/A7OpzQV.png)

# Domain Hierarchy
![](https://i.imgur.com/B7K0s0I.png)
### TLD (Top level domain)
- is the section to the far right of a site example: `tryhackme.com` the TLD would be `.com` some other examples would be `.com,.org.info,.io,.net`
### Second level domain
- With `tryhackme.com` as a example to `tryhackme` is the Second level domain the max it can be is 63 characters 
### Subdomain
- with `admin.tryhackme.com` the `admin` is the subdomain as it sits to the far left of the second level domain the max it and be is 253 characters 
# Record Types
## DNS record types
### A record
- resolve to IPv4 addresses, for example 104.26.10.229
### AAAA record
- resolve to IPv6 addresses, for example 2606:4700:20::681a:be5
### CNAME record
### MX record
### TXT record
# HTTP in detail
## Hypertext transfer protocol
- Is a set of rules used to transfer data via html for websites
## Https - Hypertext transfer protocol secure
- is the same as the above except the data is encrypted 
---
# Request and response
![](https://i.imgur.com/GXqO5Wi.png)
#### A [[URL]] is broken into sections
1. Scheme - Instructs what protocol to use such as http, https, ftp
2. User - is the auth for the login
3. Host - is the domain name or IP address you are connecting to
4. Port 
5. Query string - extra info
6. Fragment - reference to a pages location 
````http
GET / HTTP/1.1
Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/
````
#### The above segment is broken down as follows
1. This request is using the get method it lists what HTTP protocol we are using
2. The host name
3. What web server we are using 
4. What the referrer is
5. Blank line to break to inform the request is done
#### **Example Response:**
````http
HTTP/1.1 200 OK
Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98

<html>
<head>
    <title>TryHackMe</title>
</head>
<body>
    Welcome To TryHackMe.com
</body>
</html>
````
Only new thing here is line 3 , 4 and 5 
3. Data and time request was make
4. The type of content header
5. The length of the response
---
### **Content-length** tells the browser how much data to expect
# [[HTTP methods]]
## Below are some of the most common methods used
### [[GET Request]]
- used to get info on a web server
### [[POST Request]]
- used to submit data to a web server
### [[PUT Request]]
- used to submit update data to a web server
### [[DELETE Request]]
- used to remove or delete data from a web server
# [[HTTP - Status Codes]]
#### Status codes can be broken down into 5 different ranges
![](https://i.imgur.com/zSpetdD.png)
#### Common Status codes
![](https://i.imgur.com/CVGeoxi.png)
![](https://i.imgur.com/TjoGrEv.png)
# [[Headers]]
## Headers are not needed to view a site but when not using them it can cause the site to be hard to use and view
### Common request headers
![](https://i.imgur.com/qzE7512.png)
### Common response headers
![](https://i.imgur.com/OcqSRqf.png)

---
# Cookies
##### are used as a authentication method for websites they are viewable but hard to understand they use tokens rather then passwords
#### You can view them by looking at the browser developer tools under the network tab
###### The header used to save cookies on you computer is the set-cookie header
---
# Making request
- In this room we tried out some commands using Get, post and delete.
---
# How websites work
## Web-server **Is a dedicated computer handling your request**
![](https://i.imgur.com/cftjWcx.png)
### There are two major components that make up a website 
1. Front-end **Client side**
	- The way the browser process and renders a site for viewing 
1. Back-end  **Server side**
	- A server that process my requests and commands

---

# HTML
## Websites are made using 3 main types of code
### HTML **Used to build a side and give it structure**
### CSS **Used to make a site styled**
### Java **Used to add complex features**
#### HTML structure
![](https://i.imgur.com/qxC572S.png)
##### `HTML` header is the there is a start and end to the tag 
##### `head` contains the information on the page
##### `body` shows the elements that are on the page 
##### `h1` defines a large heading
##### `p` defines a paragraph 
##### `img` image
##### `button` button
## etc...

---
# [[JavaScript]]
- JavaScript is one of the most used langues in the programming world, while HTML is used to design a page. JavaScript is used to control the functions of its content
- JavaScript allows us to program things such as buttons and other interactive elements to a web page
#### It can be uploaded on to the html via two methods
1. `<script>`script
2. `<src>`source
#### We can also do things like on click or on hover with JavaScript
---
# Sensitive Data Exposure
![](https://i.imgur.com/ZkP2JOb.png)
- This happens when a user forgets to remove sensitive notes or login info from the html file before putting the site live this is why we need to always check the html of a site prior to a attack to see what info the admin might of forgotten to leave

---
# HTML Injection
- This happens when a web developer fails to sanitize the java and html inputs on a page. For instance a page with a name input when the user puts there name in the box and submits it the name appears on the page. What stops the attacker from putting there own JavaScript or html in the text box and sending it via the site. This is HTML Injection in its simplest form as we can see below.
![](https://i.imgur.com/CNJ0kj0.png)
##### In the assignment we used the text field provided and did a injection for a site and hid its identity from the victim using
![](https://i.imgur.com/Q9qOv4z.png)

---
# Other components
#### **Load Balancers**
- There main job is to distribute server load, when you connect to a site that uses a load balancer it starts buy checking servers its connected to see which one can handle the request. I then sends you there, it does with each user and sends them to the server that has the most room and spreads out users so the servers don't get bogged down. It also does periodic checks on the server.
![](https://i.imgur.com/WBWgaOY.png)
#### **CDN (Content Delivery Networks)**
- This is a server that can host things like images and JavaScript when a user connects it will send them to the server that is closest and best serve them for there needs. I litterly delivers content.
#### **Databases**
- Stores info in text files to servers there is many types not limited to MySQL, MSSQL, MongoDB, GraphQL, Postgres, and more;
#### **WAF (Web Application Firewall)**
- Works as firewall but for a network rather then a device 
![](https://i.imgur.com/7L1kZXt.png)

---
# How Web servers work.
##### Web-server
- Is software that listens for incoming connections and connects the clients to the content via HTTP protocols 
##### Virtual Hosts
- Are text based files that are used to help match the host name to the request. If it finds a match it the correct site will be provided if the match is not there it will default to the main page
##### Static Vs. Dynamic Content
- 
