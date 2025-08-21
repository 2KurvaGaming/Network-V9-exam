<h1 align="center">Layer 2 Data Link</h1>

# 🖇️ Data Link Layer is referred to as Layer 2.

## ⭐ Is responsible for:    
  🚩 TRANSFERRING DATA BETWEEN NODES ON THE SAME LOGICAL SEGMENT

  🚩 GETTING THE DATA TO THE PHYSICAL LAYER

  🚩 ERROR DETECTION
  
  🚩 ERROR CORRECTION
                      
  🚩 HARDWARE ADDRESSING
  
---
📌 At the Data Link layer, a ***segment*** is one where all nodes can send traffic to one another using hardware addresses, regardless     of whether they share access to the same media.
  A layer 2 segment might include multiple physical segments. This is referred to as a ***logical topology***:

---

### **What is a Logical Segment in the Data Link Layer?**

- A **logical segment** at the Data Link layer refers to a group of devices that can communicate directly with each other using **Layer 2 (Data Link layer) protocols**, without needing to go through a router.  
- These devices share the same **broadcast domain**, meaning a broadcast sent by one device will be received by all others in the same logical segment.  
- Communication within the segment is based on **MAC (hardware) addresses**, not IP addresses.  
- The most common example of a logical segment is a **VLAN (Virtual Local Area Network)** — it creates a separate, isolated broadcast domain within a physical network.  
- Logical segments are **logically defined** (through configuration), not physically separated — so devices in the same VLAN can be on different switches or floors but still behave as if they’re on the same local network.  
- Each logical segment operates as its own **Layer 2 network**, with its own set of MAC address tables and forwarding rules managed by switches.  
- Routers (or Layer 3 switches) are required to enable communication **between** different logical segments.

---

✨ **Real-World Example:**  
Imagine a company where Finance, HR, and IT are on different floors but use the same physical network. By creating **three VLANs** (one for each department), the network admin defines ***three logical segments*** at the Data Link layer — keeping traffic separate and secure, even though they share the same switches and cables.

---

So in short:  
👉 A **logical segment** in the Data Link layer is a **software-defined group of devices** that communicate at Layer 2, share a broadcast domain, and are often created using technologies like **VLANs**.

---
## Media Access Control (MAC) Layer: 

### **MAC Address**
- A MAC (Media Access Control) address is a unique hardware identifier assigned to a network interface card (NIC) or network interface.
- It is a 48-bit address typically expressed in hexadecimal format (e.g., `00:1A:2B:3C:4D:5E`).
- MAC addresses operate at the Data Link layer (Layer 2) of the OSI model.
- They are used to identify devices on the same local network segment.
- The first half of the address identifies the manufacturer (OUI), while the second half is the device-specific identifier.
- MAC addresses enable communication within the same Layer 2 network by ensuring frames are delivered to the correct physical device.
- The frame, as the Layer 2 PDU, encapsulates packets received from the network layer (Layer 3) and prepares them for transmission as    bits at the physical layer (Layer 1)
- IEEE 802.1 standard defines the LLC sublayer and its operations.

---

### **LLC (Logical Link Control)**
- LLC is a sublayer of the Data Link layer (Layer 2) in the OSI model.
- It provides an interface between the Network layer and the lower-level Data Link functions.
- LLC is responsible for managing frame synchronization, flow control, and error checking.
- It helps ensure reliable data transfer across the physical link.
- The LLC sublayer can support both connectionless and connection-oriented services.
- Logical Link Control (LLC) frames the data and prepares it for transmission over the physical medium.
- It adds control information to the frame, including service access points (DSAP and SSAP), which identify the sending and receiving protocols.
  
> **DASP** and **SSAP** are **obsolete** fields from the **IEEE 802.2 Logical Link Control (LLC)** header used in early **Data Link Layer** protocols like **Token Ring** and **early Ethernet**.  
> They stand for:
> - **DSAP** – Destination Service Access Point  
> - **SSAP** – Source Service Access Point
> - 🧠 Memory Trick:
> - "DSAP = Where it’s going.
> - "SSAP = Where it came from."
> - Think: "Destination = To, Source = From"

