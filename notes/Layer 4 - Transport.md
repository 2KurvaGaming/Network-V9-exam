<h1 align="center">Layer 4 Transport</h1>

# Layer 4 is Transport 

🎉 **MISSION: LAYER 4 – THE TRANSPORT LAYER**  🛣️ 👮‍♀️*"The Traffic Controller of the Internet Highway" 🚓*

### 🚦 **Ensures the following:** 

  🚩 **Error Checking Protocols at the Transport Layer ensure that data is correctly sent or received Without Errors**

   🚩 **In Sequence / Service Addressing** A number of protocols support many network services. The Transport Layer ensures that data is passed to the right service at the upper layers of the OSI model
   
   🚩 **Segmentaion** To traverse the network, blocks of data need to be broken into packets of manageable size for the lower layers to handle. 

---

🚦 **Utilizes Port Numbers to keep application sessions unique**
   🔥 ***By creating a network socket = Source & Dest IP Addrss + Source & Dest Port Number***

---

### 🌐 **What Is the Transport Layer? (Layer 4)**

> **💡 Definition**:
> 
> The **Transport Layer** (Layer 4 of the OSI model) is responsible for **end-to-end communication**, ensuring data is delivered **, in sequence, and without errors** between two hosts — *regardless of the underlying network*.

### 🚆 **The Two Main Protocols: TCP vs UDP**

> 🎭 *"The Reliable Truck vs The Speedy Motorcycle"*

| **Feature** | **TCP (Transmission Control Protocol) REC 793** 🚛 | **UDP (User Datagram Protocol) REC768** 🏍️ |
|------------|----------------------------------------|--------------------------------------|
| **Connection Type** | ✅ Connection-oriented (handshake first) | ❌ Connectionless (fire and forget) |
| **Reliability** | ✅ Guaranteed delivery with ACKs & retransmissions | ❌ Best-effort (no guarantees) |
| **Ordering** | ✅ Data arrives in order | ❌ No guaranteed order |
| **Error Checking** | ✅ Full error detection + correction | ✅ Error detection only (no fix) |
| **Flow Control** | ✅ Yes (sliding window) | ❌ No |
| **Congestion Control** | ✅ Yes | ❌ No |
| **Speed** | ⏱️ Slower (overhead for reliability) | ⚡ Very fast |
| **Header Size** | 20–60 bytes | 8 bytes (lightweight!) |
| **Use Cases** | Web (HTTP/HTTPS), Email (SMTP), File Transfer (FTP) | Live streaming, VoIP, Online gaming, DNS |
| **Port Examples** | 80 (HTTP), 443 (HTTPS), 25 (SMTP) | 53 (DNS), 67/68 (DHCP), 123 (NTP) |

> 💡 **Think**:  
> - **TCP** = Sending a *registered letter* — you get confirmation it arrived.  
> - **UDP** = Throwing a *postcard into a crowd* — fast, but hope it lands!

<img width="1019" height="617" alt="Screenshot 2025-08-22 042908" src="https://github.com/user-attachments/assets/6e493532-c4bd-4902-962a-0ffec36751c4" />
</br>
<img width="1019" height="617" alt="Screenshot 2025-08-22 042908" src="https://github.com/user-attachments/assets/eef9ad75-5593-41ee-a5d9-bafa51e5ebbb" />

## 📌 **One of the functions of the Transport layer is to identify each type of network application by assigning it a port number.**
  - For example,  data requested from an HTTP web application can be identified as port 80, while data sent to an email server can be identified as port 25.
    
## 📍 **At the Transport layer, on the sending host, data from the upper layers is packaged as a series of layer 4 PDUs, referred to as segments.**

- Each segment is tagged with the application's port number.
- The segment is then passed to the Network layer for delivery.
- Many different hosts could be transmitting multiple HTTP and email packets at the same time
- These are multiplexed using the port numbers along with the source and destination network addresses onto the same link.

The Transport layer can also implement reliable data delivery mechanisms, should the application require it. Reliable delivery means that any lost or damaged packets are resent.

