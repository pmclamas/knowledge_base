**What is a cyber attack?**

Cyber attacks are performed with malicious intent when a threat actor attempts to exploit a vulnerability or weakness in a system or individuals of an organization. These attacks threaten to steal, alter, destroy, disable or gain access to or make use of an unauthorized asset

Nearly all modern-day companies require a network of computers, servers, printers, switches, access points, and routers to operate. Unfortunately, while these devices and aplications provide a huge benefit to the company, they also represent a risk. All it takes is one employee to click a malicious link that then gain access to your network and infects your systems.

**How do you prevent cyber attacks?**

The first line of defense for any organization is to assess and implement security controls.

_Some of the most common ways to prevent cyber attacks include:_

-   developing cyber security policies
-   implementing security awareness training
-   installing spam filters and anti-malware software
-   deploying next-generation firewalls (NGFW)
-   installing endpoint detection & response (EDR)

Keep in mind that the list above is the bare minimum an organization needs to deter most common attacks.

_For advanced cyber attacks:_

-   performing vulnerability assessments
-   conducting routine penetration testing
-   implementing security information and event management (SIEM)
-   deploying intrusion detection & prevent software (IDS and IPS)
-   creating a data loss prevention (DLP) program.

Larger organizations with more mature cyber security programs will also often have dedicated Red Teams and Blue Teams that perform exercises to test the effectiveness of their IT security management systems.

Finally, the most robust security programs will have a continuous and real-time layer of defense such as a Security Operations Center (SOC), managed detection and response (MDR), or active threat hunting and analysis.

**What are the different types of cyber attacks?**

-   network security attacks
-   wireless security attacks
-   malware attacks
-   social engineering attacks

It’s important to note that no system is 100% vulnerability free or “hacker-proof”. If a threat actor has enough time, resources, and manpower to launch an attack then chances are they will find a way in.

**Network security attacks**

Network attacks are any attempts to exploit a vulnerability or weakness on a network or its systems including servers, firewalls, computers, routers, switches, printers, and more. The goal of a network attack can be to steal, modify, or remove access to valuable data. Or, it could be to bring down a network.

_**Types of network security attacks include:**_

-   _**Denial of Service (Dos) -**_ a malicious threat actor overloads a server with data preventing valid request coming from real clients on the network. The server uses resources (CPU/RAM) to process each requet, and when overloaded, the performance of the system can be slowed down to a crawl.
    
    A DoS attack can also be performed on entire networks because the attack is targeted at the central router or firewall. As a result, network bandwidth is compromised, which denies access to all systems on that network.
    
    You can prevent a denial of service attack by:
    
    -   buying more bandwidth
    -   building redundancy into your infrastructure
    -   deploying anti-DoS hardware and software modules
    -   deploying a DoS protection appliance
    -   protecting your DNS servers.
-   _**Distributed Denial of Service (DDoS) -**_ is an attack on a system that is launched from multiple sources and is intended to make a computer’s resources or services unavailable. DDoS attacks typically include sustained, abnormally high network traffic.
    
    You can prevent a DDoS attack by:
    
    -   developing a denial of service response plan.
    -   securing your network infrastructure.
    -   filtering routers at the edge of your network to spot DDoS connections.
    -   Blackholing the site that is being DDos, thereby directing all traffic to an invalid address.
-   _**Buffer overflow attacks -**_ in a buffer overflow attack, an application receives more input than it expects. As a result, the error exposes the system memory to a malicious threat. While a buffer overflow itself doesn’t cause damage, it does expose a vulnerability.
    
    Threat actors are then able to access memory locations beyond the application’s buffer, which enables them to write malicious code into this area of memory. When the application is executed the malicious code is launched.
    
    You can prevent a buffer overflow attack by:
    
    -   performing routine code auditing
    -   providing training including bounds checking, use of unsafe functions, and group standards.
    -   using compiler tools such as StackShield, StackGuard, and LibSafe.
    -   using safe functions such as strncat instead of strcat, strncpy instead of strcpy, etc.
    -   patching web and application servers regularly and be aware of bug reports relating to applications upon wich your code is dependent.
    -   periodically scan your application with one or more of the commonly available scanners that look for buffer overflow flaws in your server products and your custom web applications.
