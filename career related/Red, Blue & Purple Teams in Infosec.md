**Red Teams -** are internal or external entities dedicated to testing the effectiveness of a security program by emulating the tools and techniques of likely attackers in the most realistic way possible. The practice is similar, but not identical to Penetration Testing, and involves the pursuit of one or more objectives - usually executed as a campaign.

**Blue Teams -** refers to the internal security team that defends against both real attackers and Red Teams. Blue Teams should be distinguished from standard security teams in most organisations, as most security operations teams do not have a mentality of constant vigilance against attacks, which is the mission and perspective of a Blue Team.
The best Blue Team members are those who can employ Adversarial Empathy (thinking deeply like the enemy, which usually only comes from attack experience).

**Purple Teams -** exist to ensure and maximize the effectiveness of the Red and Blue Teams. They do this by integrating the defensive tactics and controls from the Blue Team with the threats and vulnerabilities found by the Red Team into a single narrative that maximizes both. Ideally, Purple shouldn't be a team at all, but rather a permanent dynamic between Red and Blue.

##### Red Teams
Red Teams are most often confused with Penetration Testers, but while they have tremendous overlap in skills and function, they are not the same.
Red Teams don't just test for vulnerabilities, but do so using the TTPs of their likely threat actors, and in campaigns that run continuously for an extended period of time.
If a security team uses standard pentesting tools, runs their testing for only one or two weeks, and is trying to accomplish a standard set of goals - such as pivoting to the internal network, or stealing data, or getting domain admin - then that's a Penetration Test and not a Red Team engagement.
Red Team engagements use a tailored set of TTPs and goals over a prolonged period of time.

##### Blue Teams
Blue Teams are the proactive defenders of a company from a cybersecurity standpoint.
There a number of defence-oriented Infosec tasks that are not widely considered to be Blue Team worthy. For example, a Tier1 SOC Analyst who has no training or interest in offensive techniques, no curiosity regarding the interface they're looking at, and no creativity in following up on any potential alerts.
All Blue Teams are defenders, but not all defenders are part of a Blue Team.
**What makes a Blue Team vs. just doing defensive things is the mentality:**
- a proactive vs reactive mindset
- endless curiosity regarding things that are out of the ordinary.
- continuous improvement in detection and response.
It's about curiosity and a desire to constantly improve.

##### Purple Teams
Purple is a cooperative mindset between attackers and defenders working on the same side.
The true purpose of a Red Team is to find ways to improve the Blue Team, so Purple Teams should not be needed in organisations where the Red Team/Blue Team interaction is healthy and functioning properly.

### Red Team vs Blue Team: what's the difference?
Red Teams are offensive security professionals who are experts in attacking systems and breaking into defences.
Blue Teams are defensive security professionals responsible for maintaining internal network defences against all cyber attacks and threats.
Red Teams simulate attacks against Blue Teams to test the effectiveness of the networks' security. These Red and Blue Teams exercises provide a holistic security solution ensuring strong defences while keeping in view evolving threats.

#### What is a Red Team?
A Red Team consists of security professionals who act as adversaries to overcome cybersecurity defences. Red Teams often consist of independent Ethical Hackers who evaluate system security in an objective manner.
They utilize all the available techniques to find weaknesses in people, processes, and technology, to gain unauthorised access to assets. As a result of these simulated attacks, Red Teams make recommendations and plans on how to strengthen an organisation's security posture. 
Red Teams spend more time planning an attack than they do performing attacks. In fact, Red Teams deploy a number of methods to gain access to a network. Social Engineering attacks, for example, rely on reconnaissance and research to deliver targeted Spear Phishing campaigns.
Likewise, prior to performing a Penetration Test, packet sniffers and protocol analysers are used to scan the network and gather as much information about the systems as possible.
**Typical information gathered during this phase includes:**
- uncovering operating systems in use.
- identifying the make and model of networking equipment (servers, firewalls, switches, routers, access points, computers, etc).
- understanding physical controls (doors, locks, cameras, security personnel)
- learning what ports are open/closed on a firewall to allow/block specific traffic.
- creating a map of the network to determine what hosts are running what services along with where traffic is being sent.
Once the Red Team has a more complete idea of the system, they develop a plan of action designed to target vulnerabilities specific to the information they gathered above.
After vulnerabilities are identified, a Red Team tries to exploit weaknesses and vulnerabilities in a network. Once an attacker is in your system, the typical course of action is to use privilege escalation techniques, whereby the attacker attempts to steal the credentials of an administrator who has greater/full access to the highest level of critical information.

