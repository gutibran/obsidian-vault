# CIA Triad
This is a model used to guide an organization's security principles. Each element is essential to any security program.
## Confidentiality
Prevents unauthorized disclosure. Keeps secret information secret.

## Integrity
Prevents unauthorized alteration of information or systems. Can be intentional or unintentional.

## Availability
Ensures authorized users have access to information and or systems when they are needed.


# Security Scenarios
These are little stories that are told in a question which then asks how you would react. The best way to choose the correct answer is to determine which element of the CIA triad is driving the scenario.

## Confidentiality Scenarios
Ensures data is only viewed by authorized users.

### Encryption
Encryption makes data unreadable to unauthorized personnel. Authorized personel can decrypt the data to access it. This is the best way to protect confidentiality of data.

A common example is when a person needs to send PII (personally identifiable information) through email or some unencrypted network "medium". That person could encrypt their data before sending it. This protects the data's confidentiality.

### Access Controls
These are the three core activities for **identity and access management**. Use access control to grant and restrict access.
#### Identification
Some unique identifier or piece of information that differentiates people. An example could be a username.
#### Authentication
Prove that you are who you say you are by providing information that only you would know. An example is a password.

#### Authorization
These are the actions that a user can perform once they have proven their identity. Only they can perform these actions. An example is permissions.

## Integrity Scenarios
Ensures the data has not changed through tampering, modification, corruption. Unauthorized users, malware (malicious software), system error, human errors.

A hashing algorithm can be used to enforce integrity. A hash is a alphanumeric string created by a hashing algorithm. The algorithm takes in data and produces that kind of output, called a hash. Hashes are fixed-length and irreversible.

**If the data never changes the hash will never change**. Different hashes mean different inputs (data) were were used to create the hash. This means the data was changed. Meaning the data has lost integrity.

Examples include messaging applications, downloads over the network (if a single bit is missing or changed then integrity is lost), checking hashes for downloaded data.

```bash
# create md5 hash of some data
md5sum
```

## Availability
Ensure data and or systems are available when needed for authorized users. Redundancy and fault-tolerant methods are used. Keep software up to date and patched so bugs do not interfere with availability. Address single points of failure.

Examples are RAID, failover clusters, backups, and generators.

### Redundancy and Fault Tolerance
Duplication of critical systems and or data provides **fault tolerance**. If a fault occurs the system will not go down and continue to operate.

The main goal is to **remove each single point of failure (SPOF)**. SPOFs can cause the entire system to fail.

#### Disk Redundancies
Fault-tolerant disks allow the system to operate even if a disk fails. Examples are RAID-1 (mirroring), RAID-5 (striping with parity), and RAID-10 (stripping with mirror).

#### Server Redundancies
If one server fails within a system (failover cluster), the system will switch to a redundant or standby server to keep the service up and running.

#### Network Redundancies
Use multiple servers for a single service, this is called **load balancing**. **Network Interface Card (NIC) teaming** is when multiple network cards are used in a single server to increase bandwidth and for redundancy.

#### Power Redundancies
**Uninterruptible power supplies (UPS)** and power generators are used when commercial power fails.

### Scalability and Elasticity
Scalability is the ability to increase the capacity of a system or service to meet new demand. Adding more servers to meet demand is called **horizontal scaling**.

Adding more hardware resources or upgrading hardware resources to existing servers such as RAM and CPU is called **vertical scaling**. There are limits to vertical scaling based on the hardware.

Elasticity is the automation of horizontal scaling based on the demand. For example if 3 servers are used to serve a website during normal demands but during high demands more servers are added. When the extra servers are no longer needed it goes back down to the normal amount to meet normal demands.

### Patching
When bugs are found in software, the developers that originally wrote the software squash the bugs and release the software without the bugs which in turn fixes the problems. This is important because some bugs may allow attackers way into the system.

### Resiliency
Current trends focus on resiliency rather than the highest possible availability. This if for cost reasons. **TCO (total cost ownership)**.

