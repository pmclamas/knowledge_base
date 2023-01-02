_**What is cryptography?**_

Cryptography is the practice and study of techniques for securing information and communication mainly to protect the data from third parties that the data is not intended for.

**What is the difference between Symmetric and Asymmetric encryption?** 
![[Screenshot 2022-03-09 at 14.13.12.png]]
_**What is the difference between IDS (Intrusion Detection System) and IPS (Intrusion Prevention System)?**_

IDS only detects intrusions and the administrator has to take care of preventing the intrusion.

Whereas in IPS, the system detects the intrusion and also takes actions to prevent the intrusion.

_**Explain CIA triad.**_

CIA stands for Confidentiality, Integrity, and Availability. CIA is a model that is designed to guide policies for Information Security. It is one of the most popular models used by organisations.

Confidentiality - the information should be accessible and readable only to authorised personnel. The information should be strongly encrypted just in case someone uses hacking to access the data so that even if the data is accessed, it is not readable or understandable.

Integrity - making sure the data has not been modified by an unauthorised entity. Integrity ensures that data is not corrupted or modified by unauthorised personnel. If an authorised individual/system is trying to modify the data and the modification wasn’t successful, then the data should be reversed back and should not be corrupted.

Availability - the data should be available to the user whenever the user requires it. Maintaining of hardware, upgrading regularly, Data Backups and Recovery, Network Bottlenecks should be taken care of.

_**How is encryption different from hashing?**_

Both encryption and hashing are used to convert readable data into an unreadable format. The difference is that the encrypted data can be converted back to original data by the process of decryption but the hashed data cannot be converted back to original data.

_**What is a Firewall and why is it used?**_

A Firewall is a network security system set on the boundaries of the system/network that monitors and controls network traffic. Firewalls are mainly used to protect the system/network from viruses, worms, malware, etc. Firewalls can also be to prevent remote access and content filtering.

_**What is the difference between VA (Vulnerability Assessment) and PT (Penetration Testing)?**_

Vulnerability Assessment is the process of finding flaws on the target. Here, the organisation knows that their system/network has flaws or weaknesses and want to find these flaws and prioritise the flaws for fixing.

Penetration Testing is the process of finding vulnerabilities on the target. In this case, the organisation would have set up all the security measures they could think of and would want to test if there is any other way that their system/network can be hacked.

_**What is a three-way handshake?**_

A three-way handshake is a method used in TCP/IP network to create a connection between a host and a client. It’s called a three-way handshake because it is a three-step method in which the client and server exchanges packets. The three steps are as fallows:

1.  The client sends a SYN (Synchronize) packet to the server check if the server is up or has open ports.
2.  The server sends SYN-ACK packet to the client if it has open ports
3.  The client acknowledges this and sends an ACK (Acknowledgment) packet back to the server.

_**What are the response codes that can be received from a web application?**_

1xx - Informational responses

2xx - Success

3xx - Redirection

4xx - client-side error

5xx - server-side error

_**What is traceroute? Whys is it used?**_

Traceroute is a tool that shows the path of a packet. It lists all the points (mainly routers) that the packet passes through. This is used mostly when the packet is not reaching its destination. Traceroute is used to check where the connection stops or breaks to identify the point of failure.

_**What is the difference between HIDS and NIDS?**_

HIDS (Host IDS) and NIDS (Network IDS) are both Intrusion Detection Systems and work for the same purpose (to detect intrusions). The only difference is that the HIDS is set up on a particular host/device. It monitors the traffic of a particular device and suspicious system activities. On the other hand, NIDS is set up on a network. It monitors traffic of all device of the network.

_**What are the steps to set up a firewall?**_