- LLC supports multiplexing, allowing multiple network protocols (like IPv4, IPv6, IPX) to share the same physical link.
- It works in conjunction with the MAC sublayer to manage communication between devices on a local network.
- IEEE 802.2 standard defines the LLC sublayer and its operations.

---

## ⭐ Local networks rely on centralized connectivity rather than direct point-to-point or mesh links between hosts.  
- In a local network, hosts connect individually to a central node—such as a switch or wireless access point—to reduce cabling and interface costs.  
- The central node in a local network forwards communications by receiving data from one host and sending it to the intended recipient.  
📌 Each host’s interface in a local network ***MUST*** have a Data Link Layer Address to enable accurate frame delivery.  
- Within a local network, interfaces on the same Layer 2 segment use local addresses (also called hardware addresses) to identify         devices.

## ⭐ The Data Link layer performs an encapsulation function, organizing the stream of bits from the Physical layer into structured units called ***frames.***

 <h2 align="center">(Common term for the **Protocol Data Unit** (PDU) for layer 2.)</h2> 
 
- Each **frame** Contains the data from higher layers, along with headers and trailers added by the data link layer.
- These headers include the source and destination MAC (Media Access Control) addresses, which are used for physical addressing within the local network
- The trailer often includes error-checking information, such as a Frame Check Sequence (FCS), to detect transmission errors
- The Data Link layer adds control information to the payload in the form of header fields.  

### 🔹 What is a Protocol Data Unit (PDU)?
A **Protocol Data Unit (PDU)** is a general term used in networking to describe the **"package" of data** at each layer of the OSI or TCP/IP model. Each layer has its own PDU because each adds its own header (and sometimes trailer) to the data.

Here’s a quick reference:

| Layer | Name | PDU |
|------|------|-----|
| 7–5 | Application, Presentation, Session | **Message/Data** |
| 4 | Transport | **Segment** (TCP) or **Datagram** (UDP) |
| 3 | Network | **Packet** |
| 2 | Data Link | **Frame** |
| 1 | Physical | **Bit** |

👉 So, the **PDU at Layer 2 is called a *frame***.

---

### 🔹 So… Are "PDU" and "Frame" Interchangeable at Layer 2?

✅ **Yes—but only at Layer 2.**

- **"PDU"** is the *generic term* used across all layers.
- **"Frame"** is the *specific name* of the PDU **only at Layer 2**.

Think of it like this:
- "Vehicle" is a general term (like *PDU*).
- "Car" is a specific type of vehicle (like a *frame* at Layer 2).

So:
> At Layer 2, the **PDU = Frame**.  
> They mean the same thing in this context.

---

### 🔹 What’s Actually *In* a Frame?
When data comes down from Layer 3 (the network layer), it arrives as a **packet**.  
At Layer 2, that packet gets wrapped inside a **frame**, which adds:

- **Header**: Includes the **source and destination MAC addresses**.
- **Payload**: The actual data (the packet from Layer 3).
- **Trailer**: Usually contains error-checking info like **FCS (Frame Check Sequence)**.

Then, this whole thing — header + payload + trailer — is sent to Layer 1, where it becomes bits on a wire or Wi-Fi signal.

---

### ✅ Summary
- **PDU** = General term for data package at any layer.
- **Frame** = The *specific name* of the PDU at **Layer 2**.
- So: **At Layer 2, “frame” and “PDU” refer to the same thing.**

---

## Communications at layer 2 of the OSI model.
<img width="2424" height="1832" alt="data_link" src="https://github.com/user-attachments/assets/3f1b0bda-691a-4aae-a7c8-f83b1ca60276" />