##### Examples of Red Team exercises
Red Teams use a variety of methods and tools to exploit weaknesses and vulnerabilities in a network. It's important to note that Red Teams will use any means necessary, per the terms of engagement, to break into your system.
Depending on the vulnerability, they may deploy malware to infect hosts or even bypass physical security controls by cloning access cards.
**Examples include:**
- ***Penetration Testing -*** also known as Ethical Hacking, is where the tester tries to gain access to a system, often using software tools.
- ***Social Engineering -*** is where the Red Team attempts to persuade or trick members of staff into disclosing their credentials or allowing access to a restricted area.
- ***Phishing -*** entails sending apparently authentic emails that entice staff members to take certain actions, such as logging into the hacker's website and entering credentials.
- ***Intercepting communications software tools -*** such as packet sniffers and protocol analysers can be used to map a network, or read messages sent in cleartext. The purpose of these tools is to gain information on the system.
- ***Card cloning -*** of an employee's security card to grant access into unrestricted areas, such as a server room.

#### What is a Blue Team?
A Blue Team consists of security professionals who have an inside out view of the organisation. Their task is to protect the organisation's critical assets against any kind of threat.
They are well aware of the business objectives and the organisation's security strategy. Therefore, their task is to strengthen the castle walls so no intruder can compromise the defences.

**How does a Blue Team work?**
The Blue Team first gathers data, documents exactly what needs to be protected and carries out a risk assessment. They then tighten up access to the system in many ways, including introducing stranger password policies and educating staff to ensure they understand and conform to security procedures.
Monitoring tools are often put in place, allowing information regarding access to the systems to be logged and checked for unusual activity. Blue Teams will perform regular checks on the system, for example, DNS audits, internal or external network vulnerability scans and capturing sample network traffic for analysis.

Blue Teams have to establish security measures around key assets of an organisation. They start their defensive plan by identifying the critical assets, document the importance of these assets to the business and what impact the absence of these assets will have.
Blue Teams then perform risk assessments by identifying threats against each asset and the weaknesses these threats can exploit.
By evaluating the risks and prioritising them, the Blue Team develops an action plan to implement controls that can lower the impact or likelihood of threats materialising against assets.

##### Examples of Blue Team exercises
Blue Teams use a variety of methods and tools as counter-measures to protect a network from cyber attacks.
Depending on the situation, a Blue Team may determine that additional firewalls need to be installed to block access to an internal network. Or, the risk to social engineering attacks is so critical that it warrants the cost of implementing security awareness training company-wide.
**Blue Team exercises include:**
- performing DNS audits to prevent phishing attacks, avoid stale DNS issues, avoid downtime from DNS record deletions, and prevent/reduce DNS and web attacks.
- conducting digital footprint analysis to track users' activity and identify any known signatures that might indicate a breach of security.
- installing endpoint security software on external devices such as laptops and smartphones.
- ensuring firewall access controls are properly configured and that antivirus software are kept up to date.
- deploying IDS and IPS software as a detective and preventive security control.
- implementing SIEM solutions to log and ingest network activity.
- analysing logs and memory to pick up unusual activity on the system, and identify and pinpoint an attack.
- segregating networks and ensure they are configured correctly.
- using vulnerability scanning software on a regular basis.
- securing systems by using antivirus or anti-malware software.
- embedding security in processes.


