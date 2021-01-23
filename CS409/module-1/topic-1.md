---
layout: default
course: CS409
module: 1
topic: 1
---

## Introduction

#### Security 
Security refers to any measures taken to protect something.
Eg. locks on doors, alarms in our cars, police officers.

#### Computer security
Computer Security is a field of computer science concerned with the control of risks related to computer use.
- It describe the methods of protecting the integrity of data stored on a computer. In computer
security the measures taken are focused on securing individual computer hosts.

- Network security consists of the provisions made in an underlying computer
network infrastructure, policies adopted by the network administrator to protect
the network and the network-accessible resources from unauthorized access and
the effectiveness (or lack) of these measures combined together.
- It starts from authenticating any user. Once authenticated, firewall enforces access policies
such as what services are allowed to be accessed by the network users.
- Even though it prevents unauthorized access, it prevents harmful contents such as computer
worms being transmitted over the network. An intrusion prevention system (IPS) helps
detect and prevent such malware.

## Threats in Network Security
Considering the tremendous use of distributed systems, the following are the general threats to the security:

1. Disclosure of information
    - Organizations maintain valuable information on their computer systems.

    -  This information may be used by other parties in such a way as to damage the interest of the organization owning the information.

    - Therefore information stored on or processed by computer systems must be protected
against disclosure both internal and external to the user organization.
2. Contamination of information
    - Valuable information may become worthless if unauthorized information is mixed with it.

    - The damage may be as great as the damage through information disclosure.

3. Unauthorized use of resources
    - Unauthorized use of resources may lead to destruction, modification, loss of integrity etc. of resources and thus the authorization of individual users will be limited.


4. Misuse of resources
    - Authorized use of resources may give authorized individuals the opportunity to perform activities that are harmful to the organization.
    - Misuse of resources, intentional or accidental, may be harmful to the organization through corruption, destruction, disclosure, loss or removal of resources.
    - Such misuse may affect the liability of an organization for information entrusted to it or for
transactions and information exchanged with other organizations.

5. Unauthorized information flow
    - In a distributed system, information flow must be controlled not only between users of
end-systems but also between end-systems.
    - Depending on the prevailing security policy information flow restrictions may be applied to
the basis of classification of data objects and end-systems, user clearances, etc.

6. Repudiation of information flow
    - Repudiation of information flow involves denial of transmission or receipt of messages.
    - Since such messages may carry purchasing agreement, instructions for payment etc., the
scope for criminal repudiation of such messages is considerable.

7. Denial of service
    - Because of the wide range of services performed with the aid of computer systems, denial
of service may significantly affect the capability of a user organisation to perform its
functions and to fulfill its obligations.
    - Detection and prevention of denial of service must be considered as part of any security
policy.

## Goals of Computer Security

##### Integrity:
- Guarantee that the data is what we expect
##### Confidentiality:
- The information must just be accessible to the authorized people
##### Authentication:
- Guarantee that only authorized persons can access to the resources

## Security Attacks
Any action that compromises security of information is called a security attack.

Some of the common security attacks are given below.

##### 1. Passive attack: 
Passive attack aims to learn or make use of information from the system but does not affect system resources.

##### 2. Active attack: 
Active attack attempts to alter system resources or affect their operation

---

### 1. Passive Attacks

Goal is to obtain information from the system
- No modification of content or fabrication
- Eavesdropping to learn contents or other information (transfer patterns, traffic flows etc.)

Two types
- Release of message contents
- Traffic analysis

##### 1.1. Release of message contents:
Contents of the messages are released against our wish to someone else.

##### 1.2. Traffic Analysis :
Monitoring the transmission of communication

---
### 2. Active Attacks
Modification of content and/or participation in communication to Four types
- Impersonate legitimate parties (Masquerade)
- Replay or retransmit
- Modify the content in transit
- Launch denial of service attacks

##### 2.1. Masquerade:
When one entity pretends to be a different entity.
##### 2.2. Replay : 
Captures a sequence of events or some data units and resends them.
##### 2.3. Alteration : 
Change to the original message.
##### 2.4. DOS : 
Prevent Legitimate users from accessing some services.