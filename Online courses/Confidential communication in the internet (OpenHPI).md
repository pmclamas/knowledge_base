- How does the security situation look like and which interesting attacks have occurred?
- What are the basic security objectives and how can we implement them?
- Which types of encryptions are normally used?

### 1.1 Introduction
Problem: no awareness of the need for data security as a cornerstone of a digital society.

Internet and www also offer entrance gates for multiple threats:
- faulty software or hardware
- inadequate protocols
- computer virus, worms or trojans
- Incorrect operation
- careless users
- unauthorized users, hackers
- reading information/espionage
- falsification of messages
- misdirection of email
- .... (this is only a small list)

Threats rise the more all parts of our world are interconnected by the internet.

**Information transmission on the internet is endangered in many ways:
**_Confidentiality_** of messages not secured when communicated by the internet.
	- Data packages with the messages can be manipulated during the transport through the internet.
	- Sender name and/or address can be forged.
	- Messages can contain hidden malware.

**These are the _security goals_ we which to achieve:** 
- Ensure the confidentiality of messages
- Prevent forgeries of the sender
- Uncover manipulation of messages

**Cryptography is essential for ensuring information security with the help of cryptographic methods, we can:** Ensure confidentiality

**_Encryption_** makes information incomprehensible to unauthorised outsiders.
- Only insiders who know how to reverse the encryption can "decrypt" information
- Encryption and decryption are carried out using cryptographic methods which can be controlled by parameters ("Keys").

**Kerckhoffs' Principle**
Security of a cryptographic process should only be based on the secrecy of the keys and not on the secrecy of the cryptographic process.
_Justification_: independent experts can always check the procedure for weaknesses.

#### Symmetric encryption method
uses the same key for encryption and decryption. Only sender and receiver may know this key.
- DES - Data Encryption Standard _(no more considered to be secure)_
- IDEA - International Data Encryption Algorithm
- AES - Advanced Encryption Standard

#### Hash Procedures
In information security, hash methods are used to generate "fingerprints" for documents, which characterise the possibly large document by a limited number of characters as unambiguously as possible.
_Objectives:_ 
- Compression of a document to a fixed length, which "practically" cannot be undone ("one-way hash function").
- It should be very difficult to find a second document with the same hash value ("collision resistance").
- hash function example: SHA-256 (regarded as secured)
- MD4; MD5; SHA (not considered safe today)

#### Asymmetric encryption methods
Uses two different keys for encryption and decryption. Every user gets a secret key ("Private Key") and a Public key. Public key is published, everyone can/should know it. Private key must remain absolutely secret. 

#### Brute-Force
Any symmetric or asymmetric encryption method can be cracked by Brute-Force attacks:
- Attacker systematically try all theoretically possible keys
The only protection against Brute-Force attacks:
- The number of possible keys must be so large that systematic testing is practically impossible.

##### Important differences between symmetric and asymmetric encryptions 
- symmetrical procedures, also called **_Secret Key Procedures_**, are based on very simple mathematical functions.
- Asymmetric procedures, also known as **_Public Key Procedures_**, are based on very complex mathematical facts.
- **_Public Key Procedures_** require considerably _more computing power_ than secret key procedures and are _more susceptible to implementation errors_.



