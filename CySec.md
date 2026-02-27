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

# Information Security Management

## Information Security Governance

The system by which an organization directs and controls its information security strategy to ensure that it supports business objectives, manages risk appropriately, and complies with legal and other regulatory requirements.

- **Strategic Direction**
	- Defining security objectives aligned with business goals. 
- **Leadership and Accountability**
	- Having clear roles and responsibilities for security decisions. 
- **Risk Management**
	- Defining risks and ensuring they are identified and addressed appropriately. 
- **Regulatory Compliance**
	- Ensuring adherence to laws and regulations (e.g. NIS2, HIPAA, CRA)

![[Pasted image 20260227132357.png]]

## Information Security Management Systems (ISMS)

A structured framework used to systematically manage and protect an organization’s assets through various policies, processes and controls. 

*Security governance defines **what** an organization wants to achieve. An ISMS defines **how** the organization wants to manage it.*

- **Enterprise Information Security Policy (EISP)**
	- The information security policy that sets the strategic direction and scope for all an organization's security efforts. 
- **Risk Management Process**
	- Definition of processes to identify assets, analyze threats and evaluate risk. 
- **Security Awareness and Training**
	- Educational programs to ensure employees understand their security responsibilities. 
- **Monitoring, Measurement and Audits**
	- Ongoing evaluation of control effectiveness and ISMS performance.

## Thinking of Security Controls

**Definition**: Measures to reduce risk by detecting, preventing, responding to, or mitigating threats to organizational assets.

- **Administrative / Management Controls** 
	- Policies, procedures, security training, security governance, etc. 
- **Technical / Logical Controls**
	- Firewalls, encryption, access control systems, system hardening, etc. 
- **Physical Controls** 
	- Physical locks, surveillance cameras, secure access badges, turnstiles, etc.

## Security Controls by Function

 - **Preventive Controls**
	 - Stop incidents before they occur.
	 - *e.g., Firewalls, access control, encryption, etc.* 
 - **Detective Controls**
	 - Identify incidents when they occur.
	 - *e.g., Intrusion detection, log monitoring, SIEM, CCTV, etc.* 
 - **Corrective Controls**
	 - Limit damage and restore systems after an incident.
	 - *e.g., Backups, system restore, incident response, etc.* 
 - **Deterrent Controls**
	 - Discourage malicious behavior. 
	 - *e.g., Warning banners, monitoring notices, disciplinary policies, etc.* 
 - **Compensating Controls**
	 - Reduce risk when a primary control cannot be implemented.
	 - *e.g., Network isolation, layered security, alternative safeguards, etc.*

## Business Continuity Management

**Definition**: Ensures that critical business functions can continue during and after incidents or disruptions such as cyberattacks, system failures, or physical incidents. 

*Even with strong security controls in place, incidents can and will still occur at some point. BCM prepares the organization to operate and recover during these times.*

**Key Objectives:** 

- **Maintain critical operations during incidents.** 
	- e.g., backups, redundant services, manual processing, etc. 
- **Minimize downtime and financial impact.** 
	- e.g., fast system restore, emergency support contracts, incident response team, etc. 
- **Protect people, assets and reputation**
	- e.g., evacuation plans, fire suppression systems, customer notification processes, etc. 
- **Enable fast and structured recovery**
	- e.g., disaster recovery playbooks, tested backup restoration, post-incident review processes, etc.
## What is Security and Awareness Training?

**Definition**: A coordinated program designed to ensure that all members of an organization understand their security responsibilities and have the knowledge and skills to protect information assets.

|                      | Awareness (Level 1)                                                                                  | Training (Level 2)                                                                                           | Education (Level 3)                                                                                                                |
| -------------------- | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| **Objective**        | Seeks to teach members of an organization **what** security is and what to do in certain situations. | Seeks to train members of an organization **how** they should react and respond to certain situations.       | Seeks to educate members of an organization as to **why** the organization reacts the way it does.                                 |
| **Complexity Level** | Offers **basic information** about threats and responses.                                            | Offers more **detailed knowledge** about detecting threats and teaches skills needed for effective reaction. | Offers the background and **depth of knowledge** to gain insight into how processes are developed and enables ongoing improvement. |
| **Teaching Method**  | • Videos<br>• Newsletters<br>• Posters<br>• Informal Training                                        | • Informal Training<br>• Workshops<br>• Hands-on Practice                                                    | • Theoretical Instruction<br>• Discussions / Seminars<br>• Background Reading                                                      |
| **Impact Timeframe** | Short-term                                                                                           | Intermediate                                                                                                 | Long-term                                                                                                                          |
## Gap Analysis

