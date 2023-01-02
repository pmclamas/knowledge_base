There are 5 distinct phases of a ransomware attack. Understanding what happens at each phase and recognizing the indicators of compromises (IOCs) can increase your likelihood of successfully defending against, or mitigating the effect of an attack.
The timeline of an attack is very compressed. You often have as little as 15 minutes from the exploitation and infection to receiving the ransom note. Recognising the early indicators is critical to your success in stopping an attack.

**Phase 1: Exploitation and Infection**
In order for an attack to be successful, the malicious ransomware file needs to execute on a computer. This is often done through a phishing email or an exploit kit.

**Phase 2: Delivering and Execution**
During this phase, the actual ransomware executables are delivered to the victim's system. Upon execution, persistence mechanisms will be put into place.

**Phase 3: Backup spoliation**
A few seconds later, the ransomware targets the backup files and folders on the victim's system and removes them to prevent restoring from backup. This is unique to ransomware - other types of crimeware don't bother to delete backup files.

**Phase 4: File encryption**
Once the backups are completely removed, the malware will perform a secure key exchange with the Command & Control (C2) server, establishing those encryption keys that will be used on the local system.

**Phase 5: User notification and cleanup**
With the backup files removed and the encryption done, the demand instructions for extortion and payment are presented. Quite often, the victim is given a few days to pay. After that time, the ransom increases.