1.  Username/password: modify the default password for a firewall device.
2.  Remote administration: disable the feature of the remote administration.
3.  Port forwarding: configure appropriate port forwarding for certain applications to work properly, such as a web server or FTP server
4.  DHCP server: installing a firewall on a network with an existing DHCP server will cause confict unless the firewall's DHCP is disabled.
5.  Logging: to troubleshoot firewall issues or potential attacks, ensure that logging is enabled and understand how to view logs.
6.  Policies: you should have solid security policies in place and make sure that the firewall is configured to enforce those policies.

_**Explain SSL Encryption?**_

SSL (Secure Sockets Layer) is the industry-standard security technology creating encrypted connections between Web Server and a Browser. This is used to maintain data privacy and to protect the information in online transactions. The steps for establishing an SSL connection is as follows:

1.  a browser tries to connect to the webserver secured with SSL.
2.  the browser sends a copy of its SSL certificate to the browser.
3.  the browser checks if the SSL certificate is trustworthy or not. If it is trustworthy, then the browser sends a message to the web server requesting to establish an encrypted connection.
4.  The web server sends an acknowledgment to start an SSL encrypted connection.
5.  SSL encrypted communication takes place between the browser and the web server.

_**What steps will you take to secure a server?**_

Secure servers use the Secure Sockets Layer (SSL) protocol for data encryption and decryption to protect data from unauthorized interception.

Step 1: make sure you have a secure password for your root and administrator users.

Step 2: the next thing you need to do is make new users on your system. These will be the users you use to manage the system.

Step 3: Remove remote access from the default root/administrator accounts.

Step 4: the next step is to configure your firewall rules for remote access.

_**Explain data leakage**_

Data Leakage is an intentional or unintentional transmission of data from within the organization to an external unauthorized destination. It is the disclosure of confidential information to an unauthorized entity. Data Leakage can be divided into 3 categories based on how it happens:

1.  Accidental Breach: an entity unintentionally send data to an unauthorized person due to a fault or a blunder.
2.  Intentional Breach: the authorized entity sends data to an unauthorized entity or purpose.
3.  System Hack: hacking techniques are used to cause data leakage.

Data Leakage can be prevented by using tools, software, and strategies known as DLP (Data Leakage Prevention) tools.

_**What are some of the common cyberattacks?**_

1.  Malware
2.  Phishing
3.  Password attacks
4.  DDoS
5.  Man-in-the-Middle
6.  Drive-by downloads
7.  Malvertising
8.  Rogue software

_**What is a Brute Force Attack? How can you prevent it?**_

Brute Force is a way of finding out the right credentials by repetitively trying all the permutations and combinations of possible credentials. In most cases, brute force attacks are automated attacks where the tool/software automatically tries to login with a list of credentials. There are various ways to prevent Brute Force attacks:

-   Password length
-   password complexity
-   limiting login attempts

_**What is Port Scanning?**_

Port scanning is the technique used to identify open ports and service available on a host. Hackers use port scanning to find information that can be helpful to exploit vulnerabilities. Administrators use Port Scanning to verify the security policies of the network. Some of the common Port Scanning Techniques are:

1.  Ping Scan
2.  TCP Half-Open
3.  TCP Connect
4.  UDP
5.  Stealth Scanning

_**What are the different layers of the OSI Model?**_

An OSI Model is a reference model for how applications communicate over a network. The purpose of an OSI reference is to guide vendors and developers so the digital communication products and software programs can interoperate.

Following are the OSI layers:
![[Screenshot 2022-03-09 at 14.15.04.png]]
-   _**Physical layer:**_ responsible for transmission of digital data from sender to receiver through the communication media
-   _**Data Link Layer:**_ handles the movement of data to and from the physical link. It is also responsible for encoding and decoding of data bits.
-   _**Network Layer:**_ responsible for packet forwarding and providing routing paths for network communication.
-   _**Transport Layer:**_ responsible for end-to-end communication over the network. It splits the data from the above layer and passes it to the Network Layer and then ensures that all the data has successfully reached at the receiver's end.
-   _**Session Layer:**_ controls connection between the sender and the receiver. It is responsible for starting, ending, and managing the session and establishing, maintaining and synchronizing interaction between the sender and the receiver.
-   _**Presentation layer:**_ it deals with presenting the data in a proper format and data structure instead of sending raw datagrams or packets.
-   _**Application layer:**_ it provides an interface between the application and the network. It focuses on process-to-process communication and provides a communication interface.

