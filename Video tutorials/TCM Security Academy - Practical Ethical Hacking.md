**Base (for interviews)**
- Networking (OSI Model, Protocols (TCP/IP, UDP, http, https, etc), three-way handshake, common ports, subnetting, MAC Address)
- Coding/Scripting skills (Python, Bash)
- Linux
- OWASP Top 10 2021
- Solid hacking methodology
- Tool familiarity (Metasploit; Burp Suite; Nmap; Wireshark; Splunk; Hydra)

**Soft skills needed**
- Strong desire to learn
- non-complacency
- social/people skills
- perseverance
- blog/twitter

*TCP (Transmission Control Protocol)* it's a connection-oriented protocol.
*UDP (User Datagram Protocol)* it's a connection-less protocol.

##### Starting and stopping Kali services
$ service apache2 start (it will run on our ip address and it will only holds in a single session. If we reboot the machine, the server/session is gone) 
$ service apache2 stop



**easier way to Spin up a webserver:**
$ python -m SimpleHTTPServer 8080 (navigate to the folder we want to serve and spin up this python module up).

#### Information gathering
Passive Recon
- physical/social - location info; job information
- Web/host:
	- target validation - WHOIS, nslookup, dnsrecon
	- finding subdomains - googleFu, dig, nmap, crt.sh, etc
	- fingerprinting - nmap, wappalyzer, whatweb, netcat
	- data breaches - HaveIbeenPwned, breach-parse, weleakinfo





