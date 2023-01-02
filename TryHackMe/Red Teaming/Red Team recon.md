##### Introduction
The more you know about your target's infrastructure and personnel, the better you can orchestrate your attacks.

In a Red Team operation, you might start with no more than a company name, from which you need to start gathering information about the target. This is where reconnaissance comes into play.
Reconnaissance (recon) can be defined as a preliminary survey or observation of your target without alerting them to your activities. If your recon activities create too much noise, the other party would be alerted, which might decrease the likelihood of your success.

*Reconnaissance can be broken down into two parts:*
- *passive recon -* can be carried out by watching passively
- *active recon -* requires interacting with the target to provoke it in order to observe its response.

##### Taxonomy of Reconnaissance
***Passive recon*** relies on publicly available information that is collected and maintanied by a third party. OSINT is used to collect information about the target. Example information that we might collect includes domain names, IP address blocks, email addresses, employee names, and job posts. 

***Active recon*** requires interacting with the target by sending requests and packets and observing if and how it responds. An example of active reconnaissance is using Nmap to scan target subnets and live hosts.
***Active recon can be classified as:***
1. ***External recon -*** conducted outside the target's network and focuses on the externally facing assets assessable form the internet. One example is running Nikto from outside the company network.
2. ***Internal recon -*** conducted from within the target company's network. In other words, the pentester or red teamer might be physically located inside the company building. In this scenario, they might be using an exploited host on the target's network. An example would be using Nessus to scan the internal network using one of the target's computers.

##### Built-in tools
**WHOIS -** is a request and response protocol that follows the RFC 3912 specification. A WHOIS server listens on TCP port 43 for incoming requests.
It is possible to gain a lot of valuable information with only WHOIS and a domain name.

**nslookup -** DNS queries can be executed with many different tools found on our systems. One common tool found on all systems is nslookup.

**dig -** short for Domain Information Groper. Dig provides a lot of query options and even allows you to specify a different DNS server to use. 

**host -** is another useful alternative for querying DNS servers for DNS records. 

**traceroute (tracert on windows) -** traces the route taken by the packets from our system to the target host. Traceroute provides us with the routers (hops) connecting us to the target system. It's worth stressing that some routers don't respond to the packets sent by traceroute, and as a result, we don't see their IP addresses; a * is used to indicate such case.

In summary, we can always rely on:
- WHOIS to query the WHOIS database
- nslookup, dig, or host to query DNS servers.

WHOIS databases and DNS servers hold publicly available information, and querying either does not generate any suspicious traffic.

Moreover, we can rely on Traceroute to discover the hops between our system and the target host.

##### Recon-ng
##### Maltego
