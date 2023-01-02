_by Adrian Pruteanu, ©2019_

"Becoming the Hacker" will teach you how to approach web penetration testing with an attacker's mindset.

**Rules of Engagement**

It is important to always remember the 'Rules of Engagement (ROE)' when conducting an attack. The ROE are typically written out in the pre-engagement 'Statement of Work (SoW)' and all testers must adhere to them. They outline expectations of the tester and set some limits to what can be done during the engagement.

While the goal of a typical penetration test is to simulate an actual attack and find weaknesses in the infrastructure or application, there are many limitations, and with good reason. We cannot go in guns blazing and cause more damage than an actual adversary. The target (client), should feel comfortable letting professional hackers hammer away at their applications.

**Communication**

Good communication is key to a successful engagement. _**Kickoff and close-out meetings**_ are extremely valuable to both parties involved. The client should be well aware of who is performing the exercise, and how they can reach them, or a backup, in case of an emergency.

The kickoff meeting is a chance to go over all aspects of the test, including reviewing the project scope, the criticality of the systems, any credentials that were provided, and contact information. With any luck, all of this information was included in the _**scoping document**_. The scope can be a combination of IP ranges, applications, specific domains, or URLs. This document is usually written with the input of the client, well in advance of the test start date.

Useful questions to clarify during the kickoff meeting are as follows:

-   Has the scope changed since the document's last revision? Has the target list changed? Should certain parts of the application or network be avoided?
-   Is there a testing window to which you must adhere?
-   Are the target applications in production or in a development environment? Are they customer-facing or internal only?
-   Are the emergency contacts still valid?
-   If credentials were provided, are they still valid? Now is the time to check these again.
-   Is there an application firewall that may hinder testing?

The goal is generally to test the application and not third-party defenses. Penetration testers have deadlines, while malicious actors do not.

_**Tips:**_

-   When testing an application for vulnerabilities, it is a good idea to ask the client to whitelist out IPs in any third-party web application firewalls (WAFs). WAFs inspect traffic reaching the protected application and will drop requests that match known attack signatures or patterns. Some clients will choose to keep the WAF in an enforcing mode, as their goal may be to simulate a real-world attack. This is when you should remind the clients that firewalls can introduce delays in assessing the actual application, as the tester may have to spend extra time attempting to evade defenses. Further, since there is a time limit to most engagements, the final report may not accurately reflect the security posture of the application.
-   No manager wants to hear that their critical application may go offline during a test, but this does occasionally happen. Some applications cannot handle the increased workload of a simple scan and will failover. Certain payloads can also break poorly-designed applications or infrastructure, and may bring productivity to a grinding halt.
-   If, during a test, an application becomes unresponsive, it's a good idea to call the primary contact, informing them of this as soon as possible, especially if the application is a critical production system.

Close-out meetings or post-mortems are also very important. This is the time to meet with the client and go over every finding, and explain clearly how the security breach occurred and what could be done to fix it.

**Privacy considerations**

Engagements that involve any kind of social engineering or human interaction, such as phishing exercises, should be carefully handled. A phishing attack attempts to trick a user into following an email link to a credential stealer, or opening a malicious attachment, and some employees may be uncomfortable being used in this manner.

Before sending phishing emails, for example, testers should confirm that the client is comfortable with their employees unknowingly participating in the engagement.

Unless there is explicit written permission from the client, avoid the following:

-   do not perform social engineering attacks that may be considered immoral, for example, using intelligence gathered about a target's family to entice them to click on a link.
-   Do not exflitrate medical records or sensitive user data.
-   Do not capture screenshots of a user's machines.
-   Do not replay credentials to a user's personal emails, social media, or other accounts.

**Note:** some web attacks, such as SQLi or XML External Entity (XXE), may lead to data leaks, in which case you should inform the client of the vulnerability as soon as possible and securely destroy anything already downloaded.

_"Data is a toxic asset. We need to start thinking about it as such, and treat it as we would any other source of toxicity. To do anything else is to risk our security and privacy."_

Bruce Schneier

**Cleaning up**

A successful penetration test or application assessment will undoubtedly leave many traces of the activity behind. Log entries could show how the intrusion was possible and a shell history file can provide clues as to how the attacker moved laterally. There is a benefit in leaving breadcrumbs behind, however. The defenders, also referred to as the Blue Team, can analyze the activity during or post-engagement and evaluate the efficacy of their defenses. Log entries provide valuable information on how the attacker was able to bypass the system defenses and execute code, exfiltrate data, or otherwise breach the network.

