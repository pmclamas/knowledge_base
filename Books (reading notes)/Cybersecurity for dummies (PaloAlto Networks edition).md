**About this book**

This book provides an in-depth examination of real-world attacks and APTs (Advanced Persistent Threats), the shortcomings of legacy security solutions, the capabilities of next-generation firewalls, and security best practices.

**Introduction**

APTs have changed the world of enterprise security and how networks and organizations are attacked. These treats, and the cyber-criminals behind them, are experts at remaining hidden from traditional security while exhibiting an intelligence, resiliency, and patience that has never been seen before. Controlling these threats requires multiple security disciplines working together in context. While no single solution will solve the problem of advanced threats on its own, next-generation security provides the unique visibility and control of, and the true integration of, threat-prevention disciplines needed to find and stop these threats - both known and unknown.

**Chapter 1 - Understanding the cybersecurity landscape**

Today's cybercriminals are highly motivated professionals - often well-funded by criminal organizations or nation-states - who are patient and persistent in their efforts to break through an organization's defenses.

Today's attacker fits the following profile:

-   has far more resources available to facilitate an attack
-   has greater technical depth and focus
-   is well funded
-   is better organized

Not only do we face more sophisticated adversaries today, but the types of information of value to them are continually expanding as well.

**The Lifecycle of an Advanced Attack**

Instead of a traditional, direct attack against a high-value server or asset, today's strategy employs a patient, multi-step process that blends exploits, malware, and evasion into an ongoing coordinated network attack.

As an example, an attack often begins by simply luring an individual into clicking on an infected link. The resulting page remotely exploits the individual, gains root access on the user's computer, and downloads malware to the user's computer in the background. The malware then acts as a control point inside the network, allowing the attacker to further expand the attack by finding other assets in the internal network, escalating privileges on the infected machine, and/or creating unauthorized administrative accounts - just to name a few tactics.

The key is that instead of malware and network exploits being separate disciplines as they were in the past, they are now integrated into an ongoing process. Furthermore, malware or an exploit is not an end unto itself, but simply enables the next step of an increasingly complex attack plan. Malware, which is increasingly customized to avoid detection, provides a remote attacker with a mechanism of persistence, and the network enables the malware to adapt and react to the environment it has infected. Key components of the advanced attack strategy include infection, persistence, communication, and command and control.

**Infection**

Infection often has a social aspect, such as getting users to click on a bad link in a phishing e-mail, luring them to a social networking site, or sending them to a web page with an infected image, for example. Understanding how malware and exploits have become closely interrelated in the advanced attack lifecycle is important. Exploits used to be directed at vulnerabilities on servers that were directly targeted. Most exploits today are used to crack a target system to infect it with malware: an exploit is run, causing a buffer overflow, which allows the attacker to gain shell access.
![[Screenshot 2022-03-10 at 09.19.59.png]]

With shell access, the attacker can deliver pretty much any payload. The first step is to exploit the target, then deliver the malware in the background through the application or connection that is alredy open. This is known as "drive-by-download" and is far and away the most common delivery mechanism for advanced malware today.

Infection relies heavily on hiding from and evading traditional security solutions. Targeted attacks will often develop new and unique malware that is customized specifically for the target network. This technique allows the attacker to send in malware knowing that it is unlikely to be detected by traditional antivirus tools. Another common way to avoid security is to infect the user over a connection that security can't see into, such as an encrypted channel. Attack transmissions are often obscured in SSL-encrypted (Secure Sockets Layer) traffic or other proprietary encryption used in P2P (peer-to-peer) networking applications and IM (Instant Messaging), for example.

The trend today is that threats do not necessarily come as an executable attachment in an e-mail. A link is all that is required. This is why social media, webmail, message boards, and microblogging platforms such as Twitter are rapidly becoming favorite infection vectors for attackers.

**Persistence**

Once a target machine is infected, the attacker needs to ensure persistence (the resilience or survivability of his foothold in the network). Rootkits and bootkits are commonly installed on compromised machines for this purpose. A rootkit is malware that provides privileged (root-level) access to a computer. A bootkit is a kernel-mode variant of a rootkit, commonly used to attack computers that are protected by full-disk encryption.

Backdoors enable an attacker to bypass normal authentication procedures to gain access to a compromised system. Backdoors are often installed as failover in case other malware is detected and removed from the system.

Anti-AV malware may be installed to disable any legitimately installed antivirus software on the compromised machine, thereby preventing automatic detection and removal of malware that is subsequently installed by the attacker. Many anti-AV programs work by infecting the Master Boot Record (MBR) of a target machine.

**Communication**

Attackers must be able to communicate with other infected systems or controllers to enable command and control, and to extract stolen data from a target system or network.

Attack communications must be stealthy and cannot raise any suspicion on the network. Such traffic is usually obfuscated or hidden through techniques that include:

-   Encryption with SSL, SSH (secure shell), or some other custom application. Proprietary encryption is also commonly used. For example, BitTorrent is known for its use of proprietary encryption and is a favorite attack tool - both for infection and ongoing command and control.
    
-   Circumvention via proxies, remote desktop access tools, or by tunneling applications within other (allowed) applications or protocols.
    
-   Port evasion using network anonymizers or port hopping to tunnel over open ports. For example, botnets are notorious for sending command-and-control instructions over IRC (Internet Relay Chat) on nonstandard ports.
    
