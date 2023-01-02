# Meow

**Introduction**

When first starting a penetration test or any security evaluation on a target, a primary step is known as _**Enumeration**_. This step consists of documenting the current state of the target to learn as much as possible about it.

If the target is a web server, running a public web page, you can navigate to its IP address to explore the files and folders stored on it, provided that you have the necessary credentials.

Every server uses ports in order to serve data to other clients. The first steps in the Enumeration phase involve scanning these open ports to see the purpose of the target on the network and what potential vulnerabilities might appear from the services running on it. In order to quickly scan for ports, we can use a tool called **NMAP**.

After finding the open ports on the target, we can manually access each of them using different tools to find out if we have access to their contents or not.

Different services will use different tools or scripts to be accessed. These can be discovered and learned by a beginner penetration tester only with time and practice (and some diligent googling).

**Enumeration**

Scan all of the target’s open ports to determine the services running on it. In order to start the scanning process, we can use Nmap. Nmap stands for Network Mapper, and it will send requests to the target’s ports in hopes of receiving a reply, thus determining if the said port is open or not. Some ports are used by default by certain services. Others might be non-standard, which is why we will be using the service detection flag -sV to determine the name and description of the identified services.

`sudo nmap -sV {target_IP}` 

Following the completion of the scan, we have identified port 23/tcp in an open state, running the telnet service. Telnet is an old service used for remote management of other hosts on the network. Since the target is running this service, it can receive telnet connection requests from other hosts in the network. Usually, connection requests through telnet are configured with username/password combinations for increased security. We can see this is the case for our target. We will need to find some credentials that work to continue since there are no other ports open on the target that we could explore.

_**Foothold**_

Sometimes, due to configuration mistakes, some important accounts can be left with blank passwords for the sake of accessibility. This is a significant issue with some network devices or hosts, leaving them open to simple brute-forcing attacks, where the attacker can try logging in sequentially, using a list of usernames with no password input.

Some typical important accounts have self-explanatory names, such as:

-   admin
-   administrator
-   root

A direct way to attempt logging in with these credentials in hopes that one of them exists and has a blank password is to input them manually in the terminal when the hosts request them. If the list were longer, we could use a script to automate this process, feeding it a wordlist for usernames and one for passwords. Typically, the wordlists used for this task consist of typical people names, abbreviations, or data from previous database leaks. For now, we can resort to manually trying these three main usernames above.

...Success! We have logged into the target system. We can now go ahead and take a look around the directory we landed in using the ls command.

The flag.txt file is our target in this case. Most of Hack The Box’s targets will have one of these files, which will contain a hash value called ‘a flag’. Challenges will, most of the time, not contain an actual file, but rather offer you snippets of the flag as you solve it, the respective parts being embedded into the challenge more homogeneously (text hidden in an image, or other examples).

You can read the file to have the hash value displayed in the terminal using the ‘cat’ command.

# Fawn

**Introduction**

Sometimes, when we are asked to enumerate the services of specific hosts on the client network, we will be met with file transfer services that may have high chances to be poorly configured. The purpose of this exercise is to familiarize yourself with the File Transfer Protocol (FTP), a native protocol to all host operating systems and used for a long time for simple file transfer tasks, be they automated or manual. FTP can be easily misconfigured if not correctly understood.

FTP can be used to transfer log files from one network device to another or a log collection server. Suppose the network engineer in charge of handling the configuration forgets to secure the receiving FTP server properly or decides to leave the FTP service unsecured intentionally. In that case, an attacker could gain leverage of the logs and extract all kinds of information from them, which can later be used to map out the network, enumerate usernames, detect active services, etc.

A port running an active service is a reserved space for the IP address of the target to receive requests and send results from. By having ports, you can have one IP address handling multiple services, as it adds another layer of distinction.

