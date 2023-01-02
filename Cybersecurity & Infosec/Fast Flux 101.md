How cybercriminals improve the resilience of their infrastructure

[Paloaltonetworks Link](https://unit42.paloaltonetworks.com/fast-flux-101/)

Fast Flux is a technique used by cybercriminals to increase their infrastructure's resilience by making the takedown of their servers and denylisting of their IP addresses harder. 

The motivation for cybercriminals to build fast flux networks is similar to that of benign service providers, who build redundancy in their systems to ensure uptime, for example, by utilizing Round Robin in the Domain Name System (RRDNS) or Content Delivery Networks (CDNs). The main difference is that fast flux networks are used to enable illegal and malicious activities. 
Therefore, operators need to rely on peculiar techniques such as frequently changing their IP addresses and using botnets or bulletproof hosting (hosting providers who tend not to respond to takedown requests). A fast flux network is "fast" because, using DNS, it quickly rotates through many bots, using each one for only a short time to make IP-based denylisting and takedown efforts difficult.

Cybercriminals use single fast flux networks and more advanced techniques such as double flux (when the domain name resolution becomes part of the fast flux network) an Domain Generation Algorithms (DGAs) to hamper domain denylisting and takedown efforts.

Fast Flux networks can be used to support a wide variety of criminal endeavors, such as phishing, scams, malware distribution and botnet operations. 

One way to avoid detection: write a script that can automatically update the hosts where the DNS records of the typosquatting domain are pointed. 

The most important part of the Flux Networks technique is to get a lot of compromised machines, in order to rapidly switch the DNS records.

**Double Flux -** move the DNS resolution itself to a fast flux network.