###### The image illustrates how the Data Link layer (Layer 2) operates in a network consisting of three hosts (computers) labeled with hardware addresses (AA, AB, AC) connected to a central switch via four ports (G1–G4).

###### The first step highlights that at the Data Link layer, each network interface is identified by a hardware (MAC) address. The leftmost host is labeled with the address "AA."
###### The second step shows host AA sending a frame to host AC. The data travels via a dotted line along the cable to the switch's port G1.
###### The third step explains that the switch monitors which hardware addresses are associated with which of its ports. Upon receiving the frame addressed to AC, the switch looks up its records and forwards the frame out through port G3, since host AC is connected there.
###### The fourth step shows host AC receiving the frame, recognizing the destination address as its own, and processing the data.
###### This diagram visually demonstrates frame delivery at the Data Link layer, using MAC addresses for local communication, forwarding, and identification among devices sharing a logical segment.

## Devices that operate at the Data Link Layer include the following:

- Network adapter or network interface card (NIC)—A NIC joins an end system host to network media (cabling or wireless) and enables it to communicate over the network by assembling and disassembling frames.
    (Adapter card that provides one or more Ethernet ports for connecting hosts to a network so that they can exchange data over a            link.)
- Bridge A bridge is a type of intermediate system that joins physical network segments while minimizing the performance reduction of having more nodes on the same network. A bridge has multiple ports, each of which functions as a network interface.
    (Intermediate system that isolates collision domains to separate segments while joining segments within the same broadcast domain.)
- Switch - An advanced type of bridge with many ports. A switch creates links between large numbers of nodes more efficiently.
    (Intermediate system used to establish contention-free network segments at OSI layer 2 (Data Link). An unmanaged switch does not         support any sort of configuration.)
- Wireless access point (AP) - An AP allows nodes with wireless network cards to communicate and creates a bridge between wireless networks and wired ones.
      (A device that provides a connection between wireless devices and can connect to wired networks, implementing an infrastructure mode WLAN.)
  
---

| **Device**                     | **Function**                                                                                                      |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------|
| **Network Adapter / NIC**     | Connects an end system (host) to network media (wired or wireless); enables communication by assembling/disassembling data frames. |
| **Bridge**                      | Connects physical network segments; reduces performance issues caused by too many nodes on one network. Has multiple ports, each acting as a network interface. |
| **Switch**                      | An advanced bridge with many ports; efficiently creates connections between numerous nodes in a network.         |
| **Wireless Access Point (AP)**  | Enables wireless devices to connect to the network; bridges communication between wireless and wired network segments. |

---

<h1 align="center">Terms & Definitions</h1>

---
## 🌐 Data Link Layer (Layer 2) – Protocols & Technologies