-   Fast Flux (or Dynamic DNS) to proxy through multiple infected hosts, reroute traffic, and make it extremely difficult for forensic teams to figure out where the traffic is really going.
    
    **Command and Control**
    

Command and Control rides on top of the communication platform that is established but is really about making sure that the attack is controllable, manageable, and updateable.

Command and Control is often accomplished through common applications including webmail, social media, P2P networks, blogs, and message boards. Command & Control traffic doesn't stand out or raise suspicion, is often encrypted, and frequently makes use of backdoors and proxies.

**The Central Role of Malware**

Attackers have developed new methods for delivering malware (such as drive-by-downloads), hiding malware communications (with encryption), and avoiding traditional signature-based detection.

To understand, control, and successfully counter advanced threats, we need to focus on not just the malware, but on all the moving parts.

**Key security lessons and opportunities**

For all their sophistication, advanced attacks exhibit some vulnerabilities of their own. Some key observations and opportunities to consider include:

-   _**Communication is the life-blood of an attack.**_ Today's threats are networked threats that need your network to communicate. If a threat can't communicate, the attack can be largely neutralized.
-   _**Numerous opportunities exist to detect and correlate.**_ By virtue of the fact that multiple steps are involved in the advanced attack lifecycle, there are multiple chances to identify and counter threats.
-   _**The framework, rather than the functionality, is the threat.**_ If an attacker can infect targets, persist on, communicate with, and manage infected hosts, then the attacker can do almost anything. See the threat as an extensible framework, not simply as the functionality of the specific payload.
-   _**Threats exist across multiple disciplines, so too must security.**_ Firewalls, intrusion prevention, antivirus, content filterting - these security solutions have traditionally been separated to provide "defense in depth". But this strategy makes it difficult - if not impossible - to identify, correlate, and counter complex, coordinated attacks that take advantage of multiple attack vectors, including:
    -   _Applications:_ can hide and enable threats.
    -   _URLs and websites:_ can host and enable threats.
    -   _Exploits:_ create shell access to the target.
    -   _Malware:_ controls and uses the compromised target.
    -   _Files:_ used to update malware and steal data.
-   _**Security must expand beyond the perimeter.**_ Organizations need to focus on expanding visibility beyond the network perimeter - both inward and outward. This is best accomplished with network segmentation and a next-generation firewall to enforce central controls on internal and external (such as remote and mobile access) network traffic.

**Chapter 2 - The role of malware in Advanced Persistent Threats (APTs)**

Some malware has the ability to mutate or can be updated to avoid detection by traditional malware signatures. Additionally, advanced malware is increasingly specialized to the point where the attacker will develop a customized piece of malware that is targeted against a specific individual or network.

Botnets are a particularly useful example for understanding some of the unique characteristics of advanced malware. Bots (individual infected machines) and botnets (the broader network of bots working together) are notoriously difficult for traditional antivirus/anti-malware solutions to detect. Bots leverage networks to gain power and resilience. A bot under the remote control of a human attacker (or bot-herder) can be updated so that the attacker can change course and dig deeper into the network, based on what he finds or to adapt to changes and contermeasures.

Botnets - and a great deal of advanced malware - are centrally coordinated, networked applications in a very real sense. All malware of the same type can work together toward a common goal, with each infected machine growing the power and value of the overall botnet. The botnet can evolve to pursue new goals or adapt to changes in security measures.
![[Screenshot 2022-03-10 at 09.21.07.png]]

**Distributed and fault-tolerant**

Advanced malware takes full advantage of the resiliency built in to the Internet itself. A botnet can have multiple control servers distributed all over the world, with multiple fallback options. Bots can also potentially leverage other infected bots as communication channels, providing them with a near infinite number of communication paths to adapt to changing access options or update their code as needed.

**Multifunctional**

Updates from the command-and-control servers can also completely change the bots functionality. For example, portions of the botnet can be used for a particular task such as collecting credit card numbers, while other segments of the botnet might be sending spam. The important point is that the infection is the most important step, because the functionality can always be changed later as needed.

**Persistent and intelligent**

Because bots are both hard to detect and can easily change function, they are particularly well-suited for targeted and long-term intrusions into a network. Since bots are under the control of a remote human bot-herder, a botnet is more like having a cybercriminal inside your network as opposed to a malicious executable program. For example, a bot can be used to learn more about the organization of the network, find targets to exploit, and install additional backdoors into the network in case the bot is ever discovered.

### Threats to the Enterprise

Given their flexibility and ability to evade defenses, botnets present an enormous threat to the enterprise. Advanced malware is virtually unlimited in terms of functionality - from sending spam to the theft of classified information and trade secrets. The ultimate impact of malware is largely left up to the attacker: a bot that was sending spam one day could be stealing credit card data the next.

**Targeted intrusions**

Botnets are also a key component of targeted, sophisticated, and ongoing attacks. These smaller botnets aim to compromise specific high-value systems that can be used to further penetrate and intrude into the target network. In these cases, an infected machine can be used to gain access to protected systems and to establish a backdoor into the network in case any part of the intrusion is discovered.

They represent one of the most dangerous threats to the enterprise because they specifically target the organization's most valuable information, such as research and development, intellectual property, strategic planning, financial data, and customer information.

**DDoS and botnets**