-   _**Ping attacks -**_ a ping attack is an attack designed to overwhelm or flood a targeted device with ICMP (Internet Control Message Protocol) pings. In normal situations, a ping is used to check connectivity between a source and a destination devices by way of ICMP echo-requests and echo-reply messages.
    
    A Ping attack on the other hand purposely floods the target device with requests packets.
    
    The destination device is forced to respond with an equal number of reply packets and eventually cannot keep up with the volume of requests. This causes the target to become inaccessible to normal traffic and unresponsive to normal ping requests.
    
    You can prevent a Ping attack by:
    
    -   configuring your firewall to block ICMP pings from entering your network at the perimeter.
    -   adding filters to tell your router to detect and drop malformed data packets or those coming from suspicious sources.
    -   looking for spoofed packets that do not originate from within your network, also known as egress filtering.
    -   installing network monitoring software to alert for traffic patterns that are not ordinary.
    -   scanning your network for open ports on a regular basis that is outside of your baseline.
-   **SYN Flood -** for every client and server connection using the TCP protocol, a required three-way handshake is established, which is a set of messages exchanged between the client and server.
    
    _The handshake process is listed below:_
    
    -   _the three-way handshake is initiated when the client system sends a SYN message to the server._
    -   _the server then receives the message and responds with a SYN-ACK message back to the client._
    -   _Finally, the client confirms the connection with a final ACK message._
    
    A SYN flood manipulates the handshake which allows the attacker to rapidly initiate a connection to a server without finalizing the connection.
    
    The server has to spend resources waiting for half-opened connections, which can consume enough resources to make the system unresponsive to legitimate traffic. The SYN flood is a form of a denial-of-service attack.
    
    You can prevent SYN flood attack by:
    
    -   installing an IPS to detect anomalous traffic patterns.
    -   if capability exists, configure the onsite firewall for SYN attack thresholds and SYN flood protection.
    -   installing up to date networking equipment that has rate-limiting capabilities.
    -   installing commercial tools to gain visibility across the entire network with the ability to see and analyze traffic from different parts of the network.
-   **DNS amplification -** a Domain Name Server (DNS) Amplification attack is a popular form of Distributed Denial of Service (DDoS), in which attackers use publically accessible open DNS servers to flood a target system with DNS response traffic.
    
    The primary technique consists of an attacker sending a DNS name lookup request to an open DNS server with the source address spoofed to be the target’s address.
    
    When the DNS server sends the DNS record response, it is sent instead to the target. Attackers will typically submit a request for as much zone information as possible to maximize the amplification effect.
    
    In most attacks of this type, the spoofed queries sent by the attacker are of the type “ANY”, which returns all known information about a DNS zone in a single request.
    
    Because the size of the response is considerably larger than the request, the attacker is able to increase the amount of traffic directed at the victim. By leveraging a botnet to produce a large number of spoofed DNS queries, an attacker can create an immense amount of traffic with little effort. Additionally, because the responses are legitimate data coming from valid servers, it is extremely difficult to prevent these types of attacks.
    
    You can prevent DNS Amplification attacks by:
    
    -   implementing source IP verification on network device.
    -   disabling recursion on Authoritative Name Servers.
    -   limiting recursion to authorized clients.
    -   implementing response rate limiting (RRL) setting on DNS Server.
-   **backdoor -** a backdoor is a malware type that negates normal authentication procedures to access a system. As a result, remote access is granted to resources within an application, such as databases and file servers, giving perpertrators the ability to remotely issue system commands and update malware.
    
    Backdoor installation is achieved by taking advantage of vulnerable components in a web application. Once installed, detection is difficult as files tend to be highly obfuscated.
    
    Webserver backdoors are used for a number of malicious activities, including:
    
    -   data theft
    -   website defacing
    -   server hijacking
    -   the launching of Distributed Denial of Service (DDoS) attacks.
    -   Infecting website visitors (watering hole attacks).
    -   Advanced persistent threat (APT) assaults.
    
    You can prevent backdoor attacks by:
    
    -   using an antivirus solution
    -   implementing a network monitoring tool
    -   implementing a solution to detect untrusted software on endpoints
    -   ensuring that every device is protected by a host firewall
-   **spoofing -** a spoofing attack occurs when a malicious party impersonates another device or user on a network in order to launch attacks against network hosts, steal data, spread malware or bypass access controls.
    
    There are several different types of spoofing attacks that malicious parties can use to accomplish this. Some of the most common methods include IP address spoofing attacks, ARP spoofing attacks and DNS server spoofing attacks.
    
    You can prevent a Spoofing attack by:
    
    -   packet filtering
    -   avoiding trust relationships with unknown entities
    -   implementing a spoofing detection software
    -   enabling cryptographic network protocols, such as Transport Layer Security (TLS), Secure Shell (SSH), HTTP Secure (HTTPS).
