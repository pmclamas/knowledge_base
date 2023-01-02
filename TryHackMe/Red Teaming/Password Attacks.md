##### Introduction
Passwords are used as an authentication method for individuals to access computer systems or applications.
A collection of passwords is often referred to as a dictionary or wordlist. Passwords with low complexity that are easy to guess are commonly found in various publicly disclosed password data breaches.

##### Password attacking techniques
Dictionary, brute-force, rule-base, and guessing attacks.
All the above techniques are considered active 'online' attacks where the attacker needs to communicate with the target machine to obtain the password in order to gain unauthorized access to the machine.

**Password Cracking vs. Password Guessing**
***Password cracking*** is a technique used for discovering passwords from encrypted or hashed data to plaintext data.
Attackers may obtain the encrypted or hashed passwords from a compromised computer or capture them from transmitting data over the network. Once passwords are obtained, the attacker can utilize password attacking techniques to crack these hashed passwords using various tools.
Password cracking is considered one of the traditional techniques in pentesting. The primary goal is to let the attacker escalate to higher privileges and access to a computer system or network. 

Password guessing and password cracking are often commonly used by information security professionals. Both have different meanings and implications. Password guessing is a method of guessing passwords for online protocols and services based on dictionaries.

***Differences between password cracking and password guessing:***
- password guessing is a technique used to target online protocols and services. Therefore, it's considered time-consuming and opens up the opportunity to generate logs for the failed login attempts. A password guessing attack conducted on a web-based system often requires a new request to be sent for each attempt, which can be easily detected. It may cause an account to be locked out if the system is designed and configured securely.
- Password cracking is a technique performed locally or on systems controlled by the attacker.

##### Password Profiling #1 (Default, Weak, Leaked, Combined, and Username Wordlists)
Having a good wordlist is critical to carrying out a successful password attack. It is important to know how you can generate username lists and password lists.

**Default passwords**
Before performing password attacks, it is worth trying a couple of default passwords against the targeted service.
Manufacturers set default passwords with products and equipment such as switches, firewalls, routers. There are scenarios where customers don't change the default password, which makes the system vulnerable. Thus, it is a good practice to try out admin:admin, admin:123456, etc. If we know the target device, we can look up the default passwords and try them out. 

Here are some websites that provide default passwords for various products:
-   [https://cirt.net/passwords](https://cirt.net/passwords)
-   [https://default-password.info/](https://default-password.info/)
-   [https://datarecovery.com/rd/default-passwords/](https://datarecovery.com/rd/default-passwords/)

**Weak passwords**
Professionals collect and generate weak password lists over time and often combine them into one large wordlist. Lists are generated based on their experience and what they see in pentesting engagements. 
These lists may also contain leaked passwords.

**Leaked passwords**
Sensitive data such as passwords or hashes may be publicly disclosed or sold as a result of a breach. These public or privately available leaks are often referred to as "dumps". 
Depending on the contents of the dump, an attacker may need to extract the passwords out of the data. In some cases, the dump may only contain hashes of the passwords and require cracking in order to gain the plaintext passwords.

##### Offline attacks - Dictionary and Brute-Force
**Dictionary attack -** is a technique used to guess passwords by using well-known words or phrases. The dictionary attack relies entirely on pre-gathered wordlists that were previously generated or found.

**Brute-Force attack -** is a common attack used by the attacker to gain unauthorized access to a personal account. This method is used to guess the victim's password by sending standard password combinations. The main difference between a dictionary and a brute-force attack is that a dictionary attack uses a wordlist that contains all possible passwords.

##### Offline attacks - Rule-Based
**Rule-based attacks -** also known as hybrid attacks. Rule-based attacks assume the attacker knows something about the password policy. Rules are applied to create passwords within the guidelines of the given password policy and should, in theory, only generate valid passwords. Using pre-existing wordlists may be useful when generating passwords that fit a policy - for example, manipulating or mangling a password such as 'password'.

##### Online password attacks
Online password attacks involve guessing passwords for networked services that use a username and password authentication scheme, including services such as HTTP, SSH, VNC, FTP, SNMP, POP3, etc.

**Hydra -** Hydra supports an extensive list of network services to attack. Using hydra, we'll brute-force network services such as web login pages, FTP, SMTP, and SSH. Often, within hydra, each service has its own options and the syntax hydra expects takes getting used to. It's important to check the help options.

##### Password spray attack
Password Spraying is an effective technique used to identify valid credentials. Nowadays, password spraying is considered one of the common password attacks for discovering weak passwords. This technique can be used against various online services and authentication systems, such as SSH, SMB, RDP, SMTP, Outlook Web Application, etc.
A Brute-Force attack targets a specific username to try many weak and predictable passwords. While a password spraying attack targets many usernames using one common weak password, which could help avoid an account lockout policy. 