Resiliency methods help the system heal itself and recover from faults with minimal downtime. Regularly perform and test full backups, backup power stores, NIC teaming, redundant disks. Resiliency methods expect components to retry after a failed process.

## Resource availability versus security constraints
The main challenge is finding the balance between availability and security constraints. For example one might think that everything in the system should use encryption. Encryption increases the size of data which means the size of the disks to store the encrypted data must be sufficient. At scale it will be costly. Encryption requires more processing power and memory. This will slow down applications and cost more for computing power. Executives want to minimize the cost without sacrificing security.

# Introducing Basic Risk Concepts
- **Risk** is the possibility of a threat exploiting a vulnerability which results in a loss.
- **Threat** is any event that has potential to compromise the CIA triad.
- **Vulnerability** is a weakness found in the hardware, software, configuration file(s), or the users.
- **Security incident** is the result of an attacker exploiting a vulnerability and negatively affecting the CIA triad of an organization's system and data. Attacks, malware, data loss, etc.
- Threats can from **malicious insiders** (someone in the organization), outsider (from anywhere in the world), nature, etc.
- **Risk mitigation** is the process of reducing risk through **security controls**. Reduce the chance that a threat will exploit a vulnerability or the impact that it will have. Implement **countermeasures** and **safeguards**.

# Selecting Effective Security Controls
There are a bunch of security controls that an organization can implement. For the exam you just need to know the categories of security controls. These are to reduce risk.

## Control categories
These are control categories. Describe how a control works.

### Technical controls
Software, hardware, firmware. Admin installs and configures a technical control which will provide protection automatically.

### Encryption
Scrambles data to be unreadable to unauthorized users. This protects the confidentiality of the data.

### Antivirus
Provides protection against malware infection.

### Firewalls
Restrict network traffic going in and out of the network.

### IDS and IPS
**Intrusion detection system (IDS)** and **Intrusion prevention system (IPS)** for monitoring the network and or host for intrusions and provide ongoing protection against a variety of threats.

### The principle of least privilege
Individuals and or processes are given the minimum amount of privileges to their work and nothing more. A combination of rights and privileges.

## Managerial controls
Administrative functions. Documented and written in an organization's in security policy. Planning and assessment methods are used to review an organizations ability to reduce and manage risk.

### Risk assessments 
Quantify and qualify risks within an organization. Quantify the value of assets to be protected and the cost of protecting those assets. Based on the cost. Qualitative is based on judgement to categorize risks based on probability and impact.

### Vulnerability assessments
Discover vulnerabilities that currently exist within the system.

## Operational controls
Ensure day to day operations comply with the security policy. Humans implement them.

### Awareness and training
Training employees about threats, best practices, etc. Making sure employees are aware of their "surroundings".

### Configuration management
Configuring systems and services with a baseline of security and hardening. Prevent changes that will result in errors.

### Media protection
Backing up and encrypting storage media that contains sensitive information.

# NIST and SP 800 Documents

**NIST (National institute of Standards and Technology)** is a part of the U.S. Department of Commerce that publishes **Special Publications (SPs) in the 800 series** that are important references for the security community. These documents aid in the design of secure systems and networks.

**SP 800-53 "Security and Privacy Controls for Information Systems and Organizations"** is about security controls. It consists of three chapters followed by three appendices. **Appendix C** is a security control catalog which provides details on hundreds of individual security controls split up among 20 different families.

NIST originally categorized the controls as technicl, managerial, or operational. Over time controls included one or more characteristics, so NIST removed these references.