A slight twist on the spamming botnet model uses bots as part of a distributed denial-of-service attack (DDoS) - overwhelming a target server or network with traffic from a larger number of infected endpoints. In such cases, the organization with the infected machine(s) is often not the target of the attack itself. Instead, the infected machine(s) is used to flood some other remote target with traffic. The bot-herder leverages the massive scale of the botnet to generate traffic that overwhelms the network and server resources of the target. DDoS attacks often target specific companies for personal or political reasons, or to extort payment from the target in return for stopping the DDos attack.

DDoS botnets represent a dual risk for the organization. The enterprise itself can potentially be the target of a DDoS attack, resulting in downtime and lost productivity. Even if the enterprise is not the ultimate target, any infected machines participating in the attack will consume valuable network resources.

**Botnets: attack or defend?**

The goal is to separate the bots (the infected machines) from their brain (the command-and-control servers). If the bots can't get to their servers, they can't get new instructions, upload data, or do any of the things that make botnets so dangerous. The most obvious limitation to this approach is that it is incredibly time and resource intensive.

Your security team needs to be more narrowly focused on such things as preventing infections, finding machines that are infected, and limiting the scope of any damage.

**Analyzing the indestructible Botnet: TDL-4**

TDL-4 is primarly spread through affiliates - often pornographic, piracy, and video/file sharing websites.

Persistence is achieved through installation of a bootkit that infects the Master Boot Record (MBR) of the victim machine, and more than 20 additional malware programs, including fake antivirus programs, adware, and a spamming bot. Very cleverly, TDL-4 actually removes approximately 20 common malware programs - such as Gbot and ZeuS - to avoid drawing unwanted attention to a victim computer when legitimately installed antivirus software detects these common malware programs on the computer.

Communications are concealed using proprietary encryption that is tunneled within SSL. TDL-4 can also install a proxy server on an infected machine, which can then be rented out as an anonymous browsing service that proxies traffic through numerous infected machines.

For command and control, TDL-4 uses the Kad P2P network, a publicly accessible P2P file exchange network. TDL-4 updates and distributes information about infected machines over the Kad network, so that even if a command-and-control server is taken down, other infected bots can be found to maintain the botnet - without command-and-control servers.

To detect and stop these threats, security teams need to regain full visibility into network traffic, reduce the exposure of the network and user, and establish new techniques to detect and prevent advanced malware.

**Chapter 3 - Why traditional security solutions fail to control APTs**

**The rapidly expanding attack surface**

In the past, exploits targeted servers and malware was delivered to end-users through e-mail. These threats were largely independent and were handled in different ways. Today, exploits also target end-users and work with a number of applications to deliver malware to users in unexpected ways. The applications include:

-   file transfer apps
-   instant messaging
-   webmail
-   social media platforms
-   microblogging
-   workflow and collaboration applications

To make matters worse, these applications often operate on a real-time model.

**A lack of visibility**

In order to maximize their accessibility and use, many applications are designed from the outset to circumvent traditional port-based firewalls by dynamically adjusting how they communicate - often bringing malware along for the ride. Simply stated, you can't control threats that you can't see, and APTs use a variety of tricks to hide their true nature or existence on the network, including:

-   _**Nonstandard ports and port hopping.**_ Evasive applications are one of the key factors leading to the demise of traditional port based firewalls. However, traditional IPS and threat products also rely heavily on port to determine which signatures or analysis to apply to the traffic. This weakness is magnified by the fact that APTs are often communicated from the inside of an infected network back to the remote attacker outside. This gives the attacker full flexibility to use any port, protocol, and encryption that he wants - fully subverting any port-based controls in the process.
-   _**SSL encryption.**_ Malware creators rely heavily on various forms of encryption to hide the infection of traffic, as well as the ongoing command-and-control traffic associated with botnets. SSL is a favorite, simply because it has become a default protocol. As a result of SSL encryption, many IT security teams lack the ability to see malware traffic on their network. Other types of encryption have also become popular for hiding malware traffic. P2P applications provide both infection and command-and-control capabilities, and often use proprietary encryption, again allowing malicious content to pass through the traditional network perimeter undetected.
-   _**Tunneling.**_ Many applications and protocols support the ability to tunnel other applications and protocols within them. This lets attackers disguise their communications as allowed services or applications to get past traditional perimeter security solutions.
-   _**Proxies.**_ Advanced malware and hackers use proxies to traverse traditional firewalls. TDL-4 installs a proxy server on every host that it infects. This allows the bot to not only protect its own communications, but also to establish an anonymous network that anyone can use to hide his tracks while hacking or conducting other illegal activities.
-   _**Anonymizers and circumventors.**_ Tools such as UltraSurf, Tor, and Hamachi are purpose-built to avoid network security controls. Circumventors have almost no legitimate use in an enterprise network. These applications are updated on a weekly/monthly basis to avoid detection in a perpetual cat-and-mouse game with traditional security solutions.
-   _**Encoding and obfuscation.**_ Malware almost always encodes transmissions in unique ways. Encoding and obfuscation not only help them avoid detection signatures, but also hide the true goal of the malware. This technique can be as simple as converting strings to hexadecimal, or as sophisticated as developing custom algorithms for detailed translations.
![[Screenshot 2022-03-10 at 09.22.16.png]]

**Signature Avoidance**

The traditional approach to detecting and blocking malware is based on the simple notion of collecting samples of malware and then writing a signature for that sample. Even at its best, this approach has several drawbacks simply due to the reactive nature of the strategy.

