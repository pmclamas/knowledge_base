**Threat Intelligence (TI) or Cyber Threat Intelligence (CTI)** is the information, or TTPs (Tactics, Techniques, and Procedures), attributed to an adversary, commonly used by defenders to aid in detection measures.

The Red Team can leverage CTI from an offensive perpective to assist in adversary emulation.

**What is Threat Intelligence?**

CTI can be consumed (to taken action upon data) by collecting IOCs (Indicators of Compromise) and TTPs commonly distributed and maintained by ISACs (Information and Sharing Analysis Centers). Intelligence platforms and frameworks also aid in the consumption of CTI, primarly focusing on an overarching timeline of all activities.

_Note: the term ISAC is used loosely in the threat intelligence landscape and often refers to a threat intelligence platform._

Traditionally, defenders use threat intelligence to provide context to the ever-changing threat landscape and quantify findings. IOCs are quantified by traces left by adversaries such as domains, IPs, files, strings, etc. The Blue Team can utilize various IOCs to build detections and analyze behavior. From a Red Team perspective, you can think of threat intelligence as the Red Team’s analysis of the Blue Team’s ability to properly leverage CTI for detections.

**Applying Threat Intel to the Red Team**

To aid in consuming CTI and collecting TTPs, Red Teams will often use threat intelligence platforms and frameworks such as MITRE ATT&CK, TIBER-EU, and OST Map.

These cyber frameworks will collect known TTPs and categorize them based on varying characteristics such as:

1.  Threat group
2.  Kill Chain phase
3.  Tactic
4.  Objective/Goal

Once a targeted adversary is selected, the goal is to identify all TTPs categorized with that chosen adversary and map them to a known Cyber Kill Chain.

Leveraging TTPs is used as a planning technique rather than something a team will focus on during engagement execution. During the execution of an engagement, the Red Team will use threat intelligence to craft tooling, modify traffic and behavior, and emulate the targeted adversary.

Overall, the Red Team consumes threat intelligence to analyze and emulate the behaviors of adversaries through collected TTPs and IOCs.

**The TIBER-EU framework**

TIBER-EU (Threat Intelligence-based Ethical Red Teaming - European Union), is a common framework developed by the European Central Bank (ECB).

The TIBER-EU enables European and national authorities to work with financial infrastructures and institutions to put in place a programme to test and improve their resilience against sophisticated cyber attacks.

![[Screenshot 2022-03-10 at 16.34.47.png]]

The main difference between this framework and others is the “Testing” phase that requires threat intelligence to feed the Red Team’s testing.

This framework encompasses a best practice rather than anything actionable from a Red Team perspective.

**TTP Mapping**

TTP Mapping is employed by Red Teams to map adversaries’ collected TTPs to a standard cyber kill chain. Mapping TTPs to a kill chain aids the Red Team in planning an engagement to emulate an adversary.

To begin the process of mapping TTPs, an adversary must be selected as the target. An adversary can be chosen based on:

1.  Target Industry
2.  Employed Attack Vectors
3.  Country of origin
4.  other factors

As an example, we will use APT39, a cyber-espionage group run by the Iranian ministry, known for targeting a wide variety of industries.

We will use the Lockheed Martin cyber kill chain as our standard cyber kill chain to map TTPs.
![[Screenshot 2022-03-10 at 16.35.22.png]]

The first cyber framework we will be collecting TTPs from is MITRE ATT&CK. It provides IDs and descriptions of categorized TTPs.

MITRE provides a basic summary of a group’s collected TTPs. We can use ATT&CK Navigator to help us visualize each TTP and categorize its place in the kill chain. Navigator visualizes the ATT&CK chain with the adversaries’ designated TTPs highlighted under the corresponding sub-section.

Going through the Navigator layer, we can assign various TTPs we want to employ during the engagement. Below is a compiled kill chain with mapped TTPs for APT39.