There are many tools to wipe logs post-exploitation, but unless the client has explicitly permitted these actions, this practice should be avoided. There are instances where the Blue Team may want to test the resilience of their security information and event monitoring (SIEM) infrastructure (a centralized log collection and analysis system), so wiping logs may be in scope, but this should be explicitly allowed in the engagement documents.

There are certain artifacts that should almost always be completely removed from systems or application databases when the engagement has completed. The following artifacts can expose the client to unnecessary risk, even after they've patched the vulnerabilities:

-   web shells providing access to the Operating System (OS)
-   Malware droppers, reverse shells, and privilege escalation exploit payloads
-   modified or backdoored application or system components (example: overwriting the password binary with a race condition root exploit and not restoring the backup before leaving the system).
-   Stored XSS payloads: this can be more of a nuisance to users on production systems.

Not all malware introduced during the test can be removed by the tester. Cleanup requires reaching out to the client.

_Tips:_

-   make a note of all malicious files, paths, and payloads used in the assessment. At the end of the engagement, attempt to remove as much as possible. If anything is left behind, inform the primary contact, providing details and stressing the importance of removing the artifacts.
-   Tagging payloads with a unique keyword can help to identify bogus data during the cleanup effort, for example: "Please remove any database records that contain the keyword: 2017Q3TestXyZ123."

A follow-up email confirming that the client has removed any lingering malware or artifacts serves as a reminder and is always appreciated.

### **The tester's toolkit**

The penetration testing tools used vary from professional to professional. Tools and techniques evolve every day and you have to keep up.

**Kali Linux**

Previously known as BackTrack, Kali Linux has been the Linux distribution of choice for penetration testers for many years. It incorporates almost all of the tools required to do application and network assessments. Kali Linux is easy to deploy and it comes in many formats. There are 32-bit and 64-bit variants, portable virtual machine packages, and even a version that runs on the Android OS.

One alternative or supplement to Kali Linux is the Penetration Testing Framework (PTF) from the TrustedSec team and it is written in Python. This is a modular framework that allows you to turn the Linux environment of your choice into a penetration testing toolset. PTF can aslo be run on Kali to quickly organize existing tools in one location.

### **The attack proxy**

When testing applications, traffic manipulation and recording is invaluable. The major players in this market are also extendable, allowing the community of researchers to improve functionality with free add-ons. Well-built and supported proxies are powerful weapons in the attacker's arsenal.

**Burp Suite**

It allows you to intercept, change, replay, and record traffic out of the box. Burp Suite is highly extendable, with powerful community plugins that integrate with sqlmap (the de facto SQLi exploitation tool), automatically test for privilege escalation, and offer other useful modules:

-   Proxy: record, intercept, and modify requests on the fly
-   Spider: content discovery with powerful crawling capabilities
-   Decoder: unscramble encoded data quickly
-   Intruder: a highly customizable brute-forcing module
-   Repeater: allows the replay of any request previously recorder, with the ability to modify any part of the request itself
-   Scanner (pro only): a vulnerability scanner that integrates with Burp Collaborator to find obscure vulnerabilities
-   Collaborator: aids in the discovery of obscure vulnerabilities, which whould normally be missed by traditional scanners.

**Zed Attack Proxy**

OWASP's Zed Attack Proxy (ZAP) is another really great attack proxy. It is extendable and easy to use. However, it lacks some of the features of Burp Suite. ZAP is open-source and it is actively worked on by hundreds of volunteers.

### **Cloud Infrastructure**

When conducting assessments, it is common for an attacker to leverage Command and Control (C2) servers during a campaign. The purpose of most C2 servers is to issue commands to malware running inside the compromised environment.

Attackers can instruct malware to exfiltrate data, start a keylogger, execute arbitrary commands or shellcode, and much more.

A C2 server, being accessible from anywhere, is versatile in any engagement. The cloud is the perfect location to host C2 infrastructure. It allows quick and programmable deployments that can be accessed from anywhere in the world. Some cloud providers will even support HTTPS, allowing for the quick spin up of a C2 without having to worry about purchasing and managing domains or certificates.

Cloud internet service providers (ISPs) should have a form available for you to fill out that will detail an upcoming penetration test on their infrastructure. A testing window and contact information will likely need to be provided.

Whether we are using the cloud to house a C2 for an engagement or attacking applications hosted in the cloud, we should always notify the client of penetration testing - related activity.

The attacker's job will always be easier than that of the defender. The attacker needs just one weak link in the chain - even if that weakness is temporary - to own the environment completely.