-   **Smurf attack -** is a form of DDoS attack that causes packet flood on the victim by exploiting/abusing ICMP protocol. When deployed, large packets are created using a technique called “spoofing”.
    
    The phony source address that is now attached to these packets becomes the victim, as their IP is flooded with traffic. The intended result is to slow down the target’s sytem to the point that it is inoperable and vulnerable.
    
    The Smurf DDoS attack took its name from an exploit tool called Smurf widely used back in the 1990s. The small ICMP packet generated by the tool causes big trouble for a victim, hence the name Smurf.
    
    Smurf attacks are an old technique but remain relevant due to the popularity of deployment and necessary preemptive prevention tactics.
    
    You can prevent a Smurf attack by:
    
    -   blocking directed broadcast traffic coming into the network
    -   configuring hosts and routers not to respond to ICMP echo requests
    -   deploying inline or scrubbing DDoS mitigation technology
    -   ingress filtering can be used to examine all packets that are moving inbound.
-   **tcp/ip hijacking -** is a cyber attack in which an authorized user gains access to a legitimate connection of another client in the network. Having hijacked the TCP/IP session, the attacker can read and modify transmitted data packets, as well as send their own requests to the addresses.
    
    The intruder can determine the IP addresses of the two-session participants, make one of them inaccessible using a DoS (Denial of Service) attack, and connect to the other by spoofing the network ID of the former.
    
    You can prevent TCP/IP hijacking by:
    
    -   using SSL when authenticating users or perfoming sensitive operations.
    -   regenerating the session ID whenever the security level changes (such as logging in). You can even regenerate the session ID every request if you wish.
    -   implementing session timeouts.
    -   storing authentication details on the server and do not send details such as username a cookie.
    -   locking down access to the sessions on the file system or use custom session handling.
-   **Man in the Middle attacks (MitM) -** is when an attacker intercepts communications between two parties either to secretly eavesdrop or modify traffic traveling between the two. Attackers might use MitM attacks to steal login credentials or personal information, spy on the victim, or sabotage communications or corrupt data.
    
    MitM attacks consist of sitting between the connection of two parties and either observing or manipulating traffic. This could be through interfering with legitimate networks or creating fake networks that the attacker controls. Compromised traffic is then stripped of any encryption in order to steal, change or reroute that traffic to the attacker’s destination of choice.
    
    You can prevent a MitM attack by:
    
    -   incorporating the latest version of encryption protocols such as TLS on infrastructure assets.
    -   Training staff not to use open public Wi-Fi or Wi-Fi offerings at public places where possible.
    -   Training staff to recognize browser warnings from sites or connections that may not be legitimate.
    -   Implementing VPNs to help ensure secure connections.
    -   Implementing multi-factor authentication.
-   **Replay attacks -** occurs when a cybercriminal eavesdrops on a secure network communication, intercepts it, and then fraudulently delays or resends it to misdirect the receiver into doing what the hacker wants.
    
    The attacker unwittingly deceives the participants into believing they have successfully completed the data transmission. Replay attacks help attackers to gain access to a network, gain information that would not have been easily accessible.
    
    You can prevent a Replay attack by:
    
    -   creating unique and random session keys between a sender and receiver’s communication.
    -   using digital signatures timestamps on all messages.
    -   ensuring a password for each transaction that’s only used once and discarded.
    -   implementing non-acceptance of duplicated messages.
-   **DNS poisoning -** also known as DNS cache poisoning or DNS spoofing, is a type of attack which uses security gaps in the Domain Name System (DNS) protocol to redirect internet traffic to malicious websites.
    
    DNS poisoning happens when a malicious actor intervenes in that process and supplies the wrong answer. These types of man in the middle attacks are often called DNS spoofing attacks because the malicious actor is in essence tricking the DNS server into thinking that it has found the authoritative name server, when in fact it hasn’t.
    
    Once it has tricked the browser or application into thinking that it received the right answer to its query, the malicious actor can feed back whatever fake website it wants back to the host device - usually web pages which look like the desired website but actually are there to collect valuable information like passwords, banking information, and the like.
    
    You can prevent DNS poisoning by:
    
    -   enabling DNSSEC on internal DNS servers.
    -   not letting your corporate DNS servers answer internet DNS queries.
    -   paying attention to DNS responses.
    -   disabling host file resolution on clients and servers.
    -   using DNS forwarders only to verified DNS servers.
