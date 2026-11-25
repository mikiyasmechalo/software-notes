---
title: Mobile Programming
---
# CH1: Fundamentals of Mobile Computing
**Mobile** 
We can see mobility within 3 perspectives
- **Device Mobility**: devices like smartphones, tablets, or laptops can move between different locations while maintaining seamless access to data and services.
- **User Mobility**: users being able to switch devices or change physical locations while still accessing their data and services. User moves service follow him.
- **Data Mobility**: It enables data to be accessed and used across various devices and locations.

**Computing** 
- Using computers to process data, perform calculations and run applications.
- It encompasses both hardware and software parts.

***Mobile Computing*** 
Using portable devices to perform computing tasks and access data wirelessly from virtually aby location.
Is a term used to describe technologies that enable people transmit process elements (voice, data...) in computing.

Mobile Computing is a technical field that covers the design, development and evaluation of mobile applications using appropriate solutions that meet user requirements.

There are 2 aspects of mobile computing
1. *User Mobility* - users communicate from anywhere with anyone with the same services.
2. *Device portability* - ability for devices to be connected anytime & anywhere to the network.

**Portability** - designed for on-the-go use, stay connected anywhere.
**Connectivity/mobility** - WI-FI and cellular data enables seamless access to information and service.
**Versatility** - multiple functions from communication to entertainment in one package.

Key Elements of Mobile Computing:
*Wireless Data Transmission* - without cables and physical connections.
*Mobility* - on the go computation from anywhere.
*Flexible Connectivity* - Seamless integration of voice, image, data ... across devices and networks.

#### Mobile Computing Evolution
The evolution of mobile computing spans four decades of transformative change:
- 1980s: IBM Simon. Basic mobile calls and email established the first foundation.
- 2000s: BlackBerry & iPhone. Push notifications and the shift to the app-driven interface.
- 2010s: 4G & Cloud. Faster networks enabled cloud-powered navigation and true multitasking.
- 2020s: 5G & AI. Integration of 5G and AI drives sophisticated real-time services like location tracking and instant alerts.

#### Mobile Computing Components
- Hardware: Consists of portable devices (smartphones, tablets, wearables) and essential infrastructure like base stations and servers, designed for full-duplex data processing.
- Software: Includes the operating system, mobile applications (apps), and middleware/APIs that manage the unique requirements and characteristics of the mobile environment.
- Communication: The infrastructure of wireless networks (cellular, Wi-Fi, Bluetooth), protocols (TCP/IP), and services that enable reliable, and continuous data exchange between devices.

#### Device Mobility and Connectivity
- Fixed and Wired: Devices are stationary and use a physical link (e.g., ethernet cable) for network communication (Ex: Desktop appliance).
- Fixed and Wireless: Devices are stationary but use a wireless medium (e.g., radio waves) for network communication (Ex: Wi-Fi router).
- Mobile and Wired: Devices are portable but require a physical connection (e.g., telephone network/modem) to reconnect to the network when moved (Ex: Laptops).
- Mobile and Wireless: Devices are portable and maintain communication seamlessly regardless of location using only a wireless connection (Ex: Portable Router, Smartphone).


### Network Reference Model
A network reference model is a conceptual framework (like the OSI model) that organizes telecommunication functions into abstraction layers to manage complex mobile network interactions, ensuring standardization, interoperability, and efficient data transmission.

The OSI model is one of these frameworks.
##### 1. Physical Layer 
Deals with the physical connection b/n devices transmitting **raw bit** streams over physical medium.
Functions:
- defines hardware specifications
- handle bit rate control
- manages physical connections

Example Devices - Hubs, repeaters, network adapters

##### 2. Data Link Layer
Does node-to-node data transfer and error detection and correction. 
- Deals with **Frames**.
Functions:
- Error detection and correction
- Frame synchronization (organizing data into frames)
- Flow Control
- Media Access Control (MAC) for controlling access to shared medium.

Devices - Switches, bridges, and network interface cards (NICs).

##### 3. Network Layer
Manages data routing and forwarding between devices across different networks. 
- Deals with **Packets**.
Functions: 
- Logical (IP) addressing
- Routing (finding best path)
- Fragmentation and reassembly

Devices - Routers, Layer 3 switches.

##### 4. Transport Layer
Provides reliable data transfer services to the upper layers. It ensures complete data transfer and error recovery.
Deals with Segments (TCP) or Datagram (UDP).
Function:
- Flow control
- Error checking and data recovery.
- End-to-end communication (handles app specific delivery using port numbers)
- Segmentation and reassembly.

Protocols - TCP and UDP
Devices - Firewalls (for filtering ports), proxies, gateways