Security is difficult to do right the first time and it is even more difficult to keep it close to the baseline as time passes. There are often resourcing issues, lack of knowledge, or wrong priorities, including simply making the organization profitable. Applications have to be useable - they must be available and provide feature enhancements to be useful. There never seems to be enough time to test the code properly, let alone to test it for security bugs.

There is no silver bullet for security testing applications and there is rarely enough money in the budget. There are many pieces to this puzzle and many factors that act against a completely secure application and underlying infrastructure.

This is where the professional hacker, who understands these limitations, can shine. With shell access to a server, one can search for a potential privilege escalation exploit, try to get it working, and, after some trial and error, gain full access.

## Chapter 2 - Efficient discovery

Content discovery and information gathering are typically the first steps when attacking an application. The goal is to figure out as much as possible about the application in the quickest manner possible.

Efficiency can also help us to remain a bit quieter when attacking applications.

### **Types of assessments**

White-box testing allows for a thorough examination of the application. In this case, the attackers have essentially the same access as the developer. They not only have authenticated access to the application, but also its source code, any design documents, and anything else they'll need.

White-box testing is typically conducted by internal teams and it is fairly time-consuming. A tester is provided with any information they require to fully assess the application or infrastructure. The benefit of providing testers with this level of knowledge is that they will be able to look at every bit of an application and check for vulnerabilities.

Gray-box scenarios are more common, as they provide just enough information to let the testers get right into probing the application. The idea here is that the client assumes that a malicious actor already has a certain level of access or knowledge, and the client needs to understand how much more damage can be done.

Black-box testing will simulate an attack from the perspective of an outsider without any knowledge of the application or infrastructure. Companies that expose applications to the internet are subjected to constant attack by external threats.

### **Target mapping**

The traditional nmap of the entire port range, with service discovery, is always a good place to start when gathering information on a target. Nmap is the network scanning tool of choice and has been for many years.

Metasploit Framework (MSF) is a penetration testing framework commonly used by security professionals. Besides being a fantastic collection of easy-to-deliver exploits, it can also help to organize engagements. For target mapping specifically, you can leverage the workspace feature and neatly store your Nmap scan results in a database.

Note: take note of the scope provided by the client. Some will specifically constrain application testing to one port, or sometimes even only one subdomain or URL. The scoping call is where the client should be urged not to limit the attack surface available to the tester.

**Masscan**

Nmap is fully featured, with a ton of options and capabilities, but there is one problem: speed. For large network segments, Nmap can be very slow and sometimes can fail altogether.

Masscan can scan the internet IP space in about six minutes. This is an impressive feat and it is certainly one of the fastest port scanners out there.

Masscan's results can then be fed into either Nmap for further processing, or a web scanner for more in-depth vulnerability discovery.

**WhatWeb**

Once we've identified one or more web applications in the target environment with masscan or Nmap, we can start digging a bit deeper. WhatWeb is a simple, yet effective, tool that can look at a particular web application and identify what technologies have been used to develop and run it.

**Nikto**

Nikto provides value during the initial phases of the engagement. It is fairly no-intrusive and with its built-in plugins, it can provide quick insight into the application. It also offers some more aggresive scanning features that may yield success on older applications or infrastructure.

Nikto can guess subdomains, report on unusual headers, and check the robots.txt file for interesting information.

Nikto outputs information on the HTTPS certificate, the server banner, any security-related HTTP headers that may be missing, and any other information that may be of interest.

### Efficient brute-forcing

A brute-force attack typically involves a barrage of requests, or guesses, to gain access or reveal information that may be otherwise hidden.

Many successful engagements were made so by weak credentials or application misconfiguration. Brute-forcing can help to reveal information that may have been obscured, or can grant access to a database because the developer forgot to change the default credentials.

There are obvious challenges to brute-forcing. Primarly, it is time-consuming and can be very noisy.

Hopefully, target mapping has already provided a few key pieces of information that can help you to brute-force more efficiently. While Nikto and Nmap may not always find a quick and easy remote code execution vulnerability, they do return data that can be useful when deciding what wordlist to use for discovery.

Useful information can include the following:

-   The webserver software: Apache, NGINX, or IIS
-   Server-side development language
-   Underlying operating system
-   robots.txt
-   Interesting response headers
-   WAF detection: F5 or Akamai

You can make assumptions about the application based on the very simple information shown in the preceding list.

**The robots.txt file**

The 'robots.txt' file is generally interesting, as it can provide "hidden" directories or files, and can be a good starting point when brute-forcing for directories or files. The 'robots.txt' file essentially provides instructions for legitimate crawler bots on what they're allowed to index and what they should ignore. This is a convenient way to implement this protocol, but it has the implication that this file must be readable by anonymous users, including yourself.