-   **ARP poisoning -** also known as ARP Spoofing, is a type of cyber attack carried out over a Local Area Network (LAN) that involves sending malicious ARP packets to a default gateway on a LAN in order to change the pairings in its IP to MAC address table. ARP Protocol translates IP addresses into MAC addresses.
    
    The attack consists of an attacker sending a false ARP reply message to the default network gateway, informing it that his MAC address should be associated with his target’s IP address (and vice-versa, so his target’s MAC is now associated with the attacker’s IP address).
    
    Once the default gateway has received this message and broadcasts its changes to all other devices on the network, all of the target’s traffic to any other device on the network travels through the attacker’s computer, allowing the attacker to inspect or modify it before forwarding it to its real destination.
    
    You can prevent ARP Poisoning by:
    
    -   using static ARP entries.
    -   implement encryption on web traffic.
    -   implementing VPNs.
    -   enabling network firewall to filter out and block malicious packets.
-   **Typosquatting -** also known as URL hijacking, is a form of cybersquatting (sitting on sites under someone else’s brand or copyright) that targets internet users who incorrectly type a website address into their web browser.
    
    The typo squatted domain owner may redirect traffic to a different URL, show ads, or simply park the domain with the hope that the brand buys the domain from them.
    
    You can prevent typosquatting attacks by:
    
    -   trademarking your domain
    -   purchasing all related URL’s that could be easy misspellings.
    -   sending users to third-party from your official website.
    -   using an open-source tool like DNS Twist to automatically scan your company’s domain for any typosquatting attacks in progress.
    -   checking with your ISP to determine if they offer typosquatting protection as a service offering.
-   **Client side attacks -** require user-interaction usually initiating from a web browser to an internet website. The tactics used to invoke the attack are seamless to the end user, such as, enticing them to click a link, open a document, or somehow download malicious content.
    
    The flow of data is reversed compared to server-side attacks: client-side attacks initiate from the victim who downloads content from the attacker.
    
    You can prevent client-side attacks by:
    
    -   defining permissions for approved third-party vendors you choose to allow to access data - or block from receiving any specific types of data.
    -   auditing of new scripts.
    -   stopping injection-based attacks like form jacking.
    -   enforcing user data sanitization and input validation.
    -   comprehensive reporting of site traffic and real-time user activity to identify any suspicious patterns or network requests.
-   **Watering hole attacks -** a watering hole attack is a targeted attack. It is designed to compromise users within a specific industry or group of users by infecting websites they typically visit and luring them to a malicious site. The end goal is to infect the user’s computer and gain access to their organization’s network.
    
    Watering Hole attacks, also known as stategic website compromise attacks, are limited in scope as they rely on an element of luck. They do however become more effective, when combined with email prompts to lure users to websites.
    
    You can prevent Watering Hole attacks by:
    
    -   installing web gateways to defend the enterprise against opportunistic drive-by downloads.
    -   implementing an email security solution that filters outgoing and inbound email.
    -   creating and enforcing a Security Awareness training program.
    -   implementing a dynamic malware analysis.
-   **Zero Day attacks -** if a hacker manages to exploit the vulnerability before software developers can find a fix, that exploit becomes known as a zero-day attack.
    
    Zero-day vulnerabilities can take almost any form because they can manifest as any type of broader software vulnerability. For example, they could take the form of missing data encryption, SQL injection, buffer overflows, missing authorizations, broken algorithms, URL redirects, bugs, or problems with password security.
    
    This makes zero-day vulnerabilities difficult to proactively find - which in some ways is good news because it also means hackers will have a hard time finding them. But it also means it’s difficult to guard against these vulnerabilities effectively.
    
    You can prevent Zero-Day attacks by:
    
    -   staying informed by joining threat lists from established security organizations.
    -   implementing a WAF (Web Application Firewall) to monitor incoming traffic.
    -   Keeping your systems updated to the latest software and hardware patches.
    -   Monitoring inbound and outbound traffic for malicious traffic.
    -   Implementing an IPS solution.

**Wireless attacks**

A wireless attack involves identifying and examining the connections between all devices connected to the business’s wifi. These devices include laptops, tablets, smartphones, and any other Internet of Things (IoT) devices.