It is considered non-standard for FTP to be used without the encryption layer provided by protocols such as SSL/TLS (FTPS) or SSH-tunneling (SFTP). FTP by itself does have the ability to require credentials before allowing access to the stored files. However, the deficiency here is that traffic containing said files can be intercepted with what is known as a Man-in-the-Middle Attack (MitM). The contents of the files can be read in plaintext(meaning unencrypted, human-readable form).

However, if the network administrators choose to wrap the connection with the SSL/TLS protocol or tunnel the FTP connection through SSH to add a layer of encryption that only the source and destination hosts can decrypt, this would successfully foil most MitM attacks.

**Enumeration**

We can start by scanning the open services on the host.

_$ sudo nmap {target_IP}_

We can see the FTP service open and running on port 21.

However, what if we would like to know the actual version of the service running on this port? Could scanning it with different switches present us with the needed information?

_$ sudo nmap -sV {target_IP}_

The -sV command stands for version detection. Using this switch will consequently make our scan take longer but will offer us more insight into the version of the service running on the previous detected port. This means that at a glance, we would be able to tell if the target is vulnerable due to running outdated software or if we need to dig deeper to find our attack vector.

**Foothold**

In order to access the FTP service, we will use the ftp command on our own host. It’s good practice to have a quick check that your ftp is up to date and installed properly. Running the command below will display the same output as pictured if your ftp service is installed. Otherwise, it will continue with the installation. The -y switch is used to accept the installation without interrupting the process to ask if you’d like to proceed.

$ sudo apt install ftp -y

After it has done installing, you can run the ftp -h command to see what the service is capable of.

We can connect to the target host using the command below. This will initiate a request to authenticate on the FTP service running on the target, which will return a prompt back to our host:

$ ftp {target_IP}

The prompt will ask us for the username we want to log in with.

A typical misconfiguration for running FTP services allows an anonymous account to access the service like any other authenticated user. The anonymous username can be input when the prompt appears, followed by any password whatsoever since the service will disregard the password for this specific account. (password: anon123)

We can now issue FTP commands.

Let’s use the ls command and view the contents of the folder.

_$ ls_

Now, we can proceed to download the ‘flag.txt’ file to our host. In order to do so, we can use the get command, followed by the name of the file we want to download.

_ftp> get flag.txt_

This will trigger the download of the file to the same directory you were in when you issued the ftp {machineIP} command. If we exit the FTP service, we will see the same file on our host now.

_$ cat flag.txt_

# Dancing

**SMB (Server Message Block)**

This communication protocol provides shared access to files, printers, and serial ports between endpoints on a network. We mostly see SMB services running on Windows machines.

During scanning, we will typically see port 445 TCP open on the target, reserved for the SMB protocol.

Usually, SMB runs at the Application or Presentation layers of the OSI model. Due to this, it relies on lower-level protocols for transport. The Transport Layer protocol that Microsoft SMB protocol is most often used with is NetBIOS over TCP/IP (NBT). This is why, during scans, we will most likely see both protocols with open ports running on the target.

Using the SMB protocol, an application can access files at a remote server, along with other resources such as printers. Thus, a client application can read, create, and update files on the remote server. It can also communicate with any server program that is set up to receive an SMB client request.

An SMB-enabled storage on the network is called a share. These can be accessed by any client that has the address of the server and the proper credentials. Like many other file access protocols, SMB requires some security layers to function appropriately within a network topology. If SMB allows clients to create, edit, retrieve, and remove files on a share, there is a clear need for an authentication mechanism. At a user level, SMB clients are required to provide a username/password combination to see or interact with the contents of the SMB share.

Despite having the ability to secure access to the share, a network administrator can sometimes make mistakes and accidentaly allow logins without any valid credentials or using either guest accounts or anonymous log-ons.

**Enumeration**

$ sudo nmap -sV {target_IP}

We observe that port 445 TCP for SMB is up and running, which means that we have an active share that we could potentially explore. Think of this share as a folder that can be accessed over the internet. In order to do so, we will need the appropriate services and scripts installed.

In order to successfully enumerate share content on the remote system, we can use a script called “smbclient”. If the script is not present, you can install it by typing the following command in your terminal:

