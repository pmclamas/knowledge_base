> Cybersecurity involves everyone and every entity, from you and your neighbours, to organisations, to companies, to governments.

Along with practicing personal security, organisations and businesses also need to do their part to implement the right protections.
Cybersecurity is the field of study and practice that responds to these challenges as technology evolves:
In a formal definition by CISCO: "Cybersecurity is the practice of protecting systems, networks, and programs from digital attacks."
Digital attacks can cover a whole range from fraudulent emails to a targeted shutdown of a website's traffic. Defences against these attacks, must be learned and implemented at all levels.

##### The CIA triad (Confidentiality, Integrity, Availability)
Nearly all information security policies trace back to this model.
- **_Confidentiality_ -** refers to protecting private information from eyes that shouldn't have access to it. Confidentiality is the need to enforce access - who can see the info, and who shouldn't.
	Some of the ways confidentiality is managed are:
		- keeping levels of access and setting permissions
		- encrypting data and files
		- requiring multi-factor authentication
- **_Integrity_ -** refers to data integrity. We need security controls that protect data from being changed or deleted. We must also ensure that the damage can be reversed if data was changed accidentally or by the wrong person.
	Some techniques related to integrity are:
		- keeping backups of the data in its correct state, and logging versions;
		- using cryptography to securely check for changes
		- keeping track of digital signatures to prove integrity of data.
- **_Availability_ -** refers to data being consistently, reliably available to those authorised. How is this accomplished? Always monitoring servers and networks; maintaining hardware and software; having a plan for disaster recovery.

##### The cybersecurity industry
Security roles are no longer just the hacker stereotype of cracking into systems and writing code all the time.
[Security Engineering:]
- **Information security -** protects data in any form from being accessed, modified, shared, or deleted by the wrong people.
- **Network security -** is concerned with the network infrastructure of an organisation that guards against unauthorised access or data from being intercepted.
- **Application security -** refers to implementing measures that defend an application (mobile, desktop, web) from attack, including both software and hardware solutions. Examples: secure coding, the use of antivirus and firewalls, and encryption.
- **Cloud security -** refers to the field of making sure resources uploaded into the cloud are secure. Companies and users are constantly are constantly moving more resources into the cloud, and professionals in this field need to be familiar with implementing security in this environment.
- **Cryptography -** focuses on methods to hide and unhide information so that data is only readable ir usable by authorised people. This requires familiarity with all types of encryption and hashing algorithms.
- **Critical infrastructure security -** is defending physical systems that are becoming more digital/networked, such as energy grids, hospitals, water and waste systems, and even schools. Among the issues that come up are natural disasters and outages.

#### Governance and compliance (non technical)
It's critical to understand laws and regulations for security. This has implications on the security operations for all organisations. 
Compliance refers to making sure an organisation enforces certain policies, and continuously auditing as well. This is becoming an increasingly important area of work. While these roles might not require programming knowledge, these roles require foundational knowledge of cybersecurity as well as all the laws and regulations that impact a particular industry.

**Risk management & Threat Intelligence**
No system will ever be perfect, and there will always be risk, so this area of work is about managing that risk.
*How is risk managed?* Through identifying risks, assessing the likelihood and potential threat of security vulnerabilities, and finding the most cost-effective and efficient security measures.
**_Threat Intelligence_** is the continuous gathering of knowledge of possible attacks. Intelligence could look like knowing the motivations behind attacks, what the scale of attacks could be, and what vectors that might use. These roles often intersect with Data Science and Machine Learning because of the need to process all this information.

**Security Operations**
People who work in this area responsible for implementing security principles, monitoring for incidents, and recovering from disasters. They work closely with everyone under the security umbrella to:
- detect when something has gone wrong;
- implement preventive measures against cyber attacks;
- make sure there are backups in case a system is compromised and data is lost;
- track changes to a system;
- come up with disaster recovery plans in advance;
- create documents and organisation policies for all the above.

**Education**
This domain acknowledges that the most securely designed technologies are only as strong as the people who use them.
User education teaches best practices for people to protect themselves against cyber threats. Security training also happens in large organisations, where employees are educated and updated on the organisation's security policies and practices.
This domain can also include the career development and training of new security professionals as well.

With the world as connected as it is, cybersecurity is about protecting people as much as it is about protecting computers. People are fallible, and have vulnerabilities that can be exploited: emotional manipulation and social engineering are powerful tools, used by hackers to gain access to secure systems.
With computers so integrated into our lives, it's crucial that we protect them. In cybersecurity, we must learn from our mistakes, applying the lessons learned in the past to prevent attacks in the future.
This is the domain of security researchers and ethical hackers: finding and fixing vulnerabilities before they can be exploited, and helping to make us and our computers as safe as possible.

#### Security standards, regulations, and frameworks
Regulations and frameworks have been developed to ensure that the organisations which handle our data have a responsibility to do so securely and ethically, and have guidelines for how to do so.
- **_Standard and best practices_** are generally agreed-upon rules for maintaining security, generally within an organisation. Standards may come as individual recommendations, or as part of a framework.
- **_Regulations_** are sets of standards that organisations must follow, generally due to legal obligation, and define the responsibilities organisations have.
- **_Frameworks_** are sets of standards and best practices that organisations can use to ensure their overall security. These are optional, but good practice for organisations to follow.

#### Cybercrime

**What is cybercrime?**
Cybercrime is, generally speaking, any crime that makes use of or targets a computer. When we think of cybercrime, wew might first think of evil viruses on our computer and hackers getting into company data.
_Other types of cybercrime_:
- _Extortion_ - commonly in the form of ransomware, where attackers take control of a system and demand payment from the target.
- _Fraud_ - a broad category including identity theft, scams, retail fraud, phishing, and more.
- _Theft_ - stealing information during a data breach, or theft of services and resources, such as using other people's computers to mine cryptocurrency.
Cybercrimes don't always fit clearly into a single category.

