While conventional security engagements like vulnerability assessments and penetration tests could provide an excellent overview of the technical security posture of a company, they might overlook some other aspects that a real attacker can exploit. In that sense, we could say that conventional penetration tests are good at showing vulnerabilities so that you can take proactive measures but might not teach you how to respond to an actual ongoing attack by a motivated adversary.

**Vulnerability Assessments**
This is the simplest form of security assessment, and its main objective is to identify as many vulnerabilities in as many systems in the network as possible. The objective is to look at every host on the network and evaluate its security posture individually while providing the most information to the company about where to focus its remediation efforts.

To summarize, a vulnerability assessment focuses on scanning hosts for vulnerabilities as individual entities so that security deficiencies can be identified and effective security measures can be deployed to protect the network in a prioritized manner. Most of the work can be done with automated tools and performed by operators without requiring much technical knowledge.

**Penetration Tests**
On top of scanning every single host for vulnerabilities, we often need to understand how they impact our network as a whole. Penetration tests add to vulnerability assessments by allowing the pentester to explore the impact of an attacker on the overall network by doing additional steps that include:
- attempt to exploit the vulnerabilities found on each system. This is important as sometimes a vulnerability might exist in a system, but compensatory controls in place effectively prevent its exploitation. It also allows us to test if we can use the detected vulnerabilities to compromise a given host.
- Conduct post-exploitation tasks on any compromised host, allowing us to find if we can extract any helpful information from them or if we might use them to pivot to other hosts that were not previously accessible from where we stand.

Penetration Tests might start by scanning for vulnerabilities just as a regular vulnerability assessment but provide further information on how an attacker can chain vulnerabilities to achieve specific goals. While its focus remains on identifying vulnerabilities and establishing measures to protect the network, it also considers the network as a whole ecosystem and how an attacker could profit from interactions between its components.

By analyzing how an attacker could move around our network, we also gain a basic insight on possible security measure bypasses and our ability to detect a real threat actor to a certain extent, limited because the scope of a penetration test is usually extensive and Penetration Testers don't care much about being loud or generating lots of alerts on security devices since time constraints on such projects often requires us to check the network in a short time.

**APT's and why regular pentesting is not enough**
While the conventional security engagements mentioned above cover the finding of most technical vulnerabilities, there are limitations on such processes and the extent to which they can effectively prepare a company against a real attacker.
Such limitations include: time constraints, budget, limited scope, non-discruptive, heavy IT focus.

As a consequence, some aspects of penetration tests might significantly differ from a real attack, like:
- Penetration tests are "loud": usually, pentesters won't put much effort into trying to go undetected. Unlike real attackers, they don't mind being easy to detect, as they have been contracted to find as many vulnerabilities as they can in as many hosts as possible.
- Non-technical attack vectors might be overlooked: attacks based on social engineering or physical intrusions are usually not included in what is tested.
- Relaxation of security mechanisms: while doing a regular penetration test, some security mechanisms might be temporarily disabled or relaxed for the pentesting team in favor of efficiency. Although this might sound conterintuitive, it is essential to remember that pentesters have limited time to check the network. Therefore, it is usually desired not to waste their time searching for exotic ways to bypass IDS/IPS, WAF, intrusion deception or other security measures, but rather focus on reviewing critical technological infrastructure for vulnerabilities.

Nowadays, the most prominent threat actors are known as Advanced Persistent Threats (APT), which are highly skilled groups of attackers, usually sponsored by nations or organised criminal groups. They primarily target critical infrastructure, financial organisations, and government institutions. They are called persistent because the operations of these groups can remain undetected on compromised networks for long periods.
If a company is affected by an APT, would it be prepared to respond effectively? Could they detect the methods used to gain and maintain access on their networks if the attacker has been there for several months?

**Red Team engagements**
To keep up with the emerging threats, Red Team engagements were designed to shift the focus from regular penetration tests into a process that allows us to clearly see our defensive team's capabilities at detecting and responding to a real threat actor. They don't replace traditional penetration tests, but complement them by focusing on detection and response rather than prevention.

