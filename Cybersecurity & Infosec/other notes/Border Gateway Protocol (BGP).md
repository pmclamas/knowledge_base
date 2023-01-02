BGP is a routing protocol used to transfer data and information between different host gateways, the Internet or autonomous systems. BGP is a Path Vector Protocol (PVP), which maintains paths to different hosts, networks and gateway routers and determines the routing decision based on that. It does not use Interior Gateway Protocol (IGP) metrics for routing decisions, but only decides the route based on path, network policies and rule sets. Sometimes, BGP is described as a reachability protocol rather than a routing protocol.
_BGP roles include:_
- Because it is a PVP, BGP communicates the entire autonomous system/network path topology to other networks.
- Maintains its routing table with topologies of all externally connected networks.
- Supports Classless Interdomain Routing (CIDR), which allocates Internet Protocol (IP) addresses to Connected Internet devices. 

When used to facilitate communication between different autonomous systems, BGP is referred to as External BGP (EBGP). 
When used at host networks/autonomous systems, BGP is referred to as Internal BGP (IBGP).
BGP was created to extend and replace Exterior Gateway Protocol (EGP).