**Digital forensics**
Is the process of gathering the evidence of a cybercrime in a way that the evidence can be used in a court of law. It is a broad field with specializations, including:
- _Disk Forensics_ 
- _Memory Forensics_  
- _Network Forensics_  
- _Mobile Forensics_ 
- _Cloud Forensics_ 
The most important aspect of digital forensics is maintaining a chain of custody to prove that the data and evidence have not been modified or tampered with.
Simply gathering evidence is not enough; the evidence must hold up to legal scrutiny in order to be useful, and conducting a forensic investigation incorrectly can destroy the original evidence.

**The NIST framework**
Is an optional framework originally developed to protect critical infrastructure from cyber threats.
_The NIST framework consists of five main elements:_
- _Identify_ and understand the threats and risks the organisation is likely to face.
- _Protect_ the organisation's assets from those threats and risks.
- _Detect_ incidents, such as cyberattacks or other events.
- _Respond_ to incidents, preventing further damage.
- _Recover_ from incidents, evaluating how to prevent reoccurrence cleaning up any damage that occurred.

Frameworks are not generally a one-size-fits-all solution to cybersecurity. Instead, they are a starting point for organisations to customize to their needs and threats. Frameworks and regulations are meant to work together, helping the organisations we rely on to remain secure, and protecting our information from those who would misuse it.

#### Introduction to cyber threats
**_Malware_** is malicious code inserted into a system to cause damage or gain unauthorised access to a network. Any type of malware can greatly compromise the security principles of _Confidentiality_, _Integrity_, or _Availability_.

**_Adware_** is unwanted software designed to throw advertisements on your screen. While not overly malicious on the surface, sometimes adware can come bundled with other, more harmful malware.

**_Virus_** is a malicious self-replacing application that attaches itself to other programs and executables without the permission of the user. It's possible a downloaded virus could alter or delete data on the computer.
If the virus was able to access or alter data, the confidentiality and integrity of that data is now in question.

**_Worm_** is self-replicating code that copies itself from computer to computer without user intervention. This worm could be just as dangerous as a vírus. The worm could also replicate so much that it overloads your client's system. By doing this, the worm could bring down the system and violate availability.

**_Trojan horse_**, sometimes just called a "Trojan", does more than just monitor what's happening on a system. Trojans are a type of contained, non-replicating malware that disguises itself as legitimate software in order to allow scammers and hackers access to a user's system.

**_Spyware_** is malicious code downloaded without a user's authorization which is used to steal sensitive information and relay it to an outside party in a way that harms the original user. If the spyware contained a keylogger, a threat actor could be recording everything your client types.
While spyware usually isn't used to alter data, it definitely violates the principle of confidentiality.

**_Rootkits_** are a collection of malicious programs that secretly provide continued, privileged access to a system for an unauthorised user. A rootkit can create a backdoor on a computer to let a hacker in. This rootkit was able to gain admin access to this computer, and it will be increadibly hard to remove.
This means that a malicious, third-party somewhere has admin access to this computer and its data. This is a nightmare scenario for the confidentiality and integrity of your client's system, while some specialised tools can remove a rootkit, it isn't easy.

> While spyware is characterized by attackers observing actions on your computer, a rootkit also gives the attackers continued, privileged access to a user's computer.

**_Ransomware_** is one of the largest cybersecurity threats facing industries today. Blocking a user's access to data greatly threatens availability. While availability might not seem important, it can be devastating to some, like hospital or flight systems.

**_FIleless malware_** is a type of malware that "lives of the land" and uses legitimate tools and the user's operating system to perform malicious activities like privilege escalation, data collection, and more. It's incredibly hard to detect and almost always missed by antivirus software.
Unlike a Trojan Horse, fileless malware is not pretending to be legitimate software, it actually is a part of legitimate software. Fileless malware hides itself within the code of legitimate software, often altering existing code to make it malicious.

**_Phishing_** is one of the most well-known types of cyber attacks. No matter what technical controls are in place to secure a system, humans within the system are still hackable. The practice of tricking humans to get important data or access is also known as **_Social Engineering_**.

##### SQL Injection 
When you provide your credentials to authentication in a website, the server will take your input and compare it against user data inside a database. That step of checking the input against the database can be abused by attackers.
Through a cleverly and carefully crafted input an attacker can inject code directly into the database query, getting precious data!
	_What are SQL Injections?_
A SQL Injection is a common vulnerability affecting applications that use SQL as their database language. A hacker can use their knowledge of the SQL language to cleverly construct text inputs that modify the backend SQL query to their liking. They can force the application to output private data or respond in ways that provide intel.

Using the following injection techniques, threat actors may be able to access information they shouldn't have, change database records, or even take complete control of the system:
- _Union-based injections:_ a union-based injection leverages the power of the SQL keyword UNION. UNION allows us to take two separate SELECT queries and combine their results.
- _Error-based injections:_ in an error-based injection, an attacker writes a SQL query to force the appplication to return an error message with sensitive data.
- _Boolean-based injections:_ involve SQL statements that can confirm TRUE/FALSE questions about the database. When using this method, the attacker take note of the difference in the web response (changes in html, http response code, or other web session data) when the result of their question is true or false. Boolean injections are often used to figure out the name of a database table (possibly to build up for an union-based injection), manipulating one query at a time to confirm one character at a time.
- _Time-based injections:_ not all SQL injections will provide visible output. A time-based injection makes use of several built in SQL functions, such as SLEEP() and BENCHMARK(), to cause visible delays in an application's response time. While the output of a command isn't visible, delays in the response time can be used to infer some information.
- _Out-of-band SQL injections:_ are generally the rarest and most difficult injections to execute for attackers. Unlike the other methods, which return the results via the web application, an out-of-band injection will leverage a new channel to retrieve information from a query. Generally, these SQL injections will cause the database server to send http or DNS requests containing SQL query results to an attacker-controlled server. From there, the attacker could review the log files to identify the query results. 

