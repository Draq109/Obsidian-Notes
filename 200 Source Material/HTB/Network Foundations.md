---
Start: 2025-07-17
End: 2025-07-23
Sessions: 4
tags:
  - source
  - status/finished
---
### Module Sections
- [[#Introduction to Networks]]
- [[#Network Concepts]]
- [[#Components of a Network]]
- [[#Network Communication]]
- [[#Dynamic Host Configuration Protocol (DHCP)]]
- [[#Network Address Translation (NAT)]]
- [[#Domain Name System (DNS)]]
- [[#Internet Architecture]]
- [[#Wireless Networks]]
- [[#Network Security]]
- [[#Data Flow Example]]
- [[#Skills Assessment]]
- [[#Exercises/Questions]]
### Reference
https://academy.hackthebox.com/module/details/75

------------------------------------------------------------------------
# Introduction to Networks

Welcome to Network Foundations! In this introductory module, we will explore the technology behind computer networking - also known as "networking" or "networks" - and why it is essential to our lives. We will mostly focus on two primary types of networks: `Local Area Networks (LANs)` and `Wide Area Networks (WANs)`.

Understanding how devices are able to communicate with one another, from inside our homes to across the globe, is fundamental knowledge for those looking to enter the field of cyber security. The interconnectedness of almost every device in our world today sets the backdrop for the ever increasing demand for security professionals.

---

## What is a Network?

A `network` is a collection of interconnected devices that can communicate - sending and receiving data, and also sharing resources with each other. These individual endpoint devices, often called `nodes`, include computers, smartphones, printers, and servers. However, `nodes` alone do not comprise the entire network. The table below shows some networking `key concepts`.

|**Concepts**|**Description**|
|---|---|
|`Nodes`|Individual devices connected to a network.|
|`Links`|Communication pathways that connect nodes (wired or wireless).|
|`Data Sharing`|The primary purpose of a network is to enable data exchange.|

Let's explain the above using a real-world example. Think of a group of friends chatting in a room. Each person represents a device (`node`), and their ability to talk and listen represents the `communication links`. The conversation is the `data` being shared.

---

## Why Are Networks Important?

Networks, particularly since the advent of the Internet, have radically transformed society, enabling the multitude of possibilities that are now essential to our lives. Below are just a few of the benefits afforded to us by this incredible technology.

|**Function**|**Description**|
|---|---|
|`Resource Sharing`|Multiple devices can share hardware (like printers) and software resources.|
|`Communication`|Instant messaging, emails, and video calls rely on networks.|
|`Data Access`|Access files and databases from any connected device.|
|`Collaboration`|Work together in real-time, even when miles apart.|

---

## Types of Networks

Networks vary in size and scope. The two primary types are `Local Area Network (LAN)` and `Wide Area Network (WAN)`.

#### Local Area Network (LAN)

A `Local Area Network (LAN)` connects devices over a short distance, such as within a home, school, or small office building. Here are some of its key characteristics:

|**Characteristic**|**Description**|
|---|---|
|`Geographical Scope`|Covers a small area.|
|`Ownership`|Typically owned and managed by a single person or organization.|
|`Speed`|High data transfer rates.|
|`Media`|Uses wired (Ethernet cables) or wireless (Wi-Fi) connections.|

The following diagram shows how a home's Wi-Fi connects devices such as laptops, smartphones, and smart TVs, allowing them to share files and access the internet.

![[Assets/Network Foundations/6eaad2850f4821acb3fd4c61ec05d737_MD5.webp]]

#### Wide Area Network (WAN)

A `Wide Area Network (WAN)` spans a large geographical area, connecting multiple LANs. Below are some of its key characteristics:

|**Characteristic**|**Description**|
|---|---|
|`Geographical Scope`|Covers cities, countries, or continents.|
|`Ownership`|Often a collective or distributed ownership (e.g., internet service providers).|
|`Speed`|Slower data transfer rates compared to LANs due to long-distance data travel.|
|`Media`|Utilizes fiber optics, satellite links, and leased telecommunication lines.|

The Internet is the largest example of a `WAN`, connecting millions of `LANs` globally.

![[Assets/Network Foundations/f963eb6f8083836295f97d664b7a68f1_MD5.webp]]

---

#### Comparing LAN and WAN

|Aspect|LAN|WAN|
|---|---|---|
|`Size`|Small, localized area|Large, broad area|
|`Ownership`|Single person or organization|Multiple organizations/service providers|
|`Speed`|High|Lower compared to LAN|
|`Maintenance`|Easier and less expensive|Complex and costly|
|`Example`|Home or office network|The Internet|

---

## How Do LANs and WANs Work Together?

Local Area Networks (LANs) can connect to Wide Area Networks (WANs) to access broader networks beyond their immediate scope. This connectivity allows for expanded communication and resource sharing on a much larger scale.

For instance, when accessing the Internet, a home LAN connects to an `Internet Service Provider's (ISP's)` WAN, which grants Internet access to all devices within the home network. An ISP is a company that provides individuals and organizations with access to the Internet. In this setup, a device called a modem (modulator-demodulator) plays a crucial role. The modem acts as a bridge between your home network and the ISP's infrastructure, converting digital signals from your router into a format suitable for transmission over various media like telephone lines, cable systems, and fiber optics. This connection transforms a simple local network into a gateway to the resources available online.

In a business setting, companies link multiple office LANs via WANs to achieve unified communication and collaboration across different geographic locations. By connecting these LANs through a WAN, employees in various offices can share information, access centralized databases, and work together in real-time, enhancing productivity within the organization.

Let's consider the following scenario to illustrate how LANs and WANs work together. At home, our devices—such as laptops, smartphones, and tablets—connect to our home router, forming a LAN. This router doesn't just manage local traffic; it also communicates with our ISP's WAN. Through this connection to the WAN, our home network gains the ability to access websites and online services hosted all over the world. This seamless integration between the LAN and WAN enables us to reach global content and interact with services beyond our local network.
# Network Concepts

---

Understanding the nuts and bolts behind networking is undoubtedly important. However, many are not aware of just how ubiquitous networking become. The incredibly complex technology stack in use today - what we see across consumer electronics, multimedia devices, hardware, software, and firmware - was all built in conjunction with (or on top of) the `TCP/IP` stack.

Furthermore, in this section we will cover a few key concepts that help to illustrate how networking fits into the wider ecosystem of technology. We will discuss the `OSI` and `TCP/IP` models, several common network protocols used as standards for data exchange, and the various `transmission methods` that enable information to traverse efficiently and securely across the network.

---

## OSI Model

The `Open Systems Interconnection (OSI) model` is a conceptual framework that standardizes the functions of a telecommunication or computing system into seven abstract layers. This model helps vendors and developers create interoperable network devices and software. Below we see the seven layers of the OSI Model.

#### Physical Layer (Layer 1)

The `Physical Layer` is the first and lowest layer of the OSI model. It is responsible for transmitting raw bitstreams over a physical medium. This layer deals with the physical connection between devices, including the hardware components like Ethernet cables, hubs, and repeaters.

#### Data Link Layer (Layer 2)

The `Data Link Layer` provides node-to-node data transfer - a direct link between two physically connected nodes. It ensures that data frames are transmitted with proper synchronization, error detection, and correction. Devices such as switches and bridges operate at this layer, using [MAC (Media Access Control)](https://en.wikipedia.org/wiki/MAC_address) addresses to identify network devices.

#### Network Layer (Layer 3)

The `Network Layer` handles packet forwarding, including the routing of packets through different routers to reach the destination network. It is responsible for logical addressing and path determination, ensuring that data reaches the correct destination across multiple networks. Routers operate at this layer, using [IP (Internet Protocol) addresses](https://usa.kaspersky.com/resource-center/definitions/what-is-an-ip-address?srsltid=AfmBOoq0TltVlJi8PKDn6j4yNB0V5Av5Y4srTxb32Bbbg4TcAfZ5FG8H) to identify devices and determine the most efficient path for data transmission.

#### Transport Layer (Layer 4)

The `Transport Layer` provides end-to-end communication services for applications. It is responsible for the reliable (or unreliable) delivery of data, segmentation, reassembly of messages, flow control, and error checking. Protocols like `TCP (Transmission Control Protocol)` and `UDP (User Datagram Protocol)` function at this layer. TCP offers reliable, connection-oriented transmission with error recovery, while UDP provides faster, connectionless communication without guaranteed delivery.

#### Session Layer (Layer 5)

The `Session Layer` manages sessions between applications. It establishes, maintains, and terminates connections, allowing devices to hold ongoing communications known as sessions. This layer is essential for session checkpointing and recovery, ensuring that data transfer can resume seamlessly after interruptions. Protocols and `APIs (Application Programming Interfaces)` operating at this layer coordinate communication between systems and applications.

#### Presentation Layer (Layer 6)

The `Presentation Layer` acts as a translator between the application layer and the network format. It handles data representation, ensuring that information sent by the application layer of one system is readable by the application layer of another. This includes data encryption and decryption, data compression, and converting data formats. Encryption protocols and data compression techniques operate at this layer to secure and optimize data transmission.

#### Application Layer (Layer 7)

The `Application Layer` is the topmost layer of the OSI model and provides network services directly to end-user applications. It enables resource sharing, remote file access, and other network services. Common protocols operating at this layer include `HTTP (Hypertext Transfer Protocol)` for web browsing, `FTP (File Transfer Protocol)` for file transfers, `SMTP (Simple Mail Transfer Protocol)` for email transmission, and `DNS (Domain Name System)` for resolving domain names to IP addresses. This layer serves as the interface between the network and the application software.

![[Assets/Network Foundations/43553ff827b60c3ea64f96fe5b2e1436_MD5.webp]]

#### Example of Sending a File Across Network Layers

When sending a file over a network, several steps occur across different layers of the network model. The process begins at the `Application Layer`, which initiates the file transfer request. Following this, the `Presentation Layer` encrypts the file to ensure its security during transmission. The `Session Layer` then establishes a communication session with the receiving device. At the `Transport Layer`, the file is broken down into segments to ensure error-free transmission. The `Network Layer` takes over to determine the best route for transferring the data across the network. Next, the `Data Link Layer` encapsulates the data into frames, preparing it for node-to-node delivery. Finally, the `Physical Layer` handles the actual transmission of bits over the physical medium, completing the process.

---

## TCP/IP Model

The `Transmission Control Protocol/Internet Protocol (TCP/IP) model` is a condensed version of the `OSI` model, tailored for practical implementation on the internet and other networks. Below we see the four layers of the `TCP/IP Model`.

#### Link Layer

This layer is responsible for handling the physical aspects of network hardware and media. It includes technologies such as Ethernet for wired connections and Wi-Fi for wireless connections. The Link Layer corresponds to the Physical and Data Link Layers of the OSI model, covering everything from the physical connection to data framing.

#### Internet Layer

The `Internet Layer` manages the logical addressing of devices and the routing of packets across networks. Protocols like IP (Internet Protocol) and ICMP (Internet Control Message Protocol) operate at this layer, ensuring that data reaches its intended destination by determining logical paths for packet transmission. This layer corresponds to the Network Layer in the OSI model.

#### Transport Layer

At the `Transport Layer`, the TCP/IP model provides end-to-end communication services that are essential for the functioning of the internet. This includes the use of TCP (Transmission Control Protocol) for reliable communication and UDP (User Datagram Protocol) for faster, connectionless services. This layer ensures that data packets are delivered in a sequential and error-free manner, corresponding to the Transport Layer of the OSI model.

#### Application Layer

The `Application Layer` of the TCP/IP model contains protocols that offer specific data communication services to applications. Protocols such as HTTP (Hypertext Transfer Protocol), FTP (File Transfer Protocol), and SMTP (Simple Mail Transfer Protocol) enable functionalities like web browsing, file transfers, and email services. This layer corresponds to the top three layers of the OSI model (Session, Presentation, and Application), providing interfaces and protocols necessary for data exchange between systems.

![[Assets/Network Foundations/4d37c462ac0703a3821891a47d112d80_MD5.webp]]

#### Comparison with OSI Model:

The TCP/IP model simplifies the complex structure of the OSI model by combining certain layers for practical implementation. Specifically designed around the protocols used on the internet, the TCP/IP model is more application-oriented, focusing on the needs of real-world network communication. This design makes it more effective for internet-based data exchange, meeting modern technological needs.

![[Assets/Network Foundations/612b20f4d5da97467444fd182787d7ab_MD5.webp]]

#### Example of Accessing a Website

When accessing a website, several layers of the TCP/IP model work together to facilitate the process. At the Application Layer, your browser utilizes HTTP to request the webpage. This request then moves to the Transport Layer, where TCP ensures the data is transferred reliably. The Internet Layer comes into play next, with IP taking charge of routing the data packets from our device to the web server. Finally, at the Network Interface Layer, the data is physically transmitted over the network, completing the connection that allows us to view the website.

#### Model Roles

In practical terms, the TCP/IP model is the backbone of network data transmission, actively employed across various networking environments. On the other hand, the OSI model, while not directly implemented, plays a crucial role as a comprehensive theoretical framework. It helps demystify the complexities of network operations, providing clear insights and a structured approach to understanding how networks function. Together, these models form a complete picture, bridging the gap between theoretical knowledge and practical application in networking.

---

## Protocols

`Protocols` are standardized rules that determine the formatting and processing of data to facilitate communication between devices in a network. These protocols operate at different layers within network models, each tailored to handle specific types of data and communication needs. Here’s a look at some common network protocols and their roles in data exchange.

#### Common Network Protocols

Network protocols are essential for defining how data is exchanged across networks. Each protocol operates at a specific layer of the OSI model, ensuring structured and efficient data handling.

|**Protocol**|**Description**|
|---|---|
|`HTTP (Hypertext Transfer Protocol)`|Primarily used for transferring web pages. It operates at the Application Layer, allowing browsers and servers to communicate in the delivery of web content.|
|`FTP (File Transfer Protocol)`|Facilitates the transfer of files between systems, also functioning at the Application Layer. It provides a way for users to upload or download files to and from servers.|
|`SMTP (Simple Mail Transfer Protocol)`|Handles the transmission of email. Operating at the Application Layer, it is responsible for sending messages from one server to another, ensuring they reach their intended recipients.|
|`TCP (Transmission Control Protocol)`|Ensures reliable data transmission through error checking and recovery, operating at the Transport Layer. It establishes a connection between sender and receiver to guarantee the delivery of data in the correct order.|
|`UDP (User Datagram Protocol)`|Allows for fast, connectionless communication, which operates without error recovery. This makes it ideal for applications that require speed over reliability, such as streaming services. UDP operates at the Transport Layer.|
|`IP (Internet Protocol)`|Crucial for routing packets across network boundaries, functioning at the Internet Layer. It handles the addressing and routing of packets to ensure they travel from the source to the destination across diverse networks.|

---

## Transmission

`Transmission` in networking refers to the process of sending data signals over a medium from one device to another. To further understand this concept, let’s examine the different types of transmission, the modes in which these transmissions can occur, and the media that carry the signals.

#### Transmission Types

Transmission in networking can be categorized into two main types: `analog` and `digital`. Analog transmission uses continuous signals to represent information, commonly seen in traditional radio broadcasts. In contrast, digital transmission employs discrete signals (bits) to encode data, which is typical in modern communication technologies like computer networks and digital telephony.

#### Transmission Modes

Transmission modes define how data is sent between two devices. `Simplex` mode allows one-way communication only, such as from a keyboard to a computer, where signals travel in a single direction. `Half-duplex` mode permits two-way communication but not simultaneously; examples include walkie-talkies where users must take turns speaking. `Full-duplex` mode, used in telephone calls, supports two-way communication simultaneously, allowing both parties to speak and listen at the same time.

#### Transmission Media

The physical means by which data is transmitted in a network is known as transmission media, which can be wired or wireless. Wired media includes `twisted pair` cables, commonly used in Ethernet networks and local area network (LAN) connections; `coaxial` cables, used for cable TV and early Ethernet; and `fiber optic` cables, which transmit data as light pulses and are essential for high-speed internet backbones. Wireless media, on the other hand, encompasses `radio waves` for Wi-Fi and cellular networks, `microwaves` for satellite communications, and `infrared` technology used for short-range communications like remote controls. Each type of media has its specific use cases depending on the requirements of the network environment.

# Components of a Network

---

As we continue our journey into infosec, understanding the components that comprise a network is essential. We know that currently, devices are able to communicate with each other, share resources, and access the internet with almost uniform consistency. What exactly facilitates this? The primary components of such a network include:

|**Component**|**Description**|
|---|---|
|`End Devices`|Computers, Smartphones, Tablets, IoT / Smart Devices|
|`Intermediary Devices`|Switches, Routers, Modems, Access Points|
|`Network Media and Software Components`|Cables, Protocols, Management and Firewalls Software|
|`Servers`|Web Servers, File Servers, Mail Servers, Database Servers|
|||

Let's explore each of these in detail.

## End Devices

An `end device`, also known as a `host`, is any device that ultimately ends up sending or receiving data within a network. Personal computers and smart devices (such as phones and smart TVs) are common end devices; users routinely interact with them directly to perform tasks like browsing the web, sending messages, and creating documents. In most networks, such devices play a crucial role in both data generation and data consumption, like when users stream videos or read web content. End devices serve as the primary user interface to the world wide web, enabling users to access network resources and services seamlessly, through both wired (Ethernet) and wireless (Wi-Fi) connections. Another typical example of this would be a student using a notebook to connect to a school’s Wi-Fi network, allowing them to access online learning materials, submit assignments, and communicate with instructors.

## Intermediary Devices

An `intermediary device` has the unique role of facilitating the flow of data between `end devices`, either within a local area network, or between different networks. These devices include routers, switches, modems, and access points, all of which play crucial roles in ensuring efficient and secure data transmission. Intermediary devices are responsible for `packet forwarding`, directing data packets to their destinations by reading network address information and determining the most efficient paths. They connect networks and control traffic to enhance performance and reliability. By managing data flow with protocols, they ensure smooth transmission and prevent congestion. Additionally, intermediary devices often incorporate security features like `firewalls` to protect certain networks from unauthorized access and potential threats. Operating at different layers of the OSI model—for example, routers at the `Network Layer (Layer 3)` and switches at the `Data Link Layer (Layer 2)`—use routing tables and protocols to make informed decisions about data forwarding . A common example is a home network where intermediary devices like routers and switches connect all household devices (including notebooks, smartphones, and smart TVs) to the internet, enabling communication and access to online resources.

#### Network Interface Cards (NICs)

A `Network Interface Card (NIC)` is a hardware component installed in a computer, or other device, that enables connection to a network. It provides the physical interface between the device and the network media, handling the sending and receiving of data over the network. Each NIC has a unique Media Access Control (MAC) address, which is essential for devices to identify each other, and facilitate communication at the data link layer. NICs can be designed for wired connections, such as Ethernet cards that connect via cables, or for wireless connections, like Wi-Fi adapters utilizing radio waves. For example, a desktop computer might use a wired NIC, along with an Ethernet cable, to connect to a local network, while a laptop uses a wireless NIC to connect via Wi-Fi.

#### Routers

A `router` is an intermediary device that plays a hugely important role: the forwarding of data packets between networks, and ultimately directing internet traffic. Operating at the network layer (Layer 3) of the OSI model, routers read the network address information in data packets to determine their destinations. They use routing tables and routing protocols such as `Open Shortest Path First (OSPF)` or `Border Gateway Protocol (BGP)` to find the most efficient path for data to travel across interconnected networks, including the internet.

They fulfill this role by `examining incoming data packets` and forwarding them toward their destinations, based on IP addresses. By `connecting multiple networks`, routers enable devices on different networks to communicate. They also manage network traffic by selecting optimal paths for data transmission, which helps prevent congestion—a process known as `traffic management`. Additionally, routers enhance `security` by incorporating features like firewalls and access control lists, protecting the network from unauthorized access and potential threats.

#### Example

In a home network, a router connects all household devices—such as computers, smartphones, and smart TVs—to the internet provided by an Internet Service Provider (ISP). The router directs incoming and outgoing internet traffic efficiently, ensuring that each device can communicate with external networks and with each other.

#### Switches

The `switch` is another integral component, with its primary job being to connect multiple devices within the same network, typically a Local Area Network (LAN). Operating at the data link layer (Layer 2) of the OSI model, switches use MAC addresses to forward data only to the intended recipient. By managing data traffic between connected devices, switches reduce network congestion and improve overall performance. They enable devices like computers, printers, and servers to communicate directly with each other within the network. For instance, in a corporate office, switches connect employees' computers, allowing for quick file sharing and access to shared resources like printers and servers.

#### Hubs

A `hub` is a basic (and now antiquated) networking device. It connects multiple devices in a network segment and broadcasts incoming data to all connected ports, regardless of the destination. Operating at the physical layer (Layer 1) of the OSI model, hubs are simpler than switches and do not manage traffic intelligently. This indiscriminate data broadcasting can lead to network inefficiencies and collisions, making hubs less suitable for modern networks. For example, in a small home network setup from earlier times, a hub might connect a few computers, but today, switches are preferred due to their better performance and efficiency.

## Network Media and Software Components

`Network Media and Software Components` are vital elements that enable seamless communication and operation within a network. `Network media`, such as cables and wireless signals, provide the physical pathways that connect devices and allow data to be transmitted between them. This includes wired media like Ethernet cables and fiber-optic cables, which offer high-speed connections, as well as wireless media like Wi-Fi and Bluetooth, which provide mobility and flexibility. On the other hand, `software components` like network protocols and management software define the rules and procedures for data transmission, ensuring that information is correctly formatted, addressed, transmitted, routed, and received. `Network protocols` such as TCP/IP, HTTP, and FTP enable devices to communicate over the network, while `network management software` allows administrators to monitor network performance, configure devices, and enhance security through tools like software firewalls.

#### Cabling and Connectors

`Cabling and connectors` are the physical materials used to link devices within a network, forming the pathways through which data is transmitted. This includes the various types of cables mentioned previously, but also connectors like the RJ-45 plug, which is used to interface cables with network devices such as computers, switches, and routers. The quality and type of cabling and connectors can affect network performance, reliability, and speed. For example, in an office setting, Ethernet cables with RJ-45 connectors might connect desktop computers to network switches, enabling high-speed data transfer across the local area network.

#### Network Protocols

`Network protocols` are the set of rules and conventions that control how data is formatted, transmitted, received, and interpreted across a network. They ensure that devices from different manufacturers, and with varying configurations, can adhere to the same standard and communicate effectively. Protocols encompass a wide range of aspects such as:

- `Data Segmentation`
- `Addressing`
- `Routing`
- `Error Checking`
- `Synchronization`

Common network protocols include:

- `TCP/IP`: ubiquitous across all internet communications
    
- `HTTP/HTTPS`: The standard for Web traffic
    
- `FTP`: File transfers
    
- `SMTP`: Email transmissions
    
    For instance, when we browse a website, the HTTP or HTTPS protocol dictates how our browser communicates with the webserver to request and receive web pages, ensuring that the data is correctly formatted and securely transmitted.`
    

#### Network Management Software

`Network management software` consists of tools and applications used to monitor, control, and maintain network components and operations. These software solutions provide functionalities for:

- `performance monitoring`
- `configuration management`
- `fault analysis`
- `security management`

They help network administrators ensure that the network operates efficiently, remains secure, and can quickly address any issues that arise. For example, in a corporate environment, the IT department might use network management software to oversee all devices connected to the company network, monitor traffic for unusual activity, update device configurations remotely, and enforce security policies, maintaining optimal network performance and security.

#### Software Firewalls

A `software firewall` is a security application installed on individual computers or devices that monitors and controls incoming and outgoing network traffic based on predetermined security rules. Unlike hardware firewalls that protect entire networks, software firewalls (also called Host-based firewalls) provide protection at the device level, guarding against threats that may bypass the network perimeter defenses. They help prevent unauthorized access, reject incoming packets that contain suspicious or malicious data, and can be configured to restrict access to certain applications or services. For example, most operating systems include a built-in software firewall that can be set up to block incoming connections from untrusted sources, ensuring that only legitimate network traffic reaches the device.

_**The Linux-based software firewall [IPTables](https://linux.die.net/man/8/iptables) being used to drop incoming ICMP traffic.**_ ![[Assets/Network Foundations/047993ab7e27fb6dfc1b128d0d76393b_MD5.gif]]

---

## Servers

A `server` is a powerful computer designed to provide services to other computers, known as clients, over a network. Servers are the backbone behind websites, email, files, and applications. In the realm of computer networking, servers play a crucial role by hosting services that clients access (i.e., web pages and email services), facilitating `service provision`. They enable `resource sharing` by allowing multiple users to access resources like files and printers. Servers also handle `data management` by storing and managing data centrally, which simplifies backup processes and enhances security management. Additionally, they manage `authentication` by controlling user access and permissions, across multiple components in the network. Servers often run specialized operating systems optimized for handling multiple, simultaneous requests in what is known as the `Client-Server Model`, where the server waits for requests from clients and responds accordingly. Whether you knew it or not, this is what was happening under-the-hood the last time you accessed a website from your notebook. Your browser sends a request to the web server hosting the site, and the server subsequently processes the request and sends back the web page data in its response.

---

## Conclusion

As we have seen, the technology stack needed for world-wide computer networking requires multiple components. End devices are the users' primary interface with the network, intermediary devices manage data traffic and connectivity, and servers provide resources and services. Together, they enable the seamless flow of information that powers modern communication.

# Network Communication

---

For a network to function and facilitate communication properly, there are three crucial components: `MAC addresses`, `IP addresses`, and `ports`. Together, these elements ensure that data is correctly sent and received between devices across both local and global networks, forming the backbone of seamless network communication.

---

## MAC Addresses

#### What is a MAC Address?

A `Media Access Control (MAC) address` is a unique identifier assigned to the network interface card (NIC) of a device, allowing it to be recognized on a local network. Operating at the `Data Link Layer (Layer 2)` of the OSI model, the MAC address is crucial for communication within a local network segment, ensuring that data reaches the correct physical device. Each MAC address is 48 bits long and is typically represented in hexadecimal format, appearing as six pairs of hexadecimal digits separated by colons or hyphensfor (e.g., `00:1A:2B:3C:4D:5E`). The uniqueness of a MAC address comes from its structure: the first 24 bits represent the `Organizationally Unique Identifier (OUI)` assigned to the manufacturer, while the remaining 24 bits are specific to the individual device. This design ensures that every MAC address is globally unique, allowing devices worldwide to communicate without address conflicts.

_**The Windows [GETMAC](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/getmac) command will return the MAC address of every network interface card on the host.**_ ![[Assets/Network Foundations/ff7e2db46a8e92074c3afb0e9be87af6_MD5.gif]]

#### How MAC Addresses are Used in Network Communication

MAC addresses are fundamental for local communication within a local area network (LAN), as they are used to deliver data frames to the correct physical device. When a device sends data, it encapsulates the information in a frame containing the destination MAC address; network switches then use this address to forward the frame to the appropriate port. Additionally, the `Address Resolution Protocol (ARP)` plays a crucial role by mapping IP addresses to MAC addresses, allowing devices to find the MAC address associated with a known IP address within the same network. This mapping is bridging the gap between logical IP addressing and physical hardware addressing within the LAN.

Imagine two computers, Computer A (with an IP address of 192.168.1.2, which we will discuss shortly) and Computer B (192.168.1.5), connected to the same network switch. Computer A has the MAC address `00:1A:2B:3C:4D:5E`, while Computer B's MAC address is `00:1A:2B:3C:4D:5F`. When Computer A wants to send data to Computer B, it first uses the Address Resolution Protocol (ARP) to discover Computer B's MAC address associated with its IP address. After obtaining this information, Computer A sends a data frame with the destination MAC address set to `00:1A:2B:3C:4D:5F`. The switch receives this frame and forwards it to the specific port where Computer B is connected, ensuring that the data reaches the correct device. This is illustrated in the following diagram.

![[Assets/Network Foundations/7c6708bc3d8a396335c29e3b43539104_MD5.webp]]

---

## IP Addresses

#### What is an IP Address?

An `Internet Protocol (IP) address` is a numerical label assigned to each device connected to a network that utilizes the Internet Protocol for communication. Functioning at the `Network Layer (Layer 3)` of the OSI model, IP addresses enable devices to locate and communicate with each other across various networks. There are two versions of IP addresses: `IPv4` and `IPv6`. IPv4 addresses consist of a 32-bit address space, typically formatted as four decimal numbers separated by dots, such as `192.168.1.1`. In contrast, IPv6 addresses, which were developed to address the depletion of IPv4 addresses, have a 128-bit address space and are formatted in eight groups of four hexadecimal digits, an example being `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.

#### How IP Addresses are Used in Network Communication

Routers use IP addresses to determine the optimal path for data to reach its intended destination across interconnected networks. Unlike MAC addresses, which are permanently tied to the device's network interface card, IP addresses are more flexible; they can change and are assigned based on the network topology and policies. A communication example between two devices on the same network can be similarly illustrated as shown previously in the MAC Address subsection.

---

## Ports

A `port` is a number assigned to specific processes or services on a network to help computers sort and direct network traffic correctly. It functions at the `Transport Layer (Layer 4)` of the OSI model and works with protocols such as TCP and UDP. Ports facilitate the simultaneous operation of multiple network services on a single IP address by differentiating traffic intended for different applications.

When a client application initiates a connection, it specifies the destination port number corresponding to the desired service. Client applications are those who request data or services, while server applications respond to those requests and provide the data or services. The operating system then directs the incoming traffic to the correct application based on this port number. Consider a simple example where a user accesses a website: the user’s browser initiates a connection to the server's IP address on port 80, which is designated for HTTP. The server, listening on this port, responds to the request. If the user needs to access a secure site, the browser instead connects to port 443, the standard for HTTPS, ensuring secure communication. Port numbers range from `0` to `65535`, and it is divided into three main categories, each serving a specific function.

_**Using the [netstat](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netstat) tool to view active connections and listening ports.**_ ![[Assets/Network Foundations/a80fcdeede25dbab1d18f3708347129d_MD5.gif]]

#### Well-Known Ports (0-1023):

`Well-known ports`, numbered from 0 to 1023, are reserved for common and universally recognized services and protocols, as standardized and managed by the [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/). For instance, HTTP, which is the foundation of data communication for the World Wide Web, uses port 80, although browsers typically do not display this port number to simplify user experience. Similarly, HTTPS uses port 443 for secure communications over networks, and this port is also generally not displayed by browsers. Another example is FTP, which facilitates file transfers between clients and servers, using ports 20 and 21.

#### Registered Ports (1024-49151):

`Registered ports`, which range from 1024 to 49151, are not as strictly regulated as `well-known ports` but are still registered and assigned to specific services by the Internet Assigned Numbers Authority (IANA). These ports are commonly used for external services that users might install on a device. For instance, many database services, such as Microsoft SQL Server, use port 1433. Software companies frequently register a port for their applications to ensure that their software consistently uses the same port on any system. This registration helps in managing network traffic and preventing port conflicts across different applications.

#### Dynamic/Private Ports (49152-65535):

Dynamic or private ports, also known as ephemeral ports, range from 49152 to 65535 and are typically used by client applications to send and receive data from servers, such as when a web browser connects to a server on the internet. These ports are called `dynamic` because they are not fixed; rather, they can be randomly selected by the client's operating system as needed for each session. Generally used for temporary communication sessions, these ports are closed once the interaction ends. Additionally, dynamic ports can be assigned to custom server applications, often those handling short-term connections.

---

## Browsing the Internet Example

The following example represents the steps taken for a web request to reach the correct destination and return the information we seek.

#### 1. DNS Lookup

Our computer resolves the domain name to an IP address (e.g., `93.184.216.34` for `example.com`).

#### 2. Data Encapsulation

|**Step**|
|---|
|Your browser generates an HTTP request.|
|The request is encapsulated with TCP, specifying the destination port `80` or `443`.|
|The packet includes the destination IP address `93.184.216.34`.|
|On the local network, our computer uses ARP to find the MAC address of the default gateway (router).|

#### 3. Data Transmission

|**Step**|
|---|
|The data frame is sent to the router's MAC address.|
|The router forwards the packet toward the destination IP address.|
|Intermediate routers continue forwarding the packet based on the IP address.|

#### 4. Server Processing

|**Step**|
|---|
|The server receives the packet and directs it to the application listening on port 80.|
|The server processes the HTTP request and sends back a response following the same path in reverse.|

#### 5. Response Transmission

| **Step**                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The server sends the response back to the client’s temporary port, which was randomly selected by the client’s operating system at the start of the session.                          |
| The response follows the reverse path back through the network, being directed from router to router based on the source IP address and port information until it reaches the client. |
# Dynamic Host Configuration Protocol (DHCP)

---

#### Introduction to DHCP

In a computer network, every device needs a unique IP (Internet Protocol) address to communicate with other devices. Manually assigning IP addresses to each device can be time-consuming and cause errors, especially in large networks. To resolve this issue, networks can rely on the Dynamic Host Configuration Protocol (DHCP). `DHCP` is a network management protocol used to automate the process of configuring devices on IP networks. It allows devices to automatically receive an IP address and other network configuration parameters, such as subnet mask, default gateway, and DNS servers, without manual intervention.

DHCP simplifies network management by automatically assigning IP addresses, significantly reducing the administrative workload. This automation ensures that each device connected to the network receives a unique IP address, preventing conflicts and duplication of addresses. Furthermore, DHCP recycles IP addresses that are no longer in use when devices disconnect from the network, optimizing the available address pool.

#### How DHCP Works

The DHCP process involves a series of interactions between the client (the device requesting an IP address) and the DHCP server (the service running on a network device that assigns IP addresses). This process is often referred to as `DORA`, an acronym for `Discover`, `Offer`, `Request`, and `Acknowledge`. Below we see a breakdown of DORA. Before we explore the `DORA` steps in detail, let's first clarify the roles of the `DHCP server` and the `DHCP client`:

|**Role**|**Description**|
|---|---|
|`DHCP Server`|A network device (like a router or dedicated server) that manages IP address allocation. It maintains a pool of available IP addresses and configuration parameters.|
|`DHCP Client`|Any device that connects to the network and requests network configuration parameters from the DHCP server.|

Below, we break down each step of the DORA process:

| **Step**         | **Description**                                                                                                                                                                         |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `1. Discover`    | When a device connects to the network, it broadcasts a **DHCP Discover** message to find available DHCP servers.                                                                        |
| `2. Offer`       | DHCP servers on the network receive the discover message and respond with a **DHCP Offer** message, proposing an IP address lease to the client.                                        |
| `3. Request`     | The client receives the offer and replies with a **DHCP Request** message, indicating that it accepts the offered IP address.                                                           |
| `4. Acknowledge` | The DHCP server sends a **DHCP Acknowledge** message, confirming that the client has been assigned the IP address. The client can now use the IP address to communicate on the network. |


_**A Linux host, connected to a wireless network, initializes the DORA process.**_ ![[Assets/Network Foundations/9aa6c340533d0e68b370c5377a34d30d_MD5.gif]]

The IP address assignment via DHCP is not permanent but is instead issued with a specific lease time. For instance, a DHCP server might assign an IP address to a smartphone with a lease time of 24 hours. After this period, the smartphone must request a renewal of the lease to continue using the IP address. Regarding the renewal process, before the lease expires, the client must proactively attempt to renew its IP address lease. This involves sending a renewal request to the DHCP server. As the lease nears its expiration, the client communicates with the DHCP server, asking if it can continue using the assigned IP address, to which the server can respond affirmatively, extending the lease.

#### Example Scenario

Let's walk through a simple example, based on the steps previously discussed, of how DHCP assigns an IP address to a device: Alice brings her new laptop to the office and connects it to the network. Since the laptop doesn't have an IP address yet, it sends out a DHCP Discover message to find a DHCP server. The office's DHCP server receives this message and responds with an offer, proposing the IP address 192.168.1.10. Alice's laptop receives this offer and sends back a DHCP Request message to accept the IP address. Finally, the DHCP server acknowledges this request and confirms the assignment. The laptop is now configured with the IP address 192.168.1.10, allowing it to communicate on the network.

The IP address 192.168.1.10 assigned to Alice's laptop is not permanent but is instead provided for a specific duration, known as the lease time. As this lease nears expiration, Alice's laptop must renew it to continue using the IP address. To do this, it sends another DHCP Request to the DHCP server asking to extend the lease. If the server can renew the lease, it will respond with a DHCP Acknowledge message, confirming the continued use of the IP address.

![[Assets/Network Foundations/55a4adeb650b5e720c92cb75aa1ac3f6_MD5.webp]]

# Network Address Translation (NAT)

---

The Internet relies on a system of numerical addresses, known as IP addresses, to route data from one device to another. The original addressing scheme, IPv4, offers a finite number of IP addresses (approximately 4.3 billion). Although this might sound like a lot, the explosive growth of the internet has meant these addresses are in short supply. One solution to this insufficiency issue is `Network Address Translation (NAT)`. The idea is that `NAT` allows multiple devices on a private network to share a single public IP address. This not only helps conserve the limited pool of public IP addresses but also adds a layer of security to the internal network.

#### Private vs. Public IP Addresses

`Public IP` addresses are globally unique identifiers assigned by Internet Service Providers (ISPs). Devices equipped with these IP addresses can be accessed from anywhere on the Internet, allowing them to communicate across the global network. For example, the IP address 8.8.8.8 is used for Google's DNS server, and 142.251.46.174 identifies one of Google’s web servers. These addresses ensure that devices can uniquely identify and reach each other over the internet.

`Private IP` addresses are designated for use within local networks such as homes, schools, and offices. These addresses are not routable on the global internet, meaning packets sent to these addresses are not forwarded by internet backbone routers. Defined by RFC 1918, common IPv4 private address ranges include 10.0.0.0 to 10.255.255.255, 172.16.0.0 to 172.31.255.255, and 192.168.0.0 to 192.168.255.255. This setup ensures that these private networks operate independently of the internet while facilitating internal communication and device connectivity.

Private IP addresses contribute to conserving public IP addresses. Using Network Address Translation (NAT), a local network can utilize private IP addresses while sharing a single public IP address, reducing the number of public IPs needed. This setup makes devices accessible from the internet without using multiple public addresses. Additionally, private IPs help secure the network by isolating internal devices from direct exposure to the internet, protecting them from potential external threats.

#### What is NAT?

`Network Address Translation (NAT)` is a process carried out by a router or a similar device that modifies the source or destination IP address in the headers of IP packets as they pass through. This modification is used to translate the private IP addresses of devices within a local network to a single public IP address that is assigned to the router.

#### How NAT Works

Consider a home network with several devices, such as a laptop, a smartphone, and a gaming console, each assigned a unique private IP address: the laptop at 192.168.1.10, the smartphone at 192.168.1.11, and the gaming console at 192.168.1.12. The home router managing this network has two critical interfaces. The LAN (Local Area Network) interface connects to the private network with an IP address of 192.168.1.1, while the WAN (Wide Area Network) interface, connected to the ISP’s network, carries a public IP address, 203.0.113.50.

The process of NAT translation begins when a device, say the laptop, sends a request to visit a website like [www.google.com](http://www.google.com). This request packet, originating with the private IP of 192.168.1.10, is sent to the router. Here, the NAT function of the router modifies the source IP in the packet header from the private IP to the public IP of the router, 203.0.113.50. This packet then travels across the internet to reach the intended web server. Upon receiving the packet, the web server sends a response back to the router's public IP. As the response arrives, the router's NAT table, which keeps track of IP mappings, identifies that 203.0.113.50:4444 corresponds to the laptop at 192.168.1.10:5555 (ports 4444 and 5555 are dynamic). The router then translates the public IP back to the laptop’s private IP and forwards the internal response to the laptop, completing the communication cycle.

![[Assets/Network Foundations/7d487211a988f29e6d5969d68c5934ac_MD5.webp]]

#### Types of NAT

It's important to know that there are several types of Network Address Translation (NAT), each designed for specific networking needs. Below are the different types of NAT.

|**Type**|**Description**|
|---|---|
|`Static NAT`|Involves a one-to-one mapping, where each private IP address corresponds directly to a public IP address.|
|`Dynamic NAT`|Assigns a public IP from a pool of available addresses to a private IP as needed, based on network demand.|
|`Port Address Translation (PAT)`|Also known as NAT Overload, is the most common form of NAT in home networks. Multiple private IP addresses share a single public IP address, differentiating connections by using unique port numbers. This method is widely used in home and small office networks, allowing multiple devices to share a single public IP address for internet access.|

#### Benefits and Trade-Offs

Network Address Translation (NAT) offers a number of benefits and presents some trade-offs as well.

|**Benefits**|
|---|
|Conserves the limited IPv4 address space.|
|Provides a basic layer of security by not exposing internal network structure directly.|
|Flexible for internal IP addressing schemes.|

|**Trade-Offs**|
|---|
|Complex services like hosting a public server behind NAT can require additional configuration (e.g., port forwarding).|
|NAT can break certain protocols that rely on end-to-end connectivity without special handling.|
|Adds complexity to troubleshooting connectivity issues.|

# Domain Name System (DNS)

---

The Domain Name System (DNS) is like the phonebook of the internet. It helps us find the right number (an IP address) for a given name (a domain such as `www.google.com`). Without DNS, we would need to memorize long, often complex IP addresses for every website we visit. DNS makes our lives easier by allowing us to use human-friendly names to access online resources.

#### Domain Names vs. IP Addresses

|**Address**|**Description**|
|---|---|
|`Domain Name`|A readable address like `www.example.com` that people can easily remember.|
|`IP Address`|A numerical label (e.g., `93.184.216.34`|

DNS bridges the gap between these two, so we can just type `www.google.com` without needing to remember the underlying IP address.

#### DNS Hierarchy

DNS is organized like a tree, starting from the root and branching out into different layers.

|**Layer**|**Description**|
|---|---|
|`Root Servers`|The top of the DNS hierarchy.|
|`Top-Level Domains (TLDs)`|Such as `.com`, `.org`, `.net`, or country codes like `.uk`, `.de`.|
|`Second-Level Domains`|For example, `example` in `example.com`.|
|`Subdomains or Hostname`|For instance, `www` in `www.example.com`, or `accounts` in `accounts.google.com`.|

![[Assets/Network Foundations/95cc073badad807bf00a2a530c86b154_MD5.webp]]

#### DNS Resolution Process (Domain Translation)

When we enter a domain name in our browser, the computer needs to find the corresponding IP address. This process is known as `DNS resolution` or `domain translation`. The steps below show how this process works.

|**Step**|**Description**|
|---|---|
|`Step 1`|We type `www.example.com` into our browser.|
|`Step 2`|Our computer checks its local DNS cache (a small storage area) to see if it already knows the IP address.|
|`Step 3`|If not found locally, it queries a `recursive DNS server`. This is often provided by our Internet Service Provider or a third-party DNS service like Google DNS.|
|`Step 4`|The recursive DNS server contacts a `root server`, which points it to the appropriate `TLD name server` (such as the `.com` domains, for instance).|
|`Step 5`|The TLD name server directs the query to the `authoritative name server` for `example.com`.|
|`Step 6`|The authoritative name server responds with the IP address for `www.example.com`.|
|`Step 7`|The recursive server returns this IP address to your computer, which can then connect to the website’s server directly.|

This all happens in just fractions of a second. Below we can see a simple example of the Domain Translation process. Suppose you want to visit the website at `www.example.com`. Without the Domain Name System (DNS), we would need to know and type the IP address, such as `93.184.216.34`, every time you want to access that site. With DNS in place, we can simply type `www.example.com` into our browser. Behind the scenes, DNS automatically finds and translates this domain name into the correct IP address for us, ensuring a seamless connection to the website. The diagram below illustrates the diagram of the `DNS Query Process`.

![[Assets/Network Foundations/6b6d9acdba6324cf5d332a802c6f5681_MD5.webp]]

# Internet Architecture

---

`Internet Architecture` describes how data is organized, transmitted, and managed across networks. Different architectural models serve different needs—some offer a straightforward client-server setup (like a website), while others rely on a more distributed approach (like file-sharing platforms). Understanding these models helps us see why networks are designed and operated the way they are. Different architectures solve different problems. Often, we see a combination of architectures creating hybrid models. Each model comes with its own set of trade-offs in terms of scalability, performance, security, and manageability. In the following paragraphs, we will describe the different architectures in more detail.

---

## Peer-to-Peer (P2P) Architecture

In a `Peer-to-Peer (P2P`) network, each node, whether it's a computer or any other device, acts as both a client and a server. This setup allows nodes to communicate directly with each other, sharing resources such as files, processing power, or bandwidth, without the need for a central server. P2P networks can be fully decentralized, with no central server involved, or partially centralized, where a central server may coordinate some tasks but does not host data.

Imagine a group of friends who want to share vacation photos with each other. Instead of uploading all the photos to a single website or server, each of them sets up a folder on their own computer that can be accessed by the others. They use a file-sharing program that connects their computers directly.

First, they install a Peer-to-Peer (P2P) file-sharing application on their computer. Then, they select the folder containing the vacation photos to share with the other friends. Everyone performs the same setup on their computers. Once everyone is connected through the P2P application, they can all browse and download photos directly from each other’s shared folders, allowing for a direct exchange of files without the need for a central server.

A popular example of Peer-to-Peer (P2P) architecture is torrenting, as seen with applications like BitTorrent. In this system, anyone who has the file, referred to as a `seeder`, can upload it, allowing others to download it from multiple sources simultaneously.

![[Assets/Network Foundations/24d006b271ad7bd784762ee08b13dc4a_MD5.webp]]

In the following table, we can see the advantages and disadvantages of a Peer-to-Peer architecture.

|**Advantage**|**Description**|
|---|---|
|`Scalability`|Adding more nodes can increase total resources (storage, CPU, etc.).|
|`Resilience`|If one node goes offline, others can continue functioning.|
|`Cost distribution`|Resource burden, like bandwidth and storage, is distributed among peers, making it more cost-efficient.|

|**Disadvantage**|**Description**|
|---|---|
|`Management complexity`|Harder to control and manage updates/security policies across all nodes|
|`Potential reliability issues`|If too many peers leave, resources could be unavailable.|
|`Security challenges`|Each node is exposed to potential vulnerabilities.|

---

## Client-Server Architecture

The `Client-Server` model is one of the most widely used architectures on the Internet. In this setup, clients, which are user devices, send requests, such as a web browser asking for a webpage, and servers respond to these requests, like a web server hosting the webpage. This model typically involves centralized servers where data and applications reside, with multiple clients connecting to these servers to access services and resources.

Let's assume we want to check the weather forecast on a website. We start by opening the web browser on our phone or computer, and proceed to type in the website's name, e.g., `weatherexample.com`. When we press enter, the browser sends a request over the Internet to the server that hosts `weatherexample.com`. This server, a powerful computer set up specifically to store the website’s data and handle requests, receives the query and processes it by locating the requested page. It then sends back the data (regarding the weather, we requested) to our browser, which receives this information and displays the webpage, allowing us to see the latest weather updates.

![[Assets/Network Foundations/76750bc38310af67b8936a0750933203_MD5.webp]]

A key component of this architecture is the tier model, which organizes server roles and responsibilities into layers. This enhances scalability and manageability, as well as security and performance.

#### Single-Tier Architecture

In a `single-tier` architecture, the client, server, and database all reside on the same machine. This setup is straightforward but is rarely used for large-scale applications due to significant limitations in scalability and security.

#### Two-Tier Architecture

The `two-tier` architecture splits the application environment into a client and a server. The client handles the presentation layer, and the server manages the data layer. This model is typically seen in desktop applications where the user interface is on the user's machine, and the database is on a server. Communication usually occurs directly between the client and the server, which can be a database server with query-processing capabilities.

**Note:** In a typical web application, the client (browser) does not directly interact with the database server. Instead, the browser requests web pages from a **web server**, which in turn sends its response (HTML, CSS, JavaScript) back to the browser for rendering. The web server *may* interact with an application server or database in order to formulate it's response, but in general, the scenario of a person visiting a website does not constitute a Two-Tier Architecture.

#### Three-Tier Architecture

A `three-tier` architecture introduces an additional layer between the client and the database server, known as the application server. In this model, the client manages the presentation layer, the application server handles all the business logic and processing, and the third tier is a database server. This separation provides added flexibility and scalability because each layer can be developed and maintained independently.

#### N-Tier Architecture

In more complex systems, an `N-tier` architecture is used, where `N` refers to any number of separate tiers used beyond three. This setup involves multiple levels of application servers, each responsible for different aspects of business logic, processing, or data management. N-tier architectures are highly scalable and allow for distributed deployment, making them ideal for web applications and services that demand robust, flexible solutions.

While tiered client-server architectures offer many improvements, they also introduce complexity in deployment and maintenance. Each tier needs to be correctly configured and secured, and communication between tiers must be efficient and secure to avoid performance bottlenecks and security vulnerabilities. In the following table, we can see the advantages and disadvantages of a Client-Server architecture in general.

|**Advantage**|**Description**|
|---|---|
|`Centralized control`|Easier to manage and update.|
|`Security`|Central security policies can be applied.|
|`Performance`|Dedicated servers can be optimized for their tasks.|

|**Disadvantage**|**Description**|
|---|---|
|`Single point of failure`|If the central server goes down, clients lose access.|
|`High Cost and Maintenance`|Setting up and sustaining a client-server architecture is expensive, requiring constant operation and expert management , making it costly to maintain.|
|`Network Congestion`|High traffic on the network can lead to congestion, slowing down or even disrupting connections when too many clients access the server simultaneously.|

---

## Hybrid Architecture

A `Hybrid` model blends elements of both `Client-Server` and `Peer-to-Peer (P2P)` architectures. In this setup, central servers are used to facilitate coordination and authentication tasks, while the actual data transfer occurs directly between peers. This combination leverages the strengths of both architectures to enhance efficiency and performance. The following example gives a high-level explanation of how a hybrid architecture works.

When we open a video conferencing app and log in, the credentials (username and password) are verified by central servers, which also manage the session by coordinating who is in the meeting and controlling access. Once we're logged in and the meeting begins, the actual video and audio data is transferred directly between our device and those of other participants, bypassing the central server to reduce lag and enhance video quality. This setup combines both models: it uses the central server for initial connection and control tasks, while the bulk of data transfer occurs in a peer-to-peer style, reducing the server load and leveraging direct, fast connections between peers. The following table refers to some of the advantages and disadvantages of a Hybrid Architecture.

![[Assets/Network Foundations/60f4c521c3129814d8c01c22649ac3c9_MD5.webp]]

|**Advantage**|**Description**|
|---|---|
|`Efficiency`|Relieves workload from servers by letting peers share data.|
|`Control`|Central server can still manage user authentication, directory services, or indexing.|

|**Disadvantage**|**Description**|
|---|---|
|`Complex Implementation`|Requires more sophisticated design to handle both centralized and distributed components.|
|`Potential Single Point of Failure`|If the central coordinating server fails, peer discovery might stop.|

---

## Cloud Architecture

`Cloud Architecture` refers to computing infrastructure that is hosted and managed by third-party providers, such as AWS, Azure, and Google Cloud. This architecture operates on a virtualized scale following a client-server model. It provides on-demand access to resources such as servers, storage, and applications, all accessible over the Internet. In this model, users interact with these services without controlling the underlying hardware.

![[Assets/Network Foundations/b52a2b0df17d412ec6428ef55571fa46_MD5.webp]]

Services like Google Drive or Dropbox are some examples of Cloud Architecture operating under the `SaaS` (Software as a Service) model, where we access applications over the internet without managing the underlying hardware. Below are five essential characteristics that define a Cloud Architecture.

|**Characteristic**|**Description**|
|---|---|
|`1. On-demand self-service`|Automatically set up and manage the services without human help.|
|`2. Broad network access`|Access services from any internet-connected device.|
|`3. Resource pooling`|Share and allocate service resources dynamically among multiple users.|
|`4. Rapid elasticity`|Quickly scale services up or down based on demand.|
|`5. Measured service`|Only pay for the resources you use, tracked with precision.|

The below table shows some of the advantages and disadvantages of the Cloud Architecture.

|**Advantage**|**Description**|
|---|---|
|`Scalability`|Easily add or remove computing resources as needed.|
|`Reduced cost & maintenance`|Hardware managed by the cloud provider.|
|`Flexibility`|Access services from anywhere with Internet connectivity.|

|**Disadvantage**|**Description**|
|---|---|
|`Vendor lock-in`|Migrating from one cloud provider to another can be complex.|
|`Security/Compliance`|Relying on a third party for data hosting can introduce concerns about data privacy.|
|`Connectivity`|Requires stable Internet access.|

---

## 6. Software-Defined Architecture (SDN)

`Software-Defined Networking (SDN)` is a modern networking approach that separates the control plane, which makes decisions about where traffic is sent, from the data plane, which actually forwards the traffic. Traditionally, network devices like routers and switches housed both of these planes. However, in SDN, the control plane is centralized within a software-based controller. This configuration allows network devices to simply execute instructions they receive from the controller. SDN provides a programmable network management environment, enabling administrators to dynamically adjust network policies and routing as required. This separation makes the network more flexible and improves how it's managed.

![[Assets/Network Foundations/63ce7ae7eee6127dbd8dcf58262ed4e6_MD5.webp]]

Large enterprises or cloud providers use SDN to dynamically allocate bandwidth and manage traffic flows according to real-time demands. Below is a table with the advantages and disadvantages of the Software-Defined architecture.

|**Advantage**|**Description**|
|---|---|
|`Centralized control`|Simplifies network management.|
|`Programmability & Automation`|Network configurations can be changed quickly through software instead of manually configuring each device.|
|`Scalability & Efficiency`|Can optimize traffic flows dynamically, leading to better resource utilization.|

|**Disadvantage**|**Description**|
|---|---|
|`Controller Vulnerability`|If the central controller goes down, the network might be adversely affected.|
|`Complex Implementation`|Requires new skill sets and specialized software/hardware.|

---

## Key Comparisons

Below is a comparison table that outlines key characteristics of different network architectures

|`Architecture`|`Centralized`|`Scalability`|`Ease of Management`|`Typical Use Cases`|
|---|---|---|---|---|
|`P2P`|Decentralized (or partial)|High (as peers grow)|Complex (no central control)|File-sharing, blockchain|
|`Client-Server`|Centralized|Moderate|Easier (server-based)|Websites, email services|
|`Hybrid`|Partially central|Higher than C-S|More complex management|Messaging apps, video conferencing|
|`Cloud`|Centralized in provider’s infra|High|Easier (outsourced)|Cloud storage, SaaS, PaaS|
|`SDN`|Centralized control plane|High (policy-driven)|Moderate (needs specialized tools)|Datacenters, large enterprises|

---

## Conclusion

Each architecture has its unique benefits and challenges, and in practice, we often see these models blended to balance performance, scalability, and cost. Understanding these distinctions is important for anyone planning to set up or improve network systems.


# Wireless Networks

---

A `wireless network` is a sophisticated communication system that employs radio waves or other wireless signals to connect various devices such as computers, smartphones, and IoT gadgets, enabling them to communicate and exchange data without the need for physical cables. This technology allows devices to connect to the internet, share files, and access services seamlessly over the air, offering flexibility and convenience in personal and professional environments.

|**Advantages**|**Description**|
|---|---|
|`Mobility`|Users can move around freely within the coverage area.|
|`Ease of installation`|No need for extensive cabling.|
|`Scalability`|Adding new devices is simpler than a wired network.|

|**Disadvantages**|**Description**|
|---|---|
|`Interference`|Wireless signals can be disrupted by walls, other electronics, or atmospheric conditions.|
|`Security risks`|Without proper security measures, wireless transmissions can be easier to intercept.|
|`Speed limitations`|Generally, wireless connections are slower compared to wired connections of the same generation.|

---

## Wireless Router

A `router` is a device that forwards data packets between computer networks. In a home or small office setting, a `wireless router` combines the functions of:

|**Function**|**Description**|
|---|---|
|`Routing`|Directing data to the correct destination (within your network or on the internet).|
|`Wireless Access Point`|Providing Wi-Fi coverage.|

For example, at home, our smartphones, laptops, and smart TVs all connect wirelessly to our router. The router is plugged into a modem that brings internet service from the ISP (Internet Service Provider). Below are the main components of a wireless router.

|**Component**|**Description**|
|---|---|
|`WAN (Wide Area Network) Port`|Connects to your internet source (e.g., a cable modem).|
|`LAN (Local Area Network) Ports`|For wired connections to local devices (e.g., desktop computer, printer).|
|`Antennae`|Transmit and receive wireless signals. (Some routers have internal antennae.)|
|`Processor & Memory`|Handle routing and network management tasks.|

---

## Mobile Hotspot

A `mobile hotspot` allows a smartphone (or other hotspot devices) to share its cellular data connection via Wi-Fi. Other devices (laptops, tablets, etc.) then connect to this hotspot just like they would to a regular Wi-Fi network. A mobile hotspot uses cellular data, connecting devices to the internet via a cellular network, such as 4G or 5G. The range of a hotspot is typically limited to just a few meters. Running a hotspot can also significantly drain the battery of the device creating the hotspot. For security, access to the hotspot is usually protected by a password, similar to the security measures used for a home Wi-Fi network. To better understand this concept, we can imagine that we are traveling and don’t have access to public Wi-Fi. We can activate the hotspot on our phone and connect our laptop to our phone’s Wi-Fi signal to browse the internet.

---

## Cell Tower

A `cell tower` (or `cell site`) is a structure where antennas and electronic communications equipment are placed to create a cellular network cell. This `cell` in a cellular network refers to the specific area of coverage provided by a single cell tower, which is designed to seamlessly connect with adjacent cells created by other towers. Each tower covers a certain geographic area, allowing mobile phones (and other cellular-enabled devices) to send and receive signals.

Cell towers function through a combination of radio transmitters and receivers, which are equipped with antennas to communicate over specific radio frequencies. These towers are managed by Base Station Controllers (BSC), which oversee the operation of multiple towers. BSCs handle the transfer of calls and data sessions from one tower to another when users move across different cells. Finally, these towers are connected to the core network via backhaul links, which are typically fiber optic or microwave links.

Cell towers are differentiated by their coverage capacities and categorized primarily into `macro cells` and `micro/small cells`. Macro cells consist of large towers that provide extensive coverage over several kilometers, making them ideal for rural areas where wide coverage is necessary. On the other hand, micro and small cells are smaller installations typically located in urban centers. These towers are placed in densely populated areas and fill the coverage gaps left by macro cells. To better understand the concept of a cellular network, imagine we are on a road trip, streaming music on the phone. As we move, our phone switches from one cell tower to the next to maintain connection.

---

## Frequencies in Wireless Communications

As mentioned earlier, wireless communications utilize radio waves to enable devices to connect and communicate with each other. These radio waves are emitted at specific frequencies, known as oscillation rates, which are measured in hertz (Hz). Common frequency bands for wireless networks include:

|**Frequency Bands**|
|---|
|`1.` **2.4 GHz (Gigahertz)** – Used by older Wi-Fi standards (802.11b/g/n). Better at penetrating walls, but can be more prone to interference (e.g., microwaves, Bluetooth).|
|`2.` **5 GHz** – Used by newer Wi-Fi standards (802.11a/n/ac/ax). Faster speeds, but shorter range.|
|`3.` **Cellular Bands** – For 4G (LTE) and 5G. These range from lower frequencies (700 MHz) to mid-range (2.6 GHz) and even higher frequencies for some 5G services (up to 28 GHz and beyond).|

Different frequencies play crucial roles in wireless communication due to their varying characteristics and the trade-offs between range and speed. Lower frequencies tend to travel farther but are limited in the amount of data they can carry, making them suitable for broader coverage with less data demand. In contrast, higher frequencies, while capable of carrying more data, have a much shorter range. Additionally, frequency bands can get congested as many devices operate on the same frequencies, leading to interference that degrade performance. To manage and mitigate these issues, government agencies (such as the FCC in the United States) regulate frequency allocations, ensuring orderly use of the airwaves and preventing interference among users.

---

## Summarizing

On a typical day, we might use several forms of wireless technology. At home, our wireless router provides internet access via Wi-Fi at both 2.4 GHz and 5 GHz frequencies to devices like our phone and laptop. When we leave home, our phone automatically connects to the internet using the nearest cell tower over 4G or 5G networks. While traveling abroad, we can turn on our phone’s mobile hotspot to share our cellular data with a friend’s laptop. Throughout these activities, we engage with three key wireless technologies: Wi-Fi for local wireless access, cellular networks for wide-area coverage, and a mobile hotspot for personal data sharing.


# Network Security

---

In networking, the term security refers to the measures taken to protect data, applications, devices, and systems within this network from unauthorized access or damage. The goal is to uphold and maintain the `CIA triad`:

|**Principle**|**Description**|
|---|---|
|`Confidentiality`|Only authorized users can view the data.|
|`Integrity`|The data remains accurate and unaltered.|
|`Availability`|Network resources are accessible when needed.|

In the next paragraphs, we will discuss two critical components of network security: `Firewalls` and `Intrusion Detection/Prevention Systems (IDS/IPS)`.

---

## Firewalls

A `Firewall` is a network security device, either hardware, software, or a combination of both, that monitors incoming and outgoing network traffic. Firewalls enforce a set of rules (known as `firewall policies` or `access control lists`) to determine whether to `allow` or `block` specific traffic. We can imagine a firewall as a security guard at the entrance of a building, checking who is allowed in or out based on a list of rules. If a visitor doesn’t meet the criteria (e.g., not on the guest list), they are denied entry.

_**The open source router/firewall [pfSense](https://www.pfsense.org/). Its large number of plugins (known as "Packages") give it a range of capabilities.**_ ![[Assets/Network Foundations/754c67cdf0a00f6d5ba7509387db3439_MD5.gif]]

Firewalls operate by analyzing packets of data according to predefined rules and policies, commonly focusing on factors such as IP addresses, port numbers, and protocols. This process, known as traffic filtering, is defined by system administrators as permitting or denying traffic based on specific conditions, ensuring that only authorized connections are allowed. Additionally, firewalls can log traffic events and generate alerts about any suspicious activity. Below are some of the different types of firewalls.

#### 1. Packet Filtering Firewall

|**Description**|
|---|
|Operates at Layer 3 (Network) and Layer 4 (Transport) of the OSI model.|
|Examines source/destination IP, source/destination port, and protocol type.|
|`Example`: A simple router ACL that only allows HTTP (port 80) and HTTPS (port 443) while blocking other ports.|

#### 2. Stateful Inspection Firewall

|**Description**|
|---|
|Tracks the state of network connections.|
|More intelligent than packet filters because they understand the entire conversation.|
|`Example`: Only allows inbound data that matches an already established outbound request.|

#### 3. Application Layer Firewall (Proxy Firewall)

|**Description**|
|---|
|Operates up to Layer 7 (Application) of the OSI model.|
|Can inspect the actual content of traffic (e.g., HTTP requests) and block malicious requests.|
|`Example`: A web proxy that filters out malicious HTTP requests containing suspicious patterns.|

#### 4. Next-Generation Firewall (NGFW)

|**Description**|
|---|
|Combines stateful inspection with advanced features like deep packet inspection, intrusion detection/prevention, and application control.|
|`Example`: A modern firewall that can block known malicious IP addresses, inspect encrypted traffic for threats, and enforce application-specific policies.|

Firewalls stand between the internet and the internal network, examining traffic before letting it through. In a home environment, our router/modem often has a built-in firewall (software-based). In that case, it’s all in one device, and the firewall function is `inside` the router. In larger networks (e.g., business environments), the firewall is often a separate device placed after the modem/router and before the internal network, ensuring all traffic must pass through it.

![[Assets/Network Foundations/5b9be9394661c560b21c0720ad1f03a1_MD5.webp]]

---

## Intrusion Detection and Prevention Systems (IDS/IPS)

Intrusion Detection and Prevention Systems (IDS/IPS) are security solutions designed to monitor and respond to suspicious network or system activity. An Intrusion Detection System (IDS) observes traffic or system events to identify malicious behavior or policy violations, generating alerts but not blocking the suspicious traffic. In contrast, an Intrusion Prevention System (IPS) operates similarly to an IDS but takes an additional step by preventing or rejecting malicious traffic in real time. The key difference lies in their actions: an IDS detects and alerts, while an IPS detects and prevents.

_**The widely used [Suricata](https://suricata.io/) software can function as both an IDS and an IPS. Here, we see the user enable a detection rule, then begin inline monitoring.**_ ![[Assets/Network Foundations/69e25be8cf9c8daf5136864cd069549e_MD5.gif]]

Both IDS and IPS solutions analyze network packets and compare them to known attack signatures or typical traffic patterns. This process involves:

|**Techniques**|**Description**|
|---|---|
|`Signature-based detection`|Matches traffic against a database of known exploits.|
|`Anomaly-based detection`|Detects anything unusual compared to normal activity.|

When suspicious or malicious behavior is identified, an IDS will generate an alert for further investigation, while an IPS goes one step further by blocking or rejecting the malicious traffic in real time.

_**Suricata in IDS mode.**_ ![[Assets/Network Foundations/7d6990ae25bc1dfe4f4c669a2c697da7_MD5.gif]]

Below are some of the different types of firewalls IDS/IPS.

#### 1. Network-Based IDS/IPS (NIDS/NIPS)

|**Description**|
|---|
|Hardware device or software solution placed at strategic points in the network to inspect all passing traffic.|
|`Example`: A sensor connected to the core switch that monitors traffic within a data center.|

#### 2. Host-Based IDS/IPS (HIDS/HIPS)

|**Description**|
|---|
|Runs on individual hosts or devices, monitoring inbound/outbound traffic and system logs for suspicious behavior on that specific machine.|
|`Example`: An antivirus or endpoint security agent installed on a server.|

IDS/IPS can be placed at several strategic locations in a network. One option is to position them behind the firewall, where the firewall filters obvious threats, and the IDS/IPS inspects any remaining traffic. Another common placement is in the DMZ (Demilitarized Zone), a separate network segment within the larger network directly exposed to the internet, where they monitor traffic moving in and out of publicly accessible servers. Finally, IDS/IPS solutions can also run directly on endpoint devices, such as servers or workstations, to detect suspicious activity at the host level. The following diagram shows an IDS/IPS positioned after the firewall.

![[Assets/Network Foundations/5a132c557535c60e18a26f6348ae48df_MD5.webp]]

---

## Best Practices

Here are the best practices for enhancing network security, summarized in the following table:

| **Practice**                   | **Description**                                                                                                                                                                                                      |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Define Clear Policies`        | Consistent firewall rules based on the principle of `least privilege` (only allow what is necessary).                                                                                                                |
| `Regular Updates`              | Keep firewall, IDS/IPS signatures, and operating systems up to date to defend against the latest threats.                                                                                                            |
| `Monitor and Log Events`       | Regularly review firewall logs, IDS/IPS alerts, and system logs to identify suspicious patterns early.                                                                                                               |
| `Layered Security`             | Use `defense in depth` (a strategy that leverages multiple security measures to slow down an attack) with multiple layers: Firewalls, IDS/IPS, antivirus, and endpoint protection to cover different attack vectors. |
| `Periodic Penetration Testing` | Test the effectiveness of the security policies and devices by simulating real attacks.                                                                                                                              |


# Data Flow Example

---

Based on the knowledge we have gained from the previous sections, the following paragraphs will show precisely what happens when a user tries to access a website from their laptop. Below is a breakdown of these events in a client-server model.

#### 1. Accessing the Internet

Let's imagine a user using their laptop to connect to the internet through their home Wireless LAN (WLAN) network. As the laptop is connecting to this network, the following happens:

|**Steps**|
|---|
|The laptop first identifies the correct wireless network/SSID|
|If the network uses WPA2/WPA3, the user must provide the correct password or credentials to authenticate.|
|Finally, the connection is established, and the DHCP protocol takes over the IP configuration.|

#### 2. Checking Local Network Configuration (DHCP)

When a user opens a web browser (such as Chrome, Firefox, or Safari) and types in [www.example.com](http://www.example.com) to access a website, the browser prepares to send out a request for the webpage. Before a packet leaves the laptop, the operating system checks for a valid IP address for the local area network.

|**Steps**|**Description**|
|---|---|
|`IP Address Assignment`|If the laptop does not already have an IP, it requests one from the home router's `DHCP` server. This IP address is only valid within the local network.|
|`DHCP Acknowledgement`|The DHCP server assigns a private IP address (for example, _192.168.1.10_) to the laptop, along with other configuration details such as subnet mask, default gateway, and DNS server.|

#### 3. DNS Resolution

Next, the laptop needs to find the IP address of `www.example.com`. For this to happen, the following steps must be taken.

|**Steps**|**Description**|
|---|---|
|`DNS Query`|The laptop sends a DNS query to the DNS server, which is typically an external DNS server provided by the ISP or a third-party service like Google DNS.|
|`DNS Response`|The DNS server looks up the domain `www.example.com` and returns its IP address (e.g., 93.184.216.34).|

#### 4. Data Encapsulation and Local Network Transmission

Now that the laptop has the destination IP address, it begins preparing the data for transmission. The following steps occur within the `OSI/TCP-IP` model:

|**Steps**|**Description**|
|---|---|
|`Application Layer`|The browser creates an HTTP (or HTTPS) request for the webpage.|
|`Transport Layer`|The request is wrapped in a TCP segment (or UDP, but for web traffic it's typically TCP). This segment includes source and destination ports (HTTP default port 80, HTTPS default port 443).|
|`Internet Layer`|The TCP segment is placed into an IP packet. The source IP is the laptop's private IP (e.g., 192.168.1.10), and the destination IP is the remote server’s IP (93.184.216.34).|
|`Link Layer`|The IP packet is finally placed into an Ethernet frame (if we're on Ethernet) or Wi-Fi frame. Here, the MAC (Media Access Control) addresses are included (source MAC is the laptop's network interface, and destination MAC is the router's interface).|

When the encapsulated frame is ready, the laptop checks its ARP table or sends an ARP request to find the MAC address of the default gateway (the router). Then, the frame is sent to the router using the router’s MAC address as the destination at the `link layer`.

#### 5. Network Address Translation (NAT)

Once the router receives the frame, it processes the IP packet. At this point, the router replaces the private IP (192.168.1.10) with its public IP address (e.g., 203.0.113.45) in the packet header. This process is known as `Network Address Translation (NAT)`. Next, the router forwards the packet to the ISP's network, and from there, it travels across the internet to the destination IP (93.184.216.34). During this process, the packet goes through many intermediate routers that look at the destination IP and determine the best path to reach that network.

#### 6. Server Receives the Request and Responds

Upon reaching the destination network, the server's firewall, if there is one, checks if the incoming traffic on port 80 (HTTP) or 443 (HTTPS) is allowed. If it passes firewall rules, it goes to the server hosting `www.example.com`. Next, the web server software (e.g., Apache, Nginx, IIS) receives and processes the request, prepares the webpage (HTML, CSS, images, etc.), and sends it back as a response.

The server's response process follows a similar path in reverse. Its IP (93.184.216.34) is now the source, and our home router's public IP (203.0.113.45) is the destination. When the packet reaches our home router (203.0.113.45), NAT ensures it is mapped back to the laptop's private IP (192.168.1.10).

#### 7. Decapsulation and Display

Finally, our laptop receives the response and strips away the Ethernet/Wi-Fi frame, the IP header, and the TCP header, until the application layer data is extracted. The laptop's browser reads the HTML/CSS/JavaScript, and ultimately displays the webpage.

#### Data Flow Diagram

Below is a flow chart showing the complete journey of a user accessing a website on the internet.

![[Assets/Network Foundations/6a8c5a4bac752067f279d6650dea5a8f_MD5.webp]]

---
## Exercises/Questions
##### Exercises
[[#Relevant section|Exercise question.]] [(Link)](https://academy.hackthebox.com/module/19/section/102)
##### Questions:

[[#What is a Network?|What is the term for a collection of interconnected devices that can communicate and share resources with each other?]] A: <span class="hover-reveal">Network</span>

[[#Wide Area Network (WAN)|What is the largest Wide Area Network (WAN) that connects millions of Local Area Networks (LANs) globally?]] A: <span class="hover-reveal">Internet</span>

[[#Local Area Network (LAN)|What is the acronym for a network that connects devices over a short distance, such as within a home, school, or small office building?]] A: <span class="hover-reveal">LAN</span>

[[#Relevant Section|Question]] A: <span class="hover-reveal">Answer</span>

[[#Relevant Section|Question]] A: <span class="hover-reveal">Answer</span>

[[#Relevant Section|Question]] A: <span class="hover-reveal">Answer</span>
