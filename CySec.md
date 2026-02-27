# Basics

### Key terms

- **non-repudiation** - prevents parties from denying actions they have performed.
- **accountability** - ability to trace actions and decisions back to a specific person or system. 
- **authentication** - verifies the identity of a user or system. 
- **authorization** - determines what actions an authenticated entity is allowed to perform. 
- **access control** - restricts access to resources based on defined rules. 
- **business continuity** - ensures critical operations continue during disruptions. 
- **security policy** - a rule or expectation for protecting information. 
- **compliance** - adherence to laws, regulations, and (security-)standards.
- **asset** - any item of value belonging to an organization 
- **attack** - an act that intends to damage, steal or degrade an organizations assets 
- **vulnerability** - a flaw or weakness in a system that can be abused 
- **exploit** - a technique or method used to take advantage of a vulnerability 
- **threat** - an event or action with the potential to cause harm by exploiting a vulnerability 
- **risk** - the likelihood of a threat exploiting a vulnerability and the potential harm that could cause 
- **control** - a measure designed to reduce the potential risk of an attack 
### Information Types

**"Information" definition**: An organization’s data that has been processed, organized, or structured in a way that gives it meaning and value to an organization or individual.

1. Personal information
2. Business information
3. Financial information
4. Intellectual property
5. System information

### Information Security

**Definition**: Protection of the integrity, confidentiality and availability of information data whether in storage, transit or processing.

**Why protect information?**
- Prevent financial losses
- Protect privacy and personal data
- Maintain trust and reputation
- Ensure business continuity

### Attacks on Information

Three states of data:

- **In Storage**
	- Data that is stored on a server or in a database short-term or long-term.
- **In Transit**
	- Data that is currently being transported from one place to another.
- **In use**
	- Data that is currently being processed by a service or another entity.

An attacker only has to find a weakness in one of the steps while a defender has to defend all of them at once.


### Components of an Information System

- **Software**
	- Applications, operating systems, utilities
- **Hardware**
	- Physical devices such as computers, servers and networking equipment
- **Data**
	- The raw information in an information system.
- **People**
	- Users, administrators and other parties that interact with the IS and make decisions.
- **Procedures**
	- Policies, instructions and processes that guide how information is handled.
- **Networks**
	- Communication systems that connect devices and allow information to be transmitted.
### Balancing Security and System Usability

- Perfect Information Security is impossible
- Security needs to protect people without slowing them down
	- Too much security and people will start creating work-arounds, making the system insecure again
	- Too little and the system is exposed to unnecessary risks
	- All about finding that sweet spot between security and usability

### Implementation of Security

#### "Bottom-Up" approach

"A method of establishing security policies that is initiated by upper management instead of admins."

- Initiated by an organization’s technical staff (system engineers, admins, etc.).
- Implementations happen before policies are defined. 
- Often lacks support from management, budget and consistency. 
- Generally less effective and not scalable in large organizations.

#### "Top-Down" approach

"A method of establishing security policies as a grassroots effort in which admins attempt to improve the security of their systems."

- Initiated and supported by an organization’s upper management. 
- Policies come first and provide guidance for implementations. 
- Ensures proper funding, authority and organization-wide enforcement. 
- Generally more effective and in-line with the business strategy.


# Threats & Attacks

Threats come from different directions and can be broadly categorized for systematic analysis.

- Categories help me ask: *"Which types of attacks are most likely and most damaging?”* 
- **Typical Categories**: external or internal, intentionally or unintentionally, physical, technical, administrative, social or environmental risks

### Social Engineering

The psychological manipulation of individuals to trick them into revealing confidential information or performing actions that can compromise security.

**Subcategories**

- **Phishing** - Forged emails impersonating legitimate entities. 
- **Spear Phishing** - Targeted phishing against specific individuals. 
- **Vishing** - Voice-based phishing over phone or video calls. 
- **Smishing** - SMS / Text-based phishing.

### Software Attacks & Malware

Attacks involving malicious code or malware designed to damage systems, steal sensitive data, or gain unauthorized access to systems or services.

**We distinguish:** Weaknesses in Software and Malicious Software

**Malware Types**:

