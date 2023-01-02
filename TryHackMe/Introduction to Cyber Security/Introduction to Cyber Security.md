#### Introduction to Defensive Security
Offensive security focuses on one thing: breaking into systems.
Breaking into systems might be achieved through exploiting bugs, abusing insecure setups, and taking advantage of unenforced access control policies, among other things.
Red Teams and Penetration Testers specialize in offensive security.

Defensive Security is somewhat the opposite of offensive security, as it is concerned with two main tasks:
1. Preventing intrusions from occurring
2. Detecting intrusions when they occur and responding properly.

Blue Teams are part of the Defensive Security landscape.

Some of the tasks that are related to defensive security include:
- user cyber security awareness: training users about cyber security helps protect against various attacks that target their systems.
- documenting and managing assets: we need to know the types of systems and devices that we have to manage and protect properly.
- updating and patching systems: ensuring that computers, servers, and network devices are correctly updated and patched against any known vulnerability.
- setting up preventive security devices: firewall and intrusion prevention systems (IPS) are critical components of preventive security. Firewalls control what network traffic can go inside and what can leave the system or network. IPS blocks any network traffic that matches present rules and attack signatures.
- Setting up logging and monitoring devices: without proper logging and monitoring of the network, it won't be possible to detect malicious activities and intrusions. If a new unauthorized device appears on our network, we should be able to know.

#### Areas of Defensive Security
**Security Operations Center (SOC)**
A SOC is a team of cyber security professionals that monitors the network and its systems to detect malicious cyber security events.
*Some of the main areas of interest for a SOC are:*
- *Vulnerabilities -* whenever a system vulnerability is discovered, it is essential to fix it by installing a proper update or patch. When a fix is not available, the necessary measures should be taken to prevent an attacker from exploiting it. Remediating vulnerabilities are not necessarily assigned to the SOC.
- *Policy violations -* we can think of a security policy as a set of rules required for the protection of the network and systems. 
- *Unauthorized activity -* a SOC needs to detect such an event and block it as soon as possible before further damage is done.
- *Network intrusions -* an intrusion can occur when a user clicks on a malicious link or when an attacker exploits a public server. Either way, when an intrusion occurs, we must detect it as soon as possible to prevent further damage.

**Threat Intelligence**
In this context, Intelligence refers to information you gather about actual and potential enemies. A threat is any action that can disrupt or adversely affect a system. Threat Intelligence aims to gather information to help the company better prepare against potential adversaries. The purpose would be to achieve a threat-informed defense. 
Example adversaries include a nation-state cyber army working for political reasons and a ransomware group acting for financial purposes.

Intelligence needs data. Data has to be collected, processed, and analyzed. Data collection is done from local sources such as network logs and public sources such as forums. Processing of data aims to arrange them into a format suitable for analysis. The analysis phase seeks to find more information about the attackers and their motives; moreover, it aims to create a list of recommendations and actionable steps.

Learning about adversaries allows you to know their tactics, techniques, and procedures. As a result of Threat Intelligence, we identify the threat actor (adversary), predict their activity, and consequently, we will be able to mitigate their attacks and prepare a response strategy.

**Digital Forensics and Incident Response (DFIR)**
Digital Forensics is the application of science to investigate crimes and establish facts. With the use and spread of digital systems, such as computers and smartphones, a new branch of forensics was born to investigate related cimes: computer forensics, which later evolved into, Digital Forensics.

In defensive security, the focus of digital forensics shifts to analyzing evidence of an attack an its perpetrators and other areas such as intellectual property theft, cyber espionage, and possession of unauthorized content. 
Consequently, digital forensics will focus on different areas such as:
- *File System -* analyzing a digital forensics image (low-level copy) of a system's storage reveals much information, such as installed programs, created files, partially overwritten files, and deleted files.
- System memory - if the attacker is running their malicious program in memory without saving it to the disk, taking a forensic image (low-level copy) of the system memory is the best way to analyze its contents an learn about the attack.
- *System logs -* each client and server computer maintains different log files about what is happening. Log files provide plenty of information about what happened on a system. Some traces will be left even if the attacker tries to clear their traces.
- *Network logs -* logs of the network packets that have traversed a network would help answer more questions about whether an attack is occurring and what it entails.

**Incident Response**
An incident usually refers to a data breach or cyber attack; however, in some cases, it can be something less critical, such as a misconfiguration, an intrusion attempt, or a policy violation.
Examples of a cyber attack include an attacker making our network or systems inaccessible, defacing (changing) the public website, and data breach (stealing company data).
Incident Response specifies the methodology that should be followed to handle such a case. The aim is to reduce damage and recover in the shortest time possible. Ideally, you would develop a plan ready for Incident Response.
*The four major phases of Incident Response process are:*
1. *Preparation -* this requires a team trained and ready to handle incidents. Ideally, various measures are put in place to prevent incidents from happening in the first place.
2. Detection and Analysis - the team has the necessary resources to detect any incident; moreover, it is essential to further analyze any detected incident to learn about its severity.
3. *Containment, Eradication, and Recovery -* once an incident is detected, it is crucial to stop it from affecting other systems, eliminate it, and recover the affected systems.
4. *Post-Incident activity -* after successful recovery, a report is produced, and the learned lesson is shared to prevent similar future incidents.

**Malware Analysis**
Malware includes many types, such as:
- Virus is a pliece of code that attaches itself to a program. It is designed to spread from one computer to another; moreover, it works by altering, overwriting, and deleting files once it infects a computer. The result ranges from the computer becoming slow to unusable.
- Trojan Horse is a program that shows one desirable function but hides a malicious function underneath.
- Ransomware is a malicious program that encrypts the user's files. Encryption makes the files unreadable without knowing the encryption password. The attacker offers the user the encryption password if the user is willing to pay a "ransom".

Malware Analysis aims to learn about such malicious programs using various means:
1. ***Static Analysis*** works by inspecting the malicious program without running it. Usually, this requires solid knowlege of assembly language.
2. ***Dynamic Analysis*** works by running the malware in a controlled environment and monitoring its activities. It lets you observe how the malware behaves when running.
