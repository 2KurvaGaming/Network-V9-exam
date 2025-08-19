<h1 align="center">Layer 2 Data Link</h1>

# 🖇️ Data Link Layer is referred to as Layer 2.

## ⭐ Is responsible for:    
  🚩 TRANSFERRING DATA BETWEEN NODES ON THE SAME LOGICAL SEGMENT

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
Imagine a company where Finance, HR, and IT are on different floors but use the same physical network. By creating **three VLANs** (one for each department), the network admin defines **three logical segments** at the Data Link layer — keeping traffic separate and secure, even though they share the same switches and cables.

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
- IEEE 802.1 standard defines the LLC sublayer and its operations.

---

### **LLC (Logical Link Control)**
- LLC is a sublayer of the Data Link layer (Layer 2) in the OSI model.
- It provides an interface between the Network layer and the lower-level Data Link functions.
- LLC is responsible for managing frame synchronization, flow control, and error checking.
- It helps ensure reliable data transfer across the physical link.
- The LLC sublayer can support both connectionless and connection-oriented services.

---

### **Logical Link Control**
- Logical Link Control (LLC) frames the data and prepares it for transmission over the physical medium.
- It adds control information to the frame, including service access points (DSAP and SSAP), which identify the sending and receiving protocols.
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


 <h2 align="center">(Common term for the protocol data unit for layer 2.)</h2> 
 
- Each **frame** contains a **Network layer packet** as its payload.  
- The Data Link layer adds control information to the payload in the form of header fields.  
- These fields include source and destination hardware addresses, plus a basic error check to test if the frame was received intact.
---


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

## ✨ Data Link layer 2 protocols and technologies

- Ethernet (IEEE 802.3)  
- Wi-Fi (IEEE 802.11 a/b/g/n/ac/ax)  
- Point-to-Point Protocol (PPP)  
- High-Level Data Link Control (HDLC)  
- Frame Relay  
- Asynchronous Transfer Mode (ATM)  
- Token Ring (IEEE 802.5)  
- Fiber Distributed Data Interface (FDDI)  
- Spanning Tree Protocol (STP) – IEEE 802.1D  
- Link Aggregation Control Protocol (LACP) – IEEE 802.3ad  
- VLAN tagging – IEEE 802.1Q  
- MAC Security (MACsec) – IEEE 802.1AE  
- Bluetooth – IEEE 802.15.1  
- Zigbee – IEEE 802.15.4  
- Layer 2 Tunneling Protocol (L2TP)  
- Point-to-Point Tunneling Protocol (PPTP)  
- Local Area Network (LAN)  
- Virtual LAN (VLAN)  

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









































  
