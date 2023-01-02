Operations Security (OPSEC) definition provided by NIST:
Systematic and proven process by which potential adversaries can be denied information about capabilities and intentions by identifying, controlling, and protecting generally unclassified evidence of the planning and execution of sensitive activities. 
The process involves five steps:
- Identification of critical information
- Analysis of threats
- Analysis of vulnerabilities
- Assessment of risks
- Application of appropriate countermeasures

Denying any potential adversary the ability to gather information about our capabilities and intentions is critical to maintaining OPSEC. OPSEC is a process to identify, control and protect any information related to the planning and execution of our activities. 
Frameworks such as Lockheed Martin's Cyber Kill Chain and MITRE ATT&CK help defenders identify the objectives an adversary is trying to accomplish.
MITRE ATT&CK is arguably at the forefront of reporting and classifying adversary tactics, techniques, and procedures (TTPs) and offers a publicly accessible knowledge base as publicly available threat intelligence and incident reporting as its primary data source.

The OPSEC process has five steps:
1. Identify critical information
2. Analyse threats
3. Analyse vulnerabilities
4. Assess risks
5. Apply appropriate countermeasures
![[Screenshot 2022-09-09 at 10.01.10.png]]

If the adversary discovers that you are scanning their network with Nmap, they should easily be able to discover the IP address used. For instance, if you use this same IP address to host a phishing site, it won't be very difficult for the Blue Team to connect the two events and attribute them to the same actor.

OPSEC is not a solution or a set of rules; OPSEC is a five-step process to deny adversaries from gaining access to any critical information.

##### Critical Information Identification
Critical information includes, but is not limited to, the red team's intentions, capabilities, activities, and limitations. Critical information includes any information that, once obtained by the blue team, would hinder or degrade the red team's mission.

To identify critical information, the Red Team needs to use an adversarial approach and ask themselves what information an adversary (Blue Team), would want to know about the mission. If obtained, the adversary will be in a solid position to thwart the Red Team's attacks.
Therefore, critical information is not necessarily sensitive information; however, it is any information that might jeopardise your plans if leaked to an adversary.

*The following are some examples:*
- client information that your team has learned. It's unacceptable to share client specific information such as employee names, roles, and infrastructure that your team has discovered. The Principle of Least Privilege (PoLP) dictates that any entity (user or process) must be able to access only the information necessary to carry out its task. PoLP should be applied in every step taken by the Red Team.
- Red Team information, such as identities, activities, plans, capabilities and limitations. The adversary can use such information to be better prepared to face your attacks.
- Tactics, Techniques, and Procedures (TTP) that your team uses in order to emulate an attack.
- OS, cloud hosting provider, or C2 framework utilised by your team.
- Public IP addresses that your team will use. If the Blue Team gains access to this kind of information, they could quickly  mitigate the attack by blocking all inbound and outbound traffic to your IP addresses, leaving you to figure out what has happened.
- Domain names that your team has registered. Domain names play a significant role in attacks such as phishing. If the Blue Team figures out the domain names you will be using to lauch your attacks, they could simply block or sinkhole your malicious domains to neutralize your attack.
- Hosted websites, such as phishing websites, for adversary emulation.

##### Threat Analysis
Threat Analysis refers to identifying potential adversaries and their intentions and capabilities. 
1. Who is the adversary?
2. What are the adversary's goals?
3. What tactics, techniques, and procedures does the adversary use?
4. What critical information has the adversary obtained, if any?

The task of the Red Team is to emulate an actual attack so that the Blue Team discovers its shortcomings, if any, and becomes better prepared to face incoming threats. The Blue Team's main objective is to ensure the security of the organization's network and systems. We should note that the Blue Team's capabilities might not always be known at the beginning.

Malicious third-party players might have different intentions and capabilities and might pause a threat as a result. This party can be someone with humble capabilities scanning the systems randomly looking for low-hanging fruit, such as an unpatched exploitable server, or it can be a capable adversary targeting your company or your client systems. Consequently, the intentions and the capabilities of this third party can make them an adversary as well.

We consider any adversary with the intent and capability to take actions that would prevent us from completing our operation as a threat:
	threat = adversary + intent + capability

##### Vulnerability Analysis
This is not to be confused with vulnerabilities related to cybersecurity. An OPSEC vulnerability exists when an adversary can obtain critical information, analyse the findings, and act in a way that would affect your plans.

To better understand an OPSEC vulnerability as related to red teaming, we'll consider the following scenario:
You use Nmap to discover live hosts on a target subnet and find open ports on live hosts. Moreover, you send various phishing emails leading the victim to a phishing webpage you're hosting. Furthermore, you're using the Metasploit framework to attempt to exploit certain software vulnerabilities. These are three separate activities; however, if you use the same IP address(es) to carry out these different activities, this would lead to an OPSEC vulnerability. Once any hostile/malicious activity is detected, the Blue Team is expected to take action, such as blocking the source IP address(es) temporarily or permanently. Consequently, it would take one source IP address to be blocked for all the other activities use this IP address to fail. In other words, this would block access to the destination IP address used for the phishing server, and the source IP address using by Nmap and Metasploit Framework.

##### Risk Assessment
NIST defines a risk assessment as "the process of identifying risks to organizational operations (including mission, functions, image, reputation), organizational assets, individuals, other organizations, and the Nation, resulting from the operation of an information system." 
In OPSEC, risk assessment requires learning the possibility of an event taking place along with the expected cost of that event. Consequently, this involves assessing the adversary's ability to exploit the vulnerabilities.

Once the level of risk is determined, countermeasures can be considered to mitigate that risk. We need to consider the following three factors:
1. the efficiency of the countermeasure in reducing the risk
2. the cost of the countermeasure compared to the impact of the vulnerability being exploited.
3. the possibility that the countermeasure can reveal information to the adversary.

##### Countermeasures
"Countermeasures are designed to prevent an adversary from detecting critical information, provide an alternative interpretation of critical information or indicators (deception), or deny the adversary's collection system."

##### Summary
OPSEC process has five elements:
1. Identify critical information - critical information includes, but is not limited to, red team's intentions, capabilities, activities and limitations.
2. Analyse threats - threat analysis refers to identifying potential adversaries and their intentions and capabilities.
3. Analyse vulnerabilities - an OPSEC vulnerability exists when an adversary can obtain critical information, analyse the findings, and act in a way that would affect your plans.
4. Assess risks - risk assessment requires learning the possibilty of an event taking place along with the expected cost of that event.
5. Apply appropriate countermeasures - countermeasures are designed to prevent an adversary from detecting critical information, provide an alternative interpretation of critical information or indicators (deception), or deny the adversary's collection system.

OPSEC is a process that will help prevent the adversary from putting the pieces together, thus preventing them from taking timely action.