_$ sudo apt-get install smbclient_

Smbclient will attempt to connect to the remote host and check if there is any authentication required. If there is, it will ask you for a password for your local username. We should take note of this. If we do not specify a specific username to smbclient when attempting to connect to the remote host, it will just use your local machine’s username. That is the one you are currently logged into your VM with. This is because SMB authentication always requires a username, so by not giving it one explicitly to try to login with, it will just have to pass your current local username to avoid throwing an error with the protocol.

Nevertheless, let us use our local username since we do not know about any remote usernames present on the target host that we could potentially log in with. Next up, we will be prompted for a password. This password is related to the username you input before. In this case, we do not have such credentials, so what we will be trying to perform is any of the following:

-   guest authentication
-   anonymous authentication

Any of these will result in us logging in without knowing a proper username/password combination and seeing the files stored on the share.

We leave the password field blank, simply hitting enter to tell the script to move along.

_$ smbclient -L {target_IP}_

_-L (selecting the targeted host for the connection request)._

Running the command above, we see that four separate shares are displayed:

-   ADMIN$ - administrative shares are hidden network shares created by the Windows NT family of operating systems that allow system administrators to have remote access to every disk volume on a network-connected system. These shares may not be permanently deleted but may be disabled.
-   c$ - administrative share for the c:\disk volume. This is where the operating system is hosted.
-   IPC$ - the inter-process communication share. Used for inter-process communication via named pipes and is not part of the file system.
-   WorkShares - custom share.

**Foothold**

We will try to connect to each of the shares except for the IPC$, which is not valuable for us since it is not browsable as any regular directory would be and does not contain any files that we could use at this stage. We will use the same tactic as before, attempting to log in without the proper credentials to find improperly configured permissions on any of these shares. First, lets try the ADMIN$ one:

$ smbclient \\\\{target_IP}\\ADMIN$

The “NT_STATUS_ACCESS_DENIED” is output, letting us know that we do not have the proper credentials to connect to this share. We will follow with the C$ administrative share.

$ smbclient \\\\{target_IP}\\C$

Denied again. We proceed with attempting to log in to the custom WorkShares SMB share. This seems to be human-made, thus prone to misconfiguration.

$smbclient \\\\{target_IP}\\WorkShares

We can see our terminal prompt changed to smb: \>, letting us know that our shell is now interacting with the service.

Typing in the ls command will show us two directories, Amy.J and James.P. We visit the first one and are met with a filled called worknotes.txt, which we can download using the get command.

smb: \> ls #output: Amy.J James.P

smb: \> cd Amy.J

smb: \Amy.J> ls #output: worknotes.txt

smb: \Amy.J> get worknotes.txt

This file is now saved inside the location where we ran our smbclient command from.

Navigating to the James.P directory, we can find the sought flag.txt file. After retrieving this file, we can use the exit command to quit the shell and check the files we retrieved.

Once the SMB shell is killed, we can read the two documents we exfiltrated. The worknotes.txt seems to be hinting at further services that could be exploited. Typically, these kinds of files you can find laying around in machines within a Hack The Box Pro Lab, hinting towards your next target or being able to be used as a resource for further exploitation or lateral movement within the lab. In our case, it is just a proof of concept.

The flag.txt, however, is what we are after.

# Explosion

**Introduction**

Remote access software represents a legitimate way to connect to other hosts to perform actions or offer support. The interactions involved by using any type of remote access tool can either be CLI-based (Command Line Interface) or GUI-based (Graphical User Interface). These tools use the same protocol at their base to communicate with the other hosts, which is RDP (remote Desktop Protocol). RDP operates on ports 3389 TCP nad 3389 UDP. The only difference consists of how the information relayed by this protocol is presented to the end-user.

**CLI - remote access tools**

