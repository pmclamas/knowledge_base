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
**Host -** generic term that implies any sort of end-device on the internet. Any device which might be the original initiation of traffic or the final destination of traffic can be considered a host.
Hosts run software and applications for the end user to interact with, and they also, at some point, need to put bits on a wire. As such, it is said that Hosts operate across all seven layers of the OSI model.
In typical internet communication or network traffic, the two hosts in communication are often labeled as the Client or the Server.
The Client is the entity initiating the request and is looking to acquire a piece of information or data or a service. While the Server is the entity receiving the request and has the information, data, or service that the Client wants.

**Network -** is simply two or more connected devices. In fact, the whole Internet is nothing more than a series of inter-connected networks.

**Switch -** is a network device whose primary purpose is to facilitate communication within networks.
Switches operate at Layer 2 of the OSI model. The Layer 2 header contains information that enables hop to hop delivery, such as the Source and Destination MAC address.
A Switch operates by maintaining what is known as a MAC address table. This is a table that maps MAC addresses of devices plugged into each switch port. The MAC address Table is populated by looking at the Source MAC address field of any received frames. In order to forward the frame, the Switch will lookup the Destination MAC address in their MAC Address Table to determine what port to use.
If a Switch encounters a frame for which it does not know the location of the Destination MAC address, it simply duplicates and floods the frame out each switch port (except the port it was received on).

**Router -** is a network device whose primary purpose is to facilitate communication between networks. Each interface on a router creates a network boundary.
Routers operate at Layer 3 of the OSI Model, which means they only look into each datagram up to the Layer 3 header. The Layer 3 header contains information that enables end to end delivery, such as the Source and Destination IP address.
A Router maintains what is known as a Routing Table. This is a table that contains paths to all the networks a Router knows how to reach. These paths are sometimes known as Routes, and each entry contains an IP Network and either an interface or the IP address of the next router in the path to the target.
There are multiple ways a Router can learn of a network and populate its Routing table. 
Keep in mind, from the perspective of each router, the Route Table is a map of every network that exists. If a router receives a packet destined to a network it does not know about, then as far as the router is concerned, that network must not exist. Therefore, when a router receives a packet destined to a network which is not in its Routing Table, that packet is discarded.

**Address Resolution Protocol (ARP) -** typically, when two hosts are communicating, they already know each other's IP address. They can know each other's IP address from a variety of methods: sometimes it is manually provided by a user, sometimes by another protocol (often DNS).
However, what is definitely not known is their MAC addresses. The hosts will use ARP to discover the appropriate MAC address. The discovered mapping is then added and stored in an ARP Table, which is a mapping of IP addresses to correlating MAC addresses.

Remember, packet delivery is always the job of Layer 2, and Layer 2's primary goal is getting a packet from hop to hop. Conversely, Layer 3, which is concerned with end to end delivery is unable to put a packet on a wire and send it to another host's NIC. ARP's role is to help the client create the proper L2 header, based on the L3 header, in order to get the packet from one hop to the next.
It should also be noted that any device that intends to forward a packet based upon the IP address (L3), must also have the ability to deliver the packet to the next hop (L2). As such, any device that uses IP addresses must also use ARP to deliver the packet using MAC addresses.
Consequently, all Layer 3 devices must maintain an ARP Table.

##### Summary
- Layer 1 is the physical medium carrying the 1's and 0's across the wire
- Layer 2 is responsible for hop to hop delivery and uses MAC addresses
- Layer 3 is responsible for end to end delivery and uses IP addresses
- Layer 4 is responsible for service to service delivery and uses Port numbers
- Switches facilitate communications within networks and operate at Layer 2
- Routers facilitate communication between networks and operate at Layer 3
- ARP uses a known IP address to resolve an unknown MAC address
- Switches use a MAC Address Table which is mapping of switchports to connected MAC addresses
- Routers use a Routing Table which is a mapping of known networks to interfaces or next-hop addresses
- all L3 devices use an ARP Table which is a mapping of IP addresses to MAC addresses.

### Host to Host communication
![[Screenshot 2023-02-03 at 16.44.58.png]]
Since there are no Routers in this illustration, we know all the communication is happening within the same network - therefore, Host A and Host B are both configured with IP addresses that belong to the same network.
It is rare to find two hosts directly connected to each other. But understanding what it takes to get a packet from one Host to another is key to understanding how a Switch enables multi-host communication, or a Router enables multi-network communication.

### Host to Host through  Switch
##### Switch Functions
A Switch primarily has four functions: learning, flooding, forwarding, and filtering.

**Learning -** being a Layer 2 device, a Switch will make all its decisions based upon information found in the L2 Header. Specifically, a Switch will use the Source MAC address and Destination MAC address to make its forwarding decisions.
One of the goals of the Switch is to create a MAC address table, mapping each of its switchports to the MAC address of the connected devices.
The MAC address table starts out empty, and every time a Switch receives anything, it takes a look at the Source MAC address field of the incoming frame. It uses the Source MAC and the switchport the frame was received on to build an entry in the MAC address table.
Sooner or later, as each connected device inevitably sends something, the Switch will have a fully populated MAC address table. This table can then be used to smartly forward frames to their intended destination.

**Flooding -** it is unavoidable that a Switch will, at some point, receive a frame destined to a MAC address of which the Switch does not know the location.
In such cases, the Switch's only option is to simply duplicate the frame and send it out all ports. This action is known as Flooding.
Flooding assures that if the intended device exists and if ti is connected to the switch, it will definitely receive the frame.
Of course, so will every other device connected to that particular switch.
And though not ideal, this is perfectly normal. The NIC of each connected device will receive the frame and take a look at the Destination MAC address field. If they are not the intended recipient, they will simply silently drop the frame.
If they are the intended device, then the Switch can rest satisfied knowing it was able to deliver the frame successfully.
Moreover, when the intended device receives the frame, a response will be generated, which when sent to the Switch will allow the switch to learn and create a MAC address table mapping that unknown device to its switchport. 

**Forwarding -** 