##### 5. Session Layer
Manages sessions or connections between applications. It establishes, maintains, and terminates *connections*.
Deals with raw **Data**.

##### 6. Presentation Layer
 Translates data between the application layer and the network. It handles data *encryption*, *compression*, and *translation*.
Deals with raw **Data**.

##### 7. Application Layer
Provides network services directly to end-user applications. It includes protocols for specific applications like HTTP, FTP, and SMTP.
Deals with raw **Data**./ message

**Addresses** 
Four levels of addresses are used in an internet employing the TCP/IP protocols: 
1.  **Physical Address (MAC):** Used at the **Data Link Layer** to identify and deliver a frame to a specific device on the **local network** (LAN).
2.  **Logical Address (IP):** Used at the **Network Layer** for **global routing**, identifying the device across different networks (the Internet).
3.  **Port Address:** Used at the **Transport Layer** to specify the **application or process** that should receive the data on the destination device (e.g., your web browser).
4.  **Application-Specific Address (URL/Email):** Used at the **Application Layer** as the highest-level identifier, making it easy for users to interact with services (e.g., website names). 

#### Components
**End-Systems and Mobile Devices** 
*End-systems* encompass any Mobile Computing Devices like **PDAs**, **smartphones**, or **Kiosks**. These devices require a full **protocol stack** comprising multiple communication layers.

**Intermediate Systems and Communication** 
*Intermediate systems* are part of the Communication System and include **interworking devices** such as **routers** or **gateway devices**. In these systems, **some layers** of the protocol stack may be **disappeared** (or omitted) as they are not needed for simple forwarding.

For effective design, each layer should:
* Perform a **well-defined function**.
* Be chosen with an eye toward defining **internationally standardized protocols**.
* Have boundaries chosen to **minimize the information flow** across the interfaces.


**Simplified Reference Model**
1. Physical Layer
2. Data-Link Layer
3. Network Layer
4. Transport Layer
5. Application Layer

### Mobile Computing Architecture

3-Tier architecture of mobile computing
1. **Presentation Tier:** The user interface layer (e.g., web browsers, mobile apps) where users interact with the application, using technologies like HTML, CSS, JavaScript, Swift, or Kotlin.
	- context aware and device independent
	- UI, Input handling, Local processing, data formatting, session management
2. **Application Tier (Logic Tier):** The middle layer that handles the core functionality and **business logic**. It processes inputs and performs calculations, often using languages/frameworks like Java, Python, Spring, or Django.
    - service coordination, management, security controls
3. **Data Tier:** The layer responsible for **data storage, retrieval, and management**. This includes databases and management systems, utilizing SQL (MySQL, PostgreSQL) or NoSQL (MongoDB, Cassandra) technologies.
	- Storage, retrieval & manipulation, security, synchronization


### Types of Middleware
**Message Oriented Middleware (MOM)** - designed to connects different applications through exchange of messages.
 - message queue is used to store the messages until it can be processed.

**Transaction Processing (TP) Middleware** - Provides a mechanism for developing transaction-based distributed  applications.
- It includes management features like restarting failed processes and  enforcing consistency of distributed data.
- client requests ›→ different application tasks

**Communication Middleware** - used to connect one application to another
**Transcoding Middleware** - Changing one format of data to another format to suit the need of the client

### Mobility and standard IP routing
Standard IP Routing uses an address split into a *network part* (for routing) and a *host part*. This system works because routers only need to know the fixed network location.

When a user roams between networks, their existing IP address becomes invalid because it points to their old location.

The goal is transparency (seamless continuation of applications). Users can't change their IP address mid-application because it would break their ongoing connections.

**Mobile IP** protocol was developed to solve this problems faced by mobile users in the traditional, fixed IP environment.

**Mobile IP**: A Solution for Roaming Users (by IETP org.)
A protocol designed to let devices **stay connected to the internet regardless of their physical location** without requiring them to change their core IP address.

Key Features and Benefits:
* **Transparency:** It allows the host (user device) to move seamlessly without interrupting ongoing applications.
* **No Address Change:** Users can maintain their **original IP address** even when connected to a foreign network.
* **Minimal Impact:** It **requires no changes** to the software on non-mobile hosts or routers, minimizing deployment effort.
* **Infrastructure Addition:** It requires the addition of **new infrastructure components** (like Home and Foreign Agents) to function.
* **Universality:** It has **no geographical limitations** and supports necessary security features.

*2-type of address Mobile IP uses*
_Home Address_ → For identifying the devices (like a home address for your mail)
_Care-Of-Address_ → For the Purpose of Routing (a temporary address to deliver the mail to when away)

