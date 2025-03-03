Get to know the organization, the position you are interviewing for, and what difficulties/responsibilities both have.

Do not give a salary expectation. Instead answer like: "I think my salary expectations are within your scale. I am open to your suggestions at the proposal stage"


## Big Resource
https://github.com/LetsDefend/SOC-Interview-Questions/blob/main/README.md#general

https://danielmiessler.com/blog/infosec-interview-questions#wisdom

## Interview Questions
Pulled from
https://github.com/LetsDefend/SOC-Interview-Questions/blob/main/README.md#general

## SOC Interview Questions
### General
**What is black, white, and gray hat?**
Black hats are hackers who enter systems illegally without permission in an effort to exploit for financial gain.
White hats are ethical hackers who are certified and have permission. They protect systems/organizations
Gray hats are a mix. Illegally find vulnerabilities and access systems but do not exploit them. Usually notify owners for reward

**What is a SOC?**
A centralized unit focuses on monitoring, detecting, analyzing, and responding to threats
SOC analysts are the front line responsible to continuously monitor an organization's operations and network for suspicious activity.

**What is port scanning?**
Sending packets to specific ports on a host and analyzing the response. Used to find what ports are open and receiving/sending data.

**Blue Team vs Red Team?**
red team attacks systems, blue team defends

**What is a firewall?**
A device that filters network traffic based on a set of rules

**What is a security misconfiguration?**
A vulnerability caused by an incomplete or incorrect configuration

**Vulnerability, Risk, Threat**
Vulnerability is a weakness in a system that can be exploited
Risk is what you stand to lose: the level of impact and its likelihood
Threat is an entity or event with the potential to adversely impact operations

**What is compliance?**
Following the set of standards authorized by a governing body

**What is MITRE ATT\*CK**
Globally-accessible knowledge base of adversary attacks and techniques. 

**What is 2FA**
An extra layer of authentication before users are given access. Requires users to provide an additional piece of information. 

**Could you share some general endpoint security product categories?**
- Antivirus
- antispyware
- host-firewall
- EDR (endpoint detection and response)
- XDR (extended detection and response)
- DLP (Data loss prevention)

**What is HIDS and NIDS?**
HIDS = host intrusion detection system
NIDS = network intrusion detection system

**What is the CIA triad?**
A model that forms the basis for the security of systems
Confidentiality, Integrity, Availability
**What is AAA?**
Authentication, authorization, accounting

**What is the Cyber Kill Chain?**
Steps attackers take in a cyberattack
1: Reconnaissance: gathering intelligence
2: Weaponization: creation of a payload
3: Delivery: Delivery of payload
4: Exploitation: The payload exploits a vulnerability
5: Installation: The attacker installs persistence
6: Command and Control: Establishing connection with attacker system for remote control
7: Actions on objectives: The attacker achieves their goals

**What is SIEM?**
Security information and event management is a security solution that provides real time logging of events to detect threats.

**What are IOCs, and IOAs?**
IOC: Indicators of compromise are evidence of  the techniques used for potential intrusions
IOA: Indicators of attack are evidence of techniques used in an attack

**True positive vs False Positive**
True positive is when an alert alerts the situation it is supposed to detect.
False positive is when an alert alerts a situation that it is not supposed to detect.

**Describe the Zero Trust security concept**
A model that operates on the principle of never trust always verify. Assumes threats can come from outside and inside the network and require strict verification of very access attempt.

### Network
**What is the OSI Model? Explain each layer**
A model that describes the standard of communication processes.

7: Application: Closest to the end users, actions done via application that facilitate communication between the client and the server.

6: Presentation Layer: Establishes data formatting and translating into a format specified by the application layer.

5: Session Layer: Creates the setup, controls the connections, and ends the teardown between devices.

4: Transport Layer: Provides the mean of transferring/transporting data from source to destination across a network

3: Provides the means of transferring/transporting data to different networks

2: Data Link Layer: Provides node-to-node data transfer a link between two connected nodes. Detects and corrects errors in the physical layer and defines the protocol to establish, the flow, and terminate a connection between two physically connected devices
	- MAC Layer: How devices gain access to a medium and permission to transmit data
	- LLC Layer: Identifying and encapsulating network layer protocols, error checking, and frame synchronization
1: Physical Layer: The transmission and reception of raw unstructured data between a device and physical medium

![[Pasted image 20250225112106.png]]

**What is the Three-Way Handshake?**
TCP uses the three-way handshake to establish a reliable connection. Both sides synchronize (SYN) and acknowledge (ACK) each other.
![[Pasted image 20250225120708.png]]
**What is the TCP/IP Model?**
Default model of communication. Developed by DOD
1: Application Layer
2: Transport Layer
3: Internet Layer
4: Network Access Layer

**What is ARP?**
Address resolution protocol is a communication protocol used for discovering data link layer addresses (MAC) with the given network layer address (IP)

**What is DHCP?**
Dynamic Host Configuration Protocol is a protocol that automatically assigns IP address to devices.

**Share some general network security product names**
- firewall
- IDS (intrusion detection system)
- IPS (intrusion prevention system)
- WAF (Web application firewall)
Difference between IDS (detects) and IPS (prevents)

**How can you protect yourself from Man-in-the-Middle attacks?**
Answers vary; but encryption

**What is Kerberos?**
Authentication protocol that uses secret-key cryptography to authenticate users

