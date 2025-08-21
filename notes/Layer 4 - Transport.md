<h1 align="center">Layer 4 Transport</h1>

# Layer 4 is Transport 

🎉 **MISSION: LAYER 4 – THE TRANSPORT LAYER**  
🔥 *"The Traffic Controller of the Internet Highway"*  
🚦 **Ensures data arrives *complete*, *correct*, and *in order***  

Layer 4 Transport — where reliability meets speed, and your data gets its travel agent, quality inspector, and delivery scheduler all in one. 💻🚀

---

### 🌐 **What Is the Transport Layer? (Layer 4)**

> **💡 Definition**:
> 
> The **Transport Layer** (Layer 4 of the OSI model) is responsible for **end-to-end communication**, ensuring data is delivered **reliably, in sequence, and without errors** between two hosts — *regardless of the underlying network*.
> 
> ## 📌 **One of the functions of the Transport layer is to identify each type of network application by assigning it a port number.**
>   - For example,  data requested from an HTTP web application can be identified as port 80, while data sent to an email server can be identified as port 25.
>     
> **At the Transport layer, on the sending host, data from the upper layers is packaged as a series of layer 4 PDUs, referred to as segments.**

  > Each segment is tagged with the application's port number.
> 
  > The segment is then passed to the Network layer for delivery.
> 
  > Many different hosts could be transmitting multiple HTTP and email packets at the same time
> 
  > These are multiplexed using the port numbers along with the source and destination network addresses onto the same link.
> 
> The Transport layer can also implement reliable data delivery mechanisms, should the application require it. Reliable delivery means that any lost or damaged packets are resent.
> 
> Devices working at the Transport layer include multilayer switches - usually working as load balancers - and many types of security appliances, such as more advanced firewalls and intrusion detection systems (IDSs).

<img width="768" height="346" alt="transport_layer_diagram" src="https://github.com/user-attachments/assets/aa9d342c-d634-4bf5-b472-1aba29f02336" />

###### The image illustrates data flow at the Transport layer (Layer 4) of the OSI model. Two computers, labeled Host 2.2 and Host 2.3, are sending various types of network traffic to a third computer, labeled Host 2.1. Each data segment is marked with a different port number, representing different types of application traffic:

###### - Host 2.2 sends web traffic (port 80) and email (port 25) to Host 2.1.

###### - Host 2.3 sends file sharing traffic (port 445), voice communication (port 5061), and email (port 25) to Host 2.1.

###### - The diagram shows these data segments traveling across the network, encapsulated as Layer 3 packets in Layer 2 frames, before arriving at Host 2.1. Once at the destination, Host 2.1 examines the port number of each segment to identify the application type - such as web server, mail service, file sharing, or voice service - and directs the data accordingly for processing.

###### - The image visually conveys how the Transport layer uses port numbers to combine, transport, and then separate and deliver multiple types of application data coming from different hosts, ensuring each data type reaches the correct program on the receiving device.


### 🛜 At the Network and Data Link layers, the port number is ignored - it becomes part of the data payload and is invisible to the routers and switches that implement the addressing and forwarding functions of these layers. 

### 📞 At the receiving host, each segment is decapsulated, identified by its port number, and passed to the relevant handler at the Application layer. Put another way, the traffic stream is de-multiplexed.

It’s like the **postmaster general** of the internet: doesn’t deliver the mail itself, but makes sure it’s packed right, tracked, and resent if lost.

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

### 🚆 **The Two Main Protocols: TCP vs UDP**

> 🎭 *"The Reliable Truck vs The Speedy Motorcycle"*

| **Feature** | **TCP (Transmission Control Protocol)** 🚛 | **UDP (User Datagram Protocol)** 🏍️ |
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

> 🔍 **Live Example









































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
| **143** | TCP | IMAP | Internet Message Access Protocol – retrieves and manages email |
| **161** | UDP | SNMP | Simple Network Management Protocol – monitors network devices |
| **162** | UDP | SNMP Trap | SNMP – receives alerts (traps) from devices |
| **389** | TCP/UDP | LDAP | Lightweight Directory Access Protocol – directory services (e.g., Active Directory) |
| **443** | TCP | HTTPS | HTTP Secure – encrypted web traffic (SSL/TLS) |
| **445** | TCP | SMB/CIFS | Server Message Block – modern Windows file and printer sharing |
| **465** | TCP | SMTPS | Legacy secure SMTP (SSL) – sending encrypted email |
| **514** | UDP | Syslog | System logging service – collects log messages from devices |
| **515** | TCP | LPD | Line Printer Daemon – print job spooling |
| **587** | TCP | SMTP (Submission) | Modern secure email submission (TLS) – used by email clients |
| **636** | TCP | LDAPS | LDAP over SSL/TLS – secure directory access |
| **993** | TCP | IMAPS | IMAP over SSL/TLS – secure email retrieval |
| **995** | TCP | POP3S | POP3 over SSL/TLS – secure email retrieval |
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