**Components / Entities  of Mobile IP**
1. *Mobile Nodes* - Any device the frequently change its location without changing the  permanent IP.
	- Assigned a permanent IP called its home address to which other hosts send packets regardless of its actual location.
2. *Home Network* : It is a network to which the mobile node originally belongs as per its assigned IP address (home address).
	- The base station network to which the mobile node originally belongs to.
3. *Home Agent* - a Router on the home network.
	- It serves as the anchor point for communication with the Mobile Node.
	- Router with additional functionality Located on home network.
	- Mobility binding of MN’s IP with its Care of Address (COA) & Forwards packets to appropriate network when MN is away – uses encapsulation.
4. *Foreign Network* - Any network other than the home network. 
	- The networks on which mobile nodes have a registered IP.
5. *Foreign Agent* - a default router in the foreign network.
	- used to send and receive data between home agent and mobile node.
	- advertises itself periodically.
6. *Care-of-address (COA)* - MN's current location
	- sent by FA to HA when MN attaches
	- usually the IP address of the FA
7. *Correspondent node* - End host to w/c MN is corresponding (e.g. a web server)


**How Does Mobile IP Work?**
- data is sent
- data packets contain the correspondent (source) and home addresses (destination).
- data arrives but mobile node is away.
- the foreign agent sends the care-of-address to the home agent(happens as soon as a mobile connects). a tunnel is established b/n HA and FA by the process of tunneling.


##### Mobile IP Operation Summary
**Phase 1: Agent Discovery** 
The Mobile Node (MN) determines its network location by listening for agents.
* **Agent Advertisement:** Home Agents (HA) and Foreign Agents (FA) periodically announce their presence using extended **ICMP** messages.
* **Agent Solicitation:** If no advertisements are received, the MN actively sends a solicitation request to find an agent.

**Phase 2: Registration** 
If on a foreign network, the MN informs the HA of its current **Care-of Address (CoA)** so packets can be forwarded.
* **CoA Types:** 
    * *FA CoA:* The address of the Foreign Agent (Registration path: MN $\rightarrow$ FA $\rightarrow$ HA).
    * *Co-located CoA:* An IP acquired directly by the MN, e.g., via DHCP (Registration path: MN $\rightarrow$ HA).
* **Mobility Binding:** The HA updates its table with the MN's Home Address, current CoA, and a **Registration Lifetime**. It sends an acknowledgment (ACK) to complete the process.
* **De-registration:** When the MN returns to its home network, it sends a request with a **lifetime of zero** to the HA, instructing it to stop interception.

**Phase 3: Traffic Interception & Tunneling (To MN)**
The HA establishes a "virtual pipe" to deliver data to the roaming MN.
* **Interception:** The HA uses **Proxy ARP** to "masquerade" as the MN on the home network, intercepting packets destined for the MN's Home Address. 
* **Encapsulation (Tunneling):** The HA wraps the original packet inside a new IP packet (often **IP-in-IP**).
    * *New Source Address:* The HA's address.
    * *New Destination Address:* The Care-of Address (CoA).
* **Routing:** The encapsulated packet is routed through the Internet to the CoA.

**Phase 4: Delivery and Decapsulation**
* **Decapsulation:** The tunnel endpoint, either the **FA** or the **MN** (if using a Co-located CoA), receives the bundle and removes the outer header to recover the original IP datagram.
* **Delivery:** If an FA is used, it delivers the original packet to the MN using the MN's Layer 2 (hardware) address.

**Phase 5: Traffic From MN (Triangular Routing)** 
* **Direct Routing:** Packets sent **from** the MN to a Correspondent Node (CN) are typically routed **directly**, bypassing the HA.
* **Reverse Tunneling:** (Optional) Traffic can be tunneled back to the HA before going to the CN. This is required only if the foreign network has strict security (like ingress filtering) that blocks IPs not belonging to its subnet.

Simplified: The 3 Key Steps

| Phase                           | Description of Operation                                                                                                                                            | Key Components                      |
| :------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :---------------------------------- |
| **1. Registration**             | The **MN** informs its **HA** of its current temporary address **CoA** on the foreign network.                                                                      | **MN, HA, CoA, Mobility Binding**   |
| **2. Tunneling (To MN)**        | The **HA intercepts** traffic destined for the MN's permanent **Home Address**. It **encapsulates** the packet and forwards it through a virtual tunnel to the CoA. | **HA, Home Address, Encapsulation** |
| **3. Delivery & Decapsulation** | The tunnel endpoint (the **Foreign Agent (FA)** or the MN) receives the packet, removes the tunnel header, and delivers the original data to the MN.                | **FA, Decapsulation**               |
| **4. Traffic From MN**          | The MN sends outgoing traffic directly to the Correspondent Node (CN) using its CoA as the source.                                                                  | **Triangular Routing**              |