**Definition**: The process of comparing an organization’s current security posture with a required or desired target to identify missing or insufficient controls.

![[Pasted image 20260227140226.png]]

- **Risk Analysis:** What could go wrong?
- **Gap Analysis:** Where are we non-compliant or under-protected?

## What is a Security Framework?

**Definition**: A structured set of principles, processes, and controls that organizations use to manage risks and protect their information systems, assets, and operations.

**Popular Frameworks:** 
- **ISO/IEC 27000**
	- Global standard for information security management systems (ISMS). 
- **NIST Cybersecurity Framework**
	- Practical framework for managing cyber risk 
- **CIS Controls**
	- Defines 18 highly practical technical security controls 
- **ISACA CORBIT**
	- An IT governance and risk management framework.

### ISO/IEC 27000

**Purpose**: A set of standards for ISMS, helping organizations systematically protect information assets using a risk-based approach.

Core Standards:
- **ISO/IEC 27000:** Introduction, terminology, and key concepts (e.g., risk, asset, control, etc.) 
- **ISO/IEC 27001:** Defines requirements to establish, implement, maintain, and improve an ISMS. 
- **ISO/IEC 27002:** Practical guidance for implementing controls. 
- **ISO/IEC 27005:** Focuses on risk management methodology. 
- **ISO/IEC 27017:** Additional guidance for cloud services. 
- **ISO/IEC 27018:** Focuses on privacy and personal data protection in cloud environments.

### NIST Cybersecurity Framework

**Purpose**: A risk-based guideline that helps organizations to structure, manage, and improve their cybersecurity activities across the full lifecycle of prevention, detection, and response.

**Key Content:** 
- It’s organized into five core functions; Identify, Protect, Detect, Respond, Recover. 
- Provides categories and subcategories of cybersecurity outcomes and controls. 
- Includes implementation tiers to assess cybersecurity maturity. 
- Is very flexible and adaptable to any organization or business sector. 
- Not certifiable, primarily used as guidance and best practice.

# Risk Analysis

**Definition**: The process of identifying assets, threats, and vulnerabilities, and evaluating the likelihood and impact of potential adverse events to determine the level of risk.

![[Pasted image 20260227134538.png]]

### Identifying Assets

**Asset**: Any resource that has some kind of value to an organization and therefore requires protection.

**Types of Assets:**

- **Information Assets**
	- Customer data, intellectual property, source code, etc.
- **Technical Assets** 
	- Services, applications, databases, networks, etc.
- Physical Assets 
	- Servers, devices, facilities, infrastructure, etc.
- **Human Assets**
	- Employees, administrators, contractors, key personnel, etc.
- **Business Process Assets**
	- Critical operational workflows

### Classifying Assets

**Definition**: The process of assigning every asset to a class based on their value, sensitivity and impact if compromised.

![[Pasted image 20260227134821.png]]

### Identifying Threats

**Definition**: A potential event, actor, or action that could exploit a vulnerability and cause harm to an asset.

**Examples**:
- Power Outages
- Insider Threat
- Datacenter Fire
- Vishing Attack


# Policy, Standards and Practices

![[Pasted image 20260227133058.png]]

## Policies

### Key terms

- **policy** - instructions that dictate certain behavior within an organization. 
- **guidelines** - non-mandatory recommendations employees may use as a reference. 
- **procedures** – step-by-step instructions designed to assist employees in following policies. 
- **practices** - examples of actions that illustrate compliance with policies. 
- **standard** - a detailed statement of what must be done to comply with a policy.
- **de jure standard** - a standard that has been formally evaluated and approved by a formal standards organization 
- **de facto standard** - a standard that is widely adopted or accepted by a public group.

### What is a policy?

**Definition:** A high-level, management-approved rule that defines mandatory organizational behavior and translates external laws and regulations into enforceable internal requirements. 

#### What does a policy do? 
Establishes authority, accountability, and responsibilities for protecting information assets. Provides the foundation for standards, procedures and guidelines. 

#### Who is responsible for policies? 
Policies are created and approved by senior management, ensuring organizational commitment. Management is responsible for enforcement while employees and users are responsible for compliance. 

#### How is a policy enforced? 
By clearly communicating it to all relevant parties, integrating it into standards and procedures, monitoring compliance through audits and oversight, and applying defined disciplinary measures when violations occur

### Why do we need policies?

**Cyber Resilience Act (EU)** 
Requires secure-by-design digital products and vulnerability management (starting December 2027). 

**Health Insurance Portability and Accountability Act (U.S.)** 
Requires administrative, technical, and physical safeguards for protecting patient health data from disclosure. 