Red Team engagements consist of emulating a real threat actor's Tactics, Techniques and Procedures (TTPs) so that we can measure how well our Blue Team responds to them and ultimately improve any security controls in place.

Every Red Team engagement will start by defining clear goals, often referenced as flags, ranging from compromising a given critical host to stealing some sensitive information from the target. Usually, the Blue Team won't be informed of such exercises to avoid introducing any biases in their analysis. The Red Team will do everything they can to achieve the goals while reamining undetected and evading any existing security mechanisms like firewalls, antivirus, EDR, IPS, and others. 
A real attacker would only need to find a single path to its goal and is not interested in performing noisy scans that the Blue Team could detect.

It is important to note that the final objective of such exercises should never be for the Red Team to "beat" the Blue Team, but rather simulate enough TTPs for the Blue Team to learn to react to a real ongoing threat adequately. If needed, they could tweak or add security controls that help to improve their detection capabilities.
Red Team engagements also improve on regular penetration tests by considering several attack surfaces:
- Technical Infrastructure: like in a regular Penetration Test, a Red Team will try to uncover technical vulnerabilities, with a much higher emphasis on stealth and evasion.
- Social Engineering: targeting people through phishing campaigns, phone calls or social media to trick them into revealing information that should be private.
- Physical Intrusion: using techniques like lockpicking, RFID cloning, exploiting weaknesses in electronic access control devices to access restricted areas of facilities.

Depending on the resources available, the Red Team exercise can be run in several ways:
- Full Engagement: simulate an attacker's full workflow, from initial compromise until final goals have been achieved.
- Assumed Breach: start by assuming the attacker has already gained control over some assets, and try to achieve the goals from there.
- Table-Top Exercise: an over the table simulation where scenarios are discussed between the Red and Blue teams to evaluate how they would theoretically respond to certain threats. Ideal for situations where doing live simulations might be complicated.

**Teams and Functions of an engagement**
There are several factors and people involved within a Red Team engagement. Everyone will have their mindset and methodology to approach the engagement personnel; however, each engagement can be broken into three teams or cells. Below is a brief table illustrating each of the teams and a brief explanation of their responsibilities.
![[Screenshot 2022-03-30 at 14.37.29.png]]

These teams or cells can be broken down further into an engagement hierarchy.
![[Screenshot 2022-03-30 at 14.38.23.png]]

Below is a table outlining the roles and responsibilities of members of the Red Team.
![[Screenshot 2022-03-30 at 14.40.53.png]]

**Engagement Structure**
A core function of the Red Team is adversary emulation. While not mandatory, it is commonly used to assess what a real adversary would do in an environment using their tools and methologies. The Red Team can use various cyber kill chains to summarize and assess the steps and procedures of an engagement.

The Blue Team commonly uses cyber kill chains to map behaviors and break down an adversaries movement. The Red Team can adapt this idea to map adversary TTPs to components of an engagement.

Many regulation and standardization bodies have released their cyber kill chain. Each kill chain follows roughly the same structure, with some going more in-depth or defining objectives differently. 
Below is a small list of standard cyber kill chains:
- Lockheed Martin Cyber Kill Chain
- Unified Kill Chain
- Varonis Cyber Kill Chain
- Active Directory Attack Cycle
- MITRE ATT&CK Framework

The "Lockheed Martin Cyber Kill Chain" is a more standardized kill chain than others and is very commonly used among Red and Blue Teams.
This kill chain focuses on a perimeter or external breach. Unlike other kill chains, it does not provide an in-depth breakdown of internal movement. You can think of this kill chain as a summary of all behaviors and operations present.
![[Screenshot 2022-03-30 at 14.51.27.png]]
Components of the kill chain are broken down in the table below:
![[Screenshot 2022-03-30 at 14.52.43.png]]