### Design Consideration in MC
The design must manage applications that are both **context-independent** (behaving the same way regardless of environment) and **context-sensitive** (adapting their content and behavior based on the environment).
1. The Role of Context
	- **Context** is the basis by which an **Adaptation Manager** or algorithm decides **how to modify content or application behavior**.
2. Key Context Managers
MC systems typically require several managing components to handle and act upon this context:

| Manager                    | Function                                                                                                                               |
| :------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| **Client Context Manager** | Collects and manages information about the current environment (e.g., location, network speed, battery life).                          |
| **Policy Manager**         | Defines the **rules** and goals for adaptation (e.g., "If battery is below 10%, reduce video quality").                                |
| **Adaptability Manager**   | Executes the changes; applies the policies to modify the content or application behavior.                                              |
| **Security Manager**       | Ensures data and application security in diverse and changing contexts (e.g., handles authentication changes when switching networks). |

**1. Client Context Manager**
It operates through a set of **Awareness Modules** to manage context by:
* **Context Sensing** (capturing data).
* **Context Representation** (structuring the data).
* **Context Interpretation** (understanding the data's meaning).

**2. Policy Manager**
This is essentially a **set of rules** that govern mobility. In combination with the user's role and the current context, policies determine **what actions a user is allowed to perform**.

**3. Security Manager**
This manager provides a **secure connection** between the mobile client and the server. It enforces security policies, and if security requirements are not met, services may be **denied**. It ensures security with respect to:
* **Confidentiality** (via **Encryption**).
* **Integrity** (via **Hashing**).
* **Availability** (via **Firewall**).
* **Non-repudiation** (via **Digital signature**).
* **Trust** (via third-party recommendation systems).

**4. Adaptability Manager**
This component **adapts content and application behavior** based on the current context and policies. This involves **Content Transcoding** or adaptation to match:
* **Physical capabilities** of the device (e.g., screen size).
* **Logical capabilities** of the device (e.g., ability to display video).
* **Effective network bandwidth**.

### Security in Mobile IP
The only required authentication for secure Mobile IP is between the **Mobile Node (MN) and the Home Agent (HA)**. 
To prevent attacks like **replay attacks**, using **timestamps is mandatory**, while random numbers in request-reply packets are optional.
Importantly, the HA and Foreign Agent (FA) **do not need to share security information**.

### Mobile Computing (MC) Infrastructure and Components
The MC Infrastructure is the underlying framework that allows mobile devices to connect and compute on the go, without physical cables. Its core goals are **Connectivity, Mobility, Interoperability, and Scalability**.

| Component Area              | Examples                                                                                                                               |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| **Core Components**         | Mobile Devices (H/W + S/W), Mobile Networks (5G, Wi-Fi), Access Points (Cell Towers, Routers), and Communication Protocols (GSM, LTE). |
| **Supporting Technologies** | **Cloud Computing**, **Edge Computing**, **Virtualization**, and **Security Measures**.                                                |

Emerging Features and Future Trends: AI and ML, 5G, IoT, AR/VR, Quantum computing.
* **Mobile Edge Computing:** Moving computation and storage closer to the user to improve response times.
### Challenges in Mobile Computing Systems
The major challenges are often grouped into three areas:

| Challenge Area        | Specific Issues                                                                                                                                                                               |
| :-------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Lack of Standards** | Absence of pre-written specifications across different technologies.                                                                                                                          |
| **Connectivity**      | High **disconnection** rates, **scarcity of bandwidth** (divided among cells), facing **heterogeneous networks** (multiple network types), and **security risks** inherent in wireless links. |
| **Portability**       | High **power consumption** (battery reliance), small user interface issues, data loss, and systems issues.                                                                                    |

Mobile Computing Usage (Any Usage?)
Mobile computing is widely used in:
* **Vehicles** (GPS, Telematics).
* **Emergencies** (Dispatch, field coordination).
* **Credit Card Verification** (Mobile payment terminals).
* **Replacement of Wired Networks** (for flexibility).
* **Infotainment** (streaming media).
* **Location-dependent services** (maps, retail offers).



# CH2: Mobile Communication Technologies

### Overview on Mobile Technologies
*Telecommunications* are the means of electronic transmission of information over distances.
*Telecom Networks* is an arrangement of computing and telecommunications resources for communication of information between distant locations.

Components in Telecom Network:
1. *Terminals* - to access the network
2. *Devices* - process information and are interconnected by the network
3. *Telecommunication links* - transmission channels
4. *Telecommunication equipment* - facilitate the transmission the transmission of information. 
5. *Telecommunication software* - controls message transmission over the network.

"*Mobile Communication*" - is basically = wireless communication, no physical link

How to categorize Mobile communication system?
![[Pasted image 20251124101646.png]]

##### Terminologies
*Mobile Station* - Handheld devices w/c support cellular radio system.
*Base Station* - a Fixed Tower in radio communication with mobile station.
*Mobile Switching Center (MSC)* - coordinates the routing of calls in large area. responsible to base station and mobile to PSTN.
*PSTN (public-switched telephone network)* - a global network over worldwide.
*Channel* - various types
- Control Channel - a radio channel for transmission of call request, setup and initiation.
- Page - the actual message w/c is broadcast over entire service area
- Forward control channel - radio channel for transmission of info from BS to mobile station.
- Reverse control channel - radio channel for transmission of info from MS to BS.
*Handoff* - the process of transferring a mobile station from one channel or a base station to another.
*Simplex, Half-Duplex, Full-Duplex* ...

### Cellular Networks
0-Generation Telecom/Mobile Communication tech
##### 0G. Mobile Telephony System (MTS) - AKA *Car-Based mobile Telephony*.
- Mobile transceivers of MTS were very big and could be carried only by vehicles.
- it was analog (processed voice info as a continuous waveform)
- it was half-duplex. (push a button to switch from speaking to listening..)
- base stations used the same frequencies.
- due to power limitations mobile units transmitted not directly to the BS but to receiving units.
- Operators manually switched calls and there were only 3 channels.

IMTS (Improved MTS)
- automatic call switching
- Full duplex
- 23 channels
- had a interference problem due to large power of BS transmitter

##### 1G. First Generation

| Feature                  | 0G (MTS/IMTS – Pre‑Cellular)                        | 1G (Analog Cellular)                                                | Improvement                             |
| ------------------------ | --------------------------------------------------- | ------------------------------------------------------------------- | --------------------------------------- |
| **Call Setup**           | Manual operator assistance required                 | Automatic call setup                                                | Faster, more convenient                 |
| **Duplex Mode**          | Half‑duplex (push‑to‑talk, one direction at a time) | Full‑duplex (simultaneous talk & listen)                            | Natural conversation flow               |
| **Network Architecture** | Single high‑power base station, limited coverage    | Cellular architecture with multiple cells, frequency reuse, handoff | Larger coverage, efficient spectrum use |
| **Capacity**             | Very few channels (e.g., 3–23 channels in IMTS)     | Hundreds of channels per city                                       | Huge increase in user capacity          |
| **Mobility**             | Limited, bulky car‑based units                      | Portable handsets (though still large)                              | Greater user mobility                   |
| **Spectrum Efficiency**  | Poor, interference issues                           | Frequency reuse with cell splitting                                 | Better spectrum utilization             |
| **Quality of Service**   | Analog, noisy, prone to interference                | Improved analog voice quality with error reduction                  | Clearer calls                           |
| **Scalability**          | Could not scale to large populations                | Designed to support millions of subscribers                         | Enabled mass adoption                   |

- **1G introduced true cellular technology**: automatic switching, handoff between cells, and frequency reuse.  
- It moved from **manual, car‑based, half‑duplex systems (0G)** to **portable, full‑duplex, automatic systems (1G)**.  

##### 2G. Second Generation
The first digital cellular networks - Digital modulation
used TDMA and CDMA to auto assign users.
Has brought :
 - Digital traffic channels
 - Encryption - to prevent eavesdropping.
 - Error detection and correction - digital traffic allows for detection and correction
 - Channel access - dynamically shared by a number of users.
 - Had various standards - GSM, IS-136, PDC, CDMA/IS-95, GSM being the most notable.

###### GSM
- backward Incompatible with 1G, b/c it is designed from scratch.
- data rate up to 9.6 Kbps using 124 channels per cell.
- 8 users per channel through TDMA.
introduced 3 types of services:
1. *Bearer services* - service for data transmission / non-voice / binary data.
	had 2 modes
	1. Transparent Bearer services - only uses the physical layer.
		- had constant delay and throughput.
		- forward error correction (FEC).
	2. Non-transparent Bearer services
		- has Radio Link Protocol (RLP) on top of transparent bearer services
		- Employ protocols in Link layer and network layer for reliability
	- and more services - PSTN, ISDN, PSPDN
2. *Tele Services* - primary goal of GSM
	- encrypted voice transmission, message services, message services
	- emergency numbers - free
	- short message services (MMS) - 160 char
	- Enhanced message service (EMS) - larger, formatted text, animated pics
	- Multimedia message service (MMS)
3. *Supplementary Services* - 
	Has brought :
	 • User identification
	 • Call redirection
	 • Forwarding of ongoing calls
	 • barring of incoming/outgoing calls

GSM composed of 3 Sub-systems :
- Radio sub-system
- Network and Switching subsystem
- Operating subsystem

**Radio Sub-system**
Comprises all radio specific entities,  i.e. Mobile nodes and BSS.
*Base Station subsystem (BSS)*:
- controlled by BSC.
- Responsible for:
	- Maintain connection to Mobile Node.
	- Coding and decoding voice

*Base station controllers (BSC)*:
- provides all the control functions and physical links between the MSC and BTS
- High-capacity switch that provides function.
	 - Handover,
	 - Cell configuration data
	 - Control of radio frequency (RF) power levels

*Base transceiver station (BTS)*:
- is the radio equipment (transceivers and antennas) needed to service each cell in the network.
- A group of BTS’s are controlled by an BSC.

**Network Switching Subsystem**
- Responsible for performing call processing and subscriber related functions.

Further equipped with:
- MSC
- performs the telephony switching functions of the system.
- It controls calls to and from other telephone and data systems

1. **Home location register (HLR)**
	- DB for storage and management of subscriptions, such as service profile, location, status.
2. **Visitor location register (VLR)** - BD that contains temporary information needed by the MSC
3. **Authentication center (AUC)** - provides authentication and encryption parameters that verify the users identity and ensure the confidentiality of each call.
4. **Equipment identity register (EIR)** - DB that contains information about the identity of mobile equipment that prevents calls from stolen, unauthorized or defective mobile stations.

**The Operating Subsystem** 
The management and maintenance brain of GSM. It doesn’t directly carry user traffic but ensures the whole system runs smoothly.

Main Functions:
- *Network Operation & Maintenance* - monitoring and detecting faults.
- *Configuration Management* - configure frequency plans, cell parameters
- *Performance Management* - collects statistics to optimize quality 
- *Security & Access Control* - manages access rights
- *Billing & Administration Support*- interfaces with NSS for subscriber usage data
- *Software Updates* - centralized control


**GSM Signaling Protocol - 4 Layers** 
1. *Physical Layer*  - radio specific functions
	- TDMA Framing: Dividing radio frequencies into time slots.
	- BTS synchronization 
	- Digital modulation 
	- Encryption/decryption 
	- Channel coding & error correction 
2. *Link Layer* 
	- LAPD$_m$ (Link Access Procedure on the Dm-channel) protocol at U$_m$("Air Interface" between the MS and the BTS)
	- Segmentation & Reassembly
	- Flow Control
1. *Network Layer* 
	- *RRM:* Setup, maintain, release radio channels 
	- *MM:* Registration, authentication, identification, location update, TMSI assignment 
2. *Cell Management Layer* 
   - Overall cell-level control and management 
   - BTS Management: Controlling the internal configuration of the base station.
   - Traffic Management


###### 2.5G (GPRS)
- 2G systems with a **packet switched** domain in addition to the circuit switched domain.
- had enhanced data rates. 28 Kbps & higher, up to 144Kbps

###### 2.75G (EDGE)
Increases transmission speeds on GSM networks and enables the transmission of large amounts of data at 384Kbps.


##### 3G. Third Generation 
- speeds 144Kbps and higher.
had max transfer rates of:
- 2.05 Mbps - for stationary devices
- 284 Kbps - slow moving devices
- 128 Kbps - fast moving devices

- Enhanced audio and video streaming;
- Video-conferencing support;
- IPTV (TV through the Internet) support

International Telecommunication Union (ITU) is responsible for standardizing 3G, there are five 3G standards. CDMA: (CDMA-2000, WCDMA, TD-CDMA), TDMA: (FDMA/TDMA, TDMA-SC)

UMTS is the well-known w/c is WCDMA operating at 2.1 GHz.

###### 3.5G
HSUPA - high speed uplink packet access
- upgrades the uplink for speed up to 5.8Mbps
HSDPA - high speed downlink packet access
- speeds up to 14Mbps
###### 3.75G
HSPA - high speed packet access
- a combination of HSUPA and HSDPA with speeds of 21 to 28 Mbps.


##### 4G. Fourth Generation
Refers to all-IP *packet-switched* networks, mobile ultra-broadband access and multi-carrier transmission.
- 100Mbps to mobile users and up to 1Gbps for fixed stations.

New Tech behind 4G,
- Smart antennas for multiple input and output
- Orthogonal Frequency Division Multiplexing(OFDM)
- IPV6
- VoIP
- Software defined Radio (SDR) System

Features of 4G
- Fully IP-Based Mobile system
- Seamless switching and variety of QoS
- Ad-Hoc and Multi-hop network
- Better spectral efficiency
- Interoperability with existing wireless standards

###### LTE (Long-Term Evolution)
- Standard managed by 3GPP (3rd) Generation Partnership Project Organization
- designed to provide up to 10 times the speed of 3G Network for mobile devices
- LTE is standard along Ultra Mobile Broadband and WiMAX (IEEE 802.16)
- LTE has a theoretical net bit rate
	- 100 MBit/S, ↓ speed
	- 50 MBit/S ↑ Speed

if a 20 MHz channel is used and more if multiple-input multiple-output (MIMO), i.e. antenna arrays, are used.




### Mobile Cloud Computing
Allows users to utilize infrastructure, platforms and software by cloud providers.

- **Cloud Computing**: is storing and Accessing data and programs via TCP/IP network instead in device’s storage devices.
- **Mobile Cloud Computing**: refers to an infrastructure where both the data storage and processing happens outside the mobile device.

Enabling Technologies
- Communication system (3G, 3.5G. 3.75G, 4G, 5G)
- HTML, CSS
- Hypervisor
- Web-services

Benefits
- Flexible and portable
- On-demand services
- Cost effectiveness
- Universal access
- allows to make backup and recovery
- centralized monitoring and maintenance of software

Drawbacks
- Trust, Security and privacy issues
- Data Security
- connectivity and performance issues
- Power consumption
- Congestion issues.

Applications 
- Mobile Commerce
- Cloud Email
- Mobile Learning
- Mobile Healthcare
- Cloud Music




# CH-4: Security in Mobile Computing
Security - protecting computer-related assets that are subject to a variety if threats.
- What assets?
- How are they threatened?
- What can we counter with?

(Network security) on the other hand deals with provisions and policies adopted to prevent and monitor unauthorized access, misuse, modification, or denial of the computer network and network-accessible resources.

WHY? as of 2023
- 1B malwares of w/c 58% are Trojans.
- every minute 4 companies get ransomware attacked
- Iran has the highest mobile malware infection rate at 30%


#### Threat Vs. Vulnerabilities Vs. Risk
**Threat**: a person/thing likely to cause damage, thing that we are going to protect against (hackers, malicious program, etc.)
- A threat to a computing system is a set of circumstances that has the potential to cause loss or harm.
**Vulnerabilities**: it is a weakness / gap in our protection system which can be exploited by threats to gain unauthorized access to our asset.
- is a weakness in the system, for example, in procedures, design, or implementation, that might be exploited to cause loss or harm.
**Risk**: a potential for loss, destruction/ damage of an asset as a result of a threat exploiting vulnerabilities.

Assess Harm:
- what bad things can happen?
- who or what can cause the bad things to happen?

#### Objectives of Security
1. **Confidentiality**: preventing un-authorized access. - Interception
	- *Data confidentiality* - private or confidential info is nu-accessible by unauthorized individuals.
	- *Privacy* - individual control about what info is collected and stored by whom and to whom it is disclosed.
2. **Authenticity** is the identification and assurance of the origin of information. - Fabrication
3. **Integrity**: protection from improper modification or destruction - Modification 
	- *Data Integrity* - info and programs changed in only specified and authorized manner.
	- *System Integrity* - a system must perform its functions in an unimpaired manner, no manipulations.
4. **Availability**: system must work promptly and service is not denied to authorized users. - Interruption

###### Classifications of Security Attacks
- **Passive Attacks** - eavesdropping, spying / observation. monitor content or traffic flow
- **Active Attacks** - modification of data stream: Masquerade, modify, denial, replay


#### Mobile Security 
Why?
- to keep unauthorized users out
- To ensure that computing assets access are not inadvertently given to parties not actively seeking a system breach. (HW, SW or comm. Channels)

Security consists of four parts:
1. *Physical security*: prevent interference signals + Protecting the hardware
2. *Data Security*: what encryption techniques are used to protect the data.
3. *User authentication*:  how to protect the wireless network from unauthorized users.
4. *User anonymity*: what kind of protection is used against information gathering.


#### Security concerns for mobile applications 
**Application Layer Security** 
- most important security layer.
Standalone Applications - no network connection
- Encryption - AES to protect sensitive data
- Auth and Authorization - app access - passwords, biometrics. authorization - what the user can do once authenticated.
Networked Applications - social media or cloud services...
- DS3, 3DES as additional encryption, use HTTPS

**Presentation and Session Layer Security** 
- Ensure the data displayed to the user is accurate and secure. - presentation layer
- SSL (Secure socket layer) - cryptographic protocol to secure data exchanged between client and server. - Session layer

**Transport and Network Layer Security** 
- handle communication between apps and manages data routing respectively
- TCP in Transport layer makes sure all parts are delivered.
- IP in Network Directs data packets between the user's device and the server.

- IPSec is a suite of protocols that secures communications by encrypting and authenticating data packets.

**Data link layer & Physical Layer** 
MAC addressing
authentication and authorization of nodes.


##### Wireless Security
- nearby devices can potentially sniff or intercept these signals.
- more vulnerable.

*Layered Security Approach* - multiple layers of defense for more protection.
*Physical Security* - protecting routers and access points from unauthorized access.
*Authentication* - WPA2/3 for strong passwords, MAC address filtering
*Encryption* - WPA2/3 and AES
*Firewalls* - monitor and filter in/out traffic.
*Network Monitoring* - monitor for suspicious activity.
*Regular Updates* - for firmware and software.


**Layered Approach Levels** 
BP="best practice"
1. Level 1 - wireless deployment and policy - 
	- BP - minimum number of WAPs for coverage.
	- Policies for new WAPs, NIC operational modes, WLAN user-group access
2. Level 2 - Wireless access control
	- 2 components - device control access and user authentication (personnel A.C)
	- BP - configuring WEP for high encryption, change SSID regularly, not broadcasting SSID, verifying MAC address upon connection
3. Level 3 - Perimeter Security = protecting wireless network infrastructure
	- VPN - an extension of a private network to encapsulate, encrypt and authenticate connections. a method for securing traffic
	- BP: install IPS(intrusion prevention system) and firewall, VPN for traffic encryption, enforce access policies for auth (pass.)
4. Level 4 - Application Security 
	- is a kind of minimizing vulnerability of d/t software systems.
	- through SDLC.
	- BP: implement app-level auth, install vendor patches ASAP
	- security measures: Auth and Auth: MFA and role based access control (RBAC), encryption -AES, input validation, session management, monitoring and logging, patches

#### Wireless Network Components and Architectural Models
2 components:
1. *Wireless End Station* - any physical device that can communicate using 802.11 standard
2. *Access Points* - 2 functions: - network platform to connect b/n WLANs or to a LAN, and as a relay between stations attached to the same AP.

The IEEE 802.11 standard defines 2 design structures 
- Infrastructure Mode - "Relay on fixed infrastructure as AP"
- Ad-Hoc Mode - decentralized type of network (like P2P)

Securing wireless ad hoc networks is cumbersome task → Because
- **Vulnerability of channels**
	- message can be eavesdropped and fake messages can be injected into the network
- **Vulnerability of nodes** 
- **Absence of infrastructure** 
- **Dynamically changing topology** 


What are security issues in protocol suite?
- *Application Layer*: detecting and preventing viruses, worms, malicious codes and other abuses
- *Transport layer*: Authenticating and securing end-to-end communications through encryption
- *Network layer*: Protecting the ad hoc routing and forwarding protocols
- *Link layer*: protecting the wireless MAC protocol and providing link-layer security support
- *Physical layer*: Preventing signal jamming denial-of-service attacks

###### Security and Privacy Concerns in Location-based Services (LDS)
Location-based services (LDS) are commonly used in mobile computing, and they come with a set of security and privacy concerns:
![[Pasted image 20251222213823.png]]
most of the security & privacy intimidations related to LDS have still not been appropriately addressed.

Security Concerns
- **Authentication**: Only authorized users should be able to access location data.
- **Traceability**: It’s crucial to track and report malicious activities.
- **Confidentiality**: location of data must be shared only with authorized parties, using encryption.
- **Efficiency**: Lightweight security mechanisms should be implemented to minimize overhead.
- **Anonymity**: The ability of a user to access something without disclosing the identity to the third-parties.
- **Short-term likability**:  A receiving vehicle (VANET) must be capable of verifying that the multiple messages it is receiving within a small-time frame.
- **Pseudonymity** : It gives assurance of resource access by a user without sharing its identity, but can still be answerable for that use.
- **Location Privacy**: The location of the user must be shielded from unapproved access.


**Security Vs Privacy**
While security focuses on protecting data and systems from threats, privacy is about ensuring that users have control over their personal information.
- **Data Privacy**: Ensuring that the content of a transaction is protected from unauthorized disclosure.
- **Source and Destination Privacy**: The identity of the parties involved in the transaction should be hidden.
- **Location Privacy**: The geographical or logical location of users should remain private.
- **Time Privacy**: The specific time a transaction occurs should not be disclosed.