-   **Data emanation -** is a form of an attack whereby data is compromised by receiving the analog output from a device and transferring the by-product to another resource. The source of the attack can derive from emanations from the sound of keyboard clicks, light from LEDs, and reflected light.
    
    The electromagnetic field generated by a network cable or device can also be manipulated to eavesdrop on a conversation or to steal data.
    
    You can prevent Data Emanation attacks by:
    
    -   not placing access points near outside walls.
    -   conducting a site survey to identify the coverage area and optimal placement for wireless access points to prevent signals from going beyond identified boundaries.
    -   implement a Faraday cage to mitigate data emanation.
    -   encrypting all data transmitted through your access point.
    -   using firewalls on each network access point.
-   **Jamming -** is a type of Denial of Service (DoS) attack targeted to wireless networks. The attack happens when RF frequencies interfere with the operation of the wireless network. Normally jamming is not malicious and is caused by the presence of other wireless devices that operate in the same frequency as the wireless network.
    
    Hackers can perform Denial of Service (DoS) jamming attacks by analyzing the spectrum used by wireless networks and then transmitting a powerful signal to interfere with communication on the discovered frequencies.
    
    The main aim of a DoS attack is to direct malicious signals towards the sensor nodes’ communication channels to deplete their resources such as the battery life, bandwidth, and storage in order to prevent transmitted sensor data from reaching its destination, thereby affecting its long-term availability.
    
    You can prevent Jamming attacks by:
    
    -   implementing steganography
    -   implementing Cryptographic Puzzle hiding scheme.
    -   implementing Triple DES encryption.
    -   installing honeypots.
-   **Bluetooth vulnerabilities -** several attack methods target bluetooth devices specifically. These include:
    
    -   _**Bluejacking bluetooth attacks -**_ this is the practice of sending unsolicited messages to nearby bluetooth devices. Bluejacking messages are typically text, but can also be images or sounds. Bluejacking is relatively harmless but does cause some confusion when users start receiving messages.
    -   _**Bluesnarfing bluetooth attacks**_ - any unauthorized access to or theft of information from a bluetooth connection is bluesnarfing. A bluesnarfing attack can access information, such as email, contact lists, calendars, and text messages.
    -   _**Bluebugging bluetooth attacks -**_ allow an attacker to take over a mobile phone. Attackers can listen in on phone conversations, enable call forwarding, send messages, and more.
    
    You can prevent bluetooth vulnerability attacks by:
    
    -   enabling the “find my device” service on your phone through a trustworthy entity like Apple or Google so you have a way of using their technologies to find and remotely lock your phone if you lose it.
    -   Avoiding the use of bluetooth to communicate sensitive information like passwords.
    -   not leaving your bluetooth in “discoverable” mode when you’re pairing a new peripheral with your phone or laptop.
    -   turning bluetooth off when you’re not using it.
-   **Near-Field communication (NFC) -** NFC technology allows two devices placed within a few centimeters of each other to exchange data. In order for the technology to work, both devices must be equipped with an NFC chip. This technology is usually embedded in commuter cards, smart cards, and smartphones.
    
    The security attacks and risks that could occur in NFC are due to the physical nature of the NFC sensors and its operating mechanism which uses the insecure communication channel.
    
    NFC communication is susceptible to eavesdropping, ticket cloning, data corruption, data modification, data insertion, and Denial of Service (DoS) attacks.
    
    You can prevent NFC attacks by:
    
    -   turning off unused networking features
    -   monitoring NFC updates and patch your device promptly.
    -   limiting maximum latency.
    -   paying attention to the terminal when making a transaction.
-   War driving - is defined as the act of searching for WiFi wireless networks by a person, using a portable computing device. The term War Driving is derived from the 1980s phone hacking method known as war dialing.
    
    War dialing involves dialing all the phone numbers in a given sequence to search for modems. The War Driving gained popularity in 2001, because wireless network scanning tools became widely available.
    
    Recent wireless technology developments enable a network to extend far beyond the parking space of an office building. In some cases, a wireless network has the ability to span several miles. Now an attacker can stay far away from the building and still catch a strong signal from the network. A good war driving software package is NetStumbler.
    
    You can prevent War Driving attacks by:
    
    -   not broadcasting your SSID.
    -   changing the default factory SSID.
    -   changing the default password and secure it with a strong password.
    -   encrypting your wireless communication.
    -   filtering the MAC addresses that are allowed to connect to your router.