By design, protection can't be delivered until the malware is already "in the wild", during which time networks are blind to the threat. This means that some users and networks will be successfully breached by new malware until a new detection signature is created and downloaded. This reactive model creates a window of opportunity for attackers, leaving enterprise networks vulnerable until new malware is suspected, collected, analyzed, and identified.

Advanced malware has taken this weakness and expanded upon it by evolving techniques to avoid being captured in the wild and to avoid the signatures that have already been created. Targeted malware and polymorphism, are increasingly common techniques used to exploit the inherent weaknesses of signature-based detection.

**Targeted Malware**

Before malware became a networked threat, the main goal was often to replicate and spread the malware as widely as possible. In fact, this is how the security industry ranked malware for many years - how many machines could the malware infect in a certain period of time. This widespread replication made new malware samples readily available and relatively easy to collect.

Advanced malware has changed that model, however. Advanced malware is more intelligent and highly networked, which enables an attacker to remotely control the target user or users.

In such cases, attackers have increasingly turned to highly targeted malware. These types of malware are often specifically designed for a particular user or network.

This approach accomplishes two very important things. First, it makes it extremely unlikely that a sample of the malware will be captured in the wild, since there are only a few samples instead of millions to be caught. Second, it is designed to avoid infecting networks that are not the intended target, and thereby avoids drawing unwanted attention to itself. This targeted approach is rapidly becoming a hallmark of some of the world's most sophisticated network attacks targeting intellectual property.

**Polymorphism**

Polymorphism has been used by malware for some time, but continues to be popular today. This approach aims to avoid signatures by regularly mutating to avoid simple signature matches. Some malware applications have entire sections of code that serve no purpose other than to change the signature of the malware.

**Traditional network controls are ineffective**

Traditional network security solutions simply were never designed to meet the challenges of advanced malware.

Traditional firewalls and IPS solutions classify traffic, a firewall allows or blocks traffic, and an IPS determines which signatures to apply, all based on port. As a result, a threat that is evasive and dynamic, such as advanced malware, can simply bounce to an unexpected port, gain access to the network, and avoid detection.

**Firewalls**

Port-based firewalls are often used as a first line of defense, providing coarse filtering of traffic and segmenting the network into different password-protected zones. One drawback to port-based firewalls is that they use protocol and port to identify and control what gets in and out of the network. This port-centric design is ineffective when faced with malware and evasive applications that hop from port to port until they find and open connection to the network. Such firewalls themselves have little ability to identify and control malware.

**Intrusion prevention**

IPS provide a step in the right direction, in that they look much deeper into the traffic than a firewall does. However, IPS solutions typically don't run a complete set of IPS signatures against all traffic. Rather, the IPS attempts to apply the appropriate signatures to specific types of traffic, based on port. This limitation means that malware or exploits on unexpected or nonstandard ports are likely to be missed. Additionally, IPS solutions lack the depth of malware detection needed to protect networks, most IPS solutions only look for a few hundred types of common malware.

**Proxies**

Proxy solutions are another means of network traffic control. But they too look at a limited set of applications or protocols and only see a partial set of the network traffic that needs to be monitored. By design, proxies need to mimic the applications they are trying to control so they struggle with updates to existing applications and new applications. As a result, although proxies understand a few protocols in depth, they typically lack the breadth of protocol support needed to control the tunnels and protocols within protocols that hackers use to hide their true traffic. A final issue that plagues proxy solutions is throughput performance, caused by the manner in which a proxy terminates an application on the proxy and then forwards it on to its destination.

**Important notes:**

_The challenge with any of these network controls is that they do not have the ability to accurately identify applications and malware; they look at only a portion of the traffic and suffer from performance issues._

_Security policies must be based on the identity of users and the applications in use, not just on IP addresses, ports, and protocols. Without knowing and controlling exactly who (users) and what (applications and content) have access to the network, enterprise networks may be compromised by applications and malware that can easily bypass port-based network controls._

Over the years, enterprises have tried to compensate for the inherent deficiencies in port-based firewalls by implementing a range of supplementary security devices, such as host-based solutions and standalone appliances.

**Network vs. host-based approaches**

Traditionally, enterprises have focused most of their anti-malware time and resources at the end-users' desktops, typically in the form of host antivirus, personal firewalls, etc. However, as malware evolves from individually infected endpoints to coordinated malware networks, enterprises need to expand their security perspective to incorporate network-level intelligence and controls to complement end-point security measures. Network security has the unique advantage of allowing you to focus on the very trait that distinguishes botnets from earlier forms of malware - its reliance on communication with a larger bot network. The threat itself has become a network.

Additionally, network security mechanisms provide an independent layer of monitoring and control, unlike the endpoints themselves, which can be compromised by malware. Botnets and advanced malware can include rootkits that gain root-level access to subvert antivirus protections or other security mechanisms on the target machine. Blended threats against both the host and the network will likewise demand a security response that leverages the unique strengths of both the host and network security measures.

**Integrating multi-disciplinary solutions**

Stopping APTs and cyberattacks requires an integrated, multi-disciplinary approach to detect malicious traffic, correlate events, and respond accordingly in the enterprise network.

Many organizations have deployed various security solutions in addition to their legacy port-based firewalls, including Intrusion Prevention Systems (IPS), proxy servers, web-content filtering, antivirus gateways, and application-specific solutions - such as instant messaging or e-mail security (anti-spam) appliances - in an effort to shore up their defenses against advanced malware threats.