| **Protocol / Technology** | **Function / Purpose** | **Key Standard / Notes** | **Exam Tip 🎯** |
|---------------------------|------------------------|---------------------------|----------------|
| **Ethernet (IEEE 802.3)** 🖧 | Most common LAN tech; frames data for transmission | IEEE 802.3 (e.g., 1000BASE-T) | Uses MAC addresses; foundation of wired networks |
| **Wi-Fi (IEEE 802.11)** 📶 | Wireless LAN communication | a/b/g/n/ac/ax (Wi-Fi 4–7) | MAC sublayer manages access to airwaves (CSMA/CA) |
| **PPP (Point-to-Point Protocol)** 🔗 | Connects two nodes (e.g., dial-up, serial links) | Common in legacy WANs | Supports authentication (PAP/CHAP), used with modems |
| **HDLC (High-Level Data Link Control)** 🔄 | Cisco default serial link protocol | ISO standard; bit-oriented | Encapsulates data on point-to-point links; vendor-neutral version exists |
| **Frame Relay** 🚦 | Legacy WAN protocol (packet-switched) | Predecessor to MPLS | Uses DLCIs; operates at Layer 2 over T1 lines |
| **ATM (Asynchronous Transfer Mode)** ⚡ | Cell-based switching (fixed 53-byte cells) | Used in legacy telco networks | Combined features of circuit & packet switching |
| **Token Ring (IEEE 802.5)** 🔗 | Legacy ring topology network | IBM technology (mostly obsolete) | Uses token-passing to avoid collisions |
| **FDDI (Fiber Distributed Data Interface)** 🌉 | High-speed fiber ring network | Dual-ring for fault tolerance | Used in backbones before Ethernet dominated |
| **Spanning Tree Protocol (STP)** 🌳 | Prevents switching loops in redundant topologies | IEEE 802.1D | Essential for stable Layer 2 networks |
| **LACP (Link Aggregation Control Protocol)** 🔗🔗 | Bundles multiple physical links into one logical link | IEEE 802.3ad | Increases bandwidth and redundancy (EtherChannel) |
| **VLAN Tagging (IEEE 802.1Q)** 🏷️ | Tags frames to assign them to a VLAN | Adds 4-byte tag to Ethernet frame | Enables multiple virtual LANs on a single switch |
| **MACsec (IEEE 802.1AE)** 🔒 | Provides encryption and integrity at Layer 2 | Secures traffic between trusted devices | Protects against MAC spoofing, eavesdropping |
| **Bluetooth (IEEE 802.15.1)** 🔵 | Short-range wireless personal area network | Piconet scatternet topologies | Operates at Layer 2 for device pairing |
| **Zigbee (IEEE 802.15.4)** 🌐 | Low-power, low-data-rate mesh networking | Used in IoT (smart home devices) | Efficient for battery-powered sensors |
| **L2TP (Layer 2 Tunneling Protocol)** 🌐📦 | Tunnels PPP sessions over IP networks | Often paired with IPsec | Used for secure remote access (VPNs) |
| **PPTP (Point-to-Point Tunneling Protocol)** 📦 | Early tunneling protocol for VPNs | Microsoft legacy tech (insecure) | Avoid in modern networks (weak encryption) |
| **LAN (Local Area Network)** 🏢 | Network within a small geographic area | Built using switches/hubs | Layer 2 defines how devices communicate locally |
| **VLAN (Virtual LAN)** 🎭 | Logically segments a physical network | Created via switch configuration | Improves security, performance, and broadcast control |

---

### 🎯 Key Layer 2 Exam Tips:
- ✅ **PDU = Frame** — Layer 2 deals with **framing** and **MAC addressing**.
- ✅ **Switches** and **bridges** are the primary Layer 2 devices.
- ✅ **MAC addresses** (48-bit, e.g., `00:1A:2B:3C:4D:5E`) are used for local delivery.
- ❌ No routing — Layer 2 doesn’t handle IP addresses or cross-network delivery.

---

✨ **Quick Notes:**  
- **L2TP** and **PPTP** are tunneling protocols that operate at Layer 2 and are used for VPNs.  
- **STP (Spanning Tree Protocol)** prevents loops in switched networks.  
- **LAN** is a network architecture, but it relies heavily on Data Link layer protocols (like Ethernet) to function.  
- **VLAN** (Virtual LAN) is implemented via IEEE 802.1Q and operates at Layer 2 to segment networks logically.

✨ Although L2TP operates at Layer 2 and provides tunneling capabilities, it does not include built-in encryption or authentication mechanisms, leaving data potentially exposed if used alone.

- Responsible for establishing and maintaining direct connections between devices in a network
    - by creating virtual private networks (VPNs) through the encapsulation and tunneling of data packets across public networks like the internet, thereby enabling secure point-to-point communication.

- For this reason, it is commonly paired with IPsec, which operates at the network layer (Layer 3) and provides confidentiality, authentication, and integrity through encryption.
 
- The combined use of L2TP with IPsec—often referred to as L2TP/IPsec—creates a more secure VPN solution by leveraging the tunneling functionality of L2TP and the security features of IPsec.









































  