Again, these injections are extremely difficult to execute. They rely on permissions to database functions that are most often disabled, and would have to bypass firewalls that might stop requests to the attacker's server.

**SQL Injection prevention**
There are two main methods for preventing injection attacks:
_Sanitization:_ is the process of removing dangerous characters from user input.
When it comes to SQL injections, we would want to escape dangerous characters such as: ´; \-- 
These sorts of characters can allow attackers to extend queries to output more data from a database.
While this does provide a layer of protection, this method isn't perfect. If a user finds a way to bypass your sanitization process, they can easily inject data into your system.
Additionally, depending on your query, removing certain characters may have no effect!
_Prepared statements:_ writing prepared statements in backend code is a common, reliable, and secure solution against SQL injections. Prepared Statements are nearly foolproof. We provide the database the query we want to execute in advance. First, the database processes our query. Then we pass in the parameters/user input. Any input, regardless of whether the content has SQL syntax, is then treated only as a parameter and will not be treated as SQL code.
In addition to providing added security, prepared statements also make queries for more efficient.

##### Cross-site Scripting (XSS) & Cross-site Request Forgery (CSRF)
Cross-site Scripting (XSS), is a common web application vulnerability that occurs when a web application returns unsanitized input to the frontend of an application. In a XSS attack, an attacker takes advantage of this vulnerability by inputting malicious code, generally in the form of Javascript, through the browser.
This can lead to the attacker stealing information from a user, redirecting users to malicious pages, or taking control of the browser.

The three categories of XSS attacks are _Stored XSS_, _Reflected XSS_, and _DOM-based XSS_, which differ in how the payload is stored and executed.
- _Stored XSS_ attacks are generally considered the most serious. A Stored XSS vulnerability occurs when a web server saves an attacker's input into its datastores. Because this input is saved, it may be harder for a user to detect. In a worst case scenario, this input will be saved, and then returned to numerous victims.
- _Reflected XSS_ occurs when a user's input is immediately returned back to the user. this return may come in the form of an error message, a pop up, or a search term. In these instances, the payload is never stored by the server. Rather, it exists as a value in the URL or Request. Despite this, these payloads still pose a risk to users. Through social engineering, an attacker could spread their payload to unsuspecting victims.
- _DOM-based XSS_ is used to help scripts and the underlying webpage interact. However, when user input is interpreted by the DOM, an attacker is able to inject arbitrary code. These types of vulnerabilities do not cause any changes in how the server responds. Rather, these attacks are completely client-side. For example, a web page may use client-side javascript to customize a welcome page, displaying their name based on a value in the URL. Depending on how the javascript runs, an attacker may be able to replace the name value with a malicious script. If a victim loaded the page with the attacker's code, the vulnerable javascript may execute the code!

**Identifying XSS vulnerabilities**
As with any vulnerability, it is important that we investigate any potential input areas. When looking at the application, consider all possible fields. Comments, usernames, custom settings, and parameters all provide great starting points. Once we have identified a potential inject point, we can begin testing various inputs to create a proof-of-concept payload (PoC). A PoC payload will demonstrate that an issue exists, without causing damage.
The most basic PoC payload: `<script> alert(1); </alert>`
If a web server is not properly sanitizing user input, this will return a pop-up box.
If this payload does not work, that does not necessarily mean the system is secure. If a blocklist is in effect your request may be blocked, or your script tags could be removed. If this happens, we can look to alternative mechanisms to execute javascript.
In fact, there are numerous ways we can execute code, without even using a script tag:
```<img src="x" onerror=alert(1);>``` 
```<b onmouseover=alert(1)> Click me! </b>>```
`<body onload=alert('test1')>`

**Preventing XSS vulnerabilities**
Similar to SQL Injections, XSS is preventable with both application-level firewalls and sanitization. Similar to the SQL Injections, firewalls should be used to aid defense, but should not be used as your only line of defense.
- _Sanitization_ is the process of removing/replacing problematic characters with safe versions. We can generally succeed in preventing XSS attacks by removing characters such as <, >, ", =, and potentially dangerous keywords. Rather than removing characters, we can also replace them with HTML-encoded versions of the characters. This allows us to retain the characters, but remove their capacity to affect the page's HTML. It is important to consider all potential avenues for an attack.

**Cross-site Request Forgery (CSRF)**
Is another class of vulnerability focused on poor session controls and session management, when we log into a website, we create an active user session, and this session allows us to interact with our profile, and the site in general. By sending the right request, we can change our password, email, etc.
In some cases, the way these sessions, and the requests we send, are handled is flawed. Sometimes, the requests sent by an application aren't unique. As such, it's possible for an attacker to craft a special request and send that to a user. If the user interacts with the crafted request, and sessions aren't handled properly, an attacker may be able to make changes on behalf of a user.
If the developers don't consider the impact of cross-site request forgery attacks, a threat actor may be able to create a new password link and send it to the user. When the user opens the link, they would initiate the password change, but with the attacker-supplied password! This would allow a hacker to take over their account!
Because the request considers nothing but the current session, a user would have their password changed.

**Preventing CSRF**
While the impacts of CSRF can be large, they are relatively easy to mitigate. One of the simplest ways to prevent these attacks is to add a CSRF token. This token is a unique value that is added to each request. This value is dynamically generated by the server and used to verify all requests. Since this value is unique for every request, and constantly changing, it is nearly impossible for an attacker to pre-create the URL/Requests for an attack.
While a CSRF token can prevent many malicious requests, it can still fail. If an application is vulnerable to XSS, a hacker could use their XSS attack to extract this token! In some cases, we may want to manually enter additional information prior to a critical request. For example, prior to changing a username, email, or password, we may want the user to enter their current password. By ensuring the request has the correct password, we can ensure that an attacker isn't able to compromise a user, even with XSS.

