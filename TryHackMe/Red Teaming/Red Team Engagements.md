##### Introduction
The key to a successful engagement is well-coordinated planning and communication through all parties involved.

**Red Team engagements come in many varieties, including:**
- Tabletop exercises
- Adversary emulation
- Physical assessment

**Learning objectives:**
- Understand components and functions of a Red Team engagement.
- Learn how to properly plan an engagement based of needs and resources available and TTPs.
- Understand how to write engagement documentation in accordance to client objectives.

##### Defining scope and objectives
Engagements can be very complex. The key to a successful engagement is clearly defined client objectives or goals. Client objectives should be discussed between the client and Red Team to create a mutual understanding. Set objectives are the basis for the rest of the engagement documentation and planning.

Objectives set the tone for the rest of the engagement.
When assessing a client's objectives and planning the engagement details, you will often need to decide how focused the assessment is.

Engagements can be categorized between a general internal/network penetration test or a focused adversary emulation. A focused adversary emulation will define a specific APT or group to emulate within an engagement.
An internal or network penetration test will follow a similar structure but will often be less focused and use more standard TTPs.

The specifics of the approach will depend on a case-by-case basis of the engagement defined by the client objectives.
Client objectives will also affect the engagement's general rules of engagement and scope.

The next keystone to a precise and transparent engagement is a well-defined scope. A client's scope will typically define what you cannot do or target. A scope should only be set by the client. They should have a clear understanding of their network and the implications of an assessment. 

When analyzing a client's objectives or scopes from a red team perspective, it is essential to understand the more profound meaning and implications. When analyzing, you should always have a dynamic understanding of how your team would approach the problems/objectives. If needed, you should write your engagement plans or start them from only a bare reading of the client objectives and scope.

##### Rules of Engagement
RoE are a legally binding outline of the client objectives and scope with further details of engagement expectations between both parties. This is the first "official" document in the engagement planning process and requires proper authorization between the client and the read team. This document often acts as the general contract between the two parties; an external contract or other NDAs (Non-Disclosure Agreement) can also be used.

Each RoE structure will be determined by the client and Red Team and can vary in content length and overall sections. Below is a brief table of standard sections you may see contained in the RoE.
![[Screenshot 2022-09-07 at 16.44.09.png]]

##### Campaign Planning
Campaign planning uses the information acquired and planned from the client objectives and RoE and applies it to various plans and documents to identify how and what the Red Team will do.
![[Screenshot 2022-09-07 at 16.51.32.png]]

##### Engagement Documentation
Is an extension of campaign planning where ideas and thoughts of campaign planning are officially documented. 
**Engagement plan:**
![[Screenshot 2022-09-07 at 19.34.15.png]]
**Operations plan:**
![[Screenshot 2022-09-07 at 19.34.40.png]]
**Mission plan:**
![[Screenshot 2022-09-07 at 19.35.21.png]]

##### Concept of Operations
CONOPS is a part of the engagement plan that details a high-level overview of the proceedings of an engagement; we can compare this to an executive summary of a penetration test report. The document will serve as a business/client reference.
The CONOPS document should be written from a semi-technical summary perspective, assuming the target audience/reader has zero to minimal technical knowledge.
Although the CONOPS should be written at a high level, you should not omit details such as common tooling, target group, etc. As with most red team documents. There is not a set standard of a CONOPS document; below is an outline of critical components that should be included in a CONOPS:
- Client Name
- Service Provider
- Timeframe
- General Objectives/Phases
- Other training objectives (Exfiltration)
- High-level tools/Techniques planned to be used
- Threat group to emulate (if any)

The key to writing and understanding a CONOPS is to provide just enough information to get a general understanding of all on-goings. The CONOPS should be easy to read and show clear definitions and points that readers can easily digest.

##### Resource Plan
The resource plan is the second document of the engagement plan, detailing a brief overview of dates, knowledge required (optional), resource requirements.
The plan extends the CONOPS and includes specific details.
Unlike the CONOPS, the resource plan should not be written as a summary; instead, written as bulleted lists of subsections. As with most red team documents, there is no standard set of resource plan templates or documents.
Below is an outline of example subsections of the resource plan:
![[Screenshot 2022-09-08 at 14.13.13.png]]
The key to writing and understanding a resource plan is to provide enough information to gather what is required but not become overbearing.

##### Operations plan
Is a flexible document(s) that provides specific details of engagement and actions occurring. The plan expands upon the current CONOPS and should include a majority of specific engagement information; the ROE can also be placed here depending on the depth and structure of the ROE.
The operations plan should follow a smiliar writing scheme to the resource plan, using bulleted lists and small sub-sections.
Below is an outline of example subsections within the operations plan:
![[Screenshot 2022-09-08 at 19.11.05.png]]
The most notable addition to this document is the communications plan. The communications plan should summarize how the red cell will communicate with other cells and the client overall. (email, slack...)

##### Mission plan
Is a cell-specific document that details the exact actions to be completed by operators. The document uses information from previous plans and assigns actions to them.
How the document is written and detailed will depend on the team.
Below is a list of the minimum detail that cells should include within the plan:
- Objectives
- Operators
- Exploits/Attacks
- Targets (users/machines/objectives)
- Execution plan variations
The two plans can be thought of similarly; the operations plan should be considered from a business and client perspective, and the mission plan should be thought of from an operator and red cell perspective.


