##### Career as a Junior Security Analyst
You will be a Triage Specialist. You will spend a lot of time triaging or monitoring the event logs and alerts.

***The responsibilities for a Junior Security Analyst or Tier1 Soc Analyst include:***
- Monitor and investigate the alerts (most of the time, it's a 24x7 SOC operations environment)
- Configure and manage the security tools
- Develop and implement basic IDS (Intrusion Detection System) signatures
- Create tickets and escalate the security incidents to the Tier2 and Team Lead if needed.

***Required qualifications (most common):***
- 0-2 years of experience with Security Operations
- Basic understanding of Networking (OSI Model; TCP/IP)
- Windows/Linux
- Scripting/programming skills are a plus

***Desired certification:***
- CompTIA Security+

***An overview of the Security Operations Center (SOC) Three-Tier Model:***
![[Screenshot 2022-10-06 at 14.20.11.png]]

##### Security Operations Center (SOC)
The core function of a SOC is to investigate, monitor, prevent, and respond to threats in the cyber realm 24/7.

"Security operations teams are charged with monitoring and protecting many assets, such as intellectual property, personnel data, business systems, and brand integrity. As the implementation component of an organization's overall cybersecurity framework, security operations teams act as the central point of collaboration in coordinated efforts to monitor, assess, and defend against cyberattacks." 

**What is included in the responsibilities for the SOC?**
![[Screenshot 2022-10-06 at 14.30.22.png]]

**Preparation and Prevention**
You should stay informed of the current cybersecurity threats. It's crucil to detect and hunt threats, work on a 'Security Roadmap' to protect the organization, and be ready for the worst-case scenario.

Prevention methods include gathering intelligence data on the latest threats, threat actors, and their TTPs (Tactics, Techniques, and Procedures). It also includes the maintenance procedures like updating the firewall signatures, patching the vulnerabilities in the existing systems, block-listing and safe-listing applications, email addresses, and IPs.

**Monitoring and Investigation**
A SOC team proactively uses SIEM (Security Information and Event Management) and EDR (Endpoint Detection and Response) tools to monitor suspicious and malicious network activities. 
As a Security Analyst, you will learn how to prioritize the alerts based on their level: Low, Medium, High, and Critical.

**Response**
After the investigation, the SOC team coordinates and takes actions on the compromised hosts, which involves isolating the hosts from the network, terminating the malicious processes, deleting files, and more.

##### Pyramid of Pain
![[Screenshot 2022-10-06 at 14.56.36.png]]
This concept is being applied to improve the effectiveness of CTI (Cyber Threat Intelligence), Threat Hunting, and Incident Response exercises.

**Hash Values (Trivial)**
The hash value is a numeric value of a fixed length that uniquely identifies data. A hash value is the result of a hashing algorithm.
Most common hashing algorithms: MD5; SHA-1; SHA-2.
A hash is not considered to be cryptographically secure if two files have the same hash value or digest.

Security professionals usually use the hash values to gain insight into a a specific malware sample, a malicious or a suspicious file, and as a way to uniquely identify and reference the malicious artifact.

It is really easy to spot a malicious file if we have the hash in our arsenal. However, as an attacker, it's trivial to modify a file by even a single bit, which would produce a different hash value. With so many variations and instances of known malware or ransomware, threat hunting using file hashes as the IoC (Indicators of Compromise) can become a difficult task.

 **IP Address**
An IP Address is used to identify any device connected to a network. These devices range from desktops, to servers and even cctv cameras. We rely on IP addresses to send and receive the information over the network. But we are not going to get into the structure and functionality of the IP address. 

From a defense standpoint, knowledge of the IP addresses an adversary uses can be valuable. A common defense tactic is to block, drop, or deny inbound requests from IP addresses on your parameter or external firewall. This tactic is often not bulletproof as it's trivial for an experienced adversary to recover simply by using a new public IP address.

One of the ways an adversary can make it challenging to successfully carry out IP blocking is by using Fast Flux.
Fast Flux is a DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies. The purpose of using the Fast Flux network is to make the communication between malware and its command and control server (C&C) challenging to be discovered by security professionals.
The primary concept of a Fast Flux network is having multiple IP addresses associated with a domain name, which is constantly changing.

**Domain Names**