> Devices working at the Transport layer include multilayer switches - usually working as load balancers - and many types of security appliances, such as more advanced firewalls and intrusion detection systems (IDSs).

<img width="768" height="346" alt="transport_layer_diagram" src="https://github.com/user-attachments/assets/aa9d342c-d634-4bf5-b472-1aba29f02336" />

###### The image illustrates data flow at the Transport layer (Layer 4) of the OSI model. Two computers, labeled Host 2.2 and Host 2.3, are sending various types of network traffic to a third computer, labeled Host 2.1. Each data segment is marked with a different port number, representing different types of application traffic:

###### - Host 2.2 sends web traffic (port 80) and email (port 25) to Host 2.1.

###### - Host 2.3 sends file sharing traffic (port 445), voice communication (port 5061), and email (port 25) to Host 2.1.

###### - The diagram shows these data segments traveling across the network, encapsulated as Layer 3 packets in Layer 2 frames, before arriving at Host 2.1. Once at the destination, Host 2.1 examines the port number of each segment to identify the application type - such as web server, mail service, file sharing, or voice service - and directs the data accordingly for processing.

###### - The image visually conveys how the Transport layer uses port numbers to combine, transport, and then separate and deliver multiple types of application data coming from different hosts, ensuring each data type reaches the correct program on the receiving device.

---

### 🧩 **Key Responsibilities of the Transport Layer**

| ✅ Function | 📝 Description |
|-----------|---------------|
| **Error Checking** | ✅ Full error detection + correction | ✅ Error detection only (no fix) |
| **Service Addressing** | Uses port numbers to identify specific applications or services on a device (e.g., 80 for HTTP, 443 for HTTPS). Enables multiple apps to communicate simultaneously over the same network connection — like different apartment units sharing one building address (IP). 🔌🎯 |
| **Segmentation & Reassembly** | Breaks data from upper layers into *segments* (for TCP) or *datagrams* (for UDP), then reassembles at the destination. |
| **Flow Control** | Prevents a fast sender from overwhelming a slow receiver (like a traffic regulator). 🚦 |
| **Error Control** | Detects and retransmits lost/corrupted data (TCP only). ✅🔁 |
| **Congestion Control** | Slows down transmission if the network is overloaded (TCP). 🛑🚦 |
| **Multiplexing/Demultiplexing** | Uses **port numbers** to deliver data to the correct application (e.g., web vs email). 🔄📦 |
| **Connection Management** | Establishes, maintains, and terminates connections (TCP uses 3-way handshake). 🔗 |

---

## 👉 The Transport Layer 4 is also responsible for Data Flow Control 
---
### 🔹 **What is Data Flow Control?**

**Data flow control** (or simply *flow control*) is a mechanism used in data communication to manage the rate at which data is transmitted between a sender and a receiver. Its main purpose is to **prevent the sender from overwhelming the receiver**, which may be slower or busy processing data.

> 🎯 **Goal**: Ensure reliable data transfer by matching the sender’s transmission rate to the receiver’s processing capacity.

**Flow Control** is a key function of the **data link layer** (Layer 2) and the **transport layer** (Layer 4) in the OSI model—especially in connection-oriented protocols like **TCP**.

---

### 🔹 **Two Common Methods of Flow Control**

#### 1. 🛑 **Stop-and-Wait Flow Control = Buffering**
- The sender transmits **one frame (or packet) at a time** and then **waits for an acknowledgment (ACK)** from the receiver before sending the next one.
- Simple but not very efficient, especially over high-latency or long-distance networks.

✅ **How it works**:
1. Sender sends Frame 1.
2. Receiver gets Frame 1 and sends ACK.
3. Sender receives ACK → sends Frame 2.
4. If ACK is lost or delayed, the sender may retransmit (using a timeout).

📌 **Use case**: Simple systems or noisy channels where simplicity is preferred over speed.

📉 **Limitation**: Low link utilization—only one frame in transit at a time.

---