**NIS2 Directive (EU)** 
Mandates cybersecurity risk management and incident reporting for critical and important entities. 

**Local Laws** 
Many regions have their own data protection or breach notification laws in additional to national or EU regulations.
### Policy Example

**Secure Product Development Policy**

**Purpose**: To ensure all digital products are developed, released, and maintained in compliance with the CRA. 
**Scope**: Applied to all employees, contractors, and third parties with access to company systems, networks and information assets.

**Policy Statements:** 

- All products shall follow secure-by-design and secure-by-default principles. 
- Security risks shall be identified and treated throughout the product lifecycle. 
- Vulnerabilities shall be monitored, assessed, and remediated in a timely manner. 
- Security updates shall be provided for supported products. 
- Significant security incidents shall be reported in accordance with legal obligations.

**Enforcement**: Violations may result in disciplinary action, including termination of employment and potential legal consequences.
### From Policy to Implementation

**Policy:** Secure Product Development Policy

**Standard:** Vulnerability Remediation Standard
Critical vulnerabilities (CVSS ≥ 9.0) must be remediated within 14 days of identification before product release or through a security update if already deployed.

**Guideline:** Preventing Vulnerabilities During Development
Developers should follow secure coding best practices, validate input to prevent injection attacks and avoid using outdated libraries.

**Procedure**: Remediating a Critical Vulnerability
1. Log the vulnerability in the vulnerability tracking system.
2. Assess severity using CVSS scoring.
3. Assign remediation responsibility to the product team.
4. Release the update to customers.
5. Document remediation and close the ticket.

### Designing Effective Policies

Developing and implementing effective security policy ensures that an organization’s security objectives are clearly defined, consistently enforced, and aligned with business goals. 

1) **Development** 
	- Policies must align with organizational goals, business risks and legal requirements. 
2) **Distribution**
	- Policies must be distributed to all affected entities in a timely manner. 
3) **Comprehension**
	- Policies must be readable for, available to and read by all affected entities. 
4) **Compliance**
	- Policies must be formally agreed to by act or affirmation. 
5) **Enforcement**
	- Policies must be uniformly applied to all affected entities. 
6) **Review**
	- Policies must be reviewed regularly in a changing environment.
### Enterprise Information Security Policy (EISP)

**Definition**: The high-level information security policy that sets the strategic direction, scope and tone for all an organization's security efforts and policies.

- Guidance for the development, implementation and management of the security program. 
- Sets the requirements that must be met by the information security blueprint. 
- Defines the purpose, scope, constraints and applicability of the security program. 
- Assigns responsibilities for the various areas of information security. 
- Addresses legal compliance.
### Elements of an EISP

Although the content of EISP documents varies among organizations, most EISP documents should include the following elements. 

- **Statement of Purpose**
	- Statement of intent that defines the scope, objectives, and purpose of the enterprise information security policy and establishes its role as the foundation for all supporting security documents. 
- **Information Security Elements**
	- Definition of information security that outlines the core principles and concepts, including confidentiality, integrity, and availability, guiding the organization’s security efforts. 
- **Need for Information Security**
	- Definition of the importance of information security within an organization and its legal and ethical responsibility to protect information about customers, employees, and markets. 
- **Information Security Responsibilities and Roles**
	- Description of the organizational structure that supports information security, including defined roles and responsibilities for management, employees, and users, as well as responsibility for maintaining the policy itself.
### Issue-Specific Security Policy (ISSP)

**Definition:** An organizational policy that provides detailed, targeted guidance to instruct members of an organization in the use of a specific resource.

- Supports the EISP by translating it into an issue-specific guidance. 
- Establishes rules for access, monitoring, and protection of the resource. 
- Defines acceptable and unacceptable use of the specified technology or resource. 
- Assigns responsibilities and accountability to users, administrators, and management.
### Elements of an ISSP

Even though the details may vary from policy to policy, it is essential for management to address and specify each of the following elements.

- **Statement of Policy**
	- Definition of the policy and its purpose within the organization. 
- **Appropriate Use of Resource**
	- Specification of who can access the resource governed by the policy and what it can be used for, as well as a definition of misuse that can be penalized (e.g., personal use, copyright infringement). 
- **Violations of Policy**
	- Definition of appropriate penalties and repercussions in case of a policy compliance violation. 
- **Policy Review and Modification**
	- Procedures and a schedule for periodic review of this policy and its contents. 
- **Limitations of Liability**
	- Defines the organization’s limits of legal responsibility for damages or misuse of resources governed by the policy.