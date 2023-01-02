**Confidentiality, Integrity, Availability, also known as the CIA triad.**

Is a model designed to guide policies for information security within an organization. The model is also sometimes referred to as the AIC triad (Availability, Integrity, Confidentiality) to avoid confusion with the Central Intelligence Agency. The elements of the triad are considered the three most crucial components of security.

Confidentiality is a set of rules that limits access to information.

Integrity is the assurance that the information is trustworthy and accurate.

Availability is a guarantee of reliable access to the information by authorized people.

**Confidentiality**

Is roughly equivalent to privacy. Mesures undertaken to ensure confidentiality are designed to prevent sensitive information from reaching the wrong people while making sure that authorized people can access it. It is common for data to be categorized according to the amount and type of damage that could be done should it fall into unintended hands.

Sometimes safeguarding data confidentiality involves special training for those privy to sensitive documents. Such training would typically include security risks that could threaten this information. Further aspects of training may include strong passwords and password-related best practices and information about social engineering methods, to prevent users from bending data-handling rules with good intentions and potentially disastrous results.

A good example of methods used to ensure confidentiality is an account number or routing number when banking online. Data encryption is a common method of ensuring confidentiality. User IDs and passwords constitute a standard procedure; two-factor authentication is becoming the norm. Other options include biometric verification and security tokens, key fobs or soft tokens. In addition, users can take precautions to minimize the number of places where the information appears and the number of times it is actually transmitted to complete a required transaction. Extra measures might be taken in the case of extremely sensitive documents, such as storing only on air gapped computers, disconnected storage devices or, for highly sensitive information, in hard copy form only.

**Integrity**

Involves maintaining the consistency, accuracy, and trustworthiness of data over its entire life cycle. Data must not be changed in transit, and steps mut be taken to ensure that data cannot be altered by unauthorized people (for example, in a breach of confidentiality). These measures include file permissions and user access controls. Version control may be used to prevent erroneous changes or accidental deletion by authorized users from becoming a problem. In addition, some means must be in place to detect any changes in data that might occur as a result of non-human-caused events such as an electromagnetic pulse (EMP) or server crash. Some data might include checksums, even cryptographic checksums, for verification of integrity. Backups or redundancies must be available to restore the affected data to its correct state.

**Availability**

Is best ensured by rigorously maintaining all hardware, performing hardware repairs immediately when needed and maintaining a correctly functioning operating system environment that is free of software conflicts. It's also important to keep current with all necessary system upgrades. Providing adequate communication bandwith and preventing the occurrence of bottlenecks are equally important. Redundancy, failover, RAID even high-availability clusters can mitigate serious consequences when hardware issues do occur. Fast and adaptive disaster recovery is essential for the worst-case scenarios; that capacity is reliant on the existence of a comprehensive disaster recovery plan (DRP). Safeguards against data loss or interruptions in connections must include unpredictable events such as natural disasters and fire. To prevent data loss from such occurrences, a backup copy may be stored in a geographically-isolated location, perhaps even in a fireproof, waterproof safe. Extra security equipment or software such as firewalls and proxy servers can guard against downtime and unreachable data blocked by malicious denial-of-service (DoS) attacks and network intrusions.

**Special challenges for the CIA triad**

_**Big Data**_ poses extra challenges to the CIA paradigm because of the sheer volume of information that needs to be safeguarded, the multiplicity of sources it comes form and the variety of formats in which it exists. Duplicate data sets and disaster recovery plans can multiply the already high costs. Furthermore, because the main concern of big data is collecting and making some kind of useful interpretation of all this information, responsible data oversight is often lacking. Whistleblower Edward Snowden brought that problem to the public forum when he reported on the NSA's collection of massive volumes of american citizens' personal data.

_**Internet of Things privacy**_ is the special considerations required to protect the information of individuals from exposure in the IoT environment, in which almost any physical or logical entity or object can be given a unique identifier and the ability to communicate autonomously over the internet or a similar network. The data transmitted by a given endpoint might not cause any privacy issues on its own. However, when even fragmented data from multiple endpoints is gathered, collated and analyzed, it can yield sensitive information.

_**Internet of Things security**_ is also a special challenge because the IoT consists of so many internet-enabled devices other than computers, which often go unpatched and are often configured with default or weak passwords. IoT things could be used as separate attack vectors or part of a thingbot.