-   **Evil Twin -** is a hack attack in which a hacker sets up a fake Wi-Fi network that looks like a legitimate access point to steal victims’ sensitive details. The attack can be perfomed as a man-in-the-middle (MitM) attack.
    
    The fake Wi-Fi access point is used to eavesdrop on users and steal their login credentials or other sensitive information. Because the hacker owns the equipment being used, the victim will have no idea that the hacker might be intercepting things like bank transactions.
    
    An evil twin access point can also be used in a phishing scam. In this type of attack, victims will connect to the evil twin and will be lured to a phishing site. It will prompt them to enter their sensitive data, such as their login details. These, of course, will be sent straight to the hacker. Once the hacker gets them, they might simply disconnect the victim and show that the server is temporarily unavailable.
    
    You can prevent Evil Twin attacks by:
    
    -   not logging into any accounts on public Wi-Fi.
    -   Avoiding connecting to Wi-Fi hotspots that say ‘Unsecure’, even if it has a familiar name.
    -   Using 2FA for all your sensitive accounts. Learn to recognize social engineering attacks, phishing, and spoofed URLs.
    -   Only visiting HTTPs websites, especially when on open networks.
    -   using a VPN whenever you connect to a public hotspot.
    
    **Deauthentication and Disassociation -** a deauthentication attack is a type of denial of service attack that targets communication between a user and a Wi-Fi access point.
    
    Deauthentication frames fall under the category of the management frames. When a client wishes to disconnect from the AP, the client sends the deauthentication or disassociation frame. The AP also sends the deauthentication frame in the form of a reply. This is the normal process, but an attacker can take advantage of this process.
    
    The attacker can spoof the MAC address of the victim and send the deauth frame to the AP on behalf of the victim; because of this, the connection to the client is dropped. The aireplay-ng program i the best tool to accomplish a deauth attack.
    
    You can prevent Deauthentication and Disassociation attacks by:
    
    -   ensuring your network is using WPA2 encryption.
    -   creating a strong Wi-Fi passphrase.
    -   by recalling that once you have been disconnected from your network, make sure that you connect back to a WPA2 secure network and not an open one with the same name as yours.
    -   changing the default admin account of router that has Wi-Fi enabled.
-   **Packet sniffing and eavesdropping -** an eavesdropping attack, also known as a sniffing or snooping attack, is a theft of information as it is transmitted over a network by a computer, smartphone, or another connected device. The attack takes advantage of unsecured network communications to access data as it is being sent or received by its user.
    
    An eavesdropping attack can be difficult to detect because the network transmissions will appear to be operating normally.
    
    To be successful, an eavesdropping attack requires a weakened connection between a client and a server that the attacker can exploit to reroute network traffic. The attacker installs network monitoring software, the “packet sniffer”, on a computer or a server to intercept data as it is transmitted.
    
    You can prevent Packet Sniffing and Eavesdropping by:
    
    -   using a personal firewall
    -   keeping antivirus software updated
    -   using a virtual private network (VPN)
    -   using a strong password and changing it frequently
    -   ensure smartphone is running the most up to date version.
-   **Replay attacks (wireless) -** A simple, yet effective strategy for wireless DoS is to replay locally overheard data packets. These packets are then carried by other forwarding nodes resulting in increased levels of congestion on a wider scale. There are variations of the attack, where either control or data packets are replayed.
    
    The objective of the attacker is to make the packet to look like a legitimate unit avoiding at the same time detection. The intelligence of such an attack lies in convincing the MAC level recipient(s) of a packet to accept and forward it and, the final destination into believing that this was a legitimately retransmitted packet and that no attack is being launched.
    
    You can prevent Replay Attacks (wireless) by:
    
    -   placing the access points in separate virtual LANs and implement some type of intrusion detection to help identify when an attacker is attempting to set up a rogue access point or is using a brute force attack to gain access.
    -   encrypting all data transmitted through your access point.
    -   setting the access point to accept only MAC addresses.
    -   using firewalls on each network access point.
    -   disabling the broadcasting of the SSID from all access points.
    -   implementing EAP-TLS to use different keys for encryption and broadcast traffic.
    -   setting up a RADIUS server and a certificate authority.
-   **WPS (Wi-Fi Protected Setup) attacks -** is a wireless standard that enables simple connectivity to “secure” wireless APs. The problem with WPS is that its implementation of registrar PINs make it easy to connect to wireless and can facilitate attacks on the very WPA/WPA2 pre-shared keys used to lock down the overall system.
    
    The WPS attack is relatively straightforward using an open source tool called Reaver. Reaver works by executing a brute-force attack against the WPS PIN.
    
    You can prevent WPS attacks by:
    
    -   implementing tools to detect rogue Wireless Access Points (WAPs)
    -   Disabling WPS
    -   Setting up MAC address controls on your access points
    -   Ensure wireless router is capable of WPS intruder lockout for the WPS PIN.
