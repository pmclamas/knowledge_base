#### Why NAT?
IP addresses are a finite resource - 32 bits allows for roughly 4.2 billion possible IP address combinations.
As the internet grew in popularity, the industry realised there would one day be more hosts on the internet than there were IP addresses available.
The long term, permanent solution was to create a larger address range, and IPv6 was born which is an addressing scheme that uses 128 bits. 
However, transitioning to IPv6 would prove to be a complicated and slow process, so a short term solution had to also be implemented: RFC 1918 was created to reduce the rate of IPv4 address utilisation and delay the inevitable exhaustion of addresses.
**RFC 1918** designated three different address sets that were considered free to use and reuse by any organisation.
- 10.0.0.0 /8
- 172.16.0.0 /12
- 192.168.0.0 /16
These addresses were labeled as Private addresses, and were deemed unroutable on the Internet. All the remaining addresses remained Public addresses, and able to be routed on the Internet.
With RFC 1918, if you had 30 hosts on your network, all 30 of them would use 30 unique Private IP addresses, but for internet facing traffic, all 30 could share a single Public address, allowing you to conserve 29 Public addresses.
This is exactly what happens on Wi-Fi networks. Each device on the network has a private IP address from one of the private ranges above. When these devices speak to the Internet, they all share the IP address assigned to the Wi-Fi router.
These private addresses can be reused with each deployment without fear of duplicate addresses on the internet. So long as the Public address they are sharing is unique.

Private addresses are theoretically infinite, since they can be reused with each deployment. Public addresses are finite, and tracked by the Internet Authority for Assigned Numbers (IANA) to ensure no organisation inadvertently uses duplicate Public addresses.
Consequently, the concept of Network Address Translation was born to facilitate the translation between Private addresses and Public addresses.

**NAT vs PAT**
NAT in and of itself only affects the L3 header, which in today's world will be the IPv4 header. 
Port Address Translation (PAT) implies a translation of an IP address and Port to another IP address and Port.
PAT affects both the L3 header and the L4 header. Which means the IPv4 Header, as well as either the TCP or UDP header, will be modified.
In summary, a NAT modified only the L3 header, and a PAT modified both the L3 and L4 header. 
*Both NAT and PAT can exist in two forms:* **Static or Dynamic**.
These two terms designate whether the post-translation attributes of the packet are explicitly defined by the administrator or determined by the translation device. In either case, the pre-translation attributes are explicitly defined. This is how the NAT device knows which packets should be translated in the first place.