However, this approach to security infrastructure creates problems of its own, such as:

-   not everything that should be inspected actually is, because these solutions either can't see all of the traffic or rely on the same port - and protocol-based classification scheme as port-based firewalls.
-   Information is not easily correlated, and the all-important context between events is lost due to security solutions being separated into their specialized silos.
-   Policy management, access control rules, and inspection requirements are spread across multiple devices and consoles, making it difficult to develop and enforce a consistent enterprise security policy.
-   Performance suffers due to relatively high aggregate latency because the same traffic is scanned and analyzed on multiple devices.

Warning: more security appliances don't necessarily mean a more secure environment. In fact, the complexity and inconsistency associated with such an approach can actually be a detriment to your organization's security. How? By overwhelming your security team with data from multiple sources that cannot be easily correlated and analyzed.

**Chapter 4 - What next-generation security brings to the fight**

**Introducing the next-generation firewall**

By understanding the full stack behaviour of all traffic on the network, you can finely control the behaviours that are allowed in the corporate environment and eliminate the shadows that APTs use to hide. These attacks quite simply must talk in order to function, finding these communications is a critical component of controlling cyberattacks and the threats they pose.

A next-generation firewall performs a true classification of traffic based not simply on port and protocol, but on an ongoing process of application analysis, decryption, decoding, and heuristics. These capabilities progressively peel back the layers of a traffic stream to determine its true identity. The ability to pinpoint and analyze even unknown traffic - without regard to port or encryption - is the defining characteristic of a true next-generation firewall and is invaluable in the fight against APTs.

Cybercriminals thrive on their ability to blend in with approved or "normal" traffic. The quality of your visibility into that traffic is one of your most critical assets.

**Preventing infection with next-generation firewalls**

One of the most important steps that an enterprise can take to control advanced malware is to reduce attack vectors and eliminate the ability for bots to hide in the network. Today the majority of vectors used by malware is virtually unchecked, and malware traffic is typically small enough to easily blend into the background of "normal" network traffic. By regaining full visibility and control of exactly what traffic is allowed into the network and why, security teams can accomplish both of these goals.

**Positive control reduces the attack surface**

Enforcing positive control is essential to the fight against malware. Positive control greatly reduces the attack surface and mitigates overall risk. Positive control simply means allowing only the specific applications and traffic you want, instead of trying to block everything that you don't want.

Positive control has long been a defining characteristic of network firewalls that separates them from other types of network security services.

Applications and malware now use non-standard, commonly open ports (for example, TCP port 80, 443, and 53) or simply hop between any available open ports to evade traditional firewalls.

Extending positive control to include all applications, irrespective of port, is not as easy as simply flipping a switch. Employees may use certain applications that do not have a readily apparent business value. Additionally, some applications may be used for both personal and business purposes. For example, Facebook can be used for social networking but has also become an increasingly important tool for many company marketing, sales, and recruiting initiatives.

To reduce the attack surface, enterprises must:

-   Enforce positive control of all network traffic to prevent unnecessary or high-risk traffic, even when encryption or port evasion techniques are used to hide the traffic.
-   Establish policies for approved applications and uses based on business needs and culture, by determining:
    -   what applications and protocols are in use on the network?
    -   what applications are required for the business and who needs to use them?
    -   What dual-use or personal applications does the enterprise want to allow?

**Control advanced malware-enabling applications**

Applications are an indispensable part of the attack lifecycle, and are critical to both the initial infection of the target machine and the ongoing command and control of the attack.

Although e-mail is still used by attackers, it has lost some of its luster as e-mail security has become a focal point for many enterprises. Attackers have shifted much of their attention to softer target applications that interact with users in real-time and provide far more threat opportunities. Attackers have gravitated to applications that facilitate social engineering while hiding the presence of compromise. These applications include social networking, web-based e-mail, instant message (IM), peer-to-peer (P2P), and file transfer.

Social applications also present an ideal environment for social engineering, enabling an attacker to impersonate a friend or colleague, for example, to lure an unsuspecting victim into clicking a dangerous link. For all their sophistication, malware infections continue to rely on enticing an unsuspecting user into performing an ill-advised action, such as clicking a malicious link. Instead of opening an e-mail attachment, the click may be a link in a tweet or on a Facebook page that appears to be from a friend. Cross-site scripting can populate dangerous links among friends, and packet sniffing technologies such as FireSheep allow attackers to take over social networking accounts.
![[Screenshot 2022-03-10 at 09.23.17.png]]

**Actively test unknown files**

Malware and exploits are easily modified or customized by attackers so that their attack will not trigger known signatures. This flexibility is one of the key technologies that allows an advanced attacker to gain a foothold within a target network without arousing the suspicion of security.

To address this shift by attackers, you need to integrate new technologies that can identify unknown threats based on how it behaves, not simply based on how it looks. This sort of active analysis can be performed by executing suspicious files in a virtual sandbox. A sandbox is a fully virtualized environment where you can run and observe a suspect file to see what the file really does, providing a way of detecting new threats.

However, detection is only part of the battle. Enforcement against these threats is still needed in order to keep the network and its users safe. Typically in-line enforcements include:

-   Dynamic protections for newly identified unknwon malware, zero-day exploits, and their variants.
-   Protections for related malware that may use the command and control servers or infrastructure.
-   Protections for threats that leverage the same command and control strategy.
-   Protections for threats that use related domains and URLs

Control enabling applications by:

-   Blocking the use of known "bad" applications, such as P2P file-sharing.
-   Limiting application usage to users and groups that have a legitimate and approved business need.
-   Disabling specific features in risky applications, such as file transfers, desktop sharing, and tunneling.
-   Preventing drive-by-downloads from compromised web pages that automatically download malicious files without the user's knowledge.
-   Decrypting SSL traffic selectively, based on application and URL categories (for example, decrypt social networking and webmail, but not financial traffic).
-   Inspecting and enforcing any risky application traffic that is permitted using a next-generation firewall that provides truly integrated intrusion and threat prevention, malware protection, and URL filtering.

**Prevent use of circumventors**

Equally important, another class of applications are proactively designed to evade traditional network security. These applications include:

-   remote desktop technologies
-   proxies
-   purpose-built circumventing applications

Some of these applications have valid business uses, while others are a sure sign of unauthorized and dangerous behavior.

Remote desktop technologies are popular among end-users and IT support teams. Many web-conferencing applications have added the ability to remotely control a user's machine. Such technologies introduce two important risks:

-   When a user connects to a remote PC, he is free to surf to any destination and use any application without that traffic being inspected by the firewall. In addition to circumventing policy, the remote desktop opens an unmanaged threat vector by allowing a user to remotely undertake all kinds of risky behaviour and then have the results tunneled back to his machine inside the enterprise.
-   Remote desktop technologies potentially allow an unauthorized user to gain full access to a machine inside the trusted enterprise network. This type of remote control is one of the first objectives of malware, and as such it creates a dangerous opportunity to launch an intrusion.

Common applications that have valid uses within the enterprise can also create unintentional exposures if improperly used, or used by unauthorized or untrained users. For example, many IT departments use SSH to manage systems and applications in a corporate datacenter. By opening a tunnel into the datacenter, SSH can provide direct, unmanaged access into an enterprise's most critical assets. These applications need to be tightly controlled, limited to approved individuals only, and closely monitored and logged.

Finally, a variety of web proxies and encrypted tunneling applications have been developed to provide secure and anonymous communication across firewalls and other security infrastructure. Proxy technologies provide a relatively easy way for users to surf securely without enterprise control and have been found in more than 75% of enterprise networks.

Prevent the use of circumventors by:

-   Limiting remote desktop use, for example, to IT support personnel only;
-   Securely enabling SSH but preventing SSH tunneling;
-   Blocking unapproved proxies and encrypted tunnels, such as UltraSurf and Hamachi.

**Investigate any unknown traffic**

Malware and APT traffic often appear as "unknown" due to their unique behaviour and use of proprietary encryption.

Unknown traffic regularly sent by the same client machine should be investigated to determine whether it is being generated by a legitimate application that is not recognized or by a potential malware infection. Security teams can also investigate where the traffic is going:

-   does it go out to known malicious websites or to social networking sites?
-   Does it transmit on a regular schedule?
-   Does someone attempt to download or upload files to an unknown URL?

Any of these behaviours can indicate the presence of a bot on the client machine.

Unknowns on the network need to be investigated, identified, and managed. You can quickly and systematically manage unknown traffic by:

-   applying a policy on the firewall to block all unknown traffic, or allow and inspect it.
-   Determining what internal applications exist on the network, and either applying an application override (renaming the traffic) or creating a custom signature.
-   Analyze unknown or suspicious files in a sandbox to uncover malicious behaviours.
-   Using packet captures (PCAP) to record the unknown traffic and submit it to your security vendor.
-   Utilizing behavioral botnet reports and other forensics or reporting tools to determine whether the traffic is a threat.

Investigate "unknown" traffic for potential unauthorized user behaviour or malware activity:

-   track source, destination, and volumes of unknown traffic
-   correlate against URL, IPS, malware, and file-transfer records
-   define custom application IDs for any internal or custom applications, as needed
-   Deliver packet captures (PCAPs) to your security vendor for further analysis and identification.

**Finding infected hosts**

Enterprise machines will inevitably be infected with malware - perhaps through a new type of malware, an unknown vector, or a USB drive. Malware has proven time and again that is possible to infect even the most heavily secured systems. Thus, it is prudent to assume endpoints are infected and develop the skills necessary to find infected endpoints in the network. This can be a challenging task, given that a bot may have already avoided traditional malware signatures and may already have root-level access on an infected machine.

To pinpoint infected machines, your focus must shift from malware signatures. Instead, you need to analyze unusual or unknown behaviors that are observed on the network. It must communicate in order to function and must be difficult to find and trace. These basic requirements create patterns that can be used to identify bot traffic or behaviors that stand out from the normal network traffic - even if the bot is completely new and unknown.

**Find command-and-control traffic**

The ability to identify and classify complex streams of traffic at the application level is crucial to detecting the unique command-and-control traffic of advanced attacks.

**Chapter 5 - Creating advanced threat protection policies**

It is important to ensure that your policies are up to date and the technology solutions you are considering support a comprehensive security strategy.

**Safe enablement through smart policies**

The purpose of enterprise security policies is to reduce the risk of being infected by advanced threats in the first place. You have to assume that your network will eventually be breached, no matter how well designed your policies are, and plan accordingly.