_**What is a VPN?**_

VPN stands for Virtual Private Network. It is used to create a safe and encrypted connection. When you use a VPN, the data from the client is sent to a point in the VPN where it is encrypted and then sent through the internet to another point. At this point, the data is decrypted and sent to the server. When the server sends a response, the response is sent to a point in the VPN where it is encrypted and this encrypted data is sent to another point in the VPN where it is decrypted. And finally, the decrypted data is sent to the client. The whole point of using a VPN is to ensure encrypted data transfer.

_**What do you understand by Risk, Vulnerability & Threat in a network?**_

_Threat:_ someone with the potential to harm a system or an organization.

_Vulnerability:_ weakness in a system that can be exploited by a potential hacker.

_Risk:_ potential for loss or damage when threat exploits a vulnerability.

_**How can identity theft be prevented?**_

-   Ensure strong and unique password;
-   Avoid sharing confidential information online, especially on social media;
-   Shop from known and trusted websites;
-   Use the latest version of the browsers;
-   Install advanced malware and spyware tools;
-   Use specialized security solutions against financial data;
-   Always update your system and software;
-   Protect all your personal/private information.

_**What are Black Hat, White Hat and Grey Hat hackers?**_

Black Hat Hackers are known for having vast knowledge about breaking into computer networks. They can write malware which can be used to gain access to these systems. This type of hackers misuse their skills to steal information or use the hacked system for malicious purpose.

White Hat Hackers use their powers for good deeds and so they are also called Ethical Hackers. These are mostly hired by companies as a security specialist that attempts to find and fix vulnerabilities and security holes in the systems. They use their skills to help make the security better.

Grey Hat Hackers are an amalgamation of a White Hat and Black Hat hacker. They look for system vulnerabilities without the owner's permission. If they find any vulnerabilities, they report it to the owner. Unlike Black Hat hackers, they do not exploit the vulnerabilities found.

_**How would you reset a password-protected BIOS configuration?**_

Since BIOS is a pre-boot system it has its own storage mechanism for settings and preferences. A simple way to rest is by popping out the CMOS battery so that the memory storing the settings lose its power supply and as a result, it will lose its settings.

_**Explain MITM attack and how to prevent it?**_

A MITM (Man-in-the-Middle) attack is a type of attack where the hacker places himself in between the communication of two parties and steal information. The data from both the parties are sent to the hacker and the hacker redirects the data to the destination party after stealing the data required. While the two parties think that they are communicating with each other, in reality, they are communicating with the hacker.

You can prevent MITM attack by using the following practices:

-   Use VPN
-   Use strong WEP/WPA encryption
-   Use Intrusion Detection Systems
-   Force HTTPS
-   Public Key Pair Based Authentication

_**Explain DDoS attack and how to prevent it?**_

A Distributed Denial of Service attack is a cyber attack that causes the servers to refuse to provide services to genuine clients. DDoS attacks can be classified into two types:

-   Flooding attacks: in this type, the hacker sends a huge amount of traffic to the server which the server cannot handle. And hence, the server stops functioning. This type of attack is usually executed by using automated programs that continuously send packets to the server.
-   Crash attacks: in this type, the hackers exploit a bug on the server resulting in the system to crash and hence the server is not able to provide service to the clients.

You can prevent DDoS attacks by using the following practices:

-   Use Anti-DDoS services;
-   Configure Firewalls and Routers
-   Use front-end hardware
-   Use load balancing
-   Handle spikes in traffic

_**Explain XSS attack and how to prevent it?**_