A rudimentary example of a Command Line Interface-based Remote Access Tool is Telnet. In its most basic configuration, Telnet is considered insecure due to lacking the ability to encrypt the data being sent through it securely. This implies that an attacker with access to a network TAP (Traffic Access Point) could easily intercept the packets being sent through a Telnet connection and read the contents, be they login credentials, sensitive files, or anything else. Telnet, which runs on port 23 TCP by default, has mainly been replaced by its more secure counterpart, SSH, running on port 22 TCP by default.

_SSH (Secure Shell Protocol)_, adds the required layers of authentication and encryption to the communication model, making it a much more viable approach to perform remote access and remote file transfers. It is used both for patch delivery, file transfer, and remote management in today’s environment.

SSH uses public-key cryptography to verify the remote host’s identity, and the communication model is based on the Client-server architecture, as seen previously with FTP, SMB, and other services. The local host uses the server’s public key to verify its identity before establishing the encrypted tunnel connection. Once the tunnel is established, symmetric encryption methods and hashing algorithms are used to ensure the confidentiality and integrity of the data being sent over the tunnel.

However, both Telnet and SSH only offer the end-user access to the remote terminal part of the host being reached. In order to be able to see the remote host’s display, one can resort to CLI-based tools such as xfreerdp. Tools such as this one are called Remote Desktop Tools. The whole desktop can be remotely controlled by the user initiating the connection, like one would if they were physically in the room with the remote host, using its keyboard, mouse, and display to interact with it, including the ability to view graphical content, controlling the mouse pointer and keyboard input, easily interacting with the web browser, and more.

**GUI - remote access tools**

Two of the most prevalent tools are Teamviewer and Windows Remote Desktop Connection.

Simpler software that runs natively can sometimes be misconfigured because user experience for the inexperienced user is not always a key factor when developing technical tools integrated with some operating systems. Microsoft Remote Desktop Connection runs natively on Windows, which means that it comes pre-installed with every Windows OS, without the need from the end-user to perform any other actions other than activating the service and setting its parameters up. This is where some configuration errors come in.

**Enumeration**

We start, as always, with an nmap scan. We have to run the scan with the version scanning switch enabled to determine the exact versions of all the services running on open ports on the target, thus assessing the actual operating system of the machine and any additional potential vulnerabilities due to outdated software.

$ sudo nmap -sV {target_IP}

It is always a good idea to research the ports found in order to understand the big picture. SpeedGuide is a good resource for those just starting out with their networking basics and interested in understanding more common ports.

Looking at the results of the scan, port 3389 TCP is typically used for Windows Remote Desktop and Remote Assistance connections (over RDP - Remote Desktop Protocol). We can quickly check for any misconfigurations in access control by attempting to connect to this readily available port without any valid credentials, thus confirming whether the service allows guest or anonymous connections or not.

**Foothold**

We will be using xfreerdp to connect. You can check if you have xfreerdp installed by typing the command name in the terminal. If the script’s help menu is output to the terminal, then you are ready to go. The help menu for this script is vast, and you can find out much information about the functionality of each switch if you read through it.

If you need to install xfreerdp, you can proceed with the following command:

$ sudo apt-get install freerdp2-x11

We can first try to form an RDP session with the target by not providing any additional information for any switches other than the target IP address. This will make the script use your own username as the login username for the RDP session, thus testing guest login capabilities.

$ xfreerdp /v:{target_IP}

Our own username is not accepted for the RDP session login mechanism. We can try a myriad of other default accounts, such as ‘user’, ‘admin’, ‘Administrator’, and so on. This would be a time-consuming process. For the sake of RDP exploration, let us attempt logging in with the ‘Administrator’ user. We will also be specifying to the script that we would like to bypass all requirements for a security certificate so that our own script does not request them. The target, in this case, already does not expect any.

$xfreerdp /v:{target_IP} /cert:ignore /u:Administrator

/cert:ignore : specifies to the scripts that all security certificate usage should be ignored.

/u:Administrator : specifies the login username to be “Administrator”.

/v:{target_IP} : specifies the target IP of the host we would like to connect to.