Your security policy must help your organization control malware and reduce risks, while also meeting your business requirements. Creating effective security policies requires a keen understanding of the risks posed by the various applications and features used in your network, the business needs of the organization, and your users' work requirements.

IT must play an active role in defining smart policies that enable an organization's users and mitigate risk.

**Application controls**

Enablement is about knowing and understanding users and their behaviors, and applications and their associated risks. In the case of popular applications (such as social media), the users have long since decided on the benefits - and are, far too often, oblivious to the threats and risks. As a result, it's vital to match users' needs with the most appropriate applications and features, while also educating users about the implicit risks of those applications and features.

Application enablement typically includes restricting the use of unneeded high-risk applications while managing allowed applications to reduce the inherent risks they may bring with them.

Application controls should be part of the overarching corporate security policy. As part of the process of implementing an application control policy, IT should make a concerted effor to learn about new and evolving Web 2.0 applications. This includes embracing them for all their intended purposes and, if needed, proactively installing them or enabling them in a lab environment to see how they act. Peer discussions, message boards, blogs, and developer communities are also valuable sources of information.

**User controls**

Most companies have some type of application usage policy, outlining which applications are allowed and which are prohibited. Every employee is expected to understand the contents of this application usage policy and the ramifications of not complying with it, but there are a number of unanswered questions, including:

-   given the ever-growing numbers and types of applications, how will an employee know which applications are allowed and which are prohibited?
-   How is the list of unapproved applications updated, and who ensures employees know the list has changed?
-   What constitutes a policy violation?
-   What are the ramifications of policy violations?

The development of policy guidelines is often a challenging and polarizing process.

**Network controls**

Given that advanced threats most often use the network for infection and ongoing command and control, the network is an obvious and critical policy-enforcement point.

With application-enablement policies in place, IT can shift its attention to inspecting the content of allowed traffic. This inspection often includes looking at traffic for known malware, command-and-control patterns, exploits, dangerous URLs, and dangerous or risky file types. When possible, policies that focus on the content of traffic should be coordinated as part of a single unified policy, where the rules can all be seen in context. If content policies are spread across multiple solutions, modules, or monitors, piecing together a coordinated logical enforcement policy becomes increasingly difficult for IT security staff. Understanding whether these policies are working once they are implemented will likewise be difficult.

Another key component of network policies is the absolute need to retain visibility into the traffic content. SSL is increasingly used to secure traffic destined for the Internet. Although this may provide privacy for that particular session, if IT lacks the ability to look inside the SSL tunnel, SSL can also provide an opaque tunnel within which malware can be introduced into the network environment. IT must balance the need to look within SSL against both privacy requirements for end-users and the overall performance requirements of the network. For this reason, it is important to establish SSL decryption policies that can be enforced selectively by application and URL category. For example, social media traffic could be decrypted and inspected for malware, while traffic to financial or healthcare sites is left encrypted.

**Endpoint controls**

The end-user's machine is the most common target for advanced malware and is a critical point for policy enforcement. Endpoint policies must incorporate ways of ensuring that antivirus and various host-based security solutions are properly installed and up to date.

Although targeted attacks are becoming more common, the majority of threats today continue to be known threats with known signatures.

Many malware infections begin with a remote exploit that targets a known vulnerability in the operating system or application. Thus, keeping these components up to date is a critical aspect of reducing the attack surface of the enterprise.

**Addressing mobile and remote users**

Users simply expect to be able to connect and work from any location. This means that more and more workers and data may be beyond the physical perimeter of the enterprise, and thus also beyond the protections of traditional perimeter security solutions. The key is to build a security architecture that doesn't treat these mobile or remote users as exceptions; they need the same application, user, and content protections when they are outside the perimeter that they would receive when they are inside.

Building consistency into the architecture of the network requires careful planning and is a must for any security policy to address the realities of modern computing.

Other devices used to remotely connect to enterprise networks include smartphones, tablets, and iOS devices, such iPhones nad iPads. All of these devices must also be addressed in order to prevent blind spots in your organization's security policies.

Warning: mobile malware is still in its infancy, but it does exist and is likely to become a major threat in the near future. As mobile devices grow more powerful, they will increasingly be used as a replacement for the PC, storing vast amounts of personal - and valuable - data that is largely unprotected.

**Chapter 6 - Ten best practices for controlling APTs**

**Ensure visibility into all traffic**

Ensure visibility into all traffic on the enteprise network by:

-   Accurately classifying all traffic.
-   Extending visibility beyond the perimeter.

**Restrict high-risk applications**

Organizations should control the risk introduced by applications by restricting the use of high-risk applications. Here's how:

-   Block (or limit) P2P applications
-   Block unneeded applications that can tunnel other applications
-   Block applications known to be used by malware
-   Block anonymizers (such as Tor)
-   Block encrypted tunnel applications (such as UltraSurf)
-   Limit use of approved proxies to authorized users with a legitimate business need
-   Limit use of remote desktop protocols and applications to authorized users with a legitimate business need

**Selectively decrypt and inspect SSL traffic**

While SSL certainly provides security for the individual session, it can also create a problem for enterprise security by obscuring the traffic from network security solutions such as intrusion prevention systems (IPS), anti-malware, and data loss prevention (DLP) solutions. To make matters worse, the very sites and applications that are adopting SSL are the same ones that hackers favor for launching and maintaining their ongoing attacks.

