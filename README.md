# Net Practice

This project is a general practice exercise to let you discover networking.

"Here we go again". This is what I have in mind when I know that I have to do this project. Why? Because I have to relearn how to everything about networks because I already "give back" all the knowledge to my lecturer. 🤡

To prevent this from happening again, I decided to write this README.md to help me remember the knowledge that I have learned along the process. 🤓

> Disclaimer: There might be some stuff here that is not 100% correct. If you find any, please do your own research or contact me to fix it. Thanks!

> Another disclaimer: This README file does not include everything you need to know about networking. It only includes the stuff that I think is related to this project. There are more topics that you can explore on such as network design principles, network security, and etc.

## Table of Contents

- [Net Practice](#net-practice)
  - [Table of Contents](#table-of-contents)
  - [Basics of Networking](#basics-of-networking)
    - [Networks](#networks)
    - [Importance of networks](#importance-of-networks)
    - [OSI Model](#osi-model)
    - [TCP/IP Model](#tcpip-model)
    - [IP addresses](#ip-addresses)
      - [IPv4 vs IPv6](#ipv4-vs-ipv6)
      - [Static IP vs Dynamic IP](#static-ip-vs-dynamic-ip)
      - [Public vs Private IP addresses](#public-vs-private-ip-addresses)
      - [IP address classes](#ip-address-classes)
      - [DHCP](#dhcp)
      - [Subnetting](#subnetting)
      - [Routing](#routing)
      - [Switching](#switching)
  - [Network Components and Devices](#network-components-and-devices)
    - [Routers](#routers)
    - [Switches](#switches)
    - [Hub](#hub)
  - [Network configuration](#network-configuration)
    - [Subnet Mask](#subnet-mask)
      - [CIDR - Classless Inter-Domain Routing (Slash Notation)](#cidr---classless-inter-domain-routing-slash-notation)

## Basics of Networking

### Networks

In the context of computing, a network refers to a **collection of interconnected devices**, such as computers, servers, printers, and other devices, that are **linked together to facilitate communication and the sharing of resources**. These devices **can be physically connected by cables or wirelessly connected** through technologies like WI-FI.

The primary purpose of a network is to enable communication and data transfer between devices. By connecting devices in a network, users can:

1. Share information
2. Access shared resources
3. Collaborate on projects (using software like Google Docs, Email, etc.)
4. Communivate with each other (using software like Skype, Zoom, etc.)

Network can be categorized based on its size. They can be as small as a local network in a home or office, connecting a few devices, or as large as a global network, like the internet, which interconnects billions of devices worldwide. Network can be classified into three types based on their scale:

1. **Local Area Network (LAN)**
   
   A type of network that spans a relatively small geographical area, such as home, office building, or campus. It connects devices within a few hundred meters to a few kilometers. LANs are commonly used for sharing files, printers, and internet access among devices in a local environemnt. Ethernet is a common technology used in LANs. LANs usually owned and managed by an individual or organization.

   > Ethernet is a technology that allows devices like computers, printers, and routers to connect and communicate with each other wihin a small area, like an office or home. It uses a special cables to send and receive data between devices.

2. **Wide Area Network (WAN)**

  A WAN is a network that covers a large geographical area, like multiple cities, countries or even continents. WANs connect multiple LANs and other networks, enabling communication and data transfer over long distance. Internet is the largest WAN in the world. They typically rely on leased lines, satellite links to establish connectivity accross vast distances.

3. **Metropolitan Area Network (MAN)**

  This type of network covers a larger geographical area than a LAN but smaller than a WAN. It typically spans a city or a town, connecting multiple LANs like WANs. They are commonly employed by service providers or institutions to provide internet connectivity to a large number of users.

### Importance of networks

1. Communication and Collaboration. They enable sharing of information, resources, and services, making collaboration and communication much easier.
2. Resource sharing. Allow devices to share resources such as printer, scnanners and storage devices, without needing each devices to have separate resources. This will helps reduce to cost savings and efficiency.
3. Data transfer. They allow the information can be accessed and shared from anywhere wihtin the network, allowing for easy retriveval of files, databases, and etc.
4. Internet access. Allsow users to access the internet, access to vast amount of information, connects to people, organization worldwide.

> There are many more importance of networks. But i'm just going to list a few here.

### OSI Model

OSI model is a conceptual framework that defines the functions and interactions of various network protocols and technologies. It consists of sever layers:

> PLEASE DO NOT THROW SAUSAGE PIZZA AWAY

![OSI Model](img/osi-model.jpeg)

1. Physical layer
   
  This layer is responsible for transmitting raw data bits over physical medium, such as cables or wireless signals. It deals with the characteristics like voltage, data rates, cables, and etc.

2. Data link layer

  This layer provides error-free transmission of data frames between directly connected nodes. It ensures data integrity, performs error detection and correction.

3. Network layer

  This layer is responsible for addressing, routing, and packaging data packets. It determines the best path for data to travel from source to destination using routing protocols and IP addressing.

4. Transport layer

  This layer ensures reliable and orderly delivery of data between end systems. It establishes a connection between the source and destination, breaks down data into smaller units, and ensures that all packets are delivered correctly. Example: TCP and UDP.

5. Session layer

  This layer establishes, maintains, and terminates communication sessions between applications. It manages the coordination and synchronization of data exchange, allowing for efficient communication between endpoints.

6. Presentation layer

  This layer handles the data formatting and conversion functions, ensuring that data is readable by the application layer. It is responsible for data compression, encryption, and decryption.

7. Application layer

  This layer is the closest layer to the end-user and provides network services to applications. It enables users to access network resources and services, such as email, file transfer, and web browsing.


This model provides a structured approach to understanding and organizing network communcation, ensuring compatibility between different systems. It servers as a reference for designing, implementing, and troubleshooting network protocols and systems.

These seven layers of the OSI model work together to enable reliable, efficient and standardized communication accross networks. Each layer has its own specific functions and interacts with adjacent layers to ensuer seamless data transfer.

When a data packet is sent, it traverses the OSI model from the application layer to the physical layer, where it is transmitted (encapsulation). On the receiving side, the packet travels from the physical layer to the application layer, where it is processed (decapsulation). 

### TCP/IP Model

TCP/IP model, also known as the **Internet Protocol Suite**, is a conceptual framework that outlines the protocols and standards used for communication on the internet. It is named after its two primary protocols: TCP (Transmission Control Protocol) and IP (Internet Protocol).

OSI model is a theoretical model, while TCP/IP model is a practical implementation of the OSI model. It consists of four layers:

1. Application layer
   
  Combine the top three layers of the OSI model into a single layer (Application, Presentation, Session). It includes protocols for specific applications like HTTP, FTP, SMTP, DNS, and etc.

2. Transport layer

  The same as the transport layer in the OSI model. It deals with end-to-end communication, ensuring reliable and ordered delivery of data. TCP and UDP are the primary protocols used in the TCP/IP models's transport layer.

3. Internet layer

  Similar to the Network layer in the OSI model. It is responsible for addressing, routing, and packaging data packets. It determines the best path for data to travel from source to destination using routing protocols and IP addressing.

4. Network interface layer

  Simlar to the Data Link and Physical layers in the OSI model. It encompasses the protocols and technologies that govern the transmission of data over the physical medium.

> DNS (Domain Name System) is a protocol used on the internet to translate domain names into IP addresses that computers can understand.

### IP addresses

IP addresses is fundamental to network communication. An IP (Internet Protocol) address is a unique numerical identifier assigned to each device connected to a network. It serves as the address that allows devices to send and receive data across the internet or andy IP-based network.

#### IPv4 vs IPv6

There are two main versions of IP addresses: IPv4 and IPv6. IPv4 addresses are 32-bit numbers, expressed in four sets of decimal numbers, such as 192.168.0.1. However, with the growth of the internet, IPv4 addresses became limited. IPv6 was then introduced to address this limitation and uses 128-bit addresses expressed in eight sets of hexadecimal numbers, such as 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

#### Static IP vs Dynamic IP

1. Static IP address
   
  Normally is manually configured for a device that requires a consistent, permanet network addressing, such as servers or network printers. Staic IP will remain constant unless manually modified.

2. Dynamic IP address

  Dynamic IP address is assigned to a device automatically by a DHCP server. It is temporary and subject to change whenever the device reconnects to the network or when the DHCP lease expires. These type of IP commonly used for regular devices like computers, smartphones, and etc.

#### Public vs Private IP addresses

IP addresses can be classified as *public* or *private*. Public IP addresses are globally unique addresses assigned to devices connected directly to the internet. Private IP addresses, on the other hand, are used within private networks and are not routable on the internet.

#### IP address classes

IPv4 addresses are divided into different classes (A, B, C, D, and E) based on the range of network and host portions. Classes A, B, and C are commonly used for assigning IP addresses to devices, while classes D and E are reserved for special purposes.

It's important to note that the introduction of IPv6, the concept of IP address is no longer relevant. IPv6 does not have specific address ranges reserved for special purposes. Instead, IPv6 uses different addressing schemes and mechanisms to fulfill the same functions.

#### DHCP

DHCP (Dynamic Host Configuration Protocol) is a network protocol that automates the process of assigning IP addresses and other network configuration settings to devices on a network.

The primary function of DHCP is to dynamically allocate IP addresses to devices as they connect to a network. Instead of manually configuring IP addresses on each device, DHCP allows devices to request and receive an IP address automatically from a DHCP server.

> DORA (Discover, Offer, Request, Acknowledge)

Here's how DHCP works:

1. Discover

  When a device connects to a network, it sends a DHCP discovery message, broadcasted to all devices on the network.

2. Offer

  DHCP servers receive the discovery message and respond with a DHCP offer. The offer includes an available IP address that the server can assign to the requesting device.

3. Request

  The device selects one of the offered IP addresses and sends a DHCP request to the DHCP server, confirming its desire to use that IP address.

4. Acknowledge

  The DHCP server receives the request and sends a DHCP acknowledgement to the device, confirming that the IP address has been assigned to the device.

The party hat giver analogy:

- The DHCP server is the party hat giver.
- You are the device.
- The party hat is the IP address.
- The party is the network.
- You went to a party. At the party, you asked the party hat giver for a party hat. The party hat giver showed you a bunch of party hats and you picked one. The party hat giver then gave you the party hat. You put the party hat on and now you are part of the party.

#### Subnetting

> Subnetting is done by changin the default subnet mask by borrowing some of the bits from the host portion.

IP addresses are divided into network and host portions. Subnetting involves dividing a network into smaller subnetworks to accommodate different networks within an organization. It helps manage and optimize network traffic, improve network security, and simplify network management.

Subnetting has several benefits, including:

1. **Efficient address allocation**: Subnetting allow a network to be divided into smaller subnetworks. By doing so, IP addresses can be allocated more effectively to meet the needs of different departments, branches, or devices within an organization.
2. **Improved network performance**: Subnetting helps improve network performance by reducing network congestion. Smaller subnets means better management of network traffic and faster data transmission.
3. **Enhanced network security**: By dividing a network into smaller subnets, it is easier to isolate and contain security threats. Network administrators can implement security measures, such as firewalls or access control lists, to control and monitor traffic flow between subnets. This helps contain potential security threats and minimizes their impact on the entire network.

#### Routing

Routing is the process of **selecting the best path for data packets to travel** from a source device to a destination device across an IP-based network. When a device wants to send data to another device, it packages the data into IP packets and assigns the destination IP address to those packets. The device then relies on routing to ensure that the packets reach the intended destination.

By using routing, IP-based networks can efficiently and effectively deliver data packets across multiple devices and networkds to reach their destination. Routing ensures that data is directed along the optimal paths, avoiding network congestion and enabling reliable communication between devices. IP addresses play a crucial role in routing by providing the information needed to determine the best path for data to travel.

#### Switching

Switching is the process of forwarding data packets between devices on a LAN. A switch is a network device that operates at data link layer of the OSI model. It connects multiple devices within a LAN.

Benefits of switching:

1. **Increased Network Performance**

  Switches create dedicated communication channels between devices, allowing for simultaneously and efficent data transmission. This helps improve network performance and reduce network congestion.

2. **Enhanced Security**

  Switches segregates traffic between devices within a LAN, preventing unauthorized access to data.

3. **Flexibility and Scalability**

  Switches can be easily added to a network to accommodate new devices and network growth.

## Network Components and Devices

- Learn their functionalities and how they interact within a network.

### Routers

Routers are network devices that operate at the network layer (layer 3) of the OSI model. They are responsible for forwarding data packets between different networks, facilitating communication between devices acroos multiple networks.

The primary function of a router is to determine the best path for data packets to reach their destination. Routers examine the destination IP address of a packet and consult their routing table to make routing decisions. The routing table contains information about various networks and the associated next-hop routers or gateways through which packets should be forwarded.

> Next-hop routers: The immediate router that data packets are forwarded to along the path to their final destination.

Here are some key features of routers:

1. Interconnecting networks: Connect different networks together, such as LANs, WAN, or the internet. It's done by establish connections between networks by examining IP addresses and determining the appropriate path for data to travel.
2. Routing and Forwarding: Routers use routing protocols and algorithms to exchange routing information with other routers, build routing tables, and determine the best path for data to travel.
3. Security and Firewall Functionality: Routers can inlcude firewall featuers to enhance network security. The can enfore access control policies, filter incoming and outgoing traffic, and prevent unauthorized access to a network.
4. Gateway to the internet: In a home network, the router is the gateway to the internet. It connects the home network to the internet and allows devices to access the internet.

### Switches

Switches are commonly used in Ethernet networks to create dedicated communication channels between devices. Upon receiving a data packet, it examines the destination MAC (Media Access Control) address of the packet. Based on this address, the switch determines the appropriate port through which the packet should be forwarded. This process is known as "switching".

### Hub

A hub operates at the physical layer (layer 1) of the OSI model and simply broadcasts incoming data packets to all connected devices within a network. It does not perform any intelligent packet forwarding or filtering, resulting in a less efficient use of network bandwidth.

## Network configuration

### Subnet Mask

Revision on IP address:

IP address is an identifier for each devices on internet. It's a 32-bit numeric address, written as four numbers, separated by periods. Each group of numbers that are separated by periods is called octet. The number range in each octet is from 0 to 255. An IP address consists of two parts: network and host portions. The network portion identifies the network to which the device belongs, while the host portion identifies the specific device on that network.

The way to tell which portion of the IP address is the network address and which is the host address, is by using its subnet mask. A subnet mask is a set of numbers that represents the network and host portions of an IP address. And it reveals how many bits in the IP address are used for the network by masking the network portion of the IP address.

The reason why there's network and host portion on an IP address, is that it allows a network to be divided into smaller networks, which is known as subnetting.

| Subnet mask | Binary | Networks | Hosts |
| ----------- | ------ | -------- | ----- |
| 255.255.255.0 | 11111111.11111111.11111111.00000000 | 1 | 254 |
| 255.255.255.128 | 11111111.11111111.11111111.10000000 | 2 | 126 |
| 255.255.255.192 | 11111111.11111111.11111111.11000000 | 4 | 62 |
| 255.255.255.224 | 11111111.11111111.11111111.11100000 | 8 | 30 |
| 255.255.255.240 | 11111111.11111111.11111111.11110000 | 16 | 14 |
| 255.255.255.248 | 11111111.11111111.11111111.11111000 | 32 | 6 |
| 255.255.255.252 | 11111111.11111111.11111111.11111100 | 64 | 2 |
| 255.255.255.254 | 11111111.11111111.11111111.11111110 | 128 | 0 |

| Class | First octet address | Defaut subnet mask |
| ----- | ------------------- | ------------------ |
| A | 1-126 | 255.0.0.0 |
| B | 128-191 | 255.255.0.0 |
| C | 192-223 | 255.255.255.0 |

#### CIDR - Classless Inter-Domain Routing (Slash Notation)

CIDR is a shorter way to write a subnet mask. And it does this by writing a forward slash and then a number counting the 1s in the subnet mask. So for example: 192.168.1.0 /24.

This means that the subnet mask is 24 bits in length, meaning it has 24 ones. And the remaining 8 bits are zeros. So the subnet mask is 255.255.255.0.
