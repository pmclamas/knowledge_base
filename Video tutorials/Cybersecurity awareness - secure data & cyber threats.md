#### Introduction to cybersecurity
**What is cybersecurity? -** cybersecurity is the protection of computer systems and networks from information disclosure, theft of or damage to their hardware, software, or electronic data.

Cybersecurity:
- Computer Devices
- Networks
- Data
- Digital components

**The evolution of cyber threats and their solutions**
- 1st Generation - Virus (late 1980s) - virus attacks on standalone PCs affected all businesses and drove anti-virus products.
- 2nd Generation - Networks (mid 1990s) - attacks from the internet affected all businesses and drove creation of firewall.
- 3rd Generation - Applications (early 2000s) - exploiting vulnerabilities in applications affected most businesses and drove intrusion prevention systems (IPS) products.
- 4th Generation - Payload (approx. 2010) - rise of targeted, unknown, evasive, polymorphic attacks affected most businesses and drove anti-bot and sandboxing products.
- 5th Generation - APTs (approx. 2017) - large scale, multi-vector, mega attacks using advanced attack tools and is driving advanced threat prevention solutions.

#### Information Security goals
**1. Confidentiality -** prevents unauthorized disclosure of sensitive information.
**2. Integrity -** prevents unauthorized modification of systems and information.
**3. Availability -** prevents disruption of service and productivity.

**Threat, Vulnerability and risk**

Threat + Vulnerability = Risk

Threat: a new incident with potential to harm a system.

Vulnerability: known weaknesses that hackers could exploit.

Risk: the potential for damage when a threat exploits a vulnerability.

#### Networking Devices
**Router -** network device that forwards data packets between computer networks. Routers perform the traffic directing functions on the internet.

**Switch -** it is a small hardware device that links multiple PCs, printers, servers, together within one local area network, wide area network and different network topology.

**IP address -** is a unique address that identifies a device on the internet or a local network.

**MAC address -** is a unique number which is used to track a device in a network.

**Port address -** are particularly used to differentiate the data packets for various applications so that the PC knows which application should process the packet. For example, Port 80 is used for http packets, Port 21 for File Transfer Protocol (FTP).

**DNS (Domain Name System) -** the main function of DNS is to translate domain names into IP addresses, which computers can understand.

**VPN (Virtual Private Network) -** is an encrypted connection over the internet from a device to a network. The encrypted connection helps ensure that sensitive data is safely transmitted. It prevents unauthorized people from eavesdropping on the traffic and allows the user to conduct work remotely.

**Virus -** a malicious piece of code designed to spread from device to device.

#### Cybersecurity skills
- **_Solid ground in IT fundamentals_**
- **_Solid ground in Networking Fundamentals_**
- **_Coding skills_**
- **_Understanding of architecture of operating systems_**
- **_Cloud security_**
- **_Malware analysis and reversing_**

#### Fundamentals of Networking
**OSI model**
**_7.Application Layer -_** human-computer interaction layer, where applications can access the network services. _Protocols:_ http, ftp, snmp, telnet
**_6.Presentation Layer -_** ensures that data is in a usable format and is where data encryption occurs. _Protocols:_ ssl, tls
**_5.Session Layer -_** maintains connections and is responsible for controlling ports and sessions. _Protocols:_ pptp, netbos
**_4.Transport Layer -_** transmits data using transmission protocols including TCP and UDP. _Protocols:_ tcp, udp
**_3.Network Layer -_** decides which physical path the data will take. _Protocols:_ IP, arp, icmo, IPsec
**_2.Data Link Layer -_** defines the format of data on the network. _Protocols:_ ppp, atm, ethernet
**_1.Physical Layer -_** transmits raw bit stream over the physical medium. _Protocols:_ netbos, pptpm

**HTTP protocol (Hyper Text Transfer Protocol)** 
Allows the fetching of resources, such as html documents. It is the foundation of any data exchange on the web and it is a client-server protocol, which means requests are initiated by the recipient, usually the web browser.

**TCP protocol (Transmission Control Protocol)**
- A communications standard that enables application programs and computing devices to exchange messages over a network.
- It is designed to send packets across the internet and ensure the successful delivery of data and messages over network.
- Connection oriented.