IT and security teams should implement best practices and policies to selectively identify, decrypt, and inspect high-risk SSL traffic while maintaining an appropriate balance of performance. Enterprises need to control SSL traffic with:

-   Decrypt policies that allow decryption and inspection of the following SSL traffic:
    -   Social networking
    -   web-based e-mail
    -   instant messaging
    -   message boards
    -   microblogging
    -   gaming sites
-   Do-not-decrypt policies that protect the confidentiality and integrity of the following SSL traffic:
    -   health care applications, information, and sites
    -   financial applications, data, and sites
    -   secure channels

**Sandbox unknown files**

Advanced attackers are increasingly turning to customized malware and zero-day exploits targeted at a particular enterprise network or a specific host. This strategy makes the threats extremely unique and almost certainly enables them to pass through security measures without triggering known signatures.

Signatures can only protect against threats that have been previously detected and analyzed. This reactive approach creates a window of opportunity, the time that new malware and exploits are "in the wild", in which enterprises are not protected and vulnerable to attack.

To address this vulnerability, enterprises should supplement their signature-based tools with direct analysis of unknown files for malicious behaviors.

Active analysis is typically done by placing the unknown file in a virtual environment to observe how it would behave in a vulnerable environment. This approach can expose some of the signs of advanced threats - such as altering operating system files, making changes to registry settings, or injecting themselves into other running processes - and provides IT security teams with a method for definitively identifying malware even when it is not recognized by signature-based anti-malware solutions.

IT security teams should have the ability to create protections on demand when new malware or exploits are identified, and distribute these custom protections to all of the organization's network gateways in order to protect against unknown threats. It's not enough to simply put a sandbox into your lab. You must build in the ability to quickly and centrally determine whether a given file has already been analyzed, and then quickly deliver protections to all ingress/egress points when a malicious file is detected.

**Block URLs that are known to host malware and exploits**

Even completely valid websites can be compromised and serve up malware or exploits to unsuspecting visitors. However, some sites are clearly more dangerous than others, and a strong URL filtering solution should be able to keep track of sites that have been known to deliver threats. This approach, much like anti-malware and intrusion prevention signature-based solutions, requires constant diligence by the security vendor to keep updated. IT security teams need to challenge their vendors to ensure that URL lists are properly maintained and automatically updated.

In addition to known bad sites and URLs, extra caution should be exercised with any recently registered or unclassified domains. Attackers and their threats move quickly between such new sites in order to avoid detection and to cover their tracks.

IT security teams must be able to update URL classifications based on malware and exploits that may have been identified through sandboxing. An important benefit of a sandbox is the ability to see how and where the threat came from - and where it connects back to. This will allow security teams to immediately update the lists of dangerous URLs, based on actual threats observed in the network.

**Enforce drive-by-download protection**

Infection via drive-by-downloads has become a very common method for malware and exploit delivery. A drive-by-download occurs when a user unknowingly visits a malicious or compromised website that automatically downloads software to the user's computer without the person's knowledge or permission. The host browser and operating system fails to detect or report the download and installation, leaving the user's machine vulnerable to infection.

Enterprises must enforce drive-by-download protection to prevent infections by:

-   detecting downloads in the background, even unknown exploits and malware
-   automatically reporting drive-by-downloads to the user and either blocking the download or requiring the user to acknowledge and permit the download.
-   Training users not to just click "OK" or "Accept" but to read and understand pop-up warnings from their network firewall.

**Block known exploits and malware**

Known threats still constitute the majority of threats leading to successful malware infections and attacks against the enteprise today. Malware and exploit kits are increasingly popular and have supercharged the malware economy.

**Limit traffic for common applications to default ports**

Certain ports practically have to be open on a firewall for an enterprise network to function. For example, most web browsing requires TCP port 53 (DNS), 80 (HTTP), and 443(HTTPS), and e-mail communication requires TCP port 25 (SMTP).

Attackers take advantage of this requirement with malware that regularly communicates on ports that are almost always open by default.

Legacy port-based firewalls simply allow traffic across an open port and assume that it is the default application or protocol for that port.

**Evaluate network and application events in context**

It is important to understand that application signatures, network behaviors, and malware sources are all interrelated, and need to be correlated and evaluated in context. Traditional security infrastructures that provide "defense in depth" through separate devices such as port-based firewalls, intrusion prevention, web-content filtering, and anti-malware software can overwhelm security teams with data that cannot be easily correlated. A true solution should help you make intelligent security decisions based on context. To evaluate events in context:

-   develop context-based visibility with accurate information about applications, signatures, sources, and behaviors
-   Correlate events by user and application, including:
    -   known malware
    -   known exploits
    -   phone-home detection
    -   download history
    -   URL categories

**Investigate unknowns**

Unknown traffic should be tracked and investigated to find potential malware or other unidentified threats on the enterprise network. In addition to unknown traffic, you should investigate:

-   Unknown or unclassified URLs. Unknown or recently registered URLs are significant because malware and bot-herders regularly rotate between URLs that are used for command and control to impede discovery and takedown efforts. Unknown traffic going to unknown URL categories should be treated as highly suspicious.
-   Unknown encryption. Customized encryption is often used by malware to hide their communications. Use the capabilities of a true next-generation firewall to inspect encrypted traffic and to ensure that all traffic on the network has a known, legitimate purpose.

