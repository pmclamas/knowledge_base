"Getting started with networking, scripting, and security in Kali", by OccupyTheWeb @2019

### **Introduction**

Hacking is the most important skill set of the 21st Century!

Almost all the best hacker tools are written in Linux, so some basic Linux skills are a prerequisite to becoming a professional hacker.

Hacking is an elite profession within the IT field. As such, it requires an extensive and detailed understanding of IT concepts and technologies. At the most fundamental level, Linux is a requirement. I strongly suggest you invest time and energy into using and understanding it if you want to make hacking and information security your career.

**What is Ethical Hacking?**

With the growth of the information security field in recent years has come dramatic growth in the field of ethical hacking, also known as White Hat hacking.

Ethical Hacking is the practice of attempting to infiltrate and exploit a system in order to find out its weaknesses and better secure it.

_**Penetration Testing**_

A penetration test is essentially a legal, commissioned hack to demonstrate the vulnerability of a firm's network and systems.

Generally, organizations conduct a vulnerability assessment first to find potential vulnerabilities in their network, operating systems, and services. It is the role of the penetration tester to attempt to hack, or penetrate, these vulnerabilities. Only then can the organization know whether the vulnerability is real and decide to invest time and money to close the vulnerability.

_**Military and Espionage**_

Nearly every nation on earth now engages in cyber espionage and cyber warfare. Hacking plays a crucial part in these military and intelligence-gathering activities, and that will only be more true as time goes by. Imagine a war of the future where hackers can gain access to their adversary's war plans and knock out their electric grid, oil refineries, and water systems. These activities are taking place every day now. The hacker thus becomes a key component of their nation's defense.

**Why Hackers use Linux**

Mostly because Linux offers a far higher level of control via a few different methods.

_**Linux is Open Source**_

Meaning that the source code of the operating system is available to you. As such, you can change and manipulate it as you please. If you are trying to make a system operate in ways it was not intended to, being able to manipulate the source code is essential.

**Linux is Transparent**

To hack effectively, you must know and understand your operating system and, to a large extent, the operting system you are attacking. Linux is totally transparent, meaning we can see and manipulate all its working parts.

With Windows, you never really know what's going on "under the hood", whereas in Linux, you have a spotlight shining directly on each and every component of the operating system. This makes working with Linux more effective.

**Linux offers granular control**

That means that you have an almost infinite amount of control over the system. In Windows, you can control only what Microsoft allows you to control. In Linux, everything can be controlled by the terminal. In addition, Linux makes scripting in any of the scripting languages simple and effective.

**Most hacking tools are written for Linux**

There are exceptions, of course, such as Cain and Abel, and Wikto, but those exceptions prove the rule. Even when hacking tools such as Metasploit or Nmap are ported for Windows, not all the capabilities transfer from Linux.

**The future belongs to Linux/Unix**

Since the internet began, Linux/Unix has been the operating system of choice for web servers due to its stability, reliability, and robustness. Even today, Linux/Unix is used in two-thirds of web servers and dominates the market. Embedded systems in routers, switches, and other devices almost always use a Linux kernel, and the world of virtualization is dominated by Linux, with both VMware and Citrix built on the Linux kernel. Over 80% of mobile devices run Unix or Linux (iOS is Unix, and Android is Linux.

**Downloading Kali Linux**

Kali Linux was developed by Offensive Security as a hacking operating system built on a distribution of Linux called Debian. There are many distributions of Linux, and Debian i one of the best. You are probably most familiar with Ubuntu as a popular desktop distribution of Linux. Ubuntu is also built on Debian. Other distributions include Red Hat, CentOS, Mint, Arch, and SUSE. Although they all share the same Linux kernel (the heart of the operating system that controls the CPU, RAM, and so on), each has its own utilities, applications, and choice of graphical interface (GNOME, KDE, and others) for different purposes. As a result, each of these distributions of Linux looks and feels slightly different. Kali was designed for penetration testers and hackers and comes with a significant complement of hacking tools.

**Virtual Machines**

Virtual Machine (VM) technology allows you to run multiple operating systems from one piece of hardware like your laptop or desktop. This means that you can continue to run the Windows or MacOS operating system you are familiar with and run a virtual machine of Kali Linux inside that operating system. You don't need to overwrite your existing OS to learn Linux.

### **Getting started with the basics**

**Introductory terms and concepts**

**Binaries -** this term refers to files that can be executed, similar to executables in Windows. Binaries generally reside in the /usr/bin or usr/sbin directory.

**root -** like nearly every operating system, Linux has an administrator or superuser account, designed for use by a trusted person who can do nearly anything on the system. This would include such things as reconfigurating the system, adding users, and changing passwords. In Linux, that account is called root. As a hacker or pentester, you will often use the root account to give yourself control over the system. Many hacker tools require that you use the root account.

**script -** this is a series of commands run in an interpretive environment that converts each line to source code. Many hacking tools are simply scripts. Scripts can be run with the bash interpreter or any of the other scripting language interpreters, such as Python, Perl, or Ruby. Python is currently the most popular interpreter among hackers.

**Shell -** this is an environment and interpreter for running commands in Linux. The most widely used shell is Bash, which stands for Bourne-again shell.

**Terminal -** this is a command line interface (CLI).