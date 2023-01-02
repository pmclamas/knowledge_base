##### Introduction
This room aims to encourage you to start working with Snort to analyse live and captured traffic.

SNORT is an open-source, rule-based Network Intrusion Detection and Prevention System (NIDS/NIPS). It was developed and still maintained by Martin Roesch, open-source contributors, and the Cisco Talos team.

**The official description:** "Snort is the foremost Open Source Intrusion Prevention System (IPS) in the world. Snort IPS uses a series of rules that help define malicious network activity and uses those rules to find packets that match against them and generate alerts for users."

##### Introduction to IDS/IPS
Let's have a brief overview of what an Intrusion Detection System (IDS) and Intrusion Prevention System (IPS) is. It is possible to configure your network infrastructure and use both of them, but before starting to use any of them, let's learn the differences.

**Intrusion Detection System (IDS)**
IDS is a passive monitoring solution for detecting possible malicious activities/patterns, abnormal incidents, and policy violations. It is responsible for generating alerts for each suspicious event.
**_There are two main types of IDS systems:_**
- **_Network Intrusion Detection System (NIDS) -_** monitors the traffic flow from various areas of the network. The aim is to investigate the traffic on the entire subnet. If a signature identified, an alert is created.
- **_Host-based Intrusion Detection System (HIDS) -_** monitors the traffic flow from a single endpoint device. The aim is to investigate the traffic on a particular device. If a signature is identified, an alert is created.

**Intrusion Prevention System (IPS)**
IPS is an active protecting solution for preventing possible malicious activities/patterns, abnormal incidents, and policy violations. It is responsible for stopping/preventing/terminating the suspicious event as soon as the detection is performed.
**_There are four main types of IPS systems:_**
- **_Network Intrusion Prevention System (NIPS) -_** monitors the traffic flow from various areas of the network. The aim is to protect the traffic on the entire subnet. If a signature is identified, the connection is terminated.
- **_Behaviour-based Intrusion Prevention System (Network Behaviour Analysis - NBA) -_** behaviour-based systems monitor the traffic flow from various areas of the network. The aim is to protect the traffic on the entire subnet. If a signature is identified, the connection is terminated.
Network Behaviour Analysis System works similar to NIPS. The difference is behaviour based systems require a training period (also known as "baselining") to learn the normal traffic and differentiate the malicious traffic and threats. This model provides more efficient results against new threats.
The system is trained to know the "normal" to detect "abnormal". The training period is crucial to avoid any false positives. In case of any security breach during the training period, the results will be highly problematic. Another critical point is to ensure that the system is well trained to recognise benign activities.
- **_Wireless Intrusion Prevention System (WIPS) -_** monitors the traffic flow from of wireless network. The aim is to protect the wireless traffic and stop possible attacks launched from there. If a signature is identified, the connection is terminated.
- **_Host-based Intrusion Prevention System (HIPS) -_** actively protects the traffic flow from a single endpoint device. The aim is to investigate the traffic on a particular device. If a signature is identified, the connection is terminated.
HIPS working mechanism is similar to HIDS. The difference between them is that while HIDS creates alerts for threats, HIPS stops the threats by terminating the connection.

**Detection/Prevention techniques**
There are three main detection and prevention techniques used in IDS and IPS solutions:
- **Signature-based -** this technique relies on rules that identify the specific patterns of the known malicious behaviour. This model helps detect known threats.
- **Behaviour-based -** this technique identifies new threats with new patterns that pass through signatures. The model compares the known/normal with unknown/abnormal behaviours. This model helps detect previously unknown or new threats.
- **Policy-based -** this technique compares detected activities with system configuration and security policies. This model helps detect policy violations.

**Summary**
- **_IDS -_** can identify threats but require user assistance to stop them.
- **_IPS -_** can identify and block the threats with less user assistance at the detection time.

##### SNORT
**Capabilities of Snort:**
- Live traffic analysis
- attack and probe detection
- packet logging
- protocol analysis
- real-time alerting
- modules & plugins
- pre-processors
- cross-platform support.

**Snort has three main use models:
- **Sniffer Mode -** read IP packets and prompt them in the console application.
- **Packet Logger Mode -** log all IP packets (inbound and outbound) that visit the network.
- **NIDS (Network Intrusion Detection System) and NIPS (Network Intrusion Prevention System) Modes -** log/drop the packets that are deemed as malicious according to the user-defined rules.

##### First interaction with Snort