Learn more [here](https://csrc.nist.gov/publications/sp800.)

### Physical controls
Physical security such as locks, security guards, anything tangible that you can touch. Physical types can also categorized as different control types.

## Control types
Describe the goal they are trying to achieve.

### Preventative controls
Prevent an incident from occurring.

#### Hardening
Making a system or application more secure than its default configuration. Disable unnecessary ports and services, implement secure protocols, keep system patched and up to date, use strong passwords and password policy, disable default and unnecessary accounts. **Change management** prevents a configuration from starting an outage of a system or service.

#### Training
Keeping users and or employees aware of security vulnerabilities and threats. Good for them to know about social engineering.

#### Security guards
A deterrent. The presence of a security guard and verifying identities may prevent an attacker from trying at all.

#### Account disablement process
Disabling user accounts when an employee leaves an organization.

#### IPS (Intrusion Prevention System)
Block malicious traffic before it reaches the network.
### Detective controls
Detect when vulnerabilities have been exploited resulting in a security incident.

#### Log monitoring
Logs record details of activity on systems and networks. These methods can be automated to detect incidents and report them right after they occur.

#### SIEM (Security Information and Event Management) Systems
Monitor logs, detect trends, and raise alerts in real time. Trends are found by analyzing past alerts. Categorize by the type of attack.

#### Security Audit
Examines the security posture of an organization. Check if policies are implemented correctly.

#### Video Surveillance
**Closed-circuit Television (CCTV)** records activity and detect events. This can also act as a deterrent.

#### Motion detection
Alarm systems detect motion.

#### IDS (Intrusion Detection System)
Detect malicious traffic before it reaches the network. Send an alarm to IT personel.

### Corrective controls
Restore normal operations after an incident occurs as quickly as possible. Restore the CIA triad that was affected by the incident.

#### Backups and system recovery
Ensure data can be recovered if data is lost or corrupted.

#### Incident Handling Processes
The steps to take in response to security incidents. Incident response policy and plan.

### Deterrent controls
Discourage attackers or threats. Prevent security incidents related to unauthorized access.

#### Warning signs
Signs outside of a facility. Monitoring.

#### Login banners
Digital warning sign.

### Compensating controls
Alternative controls when primary control is not feasible. 

### Directive controls
Instructions to individuals on how they should handle security related incidents.

#### Policies, standards, procedures, and guidelines
**Policies** are high-level goal statements for the organization.
**Standards** describe how to configure systems, applications, and security controls properly.
**Procedures** are step by step guidance on achieving a goal.

#### Change management
Ensures that changes do not cause an outage. Changes are evaluated in a change management process before being made.

# Combining control categories and types
The control categories and control types are not mutually exclusive meaning the controls can be described using more than 1 category and more than 1 type.

# Logging and monitoring
Logs help admins and security investigators determine what happened, where, and who or what did it. Create an **audit trail** to find all the events that preceded a security incident.

# OS / Endpoint Logs
All OSs have the ability to generate and store logs. For the exam **be familliar with Windows and Linux logs.**

## Windows logs
View logs with the **Windows Event Viewer**.
### Security Logs
 It functions as a **security log, access log, and audit log**. Success indicates that an audited event completed successfully, such as a user logging in or deleting a file. Failure is the inverse indicates that the user did some action event that failed.
 
### System log
Records events relating to the functioning of the OS. Startup, shutdown, services starting and stopping, drivers loading or failing, any other system component deemed important by the system developers.

### Application log
Records events sent to it by applications or programs running on the system. Any application has the ability to write application logs.

## Linux logs
Logs are stored in the `/var/log/` directory. View system logs with `cat` in a terminal emulator or with a GUI system log viewer. Authentication logs are commonly stored in `auth.log` which can be viewed with `cat /var/log/auth.log`. The locations may vary depending on the Linux distribution.

- `/var/log/syslog`
- `/var/log/messages`

These contain system messages logged during startup, mail, the kernel, and other OS activities.

`/var/log/secure` contains information related to authentication and authorization of user sessions. For example SSH login, attempts, etc.

## Network logs
Records traffic on the network. These logs are on routers, firewalls, web servers, IDS/IPS. These devices can be configured to log specific information. For example all the traffic that the device passes, traffic that is blocked,  Useful for troubleshooting connectivity issues and when identifying potential intrusions or attacks.

### Firewall logs
Decide what traffic is allowed to enter and what traffic is blocked from entering. It tracks every attempt to enter the network and creates detailed logs for that.

## IDS/IPS logs
Monitor for malicious activity. IDS will simply alert admins when possible intrusions occur. IPS will try to block the suspicious content. Good source of security log data.

### Packet captures
**Protocol analyzers (sniffers)** capture network traffic allowing admins to view and analyze individual packets.

## Application logs
These are logs generated by applications. For example web servers will log requests. They follw the **Common log** format specified by **The World Wide Consortium (W3C)**. Contains metadata about the request;.

## Metadata
Information about information or data. Most applications store metadata about files or messages. Useful for security investigators. Can be found in emails, images, etc.

# Centralize logging and monitoring
Manually checking logs on all systems, applications, services, etc. can be challenging. The standard solution for this is to use a **centralized system** to collect log entries.

## SIEM (security information and event management)  systems
A centralized solution for managing, analyzing, collecting data from systems, applications, and infrastructure devices. It combines the functionality of **SEM (security event management) systems** and **SIM (security information management) solutions**.

SEM is for real-time monitoring, analysis, notifications of incidents.
SIM is for long term storage of the data, analysis (looking for trends and creating reports to verify compliance with laws and regulations).

SIEMs uses scripts to automate monitoring and reporting.

SIEM vendors may sell applications and dedicated hardware but the following capabilities are shared by most SIEMs on the market today.

### Log collectors
Collects log data from endpoints (hosts) on the network and stores them in a database.

### Data inputs
Log entries can come from a variety of different sources. Firewalls, routers, IDS/IPS, applications, web servers, databases, etc.

### Log aggregation
Aggregation in this context means to combine dissimilar items into one similar format. The data input store logs in different ways. The SIEM handles the aggregation and puts them all together in a format that is easy for the user to analyze, search, etc.

### Correlation engine
A software component that is used to collect and analyze event log data from various systems within the network. Looks for **common attributes** within the data to aggregate. Analytical tools are used to detect patterns of potential security events and raises alerts.

### Automated reporting
SIEMs come with built-in reports for different categories such as network traffic event monitoring, threat events, logon/logoff events, compliance with specific laws, etc. This what all things were in Wazuh. Need to make a lab of that when I fix my PC.

### User behavior analysis
Watches what users are doing through applications, network, system, etc. Watch critical files and see what events occurred. Search for abnormal patterns of behavior. Sounds like how I got caught.

### Security alerts
SIEMs come with predefined alerts for events. Continuous monitoring for suspicious activity. Can create new events and alerts too.

### Automated triggers
A trigger causes an action in response to a predefined number of repeated events. For example say there is a limit on the number of SSH attempts one can perform before an automated trigger fires. After that limit the SIEM will change the environment and stop the attack. It may modify the firewall, disable SSH, etc. SIEMs offer the ability to create new triggers and modify existing ones.

**Alert tuning** is the challenge of tuning the sensitivity levels to limit false positivies while avoiding false negatives.

### Time synchronization
All servers sending data to the SIEM should be synchronized with the same time. This is very important for investigations to have accurate times. The SIEM needs to compensate for the offset in times. The **Network Time Protocol (NTP)** provides a way for all system clocks of all the devices in an organization to be in sync.

### Archiving
It is not possible or reasonable to keep all information in active storage. SIEMs offer functionality to export data onto cheaper offline storage. This is for data that is not needed.

### SIEM dashboards
This is an overview of meaningful data and activity. Customization. Real-time reporting and continuous monitoring. **Large network operation center (NOC)**.

These are the common elements of a SIEM dashboard. Re-read this part later.
- sensors
- alerts
- correlation
- trends

### Syslog
The **syslog protocol** specifies the general log entry format and the details on how to transport log entries. Systems sending syslog messages are called **originators**. The systems receiving the message are called **collectors**. Collectors can receive messages from external devices and applications on the same system.

# Practice questions 
First attempt 13/15 correct.
1. C
2. B
3. A
4. A
5. D
6. B -> C
7. D
8. A
9. B
10. D
11. C
12. C ->
13. B
14. A
15. D