A sample 'robots.txt' file will look something like this:

User-agent: *

Disallow: /cgi-bin/

Disallow: /test/

Disallow: /~admin/

### **Content discovery**

Burp Suite comes bundled with the Intruder module, which allows us to easily perform content discovery. We can leverage it to look for hidden directories and files, and even guess credentials. It supports payload processing and encoding, which enables us to customize our scanning to better interface with the target application.

In the intruder module, you can leverage the same wordlists provided by SecLists and can even combine multiple lists into one attack. This is a powerful module with lots of features, including, but not limited to, the following:

-   Cluster bomb attack, which is well suited for multiple payloads, such as usernames and passwords
-   Payload processing for highly customized attacks
-   Attack throttling and variable delays for low and slow attacks
-   ...and much more...

The professional version of Burp Suite is highly recommended for those who test applications regularly. Burp Suite is also valuable when reverse engineering applications or protocols. It is quite common for modern applications or malware to communicate with external servers via HTTP. Intercepting, modifying, and replaying this traffic can be valuable.

**OWASP ZAP**

The free alternative to Burp Suite is ZAP, a powerful tool, that provides some of the discovery capabilities of Burp Suite. The ZAP equivalent for Burp's Intruder is the Fuzzer module, and it has similar functionality.

**Gobuster**

Gobuster is an efficient command-line utility for content discovery. It is written in the Go language and will require the golang compiler to be installed before it can be used for an attack.

Gobuster has many useful features, including attacking through a proxy (such as a local Burp Suite instance), out-putting to a file for further processing, or even brute-forcing subdirectories for a target domain.

A command-line URL discovery tool may prove useful on systems where we cannot run a full-blown graphical user interface (GUI) application, such as Burp or ZAP.

### **Polyglot payloads**

A polyglot payload is defined as a piece of code that can be executed in multiple contexts in the application. These types of payloads are popular with attackers because they can quickly test an application's input controls for any weaknesses, with minimal noise.

In a complex application, user input can travel through many checkpoints - from the URL through a filter, into a database, and back out to a decoder, before being displayed to the user.

![[Screenshot 2022-03-09 at 14.58.15.png]]

Any of the step along the way can alter or block the payload, which may make it more difficult to confirm the existence of a vulnerability in the application. A polyglot payload will attempt to exploit an injection vulnerability by combining multiple methods for executing code in the same stream. This attempts to exploit weaknesses in the application payload filtering, increasing the chance that at least one portion of the code will be missed and will execute successfully. This is made possible by the fact that JavaScript is a very forgiving language. Browsers have always been an easy barrier of entry for developers, and JavaScript is rooted in a similar philosophy.

**Summary**

We looked at improving your efficiency for gathering information on a target, and covered several ways to do this. If stealth is paramount during an engagement, efficient content discovery can also reduce the chance that the blue team will notice the attack.

# **Chapter 3 - Low-hanging fruit**

...

# Chapter 4 - Advanced Brute-forcing

Certain engagements require a bit more stealth and the noisiest part of the engagement is usually the brute-force scans. Whether we are looking for valid credentials on a particular login form or scanning for interesting URLs, lots of connections to the target in a short period of time can alert defenders to our activities, and the test could be over before it really begins.

Most penetration testing engagements are "smash and grab" operations. These types of assessments are usually more time-restricted, and throttling our connections for the sake of stealth during a brute-force attack can hinder progress. For engagements that may require a bit more finesse, the traditional penetration testing approach to brute-forcing and dictionary attacks may be too aggressive and could sound the alarm for the blue team. If the goal is to stay under the radar for the duration of the engagement, it may be best to employ more subtle ways to guess passwords or to look for unprotected web content using SecLists dictionaries.

**Password spraying**

A common issue that comes up with brute-forcing for account credentials is that the backend authentication system may simply lockout the target account after too many invalid attempts are made in a short period of time.

A clever way to get around some of these lockout controls, while also increasing your chances of success, is referred to as a reverse brute-force attack or password spraying. The idea is simple and it is based on the fact that as attackers, we usually only need one set of credentials to compromise an application or the environment that hosts it. Instead of focusing the brute-force attack on just one user and risk locking them out, we'd target multiple known valid users with a smaller, more targeted password list. As long as we keep the attempts per account below the lockout policy, we should successfully avoid triggering alerts.

Password spraying is not only useful when attempting to gain access to the organization VPN web application or to Outlook Web Access (OWA), but can also be used with any other application login system.