**UDP protocol (User Datagram Protocol)**
- is commonly used for applications that can handle some packet loss, such as streaming audio and video.
- Connectionless.

**DHCP protocol (Dynamic Host Configuration Protocol)**
Is a network management protocol used on Internet Protocol networks for automatically assigning IP addresses and other communication parameters to devices connected to the network using a client-server architecture.

**ARP (Address Resolution Protocol)**
- is a Layer 2 protocol used to map MAC addresses to IP addresses.
- All hosts on a network are located by their IP addresses, but NICS do not have IP addresses, they have MAC addresses.
- ARP is the protocol used to associate the IP address to a MAC address.

**IP address**
- Unique address that identifies a device on the internet
- IPV4 and IPV6
- Public and Private IP address
- Static and Dynamic IP address

**Ports**
- different applications or services use port number to communicate with each other.
- Ports are uniquely identified by 16 bit unsigned integer number, ranging from 0 to 65.535.
- any application on a computer that needs to communicate with another application in the same computer or other computer in the network will listen on a particular port number.

#### Types of attacks
**What is an attack?**
Actions taken through the use of computer networks to disrupt, deny, degrade, or destroy information resident in computers and computer networks.

**Types of attacks:** password attack; malware attack; man-in-the-middle attack; sniffing attack; DoS & DDoS attacks; phishing attack; SQL injection attack; cross-site scripting; port scanning.

**_Password attack -_** refers to any of the various methods used to maliciously authenticated into password-protected accounts.
There are dozens of password cracking programs in the market, each with their own special recipe, but they all basically do one of two things: create variations from a dictionary of known common passwords or attempt every possible combination using brute force.
These attacks are typically facilitated through the use of software that expedites cracking or guessing passwords.
- _Types of password attacks:_
	- Brute Force attacks
	- Dictionary attacks
	- Keylogger attacks

**_Malware attack -_** is when normally malicious software executes unauthorized actions on the victim's system. All an attacker needs to do is inject malware into the computer, which will then install itself without the user's knowledge. The malware will then record the data that is being sent between the victim and specifically targeted websites.

**Man-in-the-middle attack -** is a type of eavesdropping attack, where attackers interrupt an existing conversation or data transfer. After inserting themselves in the "middle" of the transfer, the attackers pretend to be legitimate participants. This can happen in any form of online communication, such as email, web browsing, social media, etc.

**Phishing attack -** is a type of social engineering where the hacker sends fraudulent emails, which appear to be coming from trusted source. It is done to install malware or to steal sensitive data like credit card information and login credentials.

**SQL Injection attack -** is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. To perform an SQL Injection attack, an attacker must locate a vulnerable input in a web application or webpage.
Malicious code is inserted into a SQL Server to obtain confidential information.

**Sniffing attack -** is a process of monitoring and capturing all data packets passing through a given network. Attackers use sniffers to capture data packets containing sensitive information such as passwords, account information, etc. Sniffers can be hardware or software installed on the system.

**Cross-site scripting (XSS) attack -** is a type of injection, in which malicious scripts are injected into trusted websites. An attacker will use a flaw in a target web application to send some kind of malicious code, most commonly client-side javascript, to an end user.
When the malicious code executes inside a victim's browser, the attacker can fully compromise their interaction with the application.

**Port scanning attack -** is a common technique that hackers use to discover open doors or weak points in a network. Port scanning is a popular method cyber criminals use to search for vulnerable servers. They often use it to discover organisations' security levels, determine whether businesses have effective firewalls, and detect vulnerable networks or servers.

**Dos attack -** a Denial-of-Service attack is an attack meant to shut down a machine or network, making it inaccessible to its intended users. DoS attacks accomplish this by flooding the target with traffic to exhaust its resources and bandwidth.

**DDoS attack -** a Distributed Denial of Service attack will send multiple requests to the attacked web resource - with the aim of exceeding the website's capacity to handle multiple request and prevent the website from functioning correctly.

#### Cryptography
**What is cryptology?**
Cryptology covers two related fields:
- _Cryptography:_ how to keep a message secure (develop ciphers that are unbreakable)
- _Cryptanalysis:_ how to break ciphers and cipher text.

