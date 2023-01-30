An IP address is the logical addressing scheme for nodes on a network. **IP addresses exist at the Network Layer of the OSI Model** and help facilitate the L3 goal of "end-to-end" delivery.

A MAC address is the physical addressing scheme for individual NIC cards on each node of the network. **MAC addresses exist at the Data Link Layer of the OSI Model** and help facilitate the L2 goal of "hop to hop" delivery.

The Address Resolution Protocol (ARP) creates the correlation which makes the union between these two addressing schemes possible.

Typically, when two hosts are communicating, the already know each other's IP address. However, what is definitely not known is their MAC addresses. The hosts will use ARP to discover the appropriate MAC addresses. To put it another way, ARP will use the known IP address, and discover the unknown MAC address.
ARP Table, which is a mapping of IP addresses to correlating MAC addresses.

- when a client is speaking to a host in the same network, it will ARP for the MAC address of the host.
- when a client is speaking to a host in a different network, it will ARP for the MAC address of the Default Gateway.

Remember, packet delivery is always the job of Layer 2, and Layer 2's primary goal is getting a packet from hop to hop. Conversely, Layer 3, which is concerned with end to end delivery is unable to put a packet on a wire and send it to another host's NIC. ARP's role is to help the client create the proper L2 header, based on the L3 header, in order to get the packet from one hop to the next.

It should also be noted that any device that intends to forward a packet based upon the IP address (L3), must also have the ability to deliver the packet to the next hop (L2). As such, any device that uses IP addresses must also use ARP to deliver the packet using MAC addresses. Consequently, all Layer 3 devices must maintain an ARP Table.

#### **Traditional ARP**
The ARP is the process by which a known L3 address is mapped to an unknown L2 address. The purpose for creating such a mapping is so a packet's L2 header can be properly populated to deliver a packet to the next NIC in the path between two end points.
The "next NIC" in the path will become the target of the ARP Request.

If a host is speaking to another host on the same IP network, the target for the ARP request is the other host's IP address. If a host is speaking to another host on a different IP network, the target for the ARP request will be the Default Gateway's IP address.

In the same way, if a Router is delivering a packet to the destination host, the Router's ARP target will be the Host's IP address. If a router is delivering a packet to the next Router in the path to the host, the ARP target will be the other Router's Interface IP address - as indicated by the relative entry in the Routing Table.

##### ARP Process
The address resolution itself is a two step process - a request and a response. 
It starts with the initiator sending an ARP request as a broadcast frame to the entire network. This request must be a broadcast, because at this point the initiator does not know the target's MAC address, and is therefore unable to send a unicast frame to the target.
Since it was a broadcast, all nodes on the network will receive the ARP Request. All nodes will take a look at the content of the ARP Request to determine whether they are the intended target. The nodes which are not the intended target will silently discard the packet.
The node which is the target of the ARP Request will then send an ARP Response back to the original sender. Since the target knows who sent the initial ARP Request, it is able to send the ARP Response unicast, directly back to the initiator.
The ARP Request includes the sender's MAC address. This is what allows the target to respond directly back to the initiator.

- ARP Request
The ARP Request is an ARP payload carried within the appropriate L2 frame for the medium in use. The majority of the time this will be Ethernet.
The Ethernet header will include three fields: a Destination MAC address, a Source MAC address, and an EtherType.

*(Notice Host B is referred to as the target, and not the destination. This is an important distinction. The ARP Request destination was the broadcast MAC address. The ARP Request existed for the purpose of resolving Host B MAC Address, hence the target is Host B. Consider the target to mean the subject of the ARP conversation.)*

- ARP Response
The Ethernet header has three parts: a destination MAC address, a Source Mac Address, and an EtherType.
The Destination MAC is Host A - the initial requester, and the source MAC is Host B - the original target. The frame is addressed directly back to Host A - this is what makes the response Unicast.
The major difference between the Request and Response is in the Opcode field. In an ARP Response, this field contains a value of 2.
The sender MAC and sender IP address include the addresses for Host B, which is expected given Host B sent the ARP Response.
The target MAC and target IP address include the addresses for Host A, as this is the target of the ARP Response.

*(The packet capture of an ARP conversation can be studied using Wireshark.)*

##### ARP Timing
When the ARP process completes, the information learned is stored in an ARP Table, or ARP cache. Every device that has an IP address maintains such a table. Entries in this table expire after a certain duration.
Typically, for clients and end hosts, the ARP timeout will be pretty short (60 seconds or less). The reason for this is at the client level, lots of mobility and movement happens, and you don't want to cache an ARP entry for a very long time. 
Whereas for network infrastructure devices (routers, firewalls, etc) the ARP timeout is longer (2-4 hours). The reason for this is at the infrastructure level, the nodes joining and leaving the network should remain pretty consistent.