![[Screenshot 2022-03-10 at 16.35.53.png]]

1.  Reconnaissance:
    -   no identified TTPs, use internal team methodology
2.  Weaponization:
    -   Command and Scripting Interpreter
        -   PowerShell
        -   Python
        -   VBA
    -   User executed malicious attachments
3.  Delivery:
    -   Exploit Public-Facing applications
    -   Spearphishing
4.  Exploitation:
    -   Registry modification
    -   Scheduled tasks
    -   Keylogging
    -   Credential dumping
5.  Installation:
    -   Ingress tool transfer
    -   Proxy usage
6.  Command & Control:
    -   Web protocols (HTTP/HTTPS)
    -   DNS
7.  Actions on Objectives
    -   Exfiltration over C2

MITRE ATT&CK will do most of the work needed, but we can also supplement threat intelligence information with other platforms and frameworks. Another example of a TTP framework is OST Map. OST Map provides a visual map to link multiple threat actors and their TTPs.

Other open-source and enterprise threat intelligence platforms can aid Red Teamers in adversary emulation and TTP mapping such as:

-   Mandiant Advantage
-   Ontic
-   CrowdStrike Falcon

**Other Red Team applications of CTI**

CTI can also be used during engagement execution, emulating the adversary’s behavioral characteristics, such as:

-   C2 Traffic:
    -   User Agents
    -   Ports, Protocols
    -   Listener Profiles
-   Malware and Tooling
    -   IOCs
    -   Behaviors

The first behavioral use of CTI we will showcase is C2 (Command & Control) traffic manipulation. A Red Team can use CTI to identify adversaries’ traffic and modify their C2 traffic to emulate it.

An example of a Red Team modifying C2 traffic based on gathered CTI is malleable profiles. A malleable profile allows a Red Team operator to control multiple aspects of a C2 listener traffic.

Information to be implemented in the profile can be gathered from ISACs and collected IOCs or packet captures, inlcuding:

-   Host Headers
-   POST URIs
-   Server Responses and Headers

The gathered traffic can aid a Red Team to make their traffic look similar to the targeted adversary to get closer to the goal of adversary emulation.

The second behavioral use of CTI is analyzing behavior and actions of an adversaries’ malware and tools to develop your offensive tooling that emulates similar behaviors or has similar vital indicators.

An example of this could be an adversary using a custom dropper. The Red Team can emulate the dropper by:

-   Identifying traffic
-   Observing syscalls and API calls
-   Identifying overall dropper behavior and objective
-   Tampering with file signatures an IOCs

Intelligence and tools gathered from behavioral threat intelligence can aid a Red Team in preparing the specific tools they will use to action planned TTPs.

**Creating a Threat Intel Driven campaign**

A well-planned and researched threat-intel-driven campaign follows the same path you would take as a Red Team to begin planning a campaign:

1.  Identify framework and general kill chain
2.  Determine targeted adversary
3.  Identify adversary’s TTPs and IOCs
4.  Map gathered threat intelligence to a kill chain or framework
5.  Draft and maintain needed engagement documentation
6.  Determine and use needed engagement resources (tools, C2 modification, domains, etc).

The hardest part of planning a threat-intel-driven campaign can be mapping two different cyber frameworks. To make this process simpler we have provided a basic table comparing the Lockheed Martin Cyber Kill Chain and the MITRE ATT&CK framework.

![[Screenshot 2022-03-10 at 16.37.13.png]]

**Conclusion**

When planning an engagement, it is essential to note the significance of adversary emulation and how threat intelligence can aid you in identifying adversaries and their behaviors.

Each Red Team will have its methodology of collecting and digesting threat intelligence in the real world.

When planning an engagement, remember that it is crucial to look at scenarios from all perspective: offensive, defensive, and the adversary’s.

Threat Intelligence allows us, as the Red Team, to look deeper into an adversary’s behavior by using the Blue Team’s methodology to our advantage.