**Conclusion**
While Cross-site Scripting and Cross-site Request Forgery both pose a serious risk to users,  and the systems they interact with, developers can take many steps to prevent these attacks. However, when developers fail, attackers can execute arbitrary code, steal information, and cause serious harm. Through careful control of sessions, we can prevent cross-site request forger attacks.
And through careful handling of data and sanitization, we can easily prevent cross-site scripting attacks.

##### Zero-day and DDoS attacks
**Zero-day attacks -** A "zero-day" vulnerability is a newly-discovered software bug that a developer was not aware of before the software was released. Therefore, after it is discovered, the developer has "zero" days to patch it before it can be exploited. When a "zero-day attack" occurs, the vulnerability quickly becomes known and is patched by the developer.
Because zero-days are difficult to discover and exploit, they are more often leveraged by nation-state actors, who have the resources and infrastructure to find and exploit these vulnerabilities.
The vast majority of cyber attacks exploit existing vulnerabilities. These vulnerabilities are catalogued and numbered as CVEs (Common Vulnerabilities and Exposures), and are maintained in places like the Mitre Corporation's database or the National Vulnerability Database (NVD).

**DDoS (Distributed Denial of Service) -** A DDoS attack is when an attacker attempts to make a resource, such as a website's servers, go offline by overwhelming it with web traffic.
How does an attacker do this? They make requests to a resource with a large number of computers, overwhelming the resource and making it run slower and slower until, eventually, it goes offline entirely.
Because an attacker must use a large number of computers, the attack is "distributed" across multiple devices. The goal is to knock the resource offline so that it "denies service".
But where does an attacker get all of these computers from? Large websites are equipped to handle thousands of visits per day, so it takes a lot of web traffic to overwhelm them. This traffic comes from _botnets_.
*Botnets* are "robot networks" made up of computers infected by malware. These botnets can be made up of millions of bots, and can even include IoT devices. A single attacker can spread malware to many devices, and then use all of those devices to act together, often times without the victims ever knowing that their devices are infected. Because botnet services can be rented out to other cybercriminals for specific attacks, anyone with the money to rent a botnet on the dark web, can carry out a DDoS attack, leveraging the power of millions of computers making DDoS attacks even more powerful.

**Types of DDoS attacks**
Network connections are defined by layers with each layer responsible for a different part of data transmission. Different types of DDoS attacks target different network layers, specifically, layers 3 (Network), 4 (Transport), and 7 (Application Layers). Different DDoS attacks target different layers in different ways.
For example, one attack that targets the application layer is called "HTTP Flooding". This is because the attacker sends lots of HTTP requests, the kind of requests your browser makes when you visit a webpage. In effect, it is like refreshing a website over and over again, making a server load content repeatedly until it becomes overwhelmed.
On the other hand, "SYN Flooding" targets the Transport Layer by taking advantage of something called a TCP Handshake. Basically, it asks the server to wait for confirmation of a connection, but then never gives that confirmation.

**Fighting DDoS**
There are a number of ways that websites try to defend against DDoS attacks, for example, by ratew-limiting: limiting the number of requests a server will accept in a single time. CAPTCHAs can also provide some protection. Theoretically, a CAPTCHA can determine whether a user is a human or a "bot", allowing legitimate web traffic to attempt to log in while blocking malicious automated traffic. In general, it is difficult to guard against DDoS attacks. This is why websites seek protection from organisations such as Cloudfare, which provides protection against DDoS attacks by sitting between the server and the client, and forwarding legitimate traffic to the server while hiding malicious traffic.

#### Introduction to cryptography, authentication, and authorization
**Why learn about Cryptography?**
Cryptography is used almost everywhere online. The HTTPS that comes before many domain names indicate that encryption is being used to exchange data between the browser and the server. That data could be login credentials, device type, or sensitive personal information.
**Authentication, Authorization, Non-repudiation**
According to CISA, "Authentication and Authorization go hand in hand". Users must be authenticated before carrying out the activity they are authorized to perform. Security is strong when the means of authentication cannot later be refuted - the user cannot later deny that he performed the activity. This is known as non-repudiation.
**Practical Cryptography: Encryption**
_How do we use encryption to send and store data securely?_
Cryptography is the science of hiding data and making it available again. In cryptography, hiding data is called encryption and unhiding it's called decryption. When data is securely exchanged, it's first encrypted by the sender, and then decrypted by the receiver using a special key.
_How do computers encrypt and decrypt?_
The answer is the XOR operation, a key component of many complex algorithms used today, such as AES, the encryption algorithm used by the US government to protect classified information.
_What is XOR?_
XOR is an operation that compares two bits and returns True (1) if only one of the bits is 1, and returns False (0), if the bits are the same value (both 0 or both 1).
XOR gives the same string back if you perform XOR on it twice. For example, if you XOR 1100 with the key 1001, it returns 0101, and if you XOR 0101 with the same key, 1001, you get 1100 again.
XOR encryption takes advantage of this reflexive property, so whatever key we XOR with a binary sequence to encrypt it, we can use that same key to decrypt the sequence.
XOR is the foundation of all the common encryption methods.

**Types of Encryption**
- _Symmetric encryption:_ uses the same key to both encrypt and decrypt data.
	Both the Caesar Cipher and basic XOR encryption, uses the same key to encrypt and decrypt data. Symmetric Encryption is the fastest way to encrypt data, and the most common for sending large chunks of data, however, it has one major vulnerability: if you send someone your key, then it's in a form that any other person can read. That means your data is vulnerable to being stolen.