-   **WEP/WPA attacks -** WEP (Wired Equivalent Privacy), was implemented in 1995 to provide the same expectation of privacy as on wired networks for users of Wi-Fi but had security problems that came to light shortly afterwards. It was deprecated in 2004, superseded by the WPA and WPA2 encryption that you see today.
    
    The reason for this was a series of increasingly devastating attacks against the encryption used in WEP, resulting in the ability to recover the password in a matter of minutes.
    
    WEP is a stream cipher which relies on never using the same key twice to provide security. Unfortunately, as demonstrated in several published attacks, an attacker is easily able to force the same key to be used twice by replaying network traffic in a way that forces a tremendous amount of packets to be generated.
    
    This allows an attacker to collect the data needed to determine the encryption key and crack the network password outright. With good range and a powerful network adapter, anyone can expect to crack WEP networks in only a few minutes.
    
    Unfortunately, WPA (Wi-Fi Protected Access) is susceptible to password-cracking attacks, especially when the network is using a weak PSK or passphrase.
    
    You can prevent WEP/WPA attacks by:
    
    -   changing the default SSIDs and passwords.
    -   Updating the firmware of Wi-Fi enabled devices, routers, and other hardware as soon as updates are available.
    -   Enabling the firewall for added security in devices, or using a virtual private network (VPN) especially when remotely accessing assets.
    -   Raising company awareness on the risks related to unsecure connections and the use of wireless networks at work as weall as at home.
    -   employing network monitoring to oversee connected devices and web traffic.
    -   regularly reviewing device logs and monitoring results for any suspicious activity.
    -   using authentication tools, such as two-factor authentication.
-   **IV attack -** also known as an Initialization Vector attack. This is a kind of wireless network attack that can be quite a threat to one’s network. This is because it causes some modifications on the Initialization Vector of a wireless packet that is encrypted during transmission.
    
    After such an attack, the attacker can obtain much information about the plaintext of a single packet and generate another encryption key which he can use to decrypt other packets using the same Initialization Vector. With that kind of decryption key, attackers can use it to come up with a decryption table which they and use to decrypt every packet being sent across the network.
    
    You can prevent IV Attacks by:
    
    -   getting rid of the encrypted nonce.
    -   initializing a complete block sized 128 bit random value as IV for the packet data encryption.
    -   Encrypting IV separately as a single block.
    -   Adding a 16 bit field for the packet length before encrypting the packet.
-   **TKIP attack -** TKIP was introduced in 2003, amongst other enhancements, including a new per-packet hashing algorithm, the Message Integrity Check (MIC). MIC is based on a weak algorithm, designed to be accommodated on legacy WEP hardware.
    
    TKIP uses MIC for guaranteeing the integrity of an encrypted frame. If more than two MIC failures are observed in a 60 second window, both the Access Point (AP) and client station shut down for 60 seconds. The new TKIP attack uses a mechanism similar to the WEP attack to decode one byte at a time by using multiple replays and observing the response over the air.
    
    When a MIC failure occurs, the attacker can observe the response and waits for 60 seconds to avoid MIC countermeasures. Using the mechanism, the attacker can decode a packet at the rate of one byte per minute. Small packets like ARP frames can typically be decoded in about 15 minutes by leveraging this exploit.
    
    You can prevent TKIP attacks by:
    
    -   changing the default Admin password on your Access Point.
    -   updating the firmware for your Wireless Access Point and drivers for your Wireless Adapter.
    -   using the highest level of WEP/WPA.
    -   authenticating wireless users with protocols like 802.1X, RADIUS, EAP.
    -   using strong encryption for all applications you use over the wireless network (e.g., SSH and TLS/HTTPS).
    -   encrypting wireless traffic using a VPN.