XSS (Cross-Site Scripting) is a cyber attack that enables hackers to inject malicious client-side scripts into web pages. XSS can be used to hijack sessions and steal cookies, modify DOM, remote code execution, crash the server etc.

You can prevent XSS attacks by using the following practices:

-   Validate user inputs
-   Sanitize user inputs
-   encode special characters
-   use anti-xss service/tools
-   use xss html filter

_**What is an ARP and how does it work?**_

Address Resolution Protocol (ARP) is a protocol for mapping an Internet Protocol Address (IP Address) to a physical machine address that is recognized in the local network.

When an incoming packet destined for a host machine on a particular local area network arrives at a gateway, the gateway asks the ARP program to find a physical host or MAC address that matches the IP address.

The ARP program looks in the ARP cache and, if it finds the address, provides it so that the packet can be converted to the right packet length and format an sent to the machine.

If no entry is found for the IP address, ARP broadcasts a request packet in a special format to all the machines on the LAN to see if one machine knows that it has that IP address associated with it.

_**What is port blocking within LAN?**_

Restricting the users from accessing a set of services within the local are network is called port blocking.

Stopping the source to not access the destination node via ports. As the application works on the ports, so ports are blocked to restricts the access filling up the security holes in the network infrastructure.

_**What protocols fall under TCP/IP internet layer?**_
![[Screenshot 2022-03-09 at 14.16.28.png]]

_**What is a Botnet?**_

A Botnet is a number of devices connected to the internet where each device has one or more bots running on it. The bots on the devices and malicious scripts used to hack a victim. Botnets can be used to steal data, send spams and execute a DDoS attack.

_**What are salted hashes?**_

Salt is a random data. When a properly protected password system receives a new password, it creates a hash value of that password, a random salt value, and then the combined value is stored in its database. This helps to defend against dictionary attacks and known hash attacks.

Example: if someone uses the same password on two different systems and they are being used the same hashing algorithm, the hash value would be same, however, if even one of the system uses salt with the hashes, the value will be different.

_**Explain SSL and TLS.**_

SSL is meant to verify the sender's identity but it doesn't search for anything more than that. SSL can help you track the person you are talking to but that can also be tricked at times.

TLS is also an identification tool just like SSL, but it offers better security features. It provides additional protection to the data and hence SSL and TLS are often used together for better protection.

_**What is data protection in transit vs. data protection at rest?**_
![[Screenshot 2022-03-09 at 14.17.05.png]]

_**What is 2FA and how can it be implemented for public websites?**_

An extra layer of security known as "multi-factor authentication".

Requires not only a password and username but also something that only, and only that user has with him, i.e. a peice of information only they should know or have immediately to hand - such as a physical token.

Authenticator apps replace the ned to obtain a verification code via text, voice call, or email.

_**What is Cognitive Cybersecurity?**_

Cognitive Cybersecurity is an application of AI technologies patterned on human thought processes to detect threats and protect physical and digital systems.

Self-learning security systems use data mining, pattern recognition, and natural language processing to simulate the human brain, albeit in a high-powered computer model.

_**What is the difference between VPN and VLAN?**_
![[Screenshot 2022-03-09 at 14.17.41.png]]
**Explain phishing and how to prevent it?**

Phishing is a cyber attack in which a hacker disguises as a trustworthy person or business and attempt to steal sensitive financial or personal information through fraudulent email or instant message.

You can prevent Phishing attacks by using the following practices:

-   don't enter sensitive information in webpages that you don't trust
-   verify the site's security
-   use firewalls
-   use antivirus software that has Internet Security
-   use anti-phishing toolbar

_**Explain SQL Injection and how to prevent it?**_

SQL Injection (SQLi) is a code injection attack where an attacker manipulates the data being sent to the server to execute malicious SQL statements to control a web application's database server, thereby accessing, modifying and deleting unauthorized data. This attack is mainly used to take over database servers.

You can prevent SQL Injection attacks by using the following practices:

-   Use prepared statements
-   Use Stored Procedures
-   Validate user input