"It is essential to keep going, be persistent. We can't succeed unless we attempt all possibilities."

###### _Tuesday, 01 Feb. 2022_      
90% of Penetration Testing consists of research done on the internet about the product we are testing.
Since the technological ecosystem is continuously evolving, it is impossible to know everything about everything. The key is to know how to look for the information you need. The ability to research effectively is the skill you need to continuously adapt and evolve into your top quality.
The objective here is not speed but meticulousness. If a resource on the target is missed during the Enumeration phase of your test, you might lose a vital attack vector which would have potentially cut your worktime on the target.

**File Transfer Protocol (FTP)**
FTP is a native protocol to all host operating systems and used for a long time for simple file transfer tasks, be they automated or manual. FTP can be easily misconfigured if not correctly understood.
FTP can be used to transfer log files from one network device to another or a log collection server. Suppose the network engineer in charge of handling the configuration forgets to secure the receiving FTP server properly or decides to leave the FTP service unsecured intentionally. In that case, an attacker could gain leverage of the logs and extract all kinds of information from them, which can later be used to map out the network, enumerate usernames, detect active services, etc.

	##### FTP definition in Wikipedia
Is a standard communication protocol used to transfer files from a server to a client on a network. FTP is built on a client-server model architecture using separate control and data connections between the client and the server. FTP users may authenticate themselves with a clear-text sign-in protocol, generally in the form of a username and password. However, they can connect anonymously if the server is configured to allow it. For secure transmission that protects the username and password and encrypts the content, FTP is often secured with SSL/TLS (FTPS) or replaced with SSH File Transfer Protocol (SFTP). 

Users can download and upload files from the client (their own host) to the server (a centralized data storage device) or vice versa.
Conceptually speaking, the client is always the host that downloads and uploads files to the server, and the server always is the host that safely stores the data being transferred.
Clients can also browse the available files on the server when using the FTP protocol. FTP services also come with a GUI (i.e. Filezilla).
It is considered non-standard for FTP to be used without the encryption layer provided by protocols such as SSL/TLS (FTPS) or SSH-tunneling (SFTP).
FTP by itself does have the ability to require credentials before allowing access to the stored files. However, the deficiency here is that traffic containing said files can be intercepted with what is known as a Man-in-the-Middle attack. The contents of the files can be read in plaintext (meaning unencrypted, human-readable form).
However, if the network administrators choose to wrap the connection with the SSL/TLS protocol or tunnel the FTP connection through SSH to add a layer of encryption that only the source and destination hosts can decrypt, this would successfully foil most MitM attacks.

###### _Wednesday, 02 Feb. 2022_
**Low overhead** - is a method of reaching the target to get a response, thus confirming our connection is established, and the target is reachable. Low-overhead means that very little data is sent to the target by default, allowing us to quickly check the status of the connection without having to wait for a whole scan to complete.

**Ping protocol** - is a low-overhead method. Can be invoked from the terminal using the `ping {target_IP}` command.
Note that this might not always work in large-scale corporate environment, as firewalls usually have rules to prevent pinging between hosts, even in the same subnet (LAN). to avoid insider threats and discover other hosts and services.

**help-command** - typing in the `help`command will show you which commands are available. You will be able to see this with every script and service that you have access to.
Typing either `-h`, `--help`or `help`command will always issue a list of all commands available to you as a user, with descriptions occasionally included. If you would like to learn about a specific command in more depth, you can use a different command: 
`man {commandName}`

###### _Thursday, 03 Feb. 2022_
It is always a good idea to research the ports found with a **nmap scan**, in order to understand the big picture. 
[SpeedGuide](https://www.speedguide.net/) is a good resource for those just starting out with network basics and interested in understanding more common ports).

###### _Friday, 04 Feb. 2022_
Remote access software represents a legitimate way to connect to other hosts to perform actions or offer support. The interactions involved by using any type of remote access tool can either be CLI-based or GUI-based.
These tools use the same protocol at their base to communicate with the other hosts, which is RDP (Remote Desktop Protocol). RDP operates on ports 3389 TCP and 3389 UDP. The only difference consists of how the information relayed by this protocol, is presented to the end-user.
	**_Remote access tools_**
**Command Line Interface (CLI)** - a rudimentary example of this is Telnet.
Telnet is considered insecure due to lacking the ability to encrypt the data being sent through it securely. This implies that an attacker with access to a network TAP (Traffic Access Point) could easily intercept the packets being sent through a Telnet connection and read the contents, be they login credentials, sensitive files, or anything else.
Telnet, which runs on port 23 TCP by default, has mainly been replaced by its more secure counterpart, SSH, running on port 22 TCP by default.
SSH (Secure Shell Protocol), adds the required layers of authentication and encryption to the communication model, making it a much more viable approach to perform remote access and remote file transfers. It is used both for patch delivery, file transfers, log transfer, and remote management.
SSH uses public-key cryptography to verify the remote host's identity, and the communication model is based on the client-server architecture.
The local host uses the server's public key to verify its identity before establishing the encrypted tunnel connection. Once the tunnel is established, symmetric encryption methods and hashing algorithms are used to ensure the confidentiality and integrity of the data being sent over the tunnel.

###### _Saturday, 05 Feb. 2022_
> HTB note: If you want to delve deeper into directory busting and web enumeration, you can follow up with our module on HTB Academy with Ffuf. Ffuf is just another tool like Gobuster. 

###### _Monday, 07 Feb. 2022_
**SQL Injection** - is a common way of exploiting web pages that use SQL statements that retrieve and store user input data. If configured incorrectly, one can use this attack to exploit the well-known SQL Injection vulnerability, which is very dangerous.
There are many different techniques of protecting from SQL Injections, same of them being input validation, parameterized queries, stored procedures, and implementing a WAF (Web Application Firewall) on the perimeter of the server's network. However, instances can be found where none of these fixes are in place, hence why this type of attack is prevalent, according to the OWASP Top 10 list of web vulnerabilities.

**Nmap (Intrusive Methods scanning)**
`sudo nmap -sC -sV {target-IP}``
Script scanning (-sC) and Version Detection (-sV) are considered more intrusive methods of scanning the target. This results in a higher probability of being caught by a perimeter security device on the target's network.
**_-sC_** - performs a script scan using the default set of scripts. Some of the scripts in this category are considered intrusive and should not be run against a target network without permission.
**_-sV_** - enables version detection, which will detect what versions are running on what port.

###### _Thursday, 10 Feb. 2022_
Learning how to navigate databases is of considerable importance because most of the critical data is stored in them, including usernames and passwords, which can potentially be used to gain the highest privileged access to the target system.
For example, if there is a website that has a small social network and e-commerce section, there would be a need for several separate sections which should not be inter-accessible:
- One containing users' private information, such as email addresses, geolocations, log-in history, and attached IP addresses, real names, credit card information, and more.
- One containing publicly searchable information such as products, services, music, videos, and other types.

An excellent example of how an SQL Service typically operates is the log-in process utilised for any user. Each time the user wants to log in, the web application sends the log-in page input (username/password combination) to the SQL Service, comparing it with stored database entries for that specific user. Suppose the specified username and password match any entry in the database. In that case, the SQL Service will report it back to the web application, which will, in turn, log the user in, giving them access to the restricted parts of the website. Post-log-in, the web application will set the user a special permission in the form of a cookie or authentication token that associates his online presence with his authenticated presence on the website. This cookie is stored both locally, on the user's browser storage, and the webserver.