- _Asymmetric encryption:_ uses two different keys to encrypt and decrypt data. 
	Differs from symmetric encryption in one way: instead of one key, you have a key pair. A key pair is made up of a public key and a private key. The public key can be given to anyone and is only used to encrypt data. The private key is kept secret and is only used to decrypt data.
	If you want to receive an encrypted message from someone, you would first generate a key pair and give them the public key. Then, they would write a message and encrypt it using the public key you have gave them. Finally, they would send you the message and you would decrypt it with your private key. You never share your private key with anyone, including the recipient, so it never has a chance to be stolen. Having two keys makes sure you are the only person who can decrypt and read those messages since you are the only one with the private key.
	If you wanted to send a message back to the original sender they would generate a key pair as well, provide you with their public key, and you would repeat the process.
	Asymmetric encryption is the most secure way to transmit data; however, it is slower and more complex than symmetric encryption. Therefore, it is primarly used to exchange smaller pieces of data.
	There are a wide variety of asymmetric encryption algorithms. The most common is RSA (which is based on the factoring of prime numbers, and is functionally unbreakable if a large enough key is used, although quantum computing could change this).
	Another asymmetric approach is Elliptical Curve Cryptography (ECC).

Note: if you are running a UNIX based operating system such as MacOS or Linux, you can run basic encryption algorithms such as "Rot13" with a single command.

**Practical Cryptography: Hashing**
You can also use cryptography to make sure your data matches what you expect. This is where hashing comes in.
Hashing does not encrypt data. Instead, hashing is a one-way process that takes a piece of data of any size and uses a mathematical function to represent that data with a unique hash value of a fixed size. You cannot compute the original data from its hash.
Because each hash should be unique, hashing allows us to see if changes have been made to documents.
No matter how large or complex a file is, hashing provides a fast, reliable way to compare files and verify their authenticity.
Ideally, hash functions always generate unique values for different inputs. When they don't it's called a hash collision. With modern algorithms like SHA-256, it would take so long to result in a collision that it's functionally impossible. Earlier hashing algorithms, like MD5 and SHA-1, are more likely to result in hash collisions.

Note - it's easy to get the hash value of some types of data. If you are on a Unix-based operating system, open your terminal and type: `echo "Hello world" | shasum -a 256`.
That will give you the SHA-256 hash of the string "Hello world".

_Using hashes to protect data_
Hashes are widely used in order to store passwords in online databases. If passwords are stored in plaintext and a database is breched, so are all of the passwords. However, if they are stored as hash values, even if someone hacks into a website's database, only the password hashes are exposed.
An attacker has no way of "decrypting" a hash value to get the original value.
Attackers can still come up with a list of common passwords, generate hashes, and find which lines in the database match those hashes. Rainbow tables, massive tables of common passwords and password-hash combinations, speed up that process even more. However, it is pratically impossible for an attacker to guess and match the hash of a complex password!

Organisations can further protect hashed information by using something called a 'salt'. A Salt is a secret random string that is combined with a password prior to hashing specifically to defend against the use of rainbow tables.

**Conclusion**
Hashing is a key application of cryptography! A cybersecurity professional uses hashing algorithms to compare files big and small, as well as to protect data.
Cryptography is a dynamic field, with new algorithms being invented, tested, and solved all the time, it is also an essential part of keeping up information security.

##### Authentication & Authorization
**_Authentication_** is the verification of who you are and **_Authorization_** is the verification of what you have the right to do.

**Different Authentication methods**
There are many different kinds of authentication, the most common of which is a password. However, the PIN number you enter when you withdraw money from an ATM, the fingerprint or face ID you use to unlock your phone, and personal information such as your phone number, social security number, or address are all forms of authentication.

**Single-Factor authentication**
Refers to when only one form of authentication is used. Is more common than Multi-Factor Authentication because it is the most convenient for users and involves less engineering. Unfortunately, due to evolving threats against common methods of single-factor authentication, this method is becoming increasingly insecure.
	_Threats to Single-Factor Authentication_
Passwords are the most common type of authentication used in single-factor authentication and are vulnerable to credential stuffing, brute forcing, phishing, social engineering, and malware.
How about PIN codes? There are tools that can be used to disable the maximum number of wrong attempts, and once that is done, a 4-digit PIN codes takes only six and a half minutes to crack on average.
For every method of authentication, there are many ways to bypass it. That's why it's much more secure to use MFA.

**Multi-Factor Authentication (MFA)**
Is the use of multiple types of authentication in order to access a single resource. The most common form of MFA is Two-Factor Authentication (2FA).
MFA can take many forms. For example, instead of sending an OTP in a text message, many organizations utilize app-based codes (like Google Authenticator). These codes regenerate every few seconds so an attacker doesn't have time to brute-force your OTP.

##### How does a website give me access after I log in?
Your web browser submits that information to the server's API to authenticate you. An API is the part of a server that sends and receives data.
_There are 3 main types of API authentication:_
- _HTTP basic auth:_ is the oldest and simplest method of authentication. It simply requires you to send your username and password every time you communicate with the web page. The reason this isn't necessary when you use your browser is because of something called cookies. Cookies store your credentials so that you don't need to send them every time you click on a button.
- _API keys:_ are similar to HTTP basic auth except, instead of a username and password, you use something called an API token. An API token is a unique string of letters and numbers generated for each user. API keys are frequently used by developers to authenticate their own scripts or applications when interacting with another application's API. You can use them to authenticate a script that queries a website for large amounts of data or to authenticate a bot on Discord. API keys have the added advantage of being long and complex to be practical for everyday users to use them to log in, and like the credentials used in HTTP Basic Auth, they are vulnerable to interception when they are submitted for authentication.
- _OAuth:_ sometimes we can sign in with Google, Twitter, LinkedIn, etc. This is possible because of OAuth.
  OAuth tokens are great at defending users against data breaches since they eliminate the need to store passwords. However, OAuth is still vulnerable to attacks. Imagine that an attacker sets up a malicious website and tells users that they must authenticate with OAuth through GitHub. Instead of asking for just an email, the website asks for access to private repositories and secret gists! If a user grants this access to the malicious application, the attacker would have access to all of the user's private information on GitHub.
  All methods of authorization have advantages and vulnerabilities and OAuth is no exception; however it remains a generally secure and convenient way to authenticate yourself on trusted applications.