- **Virus** - Malware that attaches to programs and spreads. 
- **Worms** - Self-replicating malware that spreads over a network. 
- **Trojan Horse** - Malicious software disguised as legitimate applications. 
- **Ransomware** - Malware that encrypts victim’s data and demands payment to restore access.
- **Rootkits** - Stealthy tools that hide malicious activity and maintain privileged access.
### Denial of Service (DoS)

Attacks aims at making a system or service unavailable by overwhelming it with excessive traffic or requests.

**Important Terms:**

- **DoS** - Single source denial of service attacks. 
- **DDoS** - Denial-of-service attacks performed by multiple attackers or attacking devices. 
- **Botnet** - A network of compromised computers and other devices controlled by an attacker and used to together to flood a target with excessive traffic. 
- **SYN-Flood Attack** - Sending many connection requests without completing them. 
- **Reflection Attack** - Attacker sends requests to a service and spoofs the victim’s IP making the service send (many) replies to the victim instead of back to the attacker
### Web Application Attacks

Exploits vulnerabilities in web applications to steal data, manipulate content, or gain unauthorized access.

**Subcategories:**

- **SQL Injection** - An attacker inserts malicious SQL commands into an input to manipulate a database and access, modify, or delete data. 
- **Cross-Site Scripting (XSS)** - An attacker injects malicious scripts into a website that execute in other users’ browsers to steal sensitive data. 
- **Cross-Site Request Forgery (CSRF)** - An attacker tricks a logged-in user’s browser into sending unauthorized requests to a web application on their behalf. 
- **Broken Authentication** - Weak authentication mechanisms allow attackers to compromise passwords, sessions, or identities to gain unauthorized access
### Password / Authentication Attacks

Attacks that attempt to bypass or compromise login systems to gain unauthorized access to a system or service.

**Subcategories:**

- **Rainbow Table Attacks** - Attackers using precomputed hash lookup tables to reverse weakly hashed passwords back into plaintext. 
- **Password Spraying** - Attackers trying a few common password like “password” across many accounts to avoid lockouts or timeouts. 
- **Credential Stuffing** - Attackers using leaked usernames and passwords from previous breaches to attempt logins on other services. 
- **Brute Force Attack** - Attackers repeatedly try many username and password combinations until they successfully gain access to an account.


### Physical Threats

Threats or attacks that affect the physical infrastructure supporting information systems, usually bypassing technical controls overall.

**Subcategories:**

- **Theft of devices** - Attackers physically steal hardware to gain direct access to stored data, credential, internal systems, or other sensitive data. 
- **Hardware tampering** - An attacker modifies or implants malicious components in physical equipment to intercept data, bypass security, or disrupt operations. 
- **Power disruption** - Attackers interrupt or manipulate power supply to shut down or destabilize critical systems or services impacting availability and business continuity. 
- **Environmental damage** - Natural or deliberate environmental events that damage infrastructure, causing data loss, downtime, or destruction of critical systems (e.g., earthquake, fire).
# Models
## CIA-Triad

The CIA triad is a foundational information-security model stating that **systems should protect**...

- **Confidentiality**
	- Prevent or minimize unauthorized access to information.
	- Ensured through encryption, access control and advanced auth. mechanisms
- **Integrity**
	- Protecting the reliability and correctness of information.
	- Ensured through digital signatures, hashing and checksums, and change management
- **Availability**
	- Ensuring that subjects have timely and uninterrupted access to information.
	- Ensured through redundancy and backups, DDoS protection, and Incidence Response

## STRIDE Model

A structured model developed by Microsoft used in cybersecurity to **identify** and **categorize threats to systems** by looking at how they can be attacked.

- **Spoofing** - Pretending to be someone else
- **Tampering** - Unauthorized data modification or altering
- **Repudiation** - Denying actions without proof
- **Information Disclosure** - Exposing sensitive information
- **Denial of Service** - Making systems or services unavailable
- **Elevation of Privilege** - Gaining unauthorized rights or privileges

## McCumber Cube

The McCumber Cube shows how the CIA security goals are applied across data states and safeguards to mitigate threats identified by frameworks like STRIDE.

- **Y-Axis** - Security Goals (CIA Triad)
	- Defines what needs to be protected
- **X-Axis** - Information States
	- Describes where the information exists
- **Z-Axis** - Safeguards/Controls
	- Defines how protection is implemented
	- 

![[Pasted image 20260227104540.png]]