**What is a Golden Ticket attack?**
An attacker gets access to the key distribution center account allowing them to create authentication tickets to grant access to any resource.

### Web Application Security
**What are the HTTP response codes?**
- 1XX: informational
- 2XX: Success
- 3XX: Redirection
- 4XX: Client-side Error
- 5XX Server-side Error

**Explain OWASP top 10**
A standard awareness document showing top most common security risks to web applications

**Explain SQLi and its three types**
An attacker sends unsanitized data via SQL queries through an application
1: In band SQLi: Queries sent and replied to over the same channel
2: Inferential SQLi: Queries that receive a reply that cannot be seen
3: Out of band SQLi: Queries communicate over a different channel
**How to prevent?**
Sanitize queries

**What is XSS and how to prevent?**
Malicious scripts are injected into websites. For example uploading a script to a fileshare
Sanitize every variable!
1: Reflected XSS: non-persistent, payload contained in the request
2: Stored XXS: persistent, attacker permanently uploads payload
3: DOM based XXS: Payload executed through the website code

**What is IDOR?**
Insecure direct object reference: vulnerability where someone can access an object that belongs to somebody else

**What is LFI, RFI?**
Local/Remote File Inclusion: vulnerability where a file is included to the same/different server without sanitizing the data from the user.

**What is CSRF?**
Forged requests using the credentials of authenticated user making that user preform unwanted actions

**What is WAF?**
Web Application Firewall: Filters and monitors https traffic between web app and the internet.

### Cryptography
**What are encoding, hashing, encryption?**
encoding: converts data to the desired format for exchange
hashing: maintains the integrity of data
encryption: secures data and requires verification to view data

**Differences between hashing and encryption?**
Hashing is the process of converting data into a key using a hash function. Original data cannot be retrieved
encryption is the process of converting plaintext data into unreadable garbage known as the ciphertext. Can be transformed back into plaintext using encryption key
salted hashes increases hash complexity. 

**TLS/SSL**
TLS is the newest version of SSL. Encryption protocol for web communications

### Malware Analysis

Compiler compiles written code, disassembler translates machine code back to assembly language.

**What is the difference between static and dynamic malware analysis?**
Static Analysis: Analyzing malware without running them. Analyzing each step the malware takes.
Dynamic Analysis: Analyzing the malware by running it. Analyzing the impact on the system.

**How does malware achieve persistence on Windows?**
- Services
- Registry Run Keys (Run, RunOnce)
- Task Scheduler
- Infecting clean files

### Event Log Analysis
**Which event logs are available by default on Windows?**
- security
- application
- system

**Successful authentication event ID:** 4624 (logon type 10 for remote auth, 7 for disconnected session)
**Failed logon event ID:** 4625
**Successful RDP session:** 1149

### Threat Intelligence
**What is cyber threat intelligence (CTI)?**
Analysis using techniques and tools to generate information about threats. Used to make informed and proactive security decisions.

**Is an IP address by itself Threat Intelligence?**
No, an ip address can become intelligence when contextualized with the nature of a threat

**What is TAXII in Cyber Threat Intelligence?**
Trusted Automated eXchange of Intelligence Information, defines how threat information can be shared. MIPS

**Name some Threat Intelligence Platforms**
- MISP
- Cisco Talos
- IBM X-Force Exchange
- OTX AlienVault

**What are the types of threat intelligence?**
- Strategic Threat Intelligence
- Tactical Threat Intelligence
- Technical Threat Intelligence
- Operational Threat Intelligence

**What is "living off the land"**
A method where attackers use legitimate, trusted built-in tools already in the target system to conduct attacks over using custom-made attacks.


## InfoSec Interview Questions

### System Administration
**How do you change your DNS settings in Linux/Windows?**
Linux
edit the *network configuration file*
`sudo nano /etc/systemd/resolved.conf`
modify
`DNS=8.8.8.8 8.8.4.4`

Windows
*Control Panel* > *Network and Sharing Center* > *Change Adapter*
Right click active network adapter > *Properties*
Select *Internet Protocol Version 4* > *Properties*

**Does TLS use symmetric or asymmetric encryption?**
Both: initial exchange done by using asymmetric and that bulk data requires speed and therefore asymmetric.

**Difference between symmetric and public-key encryption?**
Symmetric uses one key while public-key uses two
Symmetric encryption uses the same key to encrypt and decrypt, while asymmetric encryption requires a pair of keys using a public key to encrypt and a private key to decrypt the data.


## Fintech/GRC Interview Questions
### AML (Anti-Money Laundering) Laws
CDD (Customer Due Diligence) - Financial institutions must verify the identities of their customers, assess their risk profiles, and monitor their transactions

KYC (Know Your Customer) - Financial institutions must verify the identity of their customers before allowing them to open accounts to prevent fraudulent activities

SAR (Suspicious Activity Reporting) - Financial institutions must report suspicious transactions to regulatory authorities such as FinCEN. 

Financial institutions are also required to keep detailed records of all transactions for a specific period of time. Transactions must also be monitored to help detect illicit and fraudulent activities. Organizations must also ensure that they are not conducting business with sanctioned entities.

### Major AML Regulations
Bank Secrecy Act (BAC) (1970) - Foundation of AML regulations, requires financial institutions to report large cash transactions ($10,000) and suspicious activities.

USA PATRIOT Act (2001) - Strengthened AML measures with focus on combating terrorist financing

Financial Action Task Force (FATF) - International framework providing guidance on AML policies

EU regulations