The output is different this time, and during the initialization of the RDP session, we are asked for a Password. In our case, the Administrator account has not been configured with a password for logging in for the sake of accessibility for the end-user. This is a severe mishap in configuration and will result in us, the attacker, gaining access to the machine without much effort. When prompted to enter the Password, we can hit Enter to let the process continue without one.

Following this, a large output will be displayed on our terminal before a remote desktop window is loaded.

The flag we are looking for is located on the “Desktop”.

# Preignition

**Introduction**

Web enumeration, specifically directory busting (dir busting), is one of the most essential skills any Penetration Tester must possess. While manually navigating websites and clicking all the available links may reveal some data, most of the links and pages may not be published to the public and, hence, less secure.

**Enumeration**

Using nmap and the appropriate service version detection switch, we scan the IP address for any open ports and services.

`$ nmap -sV {target_IP}`

From the scan result, a single entry is shown and catches our attention. It is an http service running on port 80, signaling that this target might be hosting some explorable web content. To look at the contents ourselves, we can open a web browser and navigate to the target’s IP address in the URL bar at the top of the window. This will automatically address the target’s port 80 for the client-server communication and load the web page’s contents.

At the top of the page, we observe the mention of the nginx service. After researching basic information about nginx and its purpose, we conclude that our target is a web server. Web servers are hosts on the target network which have the sole purpose of serving web content internal or external users, such as web pages, images, videos, audio files, and other types. Typically, a web server is accessible from the internet to allow for the stored content to be explored by the online public for many reasons: shopping, providing and requesting services, banking, reading the news, and more.

What we are looking at on our browser screen is the default post-installation page for the nginx service, meaning that there is the possibility that this web application might not be adequately configured yest, or that default credentials are used to facilitate faster configuration up to the point of live deployment. This, however, also means that there are no buttons or links on the web page to assist us with navigation between web directories or other content.

When browsing a regular web page, we use these elements to move around on the website. However, these elements are only links to other directories containing other web pages, which get loaded in our browser as if we manually navigated to them using the URL search bar. Knowing this, could we attempt to find any “hidden” content hosted on this webserver?

The short answer is yes, but to avoid guessing URLs manually through the browser’s search bar, we can find a better solution. This method is called dir busting, short for directory busting. For this purpose, we will be using the tool called gobuster.

**Using gobuster**

In order to start our dir busting, we will need to discover what capabilities gobuster has and which ones can assist us. By looking at the tool’s help page, by typing in the ‘gobuster -h’ command in our terminal, we receive a list of all possible switches for the tool and their description.

In our case, we will only need to use the following:

dir : specify we are using the directory busting mode of the tool

-w : specify a wordlist, a collection of common directory names that are typically used for sites

-u : specify the target’s IP address

`$ sudo gobuster dir -w /usr/share/wordlists/dirb/common.txt -u {target_IP}`

In the wordlist we used, the entry ‘admin.php’ was present, and we can see that there is indeed a page with the same name present on the target. What gobuster did here was make several connection attempts to the target using the HTTP GET method (requesting web pages from the webserver) with different URL variations, such as:

GET http://{target_IP}/kittens

GET http://{target_IP}/hackers

GET http://{target_IP}/admin.php

GET http://{target_IP}/hackthebox

GET http://{target_IP}/yourespecial

Out of all the variations found in the worldist we specified, ‘admin.php’ existed and was returned to us in the output, signaling that the webpage exists and we can navigate to it manually to check out its contents.

**Foothold**

Navigating to the newly found link manually through our web browser, we are met with an administrative panel for the website. It asks us for a username and password to get past the security check, which could prove problematic in normal circumstances.

Usually, in situations such as this one, we would need to fire up some brute-forcing tools to attempt logging in with multiple credentials sets for an extended period of time until we hit a valid log-in since we do not have any underlying context about usernames and passwords that might have been registered on this web site as valid administrative accounts. But first, we can try our luck with some default credentials since this is a fresh nginx installation. Let us try logging in with the following credentials: admin admin.

We seem to be successful!