#### 2. 🪟 **Sliding Window Flow Control = Flow Control = Windowing**
- Allows the sender to transmit **multiple frames without waiting** for individual acknowledgments.
- Data is sent in groups of segments that only require ONE ACK
- The Size of the Window is determined by how many segments fit into one ACK
- Uses a "**Window Size or Window**" that defines how many frames/packets can be sent before requiring an ACK.
- As ACKs come in, the window slides forward—like a moving checkpoint as acknowledgments are received.

✅ **How it works**:
- Sender maintains a buffer of sent-but-unacknowledged frames.
- Receiver sends cumulative ACKs (e.g., "I’ve received up to frame 3").
- Both sender and receiver maintain a window of sequence numbers.
- Window size can be fixed or adjusted dynamically (e.g., in TCP congestion control).

📌 **Use case**: High-speed networks (like the internet), where efficiency and throughput are critical.

📈 **Advantage**: Much higher utilization of bandwidth compared to stop-and-wait.

🔧 **Example**: TCP uses a dynamic sliding window to adjust flow based on network conditions and receiver buffer space.

### 💡 Real-World Example
In **TCP (Transmission Control Protocol)**, **sliding window flow control** is used to manage data transfer between your browser and a web server. The receiver advertises its available buffer space (via the *window size* field in the TCP header), and the sender adjusts how much data it sends accordingly—preventing buffer overflow.

### 💡 In **TCP (Transmission Control Protocol)**, **sliding window flow control** is used to manage data transfer between your browser and a web server. The receiver advertises its available buffer space (via the *window size* field in the TCP header), and the sender adjusts how much data it sends accordingly—preventing buffer overflow.

---

### 🔢 **Port Numbers: The App Address System**

