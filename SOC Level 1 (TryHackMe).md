# Cyber Defence frameworks
### Junior Security Analyst intro

### A career as a Junior (Associate) Security Analyst
**Responsibilities for a Junior (Associate) Security Analyst/Tier1 SOC Analyst:**
- monitor and investigate the alerts (most of the time it's a 24x7 SOC operations environment)
- configure and manage the security tools
- develop and implement basic IDS (Intrusion Detection System) signatures
- participate in SOC working groups, meetings
- create tickets and escalate the security incidents to the Tier2 and Team Lead if needed.
**Required qualifications (most common):**
- basic understanding of networking (OSI model, TCP/IP, operating systems (Windows, Linux))
- scripting/programming skills are a plus

##### An overview of the SOC Three-Tier model:
- *Junior Security Analyst (Tier1) Triage:*
	- monitors the network traffic, logs, and events
	- works on the tickets, closes the alerts
	- performs basic investigations and mitigations
- *Security Operations Analyst (Tier2) Incident Responder:*
	- focuses on deeper investigations, analysis and remediation
	- proactively hunts for adversaries
	- monitors and resolves more complex alerts
- *Security Operations Analyst (Tier3) Threat Hunter:*
	- works on more advanced investigations
	- performs advanced threat hunting and adversary research
	- malware reversing

### Security Operations Center (SOC)
**What exactly is a SOC?**
The core function of a SOC is to investigate, monitor, prevent, and respond to threats 24x7.
"Security operations teams are charged with monitoring and protecting many assets, such as intellectual property, personnel data, business systems, and brand integrity. As the implementation component of an organisation's overall cybersecurity framework, security operations teams act as the central point of collaboration in coordinated efforts to monitor, assess, and defend against cyberattacks."

**What is included in the responsibilities for the SOC?**
Ticketing -> Log Collection -> Knowledge Base -> Research & Development -> Aggregation & Correlation -> Threat Intelligence -> SIEM -> Reporting

##### Preparation & Prevention
As a Junior Security Analyst, you should stay informed of the current cybersecurity threats. It's crucial to detect and hunt threats, work on a security roadmap to protect the organisation, and be ready for the worst-case scenario.
Prevention methods include gathering intelligence data on the latest threats, threat actors, and their TTPs (Tactics, Techniques, and Procedures). It also includes the maintenance procedures like updating the firewall signatures, patching the vulnerabilities in the existing systems, block-listing and safe-listing applications, email addresses, and IPs.

##### Monitoring & Investigation
A SOC Team proactively uses SIEM (Security Information and Event Management) and EDR (Endpoint Detection and Response) tools to monitor suspicious and malicious network activities.
As a Security Analyst, you will learn how to prioritise the alerts based on their level: Low, Medium, High, Critical.
Having properly configured security monitoring tools in place will give you the best chance to mitigate the threat.

Junior Security Analysts play a crucial role in the investigation procedure. They perform triaging on the ongoing alerts by exploring and understanding how a certain attack works and preventing bad things from happening if they can.
During the investigation, it's important to raise the question: "How? When? Why?". Security Analysts find the answers by drilling down on the data logs and alerts in combination with using open source tools.

##### A day in the life of a Junior (Associate) Security Analyst
To be in the frontline is not always easy and can be very challenging as you will be working with various log sources from different tools. You will get a chance to monitor the network traffic, including IPS (Intrusion Prevention System) and IDS (Intrusion Detection System) alerts, suspicious emails, extract the forensics data to analyse and detect the potential attacks, use open source intelligence (OSINT) to help you make the appropriate decisions on the alerts.

Incident Response might take hours, days, or weeks; it all depends on the scale of the attack: did the attacker manage to exfiltrate the data? Did the attacker attempt to pivot into other hosts? There are many questions to ask and a lot of detection, containment, and remediation to do.

The first thing almost every Junior Security Analyst does on their shift is to look at the tickets to see if any alerts got generated.

#### Pyramid of Pain
(understanding the Pyramid of Pain concept as a Threat Hunter)
![[Screenshot 2023-02-13 at 10.47.19.png]]
This concept is being applied to cybersecurity solutions to improve the effectiveness of CTI, Threat Hunting, and Incident Response exercises.

**Hash Values (Trivial)**
The hash value is a numeric value of a fixed length that uniquely identifies data. A hash value is the result of a hashing algorithm. A hash is not considered to be cryptographically secure if two files have the same hash value or digest.
Security professionals usually use the hash values to gain insight into a specific malware sample, a malicious or a suspicious file, and as a way to uniquely identify and reference the malicious artefact. Various online tools can be used to do hash lookups like VirusTotal.
It is easy to spot a malicious file if we have the hash. However, as an attacker, it's trivial to modify a file by even a single bit, which would produce a different hash value. With so many variations and instances of known malware or ransomware, threat hunting using file hashes as the IOC can became a difficult task.

**IP address (Easy)**
An IP address is used to identify any device connected to a network. We rely on IP addresses to send and receive the information over the network. From a defence standpoint, knowledge of the IP addresses an adversary uses can be valuable. A common defence tactic is to block, drop, or deny inbound requests from IP addresses on your parameter or external firewall. This tactic is often not bulletproof as it's trivial for an experienced adversary to recover simply by using a new public IP address.
One of the ways an adversary can make it challenging to successfully carry out IP blocking is by using Fast Flux.
Fast Flux is a DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies. The purpose of using the Fast Flux network is to make the communication between malware and its Command & Control server challenging to be discovered. So, the primary concept of a Fast Flux network is having multiple IP addresses associated with a domain name, which is constantly changing.

**Domain names (Simple)**
Domain Names can be thought as simply mapping an IP address to a string of text.
Domain Names can be a little more of a pain for the attacker to change as they would most likely need to purchase the domain, register it and modify DNS records. Unfortunately for defenders, many DNS providers have loose standards and provide APIs to make it even easier for the attacker to change the domain.

**Host Artifacts (Annoying)**
On this level, the attacker will feel a little more annoyed and frustrated if you can detect the attack. The attacker would need to circle back at this detection level and change his attack tools and methodologies. This is very time-consuming for the attacker, and probably, he will need to spend more resources on his adversary tools.
*Host Artifacts* are the traces or observables that attackers leave on the system, such as registry values, suspicious process execution, attack patterns or IOCs (Indicators of Compromise), files dropped by malicious applications, or anything exclusive to the current threat.

**Network Artifacts (Annoying)**
This means if you can detect and respond to the threat, the attacker would need more time to go back and change his tactics or modify the tools, which gives you more time to respond and detect the upcoming threats or remediate the existing ones.
A Network Artifact can be a user-agent string, C2 information, or URI patterns followed by the HTTP POST requests. An attacker might use a user-agent string that hasn't been observed in your environment before or seems out of the ordinary. The user-agent is defined by RFC2616 as the request-header field that contains the information about the user agent originating the request.
Network Artifacts can be detected in Wireshark PCAPs (file that contains the packet data of a network) by using a network protocol analyser such as TShark or exploring IDS (Intrusion Detection System) logging from a source such as SNORT.

If you can detect the custom user-agent strings that the attacker is using, you might be able to block them, creating more obstacles and making their attempt to compromise the network more annoying.

**Tools (Challenging)**
At this stage, we have levelled up our detection capabilities against the artifacts. The attacker would most likely give up trying to break into your network or go back and try to create a new tool that serves the same purpose, find a tool that has the same potential, or even get some training to learn how to be proficient in a certain tool.
Attackers would use the utilities to create malicious macro documents (maldocs) for spear-phishing attempts, a backdoor that can be used to establish C2 (Command & Control infrastructure), any custom .exe, and .dll files, payloads or password crackers.
Antivirus signatures, detection rules, and YARA rules can be great weapons for you to use against attackers at this stage.
MalwareBazaar and Malshare are good resources to provide you with access to the samples, malicious feeds, and YARA rules/results - these all can be very helpful when it comes to Threat Hunting and Incident Response.
For detection rules, SOC Prime Threat Detection Marketplace is a great platform, where security professionals share their detection rules for different kinds of threats, including the latest CVE's that are being exploited in the wild by adversaries.
Fuzzy hashing is also a strong weapon against the attacker's tools.
Fuzzy hashing helps you to perform similarity analysis - match two files with minor differences based on the fuzzy hash values.
*(on the SSDeep official website, you can find the complete explanation for fuzzy hashing)*

**TTPs (Though)**
This includes the whole MITRE ATT&CK Matrix, which means all the steps taken by an adversary to achieve his goal, starting from phishing attempts to persistence and data exfiltration.
If you can detect and respond to the TTPs quickly, you leave the adversaries almost no chance to fight back.

### Cyber Kill Chain
##### Introduction
The term kill chain is a military concept related to the structure of an attack. It consists of target identification, decision and order to attack the target, and finally the target destruction.
The Cyber Kill Chain framework defines the steps used by adversaries or malicious actors in cyberspace. To succeed, an adversary needs to go through all phases of the kill chain.
The Cyber Kill Chain will help you understand and protect against ransomware attacks, security breaches as well as APTs.
You can use the CKC to assess your network and system security by identifying missing security controls and closing certain security gaps based on company's infrastructure.

##### Reconnaissance
Is discovering and collecting information on the system and the victim. The reconnaissance phase is the planning phase for the adversaries.
OSINT also falls under reconnaissance. OSINT is the first step an attacker needs to complete. The attacker needs to study the victim by collecting every available piece of information.

##### Weaponisation
Combines malware and exploit, into a deliverable payload. Most attackers usually use automated tools to generate the malware or refer to the DarkWeb to purchase the malware.
More sophisticated actors or nation-sponsored APT groups would write their custom malware to make the malware sample unique and evade detection on the target.

**Malware** is a program or software that is designed to damage, disrupt, or gain unauthorised access to a computer.

An **Exploit** is a program or code that takes advantage of the vulnerability or flaw in the application or system.

A **Payload** is a malicious code that the attacker runs on the system.

##### Delivery
The Delivery phase is when the attacker decides to choose the method for transmitting the payload or the malware.
He has plenty of options to choose from:
- phishing email
- usb drop attack
- watering hole attack (it's a targeted attack designed to aim at a specific group of people by compromising the website they are usually visiting and then redirecting them to the malicious website of an attacker's choice)

##### Exploitation
To gain access to the system, an attacker needs to exploit the vulnerability. After gaining access to the system, the malicious actor could exploit software, system, or server-based vulnerabilities to escalate the privileges or move laterally through the network.

**Lateral Movement** refers to the techniques that a malicious actor uses after gaining initial access to the victim's machine to move deeper into a network to obtain sensitive data.
The attacker might also apply a "Zero-day Exploit" at this stage.

The **Zero-day exploit** or **Zero-day vulnerability** is an unknown exploit in the wild that exposes a vulnerability in software or hardware and can create complicated problems well before anyone realises something is wrong.
A Zero-day exploit leaves **NO** opportunity for detection at the beginning.

***These are examples of how an attacker carries out exploitation:***
- the victim triggers the exploit by opening the email attachment or clicking on a malicious link.
- using a zero-day exploit.
- exploit software, hardware, or even human vulnerabilities.
- an attacker triggers the exploit for server-based vulnerabilities.

##### Installation
The backdoor lets an attacker bypass security measures and hide the access. A backdoor is also known as an access point.
Once the attacker gets access to the system, he would want to reacess the system if he loses the connection to it or if he got detected and got the initial access removed, or if the system is later patched. He will no longer have access to it. That is when the attacker needs to install a *persistent backdoor*.
A **persistent backdoor** will let the attacker access the system he compromised in the past.
**The persistence can be achieved through:**
- installing a backdoor on the victim's machine. For example, the attacker can use Meterpreter to install a backdoor on the victim's machine. Meterpreter is a Metasploit framework payload that gives an interactive shell from which an attacker can interact with the victim's machine remotely and execute the malicious code.
- creating or modifying windows services. An attacker can create or modify the windows services to execute the malicious scripts or payloads regularly as a part of the persistence. An attacker can use the tools like sc.exe (sc.exe lets you create, start, stop, query, or delete any Windows service) and Reg to modify service configurations. 

The attacker can also ***masquerade*** the malicious payload by using a service name that is known to be related to the OS or legitimate software.
**Masquerading -** adversaries may attempt to manipulate features of their artifacts to make them appear legitimate or benign to users and/or security tools. Masquerading occurs when the name or location of an object, legitimate or malicious, is manipulated or abused for the sake of evading defences and observation. This may include manipulating file metadata, tricking users into misidentifying the file type, and giving legitimate task or service names.

- Adding the entry to the "run keys" for the malicious payload in the Registry or the Startup Folder. By doing that, the payload will execute each time the user logs in.

In this phase, the attacker can also use the Time-stomping technique to avoid detection and also to make the malware appear as a part of a legitimate program. The Time-stomping technique lets an attacker modify the file's timestamps, including the modify, access, create and change times.

##### Command & Control
After getting persistence and executing the malware on the victim's machine, the attacker opens up the C2 channel through the malware to remotely control and manipulate the victim.
This term is also known as C&C or C2 Beaconing as a type of malicious communication between a C&C Server and malware on the infected host. The infected host will consistently communicate with the C2 server; that is also where the beaconing term came from.

**C2 (Command & Control infrastructure) -** set of programs used to communicate with a victim machine. This is comparable to a reverse shell, but is generally more advanced and often communicate via common network protocols, like http/https and DNS.

The compromised endpoint would communicate with an external server set up by an attacker to establish a C2 channel. After establishing the connection, the attacker has full control of the victim's machine. Until recently, IRC (Internet Relay Chat) was the traditional C2 channel used by attackers. This is no longer the case, as modern security solutions can easily detect malicious IRC traffic.

The most common C2 channels used by adversaries nowadays:
- the protocols http on port 80 and https on port 443 - this type of beaconing blends the malicious traffic with the legitimate traffic and can help the attacker evade firewalls.
- DNS (Domain Name Server). the infected machine makes constant DNS requests to the DNS server that belongs to an attacker, this type of C2 communication is also known as DNS Tunnelling.
  Important to note that an adversary or another compromised host can be the owner of the C2 infrastructure.

##### Actions on objectives (Exfiltration)
Means taking action on the original objectives.
With access, the attacker can achieve the following:
- collect the credentials from users
- perform privilege escalation
- internal reconnaissance (for example, an attacker gets to interact with internal software to find its vulnerabilities)
- lateral movement through the company's environment.
- collect and exfiltrate sensitive data.
- deleting the backups and shadow copies (shadow copy is a Microsoft technology that can create backup copies, snapshots of computer files, or volumes).
- overwrite or corrupt data.

### Unified Kill Chain
##### Introduction
Understanding the behaviours, objectives and methodologies of a cyber threat is a vital step to establishing a strong security.

##### What is a "kill chain"?
A "Kill Chain" is a term used to explain the various stages of an attack. In cybersecurity, a "Kill Chain" is used to describe the methodologies/path attackers use to approach and intrude a target. For example, an attacker scanning, exploiting a web vulnerability, and escalating privileges will be a "Kill Chain".

##### What is "Threat Modelling"?
Threat Modelling is a series of steps to ultimately improve the security of a system.
Threat Modelling is essentially about identifying risk:
1. identifying what systems and applications need to be secured and what function they serve in environment. For example, is the system critical to normal operations, and is a system holding sensitive information like payment info or addresses?
2. assessing what vulnerabilities and weaknesses these systems and applications may have and how they could be potentially exploited.
3. creating a plan of action to secure these systems and applications from the vulnerabilities highlighted.
4. putting in policies to prevent these vulnerabilities from occurring again where possible (for example, implementing a Software Development Lifecycle (SDLC) for an application or training employees on phishing awareness).

Threat Modelling is an important procedure in reducing the risk within a system or application, as it creates a high-level overview of an organisation's IT assets and the procedures to resolve vulnerabilities.

STRIDE, DREAD and CVSS are all frameworks specifically used in Threat Modelling.

The Unified Kill Chain (UKC) can encourage Threat Modelling as the UKC framework helps identify potential attack surfaces and how these systems may be exploited.

##### Introducing the Unified Kill Chain (UKC)
The UKC published in 2017, aims to complement (not compete) with other cybersecurity kill chain frameworks such as MITRE ATT&CK.
*The UKC states that there are 18 phases to an attack:* everything from reconnaissance to data exfiltration and understanding an attacker's motive. Some large benefits of the UKC over traditional cybersecurity kill chain frameworks include the fact that it is modern and extremely detailed.

**The Unified Kill Chain**
1. Reconnaissance - researching, identifying and selecting targets using active or passive reconnaissance.
2. Weaponisation - preparatory activities aimed at setting up the infrastructure required for the attack.
3. Delivery - techniques resulting in the transmission of a weaponised object to the targeted environment.
4. Social Engineering - techniques aimed at the manipulation of people to perform unsafe actions.
5. Exploitation - techniques to exploit vulnerabilities in systems that may, amongst others, result in code execution.
6. Persistence - any access, action or change to a system that gives an attacker persistent presence on the system.
7. Defence Evasion - techniques an attacker may specifically use for evading detection or avoiding other defences.
8. Command & Control - techniques that allow attackers to communicate with controlled systems within a target network.
9. Pivoting - tunnelling traffic through a controlled system to other systems that are not directly accessible.
10. Discovery - techniques that allow an attacker to gain knowledge about a system and its network environment.
11. Privilege escalation - the result of techniques that provide an attacker with higher permissions on a system or network.
12. Execution - techniques that result in execution of attacker-controlled code on a local or remote system.
13. Credential access - techniques resulting in the access of, or control over, system, service or domain credentials.
14. Lateral movement - techniques that enable an adversary to horizontally access and control other remote systems.
15. Collection - techniques used to identify and gather data from a target network prior to exfiltration.
16. Exfiltration - techniques that result or aid in an attacker removing data from a target network.
17. Impact - techniques aimed at manipulating, interrupting or destroying the target system or data.
18. Objectives - socio-technical objectives of an attack that are intended to achieve a strategic goal.

##### Phase: In (Initial Foothold)
The main focus of this phases is for an attacker to gain access to a system or networked environment.
An attacker will employ numerous tactics to investigate the system for potential vulnerabilities that can be exploited to gain a foothold in the system. For example, a common tactic is the use of reconnaissance against a system to discover potential attack vectors. It also accommodates for an attacker creating a form of persistence (a process that allows the attacker to connect to the machine at any time).

**Reconnaissance (MITRE Tactic TA0043)**
This phase of the UKC describes techniques that an adversary employs to gather information relating to their target. This can be achieved through means of Passive and Active reconnaissance. The information gathered during this phase is used all throughout the later stages of the UKC (such as the initial foothold).
***Information gathered from this phase can include:***
- discovering what systems and services are running on the target, this is beneficial information in the weaponisation and exploitation phases of this section.
- finding contact lists or lists of employees that can be impersonated or used in either a social-engineering or phishing attack.
- Looking for potential credentials that may be of use in later stages, such as pivoting or initial success.
- understanding the network topology and other networked systems can be used to pivot too.

**Weaponisation (MITRE Tactic TA0001)**
This phase of the UKC describes the adversary setting up the necessary infrastructure to perform the attack. For example, this could be setting up  C&C Server, or a system capable of catching revere shells and delivering payloads to the system.

**Social Engineering (MITRE Tactic TA0001)**
This phase of the UKC describes techniques that an adversary can employ to manipulate employees to perform actions that will aid in adversaries attacks.
*For example, a Social Engineering attack could include:*
- getting a user to open a malicious attachment
- impersonating a webpage and having the user enter their credentials.
- calling or visiting the target and impersonating a user (for example, requesting a password reset) or being able to gain access to areas of a site that the attacker would not previously be capable of.

**Exploitation (MITRE Tactic TA0002)**
This phase of the UKC describes how an attacker takes advantage of weaknesses or vulnerabilities present in a system. The UKC defines "Exploitation" as abuse of vulnerabilities to perform code execution.
*For example:*
- uploading and executing a reverse shell to a web application.
- interfering with an automated script on the system to execute code.
- abusing a web application vulnerability to execute code on the system it is running on.

**Persistence (MITRE Tactic TA0003)**
This phase of the UKC is short and simple. Specifically, this phase of the UKC describes the techniques an adversary uses to maintain access to a system they have gained an initial foothold on.
*For example:*
- creating a service on the target system that will allow the attacker to regain access.
- adding the target system to a C&C server where commands can be executed remotely at any time.
- leaving other forms of backdoors that execute when a certain action occurs on the system (i.e. a reverse shell will execute when a system administrator logs in).

**Defence Evasion (MITRE Tactic TA0005)**
This is one of the more valuable phases of the UKC. This phase specifically is used to understand the techniques an adversary uses to evade defensive measures put in place in the system or network.
*For example, this could be:*
- web application firewalls
- network firewalls
- anti-virus systems on the target machine
- intrusion detection systems

This phase is valuable when analysing an attack as it helps form a response and better yet, gives the defensive team information on how they can improve their defence systems in the future.

**Command & Control (MITRE Tactic TA0011)**
This phase combines the efforts an adversary made during the "Weaponisation" stage of the UKC to establish communications between the adversary and target system.
An adversary can establish C&C of a target system to achieve its action on objectives.
For example, the adversary can:
- execute commands
- steal data, credentials and other information
- use the controlled server to pivot to other systems on the network

**Pivoting (MITRE Tactic TA0008)**
Pivoting is the technique an adversary uses to reach other systems within a network that are not otherwise accessible (for example, they are not exposed to the internet). There are often many systems in a network that are not directly reachable and often contain valuable data or have weaker security. For example, an adversary can gain access to a web server that is publicly accessible to attack other systems that are within the same network (but aren't accessible via the internet).

##### Phase: Through (Network Propagation)
This phase follows a successful foothold being established on the target network. An attacker would seek to gain additional access and privileges to systems and data to fulfil their goals. The attacker would set up a base on one of the systems to act as their pivot point and use it to gather information about the internal network.

**Pivoting (MITRE Tactic TA0008)**
Once the attacker has access to the system, they would use it as their staging site and a tunnel between their command operations and the victim's network. The system would also be used as the distribution point for all malware and backdoors at later stages.

**Discovery (MITRE Tactic TA0007)**
The adversary would uncover information about the system and the network it is connected to. Within this stage, the knowledge base would be built from the active user accounts, the permissions granted, applications and software in use, web browser activity, files, directories and network shares, and system configurations.

**Privilege Escalation (MITRE Tactic TA0004)**
Following their knowledge-gathering, the adversary would try to gain more prominent permissions with the pivot system. They would leverage the information on the accounts present with vulnerabilities and misconfigurations found to elevate their access to one of the following superior levels:
- system/root
- local administrator
- a user account with Admin-like access
- a user account with specific access or functions

**Execution (MITRE Tactic TA0002)**
Recall when the adversary set up their attack infrastructure. Once the attacker has access to the system, they would use it as their staging site and a tunnel between their command operations and the victim's network. The system would also be used as the distribution point for all malware and backdoors at later stages.
And weaponised payloads? This is where they deploy their malicious code using the pivot system as their host. Remote trojans, C2 scripts, malicious links and scheduled tasks are deployed and created to facilitate a recurring presence on the system and uphold their persistence.

**Credential Access (MITRE Tactic TA0006)**
Working hand in hand with the Privilege Escalation stage, the adversary would attempt to steal account names and passwords through various methods, including key-logging and credential dumping. This makes them harder to detect during their attack as they would be using legitimate credentials. 

**Lateral Movement (MITRE Tactic TA0008)**
With the credentials and elevated privileges, the adversary would seek to move through the network and jump onto other targeted systems to achieve their primary objective. The stealthier the technique used, the better.

##### Phase: Out (Action on Objectives)
This phase wraps up the journey of an adversary's attack on an environment, where they have critical asset access and can fulfil their attack goals. These goals are usually geared toward compromising the confidentiality, integrity and availability (C.I.A.) triad.

**Collection (MITRE Tactic TA0009)**
After all the hunting for access and assets, the adversary will be seeking to gather all the valuable data of interest. This, in turn, compromises the confidentiality of the data and would lead to the next attack stage - Exfiltration.

**Exfiltration (MITRE Tactic TA0010)**
To elevate their compromise, the adversary would seek to steal data, which would be packaged using encryption measures and compression to avoid any detection. The C2 channel and tunnel deployed in the earlier phases will come in handy during this process.

**Impact (MITRE Tactic TA0040)**
If the adversary seeks to compromise the integrity and availability of the data assets, they would manipulate, interrupt or destroy these assets. The goal would be to disrupt business and operational processes and may involve removing account access, disk wipes, and data encryption such as ransomware, defacement and DOS attacks.

**Objectives**
With all the power and access to the systems and network, the adversary would seek to achieve their strategic goal for the attack.
For example, if the attack was financially motivated, they may seek to encrypt files and systems with ransomware and ask for payment to release the data. In other instances, the attacker may seek to damage the reputation of the business, and they would release private and confidential information to the public.

### Diamond Model
***The Diamond Model is composed of four case features:*** adversary, infrastructure, capability, and victim, and establishes the fundamental atomic element of any intrusion activity. ***You might have also noticed two additional components or axes of the Diamond Model:*** Social, Political and Technology.
**Why is it called a "Diamond Model"?**
The four core features are edge-connected, representing their underlying relationships and arranged in the shape of a diamond.
The Diamond Model carries the essential concepts of intrusion analysis and adversary operations while allowing the flexibility to expand and encompass new ideas and concepts. The model provides various opportunities to integrate intelligence in real-time for network defence, automating correlation across events, classifying events with confidence into adversary campaigns, and forecasting adversary operations while planning and gaming mitigation strategies.
The Diamond Model can help you identify the elements of an intrusion. It can also help explain to other non-technical people about what happened during an event or any valuable information on the malicious threat actor.

**Adversary**
An adversary is also known as an attacker, enemy, cyber threat actor, or hacker. The adversary is the person who stands behind the cyberattack. Cyberattacks can be an instruction or a breach.
An adversary is an actor or organisation responsible for utilising a capability against the victim to achieve their intent. It is essential to know the distinction between adversary operator and adversary customer because it will help you understand intent, attribution, adaptability, and persistence by helping to frame the relationship between an adversary and victim pair.
It is difficult to identify an adversary during the first stages of a cyberattack. Utilising data collected from an incident or breach, signatures, and other relevant information can help you determine who the adversary might be.
*Adversary Operator* is the "hacker" or person(s) conducting the intrusion activity.
*Adversary Customer* is the entity that stands to benefit from the activity conducted in the intrusion. It may be the same person who stands behind the adversary operator, or it may be a separate person or group.
As an example, an adversary customer could control different operators simultaneously. Each operator might have its capabilities and infrastructure.

**Victim**
Victim is a target of the adversary. A victim can be a organisation, person, target email address, IP address, domain, etc.
It's essential to understand the difference between the victim persona and the victim assets because they serve different analytic functions.
A victim can be an opportunity for the attackers to get a foothold on the organisation they are trying to attack. There is always a victim in every cyberattack.
*Victim Persona* are the people and organisations being targeted and whose assets are being attacked and exploited.
*Victim Assets* are the attack surface and include the set of systems, networks, email addresses, hosts, IP addresses, etc, to which the adversary will direct their capabilities.

**Capability**
Also known as the skill, tools and techniques used by the adversary in the event. The capability highlights the adversary's Tactics, Techniques, and Procedures (TTPs).
The capability can include all techniques used to attack the victims.
*Capability Capacity* is all of the vulnerabilities and exposures that the individual capability can use.
*Adversary Arsenal* is a set of capabilities that belong to an adversary. The combined capacities of an adversary's capabilities make it the adversary's arsenal.
An adversary must have the required capabilities. The capabilities can be malware and phishing email development skills or, at least, access to capabilities, such as acquiring malware or ransomware as a service.

**Infrastructure**
Also known as software or hardware. Infrastructure is the physical or logical interconnections that the adversary uses to deliver a capability or maintain control of capabilities. For example, a C2 and the results from the victim (data exfiltration).
The infrastructure can also be IP addresses, domain names, email addresses, or even a malicious USB device found in the street and plugged into a workstation.
*Type 1 Infrastructure* is the infrastructure controlled or owned by the adversary.
*Type 2 Infrastructure* is the infrastructure controlled by an intermediary. Sometimes the intermediary might not be aware of this. This is the infrastructure that a victim will se as the adversary.
Type 2 Infrastructure has the purpose of obfuscating the source and attribution of the activity.
Type 2 Infrastructure includes malware staging servers, malicious domain names, compromised email accounts, etc.

Service Providers are organisations that provide critical services for the adversary availability of Type 1 and Type 2 Infrastructures, for example, Internet Service Providers, domain registrars, and webmail providers.

**Event Meta Features**
Six possible meta-features can be added to the Diamond Model.
Meta-features are not required, but they can add some valuable information or intelligence.
- ***Timestamp -*** is the data and time of the event. Timestamps are essential to help determine the patterns and group the malicious activity.
- ***Phase -*** these are the phases of an intrusion, attack, or breach. According to the Diamond Model Axiom 4: "Every malicious activity contains two or more phases which must be successfully executed in succession to achieve the desired result." Malicious activities don't occur in two or more events rather than just one. A great example can be the Cyber Kill Chain.
*The phases can be:*
1. Reconnaissance
2. Weaponisation
3. Delivery
4. Exploitation
5. Installation
6. Command & Control
7. Actions on Objectives
For example, an attacker needs to do some research to discover the target or a victim. Then they would try to exploit the target, establish a C&C Centre and lastly, exfiltrate the sensitive information.
- ***Result -*** while the results and post-conditions of an adversary's operations will not always be known or have a high confidence value when they re known, they are helpful to capture. It is crucial to capture the results and post-conditions of an adversary's operations, but sometimes they might not always be known. 
  The event results can be labelled as "success", "failure", or "unknown".
  The event results can also be related to the C.I.A. triad, such as Confidentiality Compromised, Integrity Compromised, and Availability Compromised. Another approach can also be documenting all of the post-conditions resulting from the event, for example, information gathered in the reconnaissance stage or successful passwords/sensitive data exfiltration.
- ***Direction -*** helps describe host-based and network-based events and represents the direction of the intrusion attack.
  The Diamond Model of Intrusion Analysis defines seven potential values for this meta-feature: victim-to-infrastructure, infrastructure-to-victim, infrastructure-to-infrastructure, adversary-to-infrastructure, infrastructure-to-adversary, bidirectional or unknown.
- ***Methodology -*** this meta-feature will allow an analyst to describe the general classification of intrusion, for example, phishing, DDoS, breach, port scan, etc.
- ***Resources -*** according to the Diamond Model, every intrusion event needs one or more external resources to be satisfied to succeed. Examples of the resources can include the following: software (e.g. operating systems, virtualisation software, or Metasploit framework), knowledge (e.g. how to use Metasploit to execute the attack and run the exploit), information (e.g. a username/password to masquerade), hardware (e.g. servers, workstations, routers), funds (e.g. money to purchase domains), facilities (e.g. electricity or shelter), access (e.g. a network path from the source host to the victim and vice-versa, network access from an ISP).

##### Social-Political component
The social-political component describes the needs and intent of the adversary, for example, financial gain, gaining acceptance in the hacker community, hacktivism, or espionage.

##### Technology component
Highlights the relationships between the core features: capability and infrastructure. The capability and infrastructure describe how the adversary operates and communicates.

##### Conclusion
The Diamond Model is a scientific method to improve the efficiency and accuracy of intrusion analysis. With this in your arsenal, you will have opportunities to leverage real-time intelligence for network defence and predict adversary operations.

### MITRE
##### Introduction to MITRE
Mitre ATT&CK -> ATT&CK means: Adversarial Tactics, Techniques & Common Knowledge.

##### Basic Terminology
**APT (Advanced Persistent Threat) -** is a stealthy threat actor, typically a nation state or state-sponsored group, which gains unauthorised access to a computer network and remains undetected for an extended period.
This can be considered a team/group (threat group), or even country (nation-state group), that engages in long-term attacks against organisations and/or countries. The term 'advanced' can be misleading as it will tend to cause us to believe that each APT group all have some super-weapon (i.e. a zero-day exploit). That is not the case.

TTP (Tactics, Techniques, and Procedures)
- The Tactic is the adversary's goal or objective.
- The Technique is how the adversary achieves the goal or objective.
- The Procedure is how the technique is executed.

##### ATT&CK framework





