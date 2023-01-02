- https://www.cynet.com/incident-response/ 

Incident Response (IR) is a set of policies and procedures that you can use to identify, contain, and eliminate cyberattacks.  The goal of incident response is to enable an organization to quickly detect and halt attacks, minimizing damage and preventing future attacks of the same type.

**Incident response steps**
***These steps occur in a cycle each time an incident occurs***
1. Preparation of systems and procedures
2. Identification of incidents
3. Containment of attackers and incident activity
4. Eradication of attackers and re-entry options
5. Recovery from incidents, including restoration of systems
6. Lessons learned and application of feedback to the next round of preparation

*Preparation* - Review existing security measures and policies to determine effectiveness. This involves performing a risk assessment to determine what vulnerabilities currently exist and the priority of your assets. Information is then applied to prioritizing responses for incident types. It is also used, if possible, to reconfigure systems to cover vulnerabilities and focus protection on high-priority assets.
This phase is where you refine existing policies and procedures or write new ones if you are lacking. These procedures include a communication plan and assignment of roles and responsibilities during an incident.

*Identification of threats* - When an incident is detected, team members need to work to identify the nature of the attack, its source, and the goals of the attacker.
Responders should document all steps taken and evidence found, including all details. This can help you more effectively prosecute if an attacker is identified.
After an incident is confirmed, communication plans are also typically initiated. These plans inform of the incident and what steps need to be taken.

*Containment of threats* - After an incident is identified, containment methods are determined and enacted. The goal is to advance to this stage as quickly as possible to minimize the amount of damage caused. 
Containment is often accomplished in sub-phases:
- Short term containment: immediate threats are isolated in place. For example, the area of your network that an attacker is currently in may be segmented off. Or, a server that is infected may be taken offline and traffic redirected to a failover.
- Long term containment - additional access controls are applied to unaffected systems. Meanwhile, clean, patched versions of systems and resources are created and prepared for the recovery phase.

*Elminination of threats* - during and after containment, the full extent of an attack is made visible. Once teams are aware of all affected systems and resources, they can begin ejecting attackers and eliminating malware from systems. This phase continues until all traces of the attack are removed. In some cases, this may require taking systems off-line so assets can be replaced with clean versions in recovery.

*Recovery and restoration* - Teams bring updated replacement systems online. Ideally, systems can be restored without loss of data but this isn't always possible.
In the latter case, teams must determine when the last clean copy of data was created and restore from it. The recovery phase typically extends for a while as it also includes monitoring systems for a while after an incident to ensure that attackers don't return.

*Feedback and refinement* - the lessons learned phase is one in which the team reviews what steps were taken during a response. Members should address what went well, what didn't, and make suggestions for future improvements. Any incomplete documentation should also be wrapped up in this phase.

***What is an Incident Response Plan (IRP)?***
An IRP is a set of documented procedures detailing the steps that should be taken in each phase of incident response. It should include guidelines for roles and reponsibilities, communication plans, and standardized response protocols.

One set of terms that are frequently confused is event, alert, and incident:
- Event - a change in system settings, status, or communication. Examples include server requests, permissions update, or the deletion of data.
- Alert - a notification triggered by an event. Alerts can warn of suspicious events or of normal events that need your attention. For example, the use of an unused port vs. storage resources running low.
- Incident - an event that puts your system at risk. For example, theft of credentials or installation of malware.

***Incident Response Frameworks***
- NIST framework - has four official steps which condense the 6 phases of incident response into the following:
	1. Preparation
	2. Detection and Analysis
	3. Containment, Eradication, and Recovery
	4. Post-Incident Activity
	
- SANS framework - includes the six phases individually, calling the phases:
	1. Preparation
	2. Identification
	3. Containment
	4. Eradication
	5. Recovery
	6. Lessons learned