**Role-Based Access Control (RBAC)**
You have permissions to access certain things (authorization) based on your role/responsibilities (authenticator).
Each user is placed in a role and given access to all of the systems that come with that role. By ensuring that each user has only the access necessary for their role, systems become more secure while streamlining operational efficiency. Implementation is similar in a web application.

##### Introduction to Network Security
**Network basics -** a _network_ is two or more computers or devices that are linked in order to share information.
Networks are broken into different subsets based on their size and function.
- _LAN (Local Area Network) -_ is a smaller network that connects multiple devices in a limited area. Examples of LANs include small offices, a home, or any other network contained within a small area.
- _CAN (Campus Area Network) -_ connects multiple computers and devices over a slightly larger area. In many cases, these types of networks will connect multiple buildings located in the same vicinity.
- _WAN (Wide Area Network) -_ connects multiple computers over a geographically large area. To ensure that computers spread over large regions are able to communicate, companies may use a VPN (Virtual Private Network) to connect systems securely. A VPN can allow systems across large regions to connect and interact with one another on the same network. The whole internet can technically be classified as a WAN!

##### OSI Model
The OSI (Open Systems Interconnection) Model was developed in the 1970s and 1980s. and it is a conceptual model that breaks networking into seven separate layers. Each layer refers to a set of functions that are responsible for specific tasks. The layers start from physical signals all the way up to the web applications we interact with.
Each layer generally only interacts with the layer below it and provides useful tools or information to the layer above it. OSI is used to help us categorize network processes so we can communicate about them during troubleshooting and while improving security.

- **_Layer 1 - Physical :_** the lowest layer of the model, covers how unstructured data is transmitted. Technology such as WiFi, Bluetooth, and cable standards such as CAT5 and CAT6 all operate at this layer. This layer also includes the hardware part of modems, adapters, and repeaters. Fixing errors that occur just at this layer means considering physical damage or interference.

- **_Layer 2 - Data Link:_** covers how data is sent from device to device when they are connected on the same local network. The data link layer includes many functionalities:
	- it structures incoming or outgoing data bits into dataframes.
	- it involves physical addresses of devices, called Media Access Control (MAC) addresses. All devices have a unique 48-bit MAC address where the first 24 bits relate to the manufacturer, and the last 24 bits make it unique to each device.
	- it routes dataframes to the correct physical addresses. A switch keeps track of local devices and their MAC addresses and makes sure dataframes get to the correct physical location.
	- it ensures that the flow of data is synchronized between devices, so data doesn't jam up the memory of a slow receiving physical device. 
	- it detects errors within dataframes. This involves a system of error control.

_{Layers 3 and 4 - in these layers, we begin to see how data is routed between different networks and how transportation protocols function within these layers}_
- **_Layer 3 - Network:_** describes how data packets are routed between wider networks such as the internet. Whereas a dataframe at the data link layers travels to local MAC addresses, a data packet at the network layer is routed from a source IP (Internet Protocol) address to a destination IP address. Think of a data packet as an envelope. IP addresses are assigned to every computer or device connected to the internet, and these addresses are formatted into four numbers each ranging from 0 to 255. At this layer, there are routing protocols designed to help packets get from point A to point B as quickly as possible over the internet.

- **_Layer 4 - Transport:_** refers to how data is actually transferred. The transport layer handles how data is split (segmentation), the rate at which the packets are sent, and how errors are handled if data packets don't make it to the site's server. The most common transport protocols on the internet are TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).

- **_Layer 5 - Session:_** when two computers or devices have started an exchange of information, we call that a session. The session layer is responsible for opening, closing, and maintaining sessions. In terms of opening and closing, the session layer includes authentication and authorization measures. Meanwhile, session management ensures communications occur successfully by providing safeguards in case a connection fails or drops.

- **_Layer 6 - Presentation:_** includes all the methods that convert data into a format usable by an application. This layer handles functions such as encoding/decoding, encryption/decryption, and compression/decompression of files.

- **_Layer 7 - Application:_** this layer includes websites, browsers, email, mobile applications, and how they render internet data so that we can interact with it.

##### TCP/IP model and Implementation
The TCP/IP model is a 4-layered model that makes direct reference to current internet implementations.
**The 4 layers of TCP/IP are:
- **_Application layer -_** this includes the opening and closing of sessions, translating data, and the interaction with content at the application level. Here, there are multiple protocols for web content, email, and accessing files, including HTTP, FTP, SMTP and more.
- **_Transport layer -_** TCP and UDP are the core protocols here. **_TCP_** is a connection-oriented protocol, where a more rigorous acknowledgment between one sender and one receiver must happen before any data can be sent. This protocol also includes flow control and error recovery, and it is used when larger amounts of data need to be sent and timing is less of a concern. **_UDP_** is a more lightweight protocol that does not require a fixed channel between a sender and receiver. It is often used when the amount of data sent needs to be transmitted quickly.
- **_Internet layer -_** this is where IP addressing and routing occur.
- **_Network Access layer -_** sometimes called the Link Layer, this layer encompasses the sending or receiving of network data at the Local Network level.

