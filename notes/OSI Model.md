<h1 align="center">1.2 OSI MODEL CONCEPTS</h1>

# 🅾️  Open Systems Interconnection OSI reference model

## 🏗️ Networks are built on common standards and models that describe how devices and protocols interconnect. 

The International Organization for Standardization (ISO) developed the Open Systems Interconnection (OSI) reference model to promote understanding of how components in a network system work. 
It does this by separating the functions of hardware and software components into seven discrete layers. 
Each layer performs a different group of tasks required for network communication.

---

<img width="1650" height="1075" alt="osi_model" src="https://github.com/user-attachments/assets/31632a4c-1acb-4074-9298-ffbe8173ed8a" />

###### The image depicts the OSI (Open Systems Interconnection) model as a vertical stack. Each layer has a number and a name, organized from the top (layer 7) to the bottom (layer 1). The seven layers, from top to bottom, are:

###### Layer 7: Application
###### Layer 6: Presentation
###### Layer 5: Session
###### Layer 4: Transport
###### Layer 3: Network
###### Layer 2: Data Link
###### Layer 1: Physical
###### Each layer is shown as a blue rectangle with its corresponding number in a white box to the left, proceeding in descending order from 7 (top) to 1 (bottom). No additional details, graphics, or protocol examples are present in the image - just the labeled layers and their order. 

👸 Although not all network systems implement layers using this precise structure, they all implement each task in some way. The OSI model is not a standard or a specification; it serves as a functional guideline for designing network protocols, software, and appliances and for troubleshooting networks.

---

# ⌨️ Data Encapsulation and Decapsulation

☑️ A ***network protocol*** is a set of rules for exchanging data in a structured format. A network protocol has two principal functions:

1️⃣ - Addressing — Describing where data messages should go. At each OSI model layer, there are different mechanisms for identifying nodes and rules for how they can send and receive messages.

2️⃣ Encapsulation—Describing how data messages should be packaged for transmission. Encapsulation is like an envelope for a letter, with the distinction that each layer requires its own envelope. At each layer, the protocol adds fields in a header to whatever payload data it receives from an application or other protocol.

🛜 A network will involve the use of many different protocols operating at different layers of the OSI model.  
- At each layer, for two nodes to communicate, they must be running the same protocol.  
- The protocol running at each layer communicates with its peer layer on the other node.  
- This communication between nodes at the same layer is described as a same-layer interaction.  
- To transmit or receive a communication, on each node, each layer provides services for the layer above and uses the services of the layer below.  
- This is referred to as adjacent-layer interaction.

<img width="1651" height="1054" alt="data_encapsulation_decapsulation" src="https://github.com/user-attachments/assets/05f6ae3a-7578-4561-83f8-7c768e4a69e6" />

###### - The image visually explains the process of encapsulation and decapsulation according to the OSI (Open Systems Interconnection) model during data transmission between two computers.  
###### - The left side depicts Computer A (the sender), while the right side shows Computer B (the receiver).  
###### - On the left, the OSI layers are listed vertically: Physical, Data link, Network, Transport, Session, Presentation, and Application.  
###### - The process begins at the top Application layer (labeled 'A' for Application), which has the raw data to send.  
###### - As the data descends each OSI layer, it gains a new header for that protocol layer (e.g., 'P' for Presentation, 'S' for Session, 'T' for Transport, and so on, marked at each step).  
###### - At the bottom-most layer (Physical), the data has been encapsulated with all previous headers and is converted into binary digits (shown as a string of 1s and 0s) for physical transmission.  
###### - The arrows and matching binary strings show that the data is transmitted over the network to Computer B.  
###### - On the right, as the data ascends the OSI layers in Computer B, each layer removes (decapsulates) its corresponding header, until finally, only the original data remains at the Application layer.  
###### - The headers at each layer ensure structured communication, and the same labels (A, P, S, T, N, DL for Data Link) are shown being stripped off in reverse order as the data moves up the layers on the receiving side.  
###### - This diagram illustrates both the encapsulation process (adding headers at each layer, left side) and decapsulation process (removing headers at each layer, right side) as defined by the OSI networking model.

---

- When a message is sent from one node to another, it travels down the stack of layers on the sending node, reaches the receiving node using the transmission media, and then passes up the stack on that node.  
- At each level (except the Physical layer), the sending node adds a header to the data payload, forming a “chunk” of data called a protocol data unit (PDU). This is the process of encapsulation.
  
👉 For example, on the sending node, data is generated by an application, such as the HyperText Transfer Protocol (HTTP), which will include its own application header.  
- At the Transport layer, a Transmission Control Protocol (TCP) header is added to this application data.  
- At the Network layer, the TCP segment is wrapped in an Internet Protocol (IP) header.  
- The IP packet is encapsulated in an Ethernet frame at the Data Link layer.  
- Then the stream of bits making up the frame is transmitted over the network at the Physical layer as a modulated electrical signal.  
- The receiving node performs the reverse process, referred to as decapsulation.  
- It receives the stream of bits arriving at the Physical layer and decodes an Ethernet frame.  
- It extracts the IP packet from this frame and resolves the information in the IP header.  
- Then it does the same for the TCP and Application headers.  
- Eventually, the HTTP application data is extracted for processing by a software program, such as a web browser or web server.

---

