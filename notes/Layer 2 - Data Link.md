<h1 align="center">Layer 1 Physical</h1>

# 🖇️ Data Link Layer is referred to as Layer 2.

⭐ It is responsible for transferring data between nodes on the same logical segment.
  - At the Data Link layer, a segment is one where all nodes can send traffic to one another using hardware addresses, regardless of           whether they share access to the same media
  
  - A layer 2 segment might include multiple physical segments. This is referred to as a logical topology.:

- Local networks rely on centralized connectivity rather than direct point-to-point or mesh links between hosts.  
- In a local network, hosts connect individually to a central node—such as a switch or wireless access point—to reduce cabling and interface costs.  
- The central node in a local network forwards communications by receiving data from one host and sending it to the intended recipient.  
- Each host’s interface in a local network must have a Data Link layer address to enable accurate frame delivery.  
- Within a local network, interfaces on the same Layer 2 segment use local addresses (also called hardware addresses) to identify devices.

- The Data Link layer performs an encapsulation function, organizing the stream of bits from the Physical layer into structured units called ***frames.***
  (Common term for the protocol data unit for layer 2.)
- Each **frame** contains a **Network layer packet** as its payload.  
- The Data Link layer adds control information to the payload in the form of header fields.  
- These fields include source and destination hardware addresses, plus a basic error check to test if the frame was received intact.

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










































  