**Network Protocols: DNS, HTTP, email**
_What are network protocols?_ They are simply a set of standards for devices interacting on the internet. It's important to understand these protocols from the angle of network security. Threat actors often abuse the rules of a protocol to gain access to sensitive information.
**_DNS -_** the Domain Name System (DNS) protocol converts domain names to IP addresses. Think of it as a phonebook for the internet. It's hard to remember an exact IP address when we want to access a website. When we request a URL, our computer sends a DNS request to a DNS server. The server then returns the correct IP addresses to route data.
**_HTTP -_** handles our web requests to servers. HTTP uses a set of verbs, like GET, POST, PUT, and HEAD, to retrieve and send data. Anytime a page is loaded, there are multiple web requests to retrieve content like images, text, and formatting code.
**_IMAP, POP, and SMTP -_** IMAP (Internet Message Access Protocol), and POP (Post Office Protocol) allow users to access emails stored on a remote web server. In IMAP, servers store your email and return copies to you, allowing you to access the same email on multiple devices.
In POP3, however, emails are generally downloaded from the server onto just a single device. 
To send email, the standard is SMTP (Simple Mail Transfer Protocol). 
_How do data packets get routed to these services from the Transport Layer?_
Specific numbers called ports are reserved so that packets for different services can come in at the same time. Think of ports as lanes for network traffic!

**Network Protocols: SSH, SMB, FTP**
**_SSH (Secure Shell) -_** is used to access a remote terminal or Virtual Machine (VM) over a secure connection. IT professionals and engineers use this to help configure and program a system remotely and securely.
**_FTP (File Transfer Protocol) -_** is used to transfer files from one system to another. Modern implementations of FTP can include encryption as well.
**SMB (Server Message Block) -** protocol allows multiple users to interact with a remote system like a file share or printing services. Multiple people can view and modify shared resources and files in a centralized server.

##### Firewalls
**What is a Firewall? -** a Firewall is a tool designed to intercept and assess incoming and outgoing packets. Depending on the types of devices we are protecting, and what we are protecting them from, we may choose to use different types of firewalls.
We can set rules for a firewall to either accept or deny a packet in the network. Those rules can be based on the source IP address of a packet, the details of a network session, or the contents of a packet.
	**_Packet-Filtering firewalls_**
Are the simplest of all firewalls. They do not check content, but can inspect and filter on information like:
- Source IP
- Destination IP
- Destination port numbers on a packet
Because of the simplicity of the rules, packet-filtering firewalls are best-suited:
- within your network
- to control traffic from internal network to internal network.
	**_Circuit-level firewalls_**
Review content related to individual sessions.
Circuit-level firewalls:
- ensure that sessions are properly configured
- identify illegitimate connections
While these may help to prevent malformed sessions from connecting, they might still allow certain threats to pass through. For example, a valid session transferring malware could be allowed as long as the session is established properly.
	**_Stateful Inspection firewalls_**
Maintain a table of active sessions, similar to circuit-level firewalls.
Stateful Inspection firewalls:
- are able to limit activity based on source and destination data, like packet-filtering firewalls.
- attempt to review the contents of active sessions, dropping packets that don't comply with the logged session.
While stateful inspection firewalls have capabilities similar to packet-filtering and circuit-level firewalls, they offer additional protections. By dropping unexpected packets, it is much more difficult for attackers to breach a network.
	**_Application firewalls_**
Offer security in ways that the three types of firewalls above cannot. Using pattern-matching, application firewalls can detect and block much more sophisticated attacks.
Application firewalls:
- utilize application-specific rules to identify malicious traffic.
For example, a firewall may use a pattern designed to identify a specific attack. A request containing the string "UNION SELECT", indicating a potential SQL Injection, may be blocked by an application firewall. In another example, an HTTP request may be passing data to a web server. While the request's IP and session information may appear safe, content sent in individual HTTP requests could pose a danger to the receiving web servers. An application firewall could identify malicious content in HTTP requests and block content.
	**_Next-generation Level Firewall (NGLF)_**
Considered the most advanced firewalls. On top of using all of the above methods, they will also identify additional malicious content in real-time.
Next-generation level firewalls:
- may use Artificial Intelligence, or even global networks, to identify new and emerging threats in real-time.
- are extremely complex.
- usually require a much higher operating cost.

**Conclusion**
While different firewalls offer different pros and cons, each excels in their own setting and maintain their own benefit.
While NGLF's can provide protection other types can't their price and upkeep costs make them less suited for internal use. In many ways, the added protection they provide would be wasted. On the same note, however, a simple packet filtering firewall or circuit level firewall may not be enough protection from external threats if placed on the edge of your network. When working with a firewall, it's extremely important we consider what we are protecting, what we would like to spend, and what the threats we face are.
Finding the right balance of protection and cost is extremely important.

#### Match the best firewall to use for each scenario
You are looking to secure several internal local networks. For security reasons Network1 cannot send packets to Network2 or Network3, regardless of contents. **_- Packet-flitering firewall_**

You are looking to identify malicious sessions within your environment. However, in order to prevent previously identified safe connections, you want the firewall to maintain a record of active connections. **_- Stateful-Inspection firewall_**

You are looking to protect your internal systems from as new and emerging threats. You are concerned about attacks from all over the internet, and not just those you are currently observing. Due to budgetary increases, price is not an issue. **_- Next-generation Level firewall_**

You are looking to protect your web server from attacks on the web application. **_- Application firewall_**

You noticed an issue with malicious sessions in your network and want to stop any sessions not following proper protocol. **_- circuit-level firewall_**

#### Wireless Network Security
Protocols and security measures are keeping up with the advent of wi-fi. With wi-fi, users have experienced an increase in device freedom, but wireless technology carries the risk that we may not physically see who is accessing a network.

**Network segmentation**
Is the basic practice of breaking apart larger networks into smaller, functionally similar networks with different access levels. This improves both security and performance.
In segmenting networks, we ahould consider:
- which assets are we trying to protect?
- who can access which networks?
These questions naturally lead us to access control lists that determine who can connect to which networks.
Often the first place people start is just implementing a guest network that's separated from the rest of the network environment.
Segmentation allows us to balance!
By segmenting our networks, we can also make more strategic use of firewalls as well. We can place stricter firewall rules on the segmented networks we must need to protect.