The Transport Layer uses **port numbers** to direct data to the right application. Think of it like apartment numbers in a building (IP = building address, port = apartment #).

#### 🏢 Well-Known Port Ranges

| Range | Purpose | Examples |
|------|--------|---------|
| **0–1023** | 🛠️ **Well-known ports** – assigned to core services | `80` (HTTP), `443` (HTTPS), `21` (FTP), `25` (SMTP) |
| **1024–49151** | 🧩 **Registered ports** – used by apps/services | `3306` (MySQL), `5432` (PostgreSQL), `8080` (HTTP alt) |
| **49152–65535** | 🕶️ **Dynamic/Private ports** – temporary, client-side | Used when your browser connects to a server |

---

<h1 align="center">Terms & Definitions</h1>

---

### **Error control** and **Error checking** are related but not the same thing.

### **Error Checking**
- Refers to the process of **detecting** errors in transmitted or stored data.
- It involves techniques like **parity checks**, **checksums**, and **cyclic redundancy checks (CRC)** to identify whether data has been corrupted during transmission.
- Example: A receiver calculates a checksum for an incoming packet and compares it to the checksum sent by the sender. If they don’t match, an error is detected.

### **Error Control**
- Is a **broader concept** that includes **error detection (checking)** and also **error correction and recovery**.
- Involves mechanisms to not only detect errors but also **correct** them or **retransmit** the data.
- Common methods include:
  - **Automatic Repeat Request (ARQ)**: Requesting retransmission of corrupted data.
  - **Forward Error Correction (FEC)**: Using redundant data to reconstruct corrupted information without retransmission.

### **Key Difference**
- **Error checking** = *Detecting* that an error occurred.
- **Error control** = *Detecting, correcting, and/or recovering* from errors.

### **Example**
In a network protocol like TCP:
- **Error checking** is done using checksums in the header.
- **Error control** is achieved by retransmitting segments when errors are detected or acknowledgments are missing.

In summary, **error checking is a subset of error control** 

---

Certainly! Below is an **expanded and categorized well-known port numbers table** (0–1023), including common services like **email, file sharing, voice communication, web, remote access, and more**. These ports are standardized by the Internet Assigned Numbers Authority (IANA) and are used by core internet protocols.

> 🔹 **Well-Known Ports**: 0–1023  
> These require administrative privileges to bind and are reserved for system-level processes and core services.

---

### 📘 **Well-Known Port Numbers (0–1023) – Categorized by Function**

| Port | Protocol | Service / Application | Description |
|------|----------|------------------------|-----------|
| **20** | TCP | FTP (Data) | File Transfer Protocol – data channel for file transfers |
| **21** | TCP | FTP (Control) | FTP – control channel for commands and responses |
| **22** | TCP/UDP | SSH | Secure Shell – encrypted remote login and command execution |
| **23** | TCP | Telnet | Unencrypted remote login (insecure, largely deprecated) |
| **25** | TCP | SMTP | Simple Mail Transfer Protocol – sending email between servers |
| **49** | TACACS | Terminal Access Controller Access Control System |
| **50** | ESP | Encapsulating Security Payload |
| **53** | TCP/UDP | DNS | Domain Name System – translates domain names to IP addresses |
| **67** | UDP | DHCP (Server) | Dynamic Host Configuration Protocol – server assigns IP addresses |
| **68** | UDP | DHCP (Client) | DHCP – client receives IP configuration |
| **69** | UDP | TFTP | Trivial File Transfer Protocol – simple, lightweight file transfer |
| **80** | TCP | HTTP | Hypertext Transfer Protocol – unencrypted web traffic |
| **110** | TCP | POP3 | Post Office Protocol v3 – retrieves email from server (legacy) |
| **119** | TCP | NNTP | Network News Transfer Protocol – Usenet news groups |
| **123** | UDP | NTP | Network Time Protocol – synchronizes system clocks |
| **135** | TCP | RPC | Remote Procedure Call – Windows service communication |
| **137–139** | TCP/UDP | NetBIOS | Legacy Windows networking for file/printer sharing |
| ***139*** | DFS |Distributed File Sysem |
| **143** | TCP | IMAP | Internet Message Access Protocol – retrieves and manages email |
| **161** | UDP | SNMP | Simple Network Management Protocol – monitors network devices |
| **162** | UDP | SNMP Trap | SNMP – receives alerts (traps) from devices |
| **389** | TCP/UDP | LDAP | Lightweight Directory Access Protocol – directory services (e.g., Active Directory) |
| **443** | TCP | HTTPS | HTTP Secure – encrypted web traffic (SSL/TLS) |
| **445** | TCP | SMB/CIFS | Server Message Block – modern Windows file and printer sharing |
| **465** | TCP | SMTPS | Legacy secure SMTP (SSL) – sending encrypted email |
| **500** | IPSec ISAKMP | IPSec SAs negotiation Protocol |
| **514** | UDP | Syslog | System logging service – collects log messages from devices |
| **515** | TCP | LPD | Line Printer Daemon – print job spooling |
| **587** | TCP | SMTP (Submission) | Modern secure email submission (TLS - TransportLayerSec ) – used by email clients |
| **636** | TCP | LDAPS | LDAP over SSL/TLS – secure directory access |
| **993** | TCP | IMAPS | IMAP over SSL/TLS – secure email retrieval |
| **995** | TCP | POP3S | POP3 over SSL/TLS – secure email retrieval |
| **1701** | L2TP | Layer 2 Tunneling Protocol |
| **1723** | PPTP | Point to Point Tunneling |
| **5060** | TCP/UDP | SIP | Session Initiation Protocol – voice/video calls (VoIP) signaling |
| **5061** | TCP | SIPS | SIP over TLS – secure VoIP signaling |

---

### 🔍 **Key Categories Summary**

#### ✉️ **Email Services**
| Port | Protocol | Use |
|------|----------|-----|
| 25 | SMTP | Sending email (server-to-server) |
| 587 | SMTP (Submission) | Sending email from clients (modern, with TLS) |
| 110 | POP3 | Download and delete emails (legacy) |
| 143 | IMAP | Sync emails across devices |
| 993 | IMAPS | Secure IMAP |
| 995 | POP3S | Secure POP3 |
| 465 | SMTPS | Legacy secure SMTP (older systems) |

#### 📁 **File Sharing**
| Port | Protocol | Use |
|------|----------|-----|
| 20/21 | FTP | Traditional file transfer |
| 69 | TFTP | Simple

<img width="1050" height="580" alt="Screenshot 2025-08-22 043051" src="https://github.com/user-attachments/assets/9a81c902-c911-4fab-8058-9362836d3138" />

---

### ✨ **Detailed Protocol List Reference**

| Protocol Acronym | Full Name | Brief Description | OSI Layer |
|------------------|---------|-------------------|---------|
| AH | Authentication Header | Part of IPSec; provides data integrity, authentication, and anti-replay (no encryption). | Network (3) |
| ARP | Address Resolution Protocol | Maps IPv4 addresses to MAC addresses on a local network. | Data Link (2) |
| BGP | Border Gateway Protocol | Routes traffic between autonomous systems on the internet (exterior gateway protocol). | Application (7) |
| BOOTP | Bootstrap Protocol | Predecessor to DHCP; assigns IP addresses during boot process. | Application (7) |
| CARP | Common Address Redundancy Protocol | Provides router redundancy (used in BSD systems). | Network (3) |
| CoAP | Constrained Application Protocol | Lightweight protocol for IoT devices using UDP. | Application (7) |
| DHCP | Dynamic Host Configuration Protocol | Automatically assigns IP addresses, subnet masks, gateways, and DNS. | Application (7) |
| DCCP | Datagram Congestion Control Protocol | Provides congestion control for real-time apps without reliability (e.g., streaming). | Transport (4) |
| DNS | Domain Name System | Translates domain names (e.g., brave.com) into IP addresses. | Application (7) |
| DNSSEC | DNS Security Extensions | Adds cryptographic authentication to DNS responses to prevent spoofing. | Application (7) |
| DoH | DNS over HTTPS | Encrypts DNS queries using HTTPS to enhance privacy. | Application (7) |
| DoT | DNS over TLS | Encrypts DNS queries using TLS for secure name resolution. | Application (7) |
| DTLS | Datagram Transport Layer Security | TLS adapted for UDP-based applications (e.g., WebRTC, SIP). | Transport (4) |
| EAP | Extensible Authentication Protocol | Framework for authentication in wireless and point-to-point connections. | Data Link (2) / Network (3) |
| EIGRP | Enhanced Interior Gateway Routing Protocol | Cisco-proprietary routing protocol using DUAL algorithm. | Network (3) |
| ESP | Encapsulating Security Payload | Part of IPSec; provides confidentiality, integrity, and anti-replay. | Network (3) |
| FTP | File Transfer Protocol | Transfers files between client and server (unencrypted). | Application (7) |
| FTPS | File Transfer Protocol Secure | FTP with added SSL/TLS encryption. | Application (7) |
| GRE | Generic Routing Encapsulation | Tunnels various network layer protocols over IP. | Network (3) |
| HSRP | Hot Standby Router Protocol | Cisco-proprietary router failover protocol for high availability. | Network (3) |
| HTTP | Hypertext Transfer Protocol | Foundation of web data communication; requests and delivers web pages. | Application (7) |
| HTTPS | Hypertext Transfer Protocol Secure | HTTP secured with TLS/SSL encryption. | Application (7) |
| ICMP | Internet Control Message Protocol | Used for error reporting and diagnostics (e.g., `ping`, `traceroute`). | Network (3) |
| ICMPv6 | Internet Control Message Protocol version 6 | ICMP for IPv6; includes Neighbor Discovery and address autoconfiguration. | Network (3) |
| IGMP | Internet Group Management Protocol | Manages IPv4 multicast group memberships. | Network (3) |
| IMAP | Internet Message Access Protocol | Retrieves and manages email on the server (supports folders, sync). | Application (7) |
| IPSec | Internet Protocol Security | Suite for securing IP communications via encryption and authentication. | Network (3) |
| IS-IS | Intermediate System to Intermediate System | Link-state routing protocol used in large-scale ISP networks. | Network (3) |
| Kerberos | Kerberos | Network authentication protocol using tickets to verify identities securely. | Application (7) |
| LDAP | Lightweight Directory Access Protocol | Accesses and manages directory services (e.g., Microsoft Active Directory). | Application (7) |
| LDAPS | LDAP over SSL/TLS | LDAP secured with SSL/TLS encryption. | Application (7) |
| LACP | Link Aggregation Control Protocol | Dynamically bundles multiple physical links into one logical link (link aggregation). | Data Link (2)
| MAC | Media Access Control | Sublayer of Data Link layer that controls how devices access the network medium. | Data Link (2) |
| MDNS | Multicast DNS | Resolves hostnames to IP addresses without a central DNS server (used in zero-configuration networks). | Application (7) |
| MLD | Multicast Listener Discovery | IPv6 equivalent of IGMP; manages multicast group membership. | Network (3) |
| MQTT | Message Queuing Telemetry Transport | Lightweight publish-subscribe protocol for IoT and low-bandwidth environments. | Application (7) |
| NAC | Network Access Control | Enforces security policies on devices before granting network access. | Data Link (2) / Network (3) |
| NAT | Network Address Translation | Translates private IP addresses to public ones (and vice versa) for internet access. | Network (3) |
| NetBIOS | Network Basic Input/Output System | Legacy API for network communication in Windows (file/printer sharing). | Session (5) |
| NetFlow | NetFlow | Cisco protocol for collecting IP traffic data (monitoring, analysis, security). | Application (7) |
| NTP | Network Time Protocol | Synchronizes clocks across networked systems to ensure accurate timekeeping. | Application (7) |
| OSPF | Open Shortest Path First | Link-state interior gateway routing protocol for IP networks. | Network (3) |
| PAP | Password Authentication Protocol | Simple authentication method for PPP connections (passwords sent in clear text). | Data Link (2) |
| PIM | Protocol Independent Multicast | Routing protocol for efficient multicast delivery. | Network (3) |
| PING | Packet InterNet Groper | Utility using ICMP to test connectivity between hosts. | Network (3) |
| POP3 | Post Office Protocol version 3 | Downloads emails from server to client; typically deletes from server. | Application (7) |
| PPP | Point-to-Point Protocol | Data link protocol for direct communication between two nodes (e.g., dial-up). | Data Link (2) |
| PPPoE | PPP over Ethernet | Extends PPP to operate over Ethernet networks (common in DSL). | Data Link (2) |
| PPTP | Point-to-Point Tunneling Protocol | Early VPN protocol for creating secure tunnels (now considered insecure). | Data Link (2) |
| RADIUS | Remote Authentication Dial-In User Service | Centralized authentication, authorization, and accounting (AAA) for network access. | Application (7) |
| RARP | Reverse Address Resolution Protocol | Maps MAC addresses to IP addresses (largely obsolete, replaced by DHCP). | Data Link (2) |
| RIP | Routing Information Protocol | Distance-vector routing protocol for small to medium networks. | Network (3) |
| RSTP | Rapid Spanning Tree Protocol | Faster version of STP; prevents loops in switched networks. | Data Link (2) |
| RTP | Real-time Transport Protocol | Delivers audio and video for real-time applications (e.g., VoIP, video conferencing). | Application (7) |
| RTCP | RTP Control Protocol | Companion to RTP; monitors transmission quality and QoS. | Application (7) |
| RTSP | Real-Time Streaming Protocol | Controls delivery of streaming media (play, pause, stop). | Application (7) |
| SFTP | SSH File Transfer Protocol | Secure file transfer over SSH (not related to FTP). | Application (7) |
| SIP | Session Initiation Protocol | Establishes, modifies, and terminates multimedia sessions (e.g., voice, video calls). | Application (7) |
| SIPS | SIP Secure | SIP secured with TLS encryption for secure signaling. | Application (7) |
| SLAAC | Stateless Address Autoconfiguration | IPv6 feature allowing devices to self-configure IP addresses. | Network (3) |
| SLIP | Serial Line Internet Protocol | Early protocol for transmitting IP packets over serial lines (obsolete). | Data Link (2) |
| SNMP | Simple Network Management Protocol | Monitors and manages network devices (routers, switches, servers). | Application (7) |
| SOAP | Simple Object Access Protocol | Protocol for exchanging structured information in web services (uses XML). | Application (7) |
| SPDY | Speedy | Early Google protocol to speed up web traffic (precursor to HTTP/2). | Application (7) |
| SSH | Secure Shell | Securely accesses and manages remote devices over unsecured networks. | Application (7) |
| SSL | Secure Sockets Layer | Early cryptographic protocol for secure communication (deprecated, replaced by TLS). | Presentation (6) / Session (5) |
| STP | Spanning Tree Protocol | Prevents network loops in Ethernet networks with redundant paths. | Data Link (2) |
| SYSLOG | System Logging Protocol | Sends and stores log messages from network devices and systems. | Application (7) |
| TACACS | Terminal Access Controller Access-Control System | Cisco protocol for remote authentication (older version). | Application (7) |
| TACACS+ | Terminal Access Controller Access-Control System Plus | Enhanced version of TACACS with separate authentication, authorization, and accounting. | Application (7) |
| TCP | Transmission Control Protocol | Reliable, connection-oriented transport protocol with error recovery and flow control. | Transport (4) |
| TELNET | Teletype Network | Unsecured remote terminal access protocol (largely replaced by SSH). | Application (7) |
| TLS | Transport Layer Security | Successor to SSL; encrypts data in transit (used in HTTPS, email, etc.). | Presentation (6) / Session (5) |
| TRILL | Transparent Interconnection of Lots of Links | Modern alternative to STP for efficient multi-path routing in LANs. | Data Link (2) |
| UDP | User Datagram Protocol | Connectionless transport protocol with low overhead; no delivery guarantees. | Transport (4) |
| VLAN | Virtual Local Area Network | Logical segmentation of a physical network into isolated broadcast domains. | Data Link (2) |
| VRRP | Virtual Router Redundancy Protocol | Provides high availability by allowing multiple routers to act as a single virtual gateway. | Network (3) |
| WAP | Wireless Application Protocol | Early protocol for accessing web-like services on mobile devices. | Application (7) |
| WebDAV | Web Distributed Authoring and Versioning | Extends HTTP to allow collaborative editing and file management on web servers. | Application (7) |
| WebSocket | WebSocket Protocol | Enables full-duplex, real-time communication between client and server over a single TCP connection. | Application (7) |
| WPA | Wi-Fi Protected Access | Security protocol for securing wireless networks (successor to WEP). | Data Link (2) |
| WPA2 | Wi-Fi Protected Access 2 | Stronger security using AES encryption and 802.11i standard. | Data Link (2) |
| WPA3 | Wi-Fi Protected Access 3 | Latest Wi-Fi security with improved encryption and protection against brute-force attacks. | Data Link (2) |
| XMPP | Extensible Messaging and Presence Protocol | Open protocol for real-time messaging, presence, and contact list maintenance. | Application (7) |
| YANG | Yet Another Next Generation | Data modeling language used with NETCONF/RESTCONF for network configuration. | Application (7) |
| Z-Wave | Z-Wave | Proprietary wireless protocol for home automation and IoT devices. | Application (7) |
| Zigbee | Zigbee | Low-power, low-data-rate wireless protocol for IoT and smart home applications. | Application (7) |

---

### 🛜 At the Network and Data Link layers, the port number is ignored - it becomes part of the data payload and is invisible to the routers and switches that implement the addressing and forwarding functions of these layers. 

### 📞 At the receiving host, each segment is decapsulated, identified by its port number, and passed to the relevant handler at the Application layer. Put another way, the traffic stream is de-multiplexed.

It’s like the **postmaster general** of the internet: doesn’t deliver the mail itself, but makes sure it’s packed right, tracked, and resent if lost.

---

