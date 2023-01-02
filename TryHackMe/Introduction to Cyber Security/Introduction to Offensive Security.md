#### Web Application Security
###### Web application security risks
There are a few main categories of common attacks against web applications.
Few formal categories from OWASP Top 10:
- **Identification and Authentication Failure**
	Identification refers to the ability to identify a user uniquely. In contrast, authentication refers to the ability to prove that the user is whom they claim to be.
	The identification and authentication is prone to different types of weaknesses, which include:
		- Allowing the attacker to use brute force (try many passwords, usually using automated tools, to find valid login credentials).
		- Allowing the user to choose a weak password, which is usually easy to guess.
		- Storing the users' passwords in plain text. If the attacker manages to read the file containing the passwords, we don't want them to be able to learn the stored password.
- **Broken Access Control**
	Access control ensures that each user can only access files related to their role or work. For example, you don't want someone in the marketing department to access (read) the finance department's documents. 
	Example of vulnerabilities related to access control include:
		- Failing to apply the principle of the least privilege and giving users more access permissions than they need.
		- Being able to view or modify someone else's account by using its unique identifier. 
		- Being able to browse pages that require authentication (logging in) as an unauthenticated user.
- **Injection**
	An injection attack refers to a vulnerability in the web application where the user can insert malicious code as part of their input. One cause of this vulnerability is the lack of proper validation and sanitization of the user's input.
- **Cryptographic failures**
	Cryptography focuses on the processes of encryption and decryption of data. Encryption scrambles cleartext into ciphertext.
	In other words, encryption ensures that no one can read the data without knowing the secret key. Decryption converts the ciphertext back into the original cleartext using the secret key.
	Examples of cryptographic failures include:
		- Sending sensitive data in clear text, for example, using HTTP instead of HTTPS. HTTP is the protocol used to access the web, while HTTPS is the secure version of HTTP.
		- Relying on a weak or old cryptographic algorithm.
		- Using default or weak keys for cryptographic functions. 

#### Operating System Security
###### Introduction to Operating System Security
When we talk about security, we should think of protecting three things:
- Confidentiality - you want to ensure that secret and private files and information are only available to intended persons.
- Integrity - it is crucial that no one can tamper with the files stored on your system or while being transferred on the network.
- Availability - you want your laptop or smartphone to be available to use anytime you decide to use it.
				![[Screenshot 2022-08-22 at 11.13.25.png]]

**Authentication and weak passwords**

**Weak file permissions**
Proper security dictates the principle of least privilege. In a work environment, you want any file accessible only by those who need to access it to get work done, you don't want to share such files publicly.
That's the principle of least privilege, or in simpler terms, "who can access what?".
Weak file permissions make it easy for the adversary to attack confidentiality and integrity. They can attack confidentiality as weak permissions allow them to access files they should not be able to access. Moreover, they can attack integrity as they might modify files that they should not be able to edit.

**Access to malicious programs**
Depending on the type of malicious program, it can attack confidentiality, integrity, and availability.
Some type of malicious programs give the attacker access to your system. Consequently, the attacker would be able to read your files or even modify them.
Some types of malicious programs attack availability. One such example is ransomware. Ransomware is a malicious program that encrypts the user's files. Encryption makes the file(s) unreadable without knowing the encryption password. The attacker offers the user the ability to restore availability, they would give the encryption password if the user is willing to pay the "ransom".

#### Network Security
Network Security refers to the devices, technologies, and processes to protect the confidentiality, integrity, and availability of a computer network and the data on it.
Network Security consists of different hardware and software solutions to achieve the set security goals. Hardware solutions refer to the devices you set up in your network to protect your network security. 

**Firewall -** allows and blocks connections based on a predefined set of rules. It restricts what can enter and what can leave a network.

**Intrusion Detection System (IDS) -** an IDS detects system and network intrusions and intrusion attempts. It tries to detect attackers' attempts to break into your network.

**Intrusion Prevention System (IPS) -** an IPS blocks detected intrusions and intrusion attempts. It aims to prevent attackers from breaking into your network.

**Virtual Private Network (VPN) -**  ensures that the network traffic cannot be read nor altered by a third party. It protects the confidentiality and integrity of the sent data.

**Antivirus software -** detect malicious files and block them from executing.

**Host firewall -** is a program that ships as part of your OS, or it is a program that you install on your system. MS Windows includes Windows Defender Firewall, and MacOS includes an application firewall; both are host firewalls.

**Methodology**
Breaking into a target network usually includes a number of steps. According to Lockheed Martin, the Cyber Kill Chain has seven steps:
1. ***Recon -*** short for reconnaissance, refers to the step where the attacker tries to learn as much as possible about the target. Information such as the types of servers, operating system, IP addresses, names of users, and email addresses, can help the attack's success.
2. ***Weaponization -*** refers to preparing a file with a malicious component, for example, to provide the attacker with remote access.
3. ***Delivery -*** means delivering the "weaponized" file to the target via any feasible method, such as email or USB flash memory.
4. ***Exploitation -*** when the user opens the malicious file, their system executes the malicious component.
5. ***Installation -*** install the malware on the target system.
6. ***Command & Control (C2) -*** the successful installation of the malware provides the attacker with a command and control ability over the target system.
7. Actions on Objectives - after gaining control over one target system, the attacker has achieved their objectives. One example objective is Data Exfiltration (stealing target's data).

#### Introduction to Defensive Security
###### Intro to Digital Forensics
Digital Forensics is the application of computer science to investigate digital evidence for a legal purpose.
*Digital Forensics is used in two types of investigations:*
1. *Public-sector investigations* refer to the investigations carried out by government and law enforcement agencies. They would be part of a crime or civil investigation.
2. *Private-sector investigations* refer to the investigations carried out by corporate bodies by assigning a private investigator, whether in-house or outsourced. They are triggered by corporate policy violations.

**Digital Forensics process**
1. *Acquire the evidence -* collect the digital devices such as laptops, storage devices, and digital cameras.
2. *Establish a chain of custody -* fill out the related form appropriately. The purpose is to ensure that only the authorized investigators had access to the evidence and no one could have tampered with it.
3. *Place the evidence in a secure container -* you want to ensure that the evidence does not get damaged. In the case of smartphones, you want to ensure that they cannot access the network, so they don't get wiped remotely.
4. *Transport the evidence* to your digital forensics lab.

At the lab, the process goes as follows:
1. Retrieve the digital evidence from the secure container.
2. Create a forensic copy of the evidence. The forensic copy requires advanced software to avoid modifying the original data.
3. Return the digital evidence to the secure container. You will be working on the copy. If you damage the copy, you can always create a new one.
4. Start processing the copy on your forensics workstation.

More generally, Digital Forensics includes:
- proper search authority. Investigators cannot commence without the proper legal authority.
- Chain of custody. This is necessary to keep track of who was holding the evidence at any time.
- Validation with mathematics. Using a special kind of mathematical function, called a hash function, we can confirm that a file has not been modified.
- Use of validation tools. The tools used in Digital Forensics should be validated to ensure that they work correctly. For example, if you are creating an image of a disk, you want to ensure that the forensic image is identical to the data on the disk.
- Repeatability. The findings of digital forensics can be reproduced as long as the proper skills and tools are available.
- Reporting. The digital forensics investigation is concluded with a report that shows the evidence related to the case that was discovered.