**Access Point Placement**
It is important we consider both the placement and strength of our access points. Access points are the systems and nodes used to distribute wireless signals. If an attacker can access the network, they may be able to attack the users on the network!
This risk is especially true in places like coffee shops or libraries. It would not be very wise to keep the router in plain sight so that anyone could physically configure it.
If we think about wireless access points that offer wi-fi in different parts of a city, it is network segmentation and administration that tries to ensure people who connect to that large network aren't able to hack into other people's network use.

**Encryption**
All wireless activity should be securely encrypted. Currently, the accepted standard for security is WPA2 (Wi-fi Protected Access 2). WPA2-Personal will require a single password to access wi-fi, while WPA2-Enterprise will require multi-factor authentication.

#### Project: Network monitoring
**Network Traffic Analysis**
When working in cybersecurity, it's common that you may need to review network activity. Whether you're a penetration tester looking for sensitive information in traffic, or a SOC Analyst looking for malicious activity, the ability to analyze network communications is crucial!

**The key to network analysis is filtering out the noise!**

#### Introduction to personal security
**Personal security best practices**
We can keep ourselves safe online by implementing best practices, choosing more secure tools, and keeping our knowledge and systems up to date.
Today, there are common methods to guess passwords in a variety of ways, such as brute-forcing, credential stuffing, dictionary attacks, and rainbow tables. 

_Account safety & Password management_
- don't reuse the same password for many sites
- use strong passwords or passphrases
- use a password manager
	(A password manager is software that usually comes in a browser extension form, and it stores all of your passwords in encrypted form so that you don't have to remember all of them individually. Instead, you only have to remember one master password).
- set multi-fractor authentication

_Using Virtual Private Networks (VPNs)_
The drawback is that accessing the internet through a VPN can slow down your internet experience, and VPN services usually cost money. But VPNs are an essential tool because they provide two things: anonymity and security.
Why is anonymity important? If you're not using a VPN, your Internet Service Provider (ISP) can see everything  you're doing. They can see which websites you visit, the device you're using, and where you are.
EU introduced the General Data Protection Regulation (GDPR) back in 2017, which made it very difficult for ISPs to capitalize on user data. Everything they do regarding data now has to be subject to informed consent, with huge fines for breaching these regulations.
When not using a VPN, every website you visit, and sometimes people and websites you communicate with online, are able to see your IP address and location by using beacons.
	_Web beacon -_ is a technique used on web pages and email to unobtrusively (usually invisibly) allow checking that a user has accessed some content. Web beacons are typically used by third parties to monitor the activity of users at a website for the purpose of web analytics or page tagging. They can also be used for email tracking. Using such beacons, companies and organisations can track the online behaviour of web servers.
VPNs also add security. They can protect you from MitM attacks, in which network traffic is intercepted by a malicious third party. When you use a VPN, it creates an encrypted tunnel between you and a remote server operated by your VPN provider. That prevents your ISP, other on your wi-fi network, and websites from seeing what you're doing.

_Messaging security_ 
Using encrypted communication platforms both protects your data from being taken and prevents companies from collecting data from your messages.

_Browser Security - Keeping software up to date_
Knowledge is power when it comes to cybersecurity. Threat actors exploit vulnerabilities to gain unauthorized access to information, but by keeping yourself and your systems up to date, you can make those vulnerabilities harder to exploit.

_Look out for Social Engineering_
Making sure you know how to spot phishing, baiting, scareware and other social engineering attacks is as important as keeping your systems secure.

**Personal security - hardening your device**
_What is hardening?_
Hardening is the process of fortifying a system against attacks. When we harden computers, we are generally focused on fortifying the operating system, making sure that it is as secure as it can be.

**Linux hardening**
Linux at its most basic is a kernel; a low-level software interface between the hardware of a computer and higer-level software. The Linux kernel is not an operating system by itself but serves as a key building block for hundreds of different Linux distros (short for "distributions"): operating systems that are built on top of Linux.
	_Ensure 'root' account has a strong password_
The root account has the most privileges on a Linux system so it should be the most secure!
In the terminal, type `sudo passwd root`. Then, you will authenticate with your password and enter the new password.
- create user accounts for everyday use
- limit sudo privileges
- check which services are running at startup
In your terminal, use `service --status -all` to see what services have started and stopped.
Services marked with a + are currently running, and services marked with a - are stopped.

#### Case studies: Notable breaches (lessons learned)
- Failing to disclose breaches is unethical and illegal. Prompt disclosure is crucial to maintaining the trust of customers and complying with the law.
- Mistakenly including keys or other sensitive data in source-control repositories is a common mistake with potentially serious repercussions. Administrative and tehcnical controls should be put in place to prevent sensitive data from being included in repositories, even internal repositories.
- Allowing access to internal resources with personal, external accounts is a security risk. Internal resources should be accessed using work accounts with strong security policies.
- Don't store private user information in an unencrypted format.
- Promptly responding to breaches is crucial to maintain both legal compliance, and professional image.
- Proper configuration is a requirement for security systems to be effective.
- Conducting a proper investigation of security alerts is crucial to catching attacks before they get out of control. Improperly configured alerts, particularly high volumes of false alarms, can cause legitimate alerts to be ignored.
- High-value targets should be hardened against attacks.
- Organisations should know their threat landscape. Organisations that provide software, particularly to high-value targets and government agencies, should consider themselves potential targets for APT groups.
- Supply chain attacks are a real and serious threat, and organisations should be aware that the tools they use could become compromised.
- Security needs to be proactive, in addition to reactive.