**Cryptography in everyday life**
- Authentication/Digital signatures
- Electronic money/online banking
- email encryption
- secure chatting

**Symmetric key cryptography -** an encryption system in which the sender and receiver of a message share a single, common key that is used to encrypt and decrypt the message.

- _Advantages of symmetric key:_
	- easy to implement
	- faster than asymmetric
	- better performance
	- efficient for large amount of data

**Asymmetric key cryptography -** the encryption process where different keys are used for encrypting and decrypting the information. Keys are different but are mathematically related, such that retrieving the plain text by decrypting ciphertext is feasible.

- _Why Asymmetric?_
	- key sharing/exchange is the risk which will always exist with symmetric key cryptography.
	- Asymmetric key cryptography uses two different keys for encryption and decryption. The key used for encryption is the public key, and the key used for decryption is the private key.

**Hashing**
- scrambling data beyond recognition
- output is called hash value, and has a fixed size
- hashing is a mathematical operation that is easy to perform, but extremely difficult to reverse. (The difference between hashing and encryption is that encryption can be reversed, or decrypted, using a specific key).

**_Purpose of hash function_**
- ensure data integrity
- secure against unauthorized modifications
- protect stored passwords

**Substitution vs. Transposition**
In a _Substitution cipher_, characters of plain text are substituted/replaced by some other character or number or symbol depending on a key.
In _Transposition cipher_, order of the alphabets in the plaintext is rearranged to create the ciphertext. The actual plaintext alphabets are not replaced.

**_Advantages of Asymmetric Key cryptography_**
1. No need of sharing keys
2. Data can't be modified
3. Longer key lengths
4. Proof of owner's authenticity

**Digital signature -** is a mathematical technique used to validate the authenticity and integrity of a message, software or digital document.

#### Security measures
Computer and network security is a set of rules and configurations designed to protect the integrity, confidentiality and accessibility of computer networks and data using both software and hardware technologies.
A solid network security system helps reduce the risk of data loss, theft and sabotage.

**Firewall**
1. A Firewall is a network security device that sits between the trusted internal network and untrusted internet.
2. It monitors the network traffic entering and leaving the trusted network.
3. Allows or restricts data packets as per the well defined set of security rules.
_Types of Firewalls:_
	- Packet Filter firewall
	- Stateful Inspection firewall
	- Proxy Server firewall

#### Cyber Law
- Is the law governing Cyberspace.
- Cyberspace refers to the virtual computer world, and more specifically, an electronic medium that is used to facilitate online communication.

**Need of Cyber Law:
- To tackle cyber crimes
- successful and smooth functioning of E-commerce and virtual communication
- increased use of mobile and internet banking
- privacy protection
- safety of software and hardware products
- provides security against frauds

**Cyber Crime -** is any criminal activity that involves a computer, networked device or a network. It describes criminal activities committed through the use of electronic communication media.
_Classification of Cyber Crime:_
- cyber crimes against person: cyber stalking; hacking; carding; dissemination of obscene material; cracking; cheating and fraud; defamation; e-mail and SMS spoofing; assault by threat
- cyber crimes against person's property: intellectual property crimes; cyber squatting; cyber vandalism; transmitting virus; internet time thefts; cyber trespass.
- cyber crimes against government: cyber terrorism; cyber warfare; distribution of pirated software; possession of unauthorized information.
- cyber crimes against society at large: cyber trafficking; online gambling; financial crime; forgery.

#### Digital Forensics
**Digital Forensics -** is defined as the process of preservation, identification, extraction, and documentation of computer evidence which can be used by court of law.
It is a science of finding evidence from digital media like a computer, mobile phone, server, or network.
It provides the forensic team with the best techniques and tools to solve complicated digital-related cases.

_Digital Forensics:_
- refers to the investigation of a device, usually in a court of law, when a person is suspected of breaching data/information.
- Digital Forensics recovers information using complex tools in order to bring a person to justice for exploiting or tampering with private information.

_Types of Digital Forensics:_
1. Disk forensics
2. network forensics
3. database forensics
4. wireless forensics
5. malware forensics
6. email forensics
7. memory forensics
8. mobile phone forensics










