[Link](https://www.comptia.org/blog/5-linux-skills-for-cybersecurity-professionals#:~:text=Apply%20to%20Cybersecurity%3F-,Linux%20plays%20an%20incredibly%20important%20part%20in%20the%20job%20of,analysis%20after%20a%20security%20breach.)

#### Linux system and network administration
Regardless of whether you are performing penetration tests, forensic analysis or security monitoring of a Linux server, network device or security appliance, you will need to understand how to perform key system and network administration functions within Linux:
- view system information (architecture, kernel version, installed packages, running processes, user sessions)
- view and modify network configuration (IP configuration, open ports, open sockets, open files, installed services)
- determine how the Linux system starts services (SysV Init or Systemd), as well as start/stop key services and processes
- modify key system and service configuration files
- identify how events get logged (rsyslogd or journald) and the location of log files
- install software on the Linux distribution (yum, dnf, apt, zypper, etc)
- view and work with the different physical and logical filesystems on the system (mount points, LVM, ZFS, btrfs, etc), including imaging data on a filesystem for analysis and evidence gathering using utilities such as dd
- analyse the content of key or suspicious files
- connect to remote systems using a wide variety of different methods, including ssh

#### Regular Expressions
Regular expressions are powerful wildcards used alongside certain Linux utilities to search files and logs for key events on a wide variety of network devices and servers. Even logs on Windows servers are often collected by Linux systems (including those running SIEM), where regular expressions can be used to narrow down key security-related events.
For example, you can use complex Linux regular expressions to search configuration and log files for pivoting (the process by which a hacker gains access to one system and then uses that system to gain access to other trusted systems easily). Once you've found evidence of a security breach, you can use the information you've found to perform a granular search of system and log files on a series of different network devices and servers using regular expression to trace the path a hacker has taken on your network, the systems that they have compromised, and the data that they have accessed.

#### SELinux and AppArmor
Both SELinux and AppArmor are application-focused security modules on Linux systems that provide a high level of protection against attacks. Nearly all internet-accessible Linux servers and Linux-based network and security devices implement either SELinux or AppArmor to prevent applications from performing tasks that may compromise system and data security. 
You should understand the in-depth configuration of both SELinux and AppArmor for use when hardening any Linux-based system. When analysing an existing system with SELinux or AppArmor, it's also important to identify the policies enforced and exceptions allowed by the security module. Moreover, both SELinux and AppArmor log information related to intrusion attempts and security breaches that is invaluable to cybersecurity professionals who are monitoring security or performing forensic analysis.

#### Open-source security tools
You should familiarise yourself with the in-depth usage of information gathering tools (such as nmap) that can be used to learn more about systems on the network (a process called reconnaissance). Additionally, you should master tools that are useful for vulnerability analysis (such as OpenVAS), traffic analysis (such as WireShark) and penetration testing (such as Ettercap, Metasploit, arpspoof, etc).
Since most cybersecurity professionals collect security information centrally using a SIEM for analysis, you should also know how to install, configure and use Linux-based open-source SIEM solutions such as Alienvault OSSIM.

#### Bash scripting
Whether you are performing cybersecurity analysis, response, forensics or administration, you will need to leverage many different Linux commands. Since many of these commands can be reused in the future within similar cybersecurity situations, you should always consider putting them within BASH shell scripts that you can save for later use.
Keep an arsenal of cybersecurity-related BASH shell scripts within a folder on all of your systems to ensure that you can perform cybersecurity analysis, response, forensics or administration as quickly as possible. And when it comes to security, quick response is vital.

