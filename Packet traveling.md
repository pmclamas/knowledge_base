#### OSI Model (Open Systems Interconnect Model)
The OSI Model explains all the individual functions that are necessary for the Internet to work.
It is a set of seven independent functions which combine to accomplish the end-goal of Computer to Computer communication.

The OSI Model is divided into seven different layers, each of which fulfils a very specific function. When combined together, each function contributes to full computer to computer data communication.

##### OSI Layer 1 - Physical
Responsible for the transfer of bits.
Represents the physical medium which is carrying the traffic between two nodes. An example would be the Ethernet cable. Wi-Fi, despite it not having a physical, tangible presence, is also considered a Layer 1 protocol.

In the case of Ethernet, bits are transferred in the form of electric pulses. In the case of Wi-Fi, bits are transferred in the form of radio waves. In the case of Fiber, bits are transferred in the form of pulses of light.

Aside from the physical cable, Repeaters and Hubs also operate at this layer.

A Repeater simply repeats a signal from one medium to the other, allowing a series of cables to be chained together and increase the range a signal can travel beyond the single cable limit. These are commonly used in large Wi-Fi deployments, where a single Wi-Fi network is "repeated" throughout multiple access-points to cover a larger range.

A Hub is simply a multi-port Repeater. If four devices are connected to a single Hub, anything sent by one device gets repeated to the other three.

##### OSI Layer 2 - Data Link
Responsible for interfacing with the physical layer. 
The Network Interface Card (NIC) that you plug your Ethernet wire into handles the Layer 2 functionality. It receives signals from the wire, and transmits signals on to the wire. The Wi-Fi NIC works the same way.

Layer 2 will then group together those signals of zeros and ones into chunks known as Frames.

There is an addressing system that exits at Layer 2 known as Media Access Control address (MAC address). the MAC address uniquely identifies each individual NIC. Each NIC is pre-configured with a MAC address by the manufacturer.

Aside from your NIC, a Switch also operates at this layer. A switch's primary responsibility is to facilitate communication within Networks.

The overarching function of the Data Layer is to deliver packets from one NIC to another.

##### OSI Layer 3 - Network
Responsible for packet delivery from end to end.
It does this by using another addressing scheme that can logically identify every node connected to the internet. This addressing scheme is known as the Internet Protocol address (IP address).
An IP address is not a permanent identification of a computer. Unlike the MAC address which is considered a physical address.

Routers are network devices that operate at Layer 3 of the OSI Model. A Router's primary responsibility is to facilitate communication between Networks. As such, a Router creates a boundary between two networks. In order to communicate with any device not directly in your network, a router must be used.

**Layer 2 vs Layer 3**
Both addressing schemes accomplish different functions:
- Layer 2 uses MAC addresses and is responsible for packet delivery from hop to hop
- Layer 3 uses IP addresses and is responsible for packet delivery from end to end

When a computer has data to send, it encapsulates it in a IP header which will include information like the Source and Destination IP addresses of the two "ends" of the communication.
The IP Header and Data are then further encapsulated in a MAC address header, which will include information like the Source and Destination MAC address of the current "hop" in the path towards the final destination.

##### OSI Layer 4 - Transport
Is responsible for distinguishing network streams.
Something has to exist in order to distinguish network streams. That "something" is Layer 4.

Layer 4 accomplishes this by using an addressing scheme known as Port Numbers.
Two methods of distinguishing network streams exist. They are known as the Transmission Control Protocol (TCP), or the User Datagram Protocol (UDP).
Both TCP and UDP have 65.536 port numbers (each), and a unique application stream is identified by both a Source and Destination port (in combination with their Source and Destination IP address).

TCP and UDP employ different strategies in how data streams are transferred.

##### OSI Layer 5, 6, and 7
The Session, Presentation, and Application layers handle the final steps before the data transferred through the network is displayed to the end user.
From a purely network engineering perspective, the distinction between Layers 5, 6, and 7 is not particularly significant. In fact, there is another popular Internet Communication model known as the TCP/IP model, which groups these three layers into one single encompassing layer.

##### Encapsulation and Decapsulation
These terms refer to how data is moved through the layers from top to bottom when sending and from bottom to top when receiving.

As the data is handed from layer to layer, each layer adds the information it requires to accomplish its goal before the complete datagram is converted to 1s and 0s and sent across the wire. For example:
- Layer 4 will add a TCP header which would include a Source and Destination Port
- Layer 3 will add an IP header which would include a Source and Destination IP address
- Layer 2 would add an Ethernet header which would include a Source and Destination MAC address.
On the receiving end, each layer strips the header from the data and passes it back up the stack towards the Application layer.
Here is the whole process in action:
![[packtrav-encap-decap.gif]]
Note that this is only an example. The header that will be added will be dependent on the underlying communication protocol. For instance, a UDP header might be added at Layer 4 instead, or an IPv6 header might be added at Layer 3.
Either way, it is important to understand that as data is sent across the wire, it gets passed down the stack and each layer adds its own header to help accomplish its goal. On the receiving end, the headers get stripped off one at a time, layer by layer, as the data is sent back up to the Application layer.

{While essential for understanding how packets move through a network, the OSI Model itself is not a strict requirement as much as it is a conceptual model - not every protocol will fit perfectly within a single layer of the OSI model}

### Key Players