A Router has no way of knowing whether an entry in its ARP cache is a host or another infrastructure device. Instead, to keep up with the mobility of clients, a Router's cache is updated whenever it receives an ARP request.
Which is to say, if a Host is refreshing its default gateway's ARP mapping every 30~ seconds due to the host's shorter ARP timing, the default gateway's ARP mapping of that same host will also be updated every 30~ seconds.

##### Proxy ARP
Proxy ARP occurs when a node is responding to an ARP request on behalf of another node.
Proxy ARP is not a malicious event, it occurs to enable connectivity between two hosts that wouldn't be possible otherwise.

The original thought process for Proxy ARP was to accommodate hosts with misconfigured subnet masks. The item which tells a host whether another IP address is on the same network or a different network is the subnet mask.

The Routers respond to ARP requests on behalf of hosts on a different network. Which is the exact definition of a Proxy ARP. The ARP response sent by the Router looks exactly like a normal ARP response. All subsequent packets sent to the host on a different network will use this MAC address in the L2 header.

**Proxy ARP unfortunately does not scale indefinitely and should not be relied upon. The long term solution is to correct the misconfigured subnet mask.**

With Proxy ARP, the host may never even realise it has an incorrect subnet mask. Many routers these days do not send Proxy ARPs by default for this very reason.

**Proxy ARP in Network Address Translation (NAT)**
There is a legitimate and necessary use case for Proxy ARP, and that has to do with Network Address Translation.
*(Network Address Translation - sometimes, while data is in route to a destination, the IP addresses used in the communication need to be translated to different IP addresses)*

##### Gratuitous ARP
A Gratuitous ARP is an ARP response that was not prompted by an ARP request. The Gratuitous ARP is sent as a broadcast, as a way for a node to announce or update its IP to MAC mapping to the entire network.

There are three primary cases for Gratuitous ARP:
- updating ARP mappings - a node can use a Gratuitous ARP to update the ARP mapping of the other hosts on the network should the node's IP to MAC mapping chance. This might happen if a user manually modifies their MAC address (they retain the same IP address, but now have a new MAC address). Manually changing the MAC address is pretty rare. However, you do sometimes see this in redundant cloud or virtual environments.
- announcing a node's existence - is when a host newly joins a network - it can use Gratuitous ARP to announce it's existence to the network. It is an attempt to preemptively populate ARP caches of neighbouring hosts without requiring them to initiate the Traditional ARP process. However, there is no mandate for hosts to cache ARP mappings in every Gratuitous ARP they receive. As a result, this use case provides little benefit.
  (This use case is often confused with an attempt to detect possible duplicate IP addresses, but a Gratuitous ARP is not used for this process. To detect an IP address conflict, hosts will use ARP Probes and Announcements)
- redundancy - with redundancy, you typically have two scenarios: two devices sharing an IP address, but each having their own MAC address. Or, two devices sharing both an IP address and a MAC address.
  In both of these cases, Gratuitous ARP is critically important to ensure the continued ability to communicate with the IP address as it shifts between the two redundant devices. 

##### ARP Probe and ARP Announcement
Both are used in a process known as Duplicate Address Detection.
The idea is if a host acquires and puts to use an IP address that happens to already be in use on the network, it will cause connectively issues for both hosts. As such, it is beneficial for a host to first test an IP address before putting it to use to ensure it is indeed unique.
One such way of determining if an IP address in use is to use ARP. Or specifically, an ARP probe.
The process is pretty straight forward, send a few ARP Probes (typically 3), and if no one responds, officially claim the IP address with an ARP Announcement. 
Both the ARP Probes and the ARP Announcements are sent as broadcast frames.
Both are sent without being solicited by a request, which therefore makes them "gratuitous". But technically, they are not exactly the same as a Gratuitous ARP.

The reason for sending the ARP Probe is to prevent an IP conflict. If the target IP address is already in use, it would be very undesirable for other hosts on the network to inadvertently update their ARP cache based upon the contents of the ARP Probe.

This is also the primary difference between an ARP Probe and a Gratuitous ARP. A Gratuitous ARP is meant to update all the ARP caches on the network, where as an ARP Probe deliberately prevents updating of ARP caches to continue protecting against IP address conflicts.

If the ARP Probe does not generate a response from whomever might already be using the IP address, the initiating host will consider this IP address unique and will send an ARP Announcement to officially "claim" the IP address on the network.