-   **WPA2 attacks -** WPA2 is a type of encryption used to secure the vast majority of Wi-Fi networks. A WPA2 networks provides unique encryption keys for each wireless client that connects to it.
    
    In 2017 an attack method called KRACK (Key Reinstallation AttaCK) was discovered to break WPA2 encryption, allowing a hacker to read information passing between a device and its wireless access point. This technique used a variation of a common - and usually highly detectable - man-in-the-middle attack.
    
    The vulnerability could potentially allow a hacker to spy on your data as well as gain access to unsecured devices sharing the same Wi-Fi network.
    
    In some instances, attackers could also have the ability to manipulate web pages, turning them into fake websites to collect your information or to install malware on your devices.
    
    You can prevent WPA2 attacks by:
    
    -   ensuring that Wi-Fi-enabled devices are updated as soon as a software update is made available.
    -   ensuring wireless router is running up to date firmware.
    -   implementing a reputable VPN solution on all mobile and computers before connecting to Wi-Fi.
    -   browsing to only HTTPS URLs when surfing the web over Wi-Fi connection.
    
    **Malware & Ransomware Attacks**
    
    Malware, or malicious software, is any piece of software that was written with the intent of doing harm to data, devices or to people.
    
    Systems infected with malware will present with symptoms such as running slower, sending emails without user action, randomly rebooting, or starting unknown processes.
    
    **Ransomware / Crypto-Malware**
    
    Ransomware is a type of malware designed to lock users out of their system or deny access to data until a ransom is paid.
    
    Crypto-Malware is a type of ransomware that encrypts user files and requires payment within a time frame and often through a digital currency like Bitcoin.
    
    **Viruses**
    
    A virus is the most common type of malware attack. In order for a virus to infect a system it requires a user to click or copy it ot media or a host.
    
    Most viruses self-replicate without the knowledge of the user. These viruses can be spread from one system to another via email, instant messaging, website downloads, removable media (USB), and network connections.
    
    Some file types are more susceptible to virus infections. Viruses typically remain dormant until it has spread on to a network or a number of devices before delivering the payload.
    
    **Keyloggers**
    
    Keylogging, or keyboard capturing, logs a user’s keystrokes and sends data to the threat actor. Users are typically unaware that their actions are being monitored.
    
    While there are use cases for employers using keyloggers to track employee activity, they’re mostly used to steal passwords or sensitive data.
    
    Keyloggers can be a physical wire discreetly connected to a peripheral like a keyboard, or installed by a Trojan.
    
    **Worms**
    
    Similar to a virus, a worm can also self-replicate and spread full copies and segments of itself via network connections, email attachments, and instant messages.
    
    Unlike viruses, however, a worm does not require a host program in order to run, self-replicate, and propagate.
    
    Worms are commonly used against email servers, web servers, and database servers.
    
    Once infected, worms spread quickly over the internet and computer networks.
    
    **Trojan Horses**
    
    Trojan horse programs are malware that is disguised as legitimate software.
    
    A Trojan horse program will hide on your computer until it’s called upon.
    
    When activated, Trojans can allow threat actors to spy on you, steal your sensitive data, and gain backdoor access to your system.
    
    Trojans are commonly downloaded through email attachments, website downloads, and instant messages.
    
    Social engineering tactics are typically deployed to trick users into loading and executing Trojans on their systems. Unlike computer viruses and worms, Trojans are not able to self-replicate.
    
    **Social Engineering attacks**
    
    Social Engineering is the attempt to manipulate a user into giving up sensitive information such as user account credentials, wiring funds, or personal customer information.
    
    This form of cyber attack is one of the most popular for deploying malicious code on to a network.
    
    1.  **Phishing attacks -** phishing refers to an attack that is usually sent in the form of a link embedded within an email. The email is disguised and looks like an email from a reliable source, but in reality, it’s a link to a malicious site.
        
    2.  **Vishing -** vishing is a social engineering attack that attempts to trick victims into giving up sensitive information over the phone. In most cases, the attacker strategically manipulates human emotions, such as fear, sympathy, and greed in order to accomplish their goals.
        
        This form of attack has become increasingly prevalent in part due to the upward trend in the amount of people working remotely today.
        
    3.  **Smishing -** is a cyber attack that uses SMS text messages to mislead its victims into providing sensitive information to a cybercriminal.
        
        Sensitive information includes your account name and password, name, banking account or credit card numbers. The cybercriminal may also embed a short url link into the text message, inviting the user to click on the link which in most cases is a redirect to a malicious site.
        
    4.  **Pretexting -** an attacker can impersonate an external IT services operator to ask internal staff for information that could allow accessing system within the organization.
        
    5.  **Whaling attacks -** whaling adopts the same methods of spear phishing attacks, but the scam email is designed to masquerade as a critical business email sent from a legitimate authority, typically from relevant and important organizations.
        
        The word whaling is used, indicating that the target is a big fish to capture.
        
    6.  Tailgating - the tailgating attack, also known as “piggybacking”, involves an attacker seeking entry to a restricted area that lacks the proper authentication.
        
        The attacker can simply walk in behind a person who is authorized to access the area.
        
        In a typical attack scenario, a person impersonates a delivery driver or a caretaker who is packed with parcels and waits when an employee opens their door.