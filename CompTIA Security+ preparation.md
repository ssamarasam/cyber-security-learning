# CompTIA Security+ (SY0-701) exam reparation

The google certified cyber security professional certification courcse(completed already) covered many concepts requried for Comptia Security exam.
For this particular exam and for the unconvered topics from previous course, Im learning it from *Ian Neil's Comptia Security+ Study Guide*

## Domain 1 : General Security Concepts

### Compare and Contrast various security controls
Security controls
1. technical
2. managerial
3. operational
4. physical

Technical
- plays a crucial role in minimizing vulnerabilities within an org's technical systems
- computer networks, software, and data management
- firewalls, data encryption

Managerial
- plays a pivoting role in reducing risks within an org
- implementing policies, procedures, practices
- performance reviews, risk assessments, code of conduct

Operational
- managing operational procedures, ensuring adherience to quality, standards, productivity and optimizing efficency
- incident respoonse procedures  - steps to be followed during an incident (mini security breaches, , mitigate security risks, restore normal operations)
- Security awareness training
- User access management

Physical controls
- Access control vestibule
- bioetric locks
- guards/security personal - visible deterrent
- security fences
- cctv
- mantraps - two door security system
- vehicle barriers
- tamper evident seals
- panic buttons/alarms

Control types:
- preventive controls
  - prevent befor they occur
  - firewall to prevent unauth access
  - training to educate staff about safety proesudres, prevent workplace accidents
  - quality contro,s checks in manufactoring to prevent defects
- deterrent controls (discourage mechanism)
  - security cameras
  - warning signs of of secu system
  - MFA, strong pwd policy
- Detective controls
  - financial audits
  - siem
- corrective controls - controls to address problems after they have been identified
  - backup / reco sys
  - impletmenig fixes
  - patches to address software vulnerability
- compensating controls - alternative meauses when pri controls are inssufient or not feasible
  - help offset the limitations or deficients of other controls
  - req additional layers of approvals for finanicla trans whn theire is no automated control sys
  - using seconda authen method when primary fails/not abvilable
  - incresing physical secu when technical controls are failing
- directive controls - involve providng specifi instructions or guidelines to ensure complaince with policies
  - clear framework for employees to follow
  - code of conduct
  - ethical gudielines
  - SOPs - std operating rpocedures - stepo by step proces to complete spcific tasks
 
### Summarize fundamental security concepts

CIA triad
1. confidentiality
2. integrity
3. availability

Non repudiation
- ensuring accountability of actions
- prevents denial of actions


key aspects of non-repudiation:
- digital signatures
- audit trials
- access controls
  - identification (SID - security identifier), name user id
  - authentication - pin,biometric
  - authorization - principle of lease privilege

Authentication, Authoirization and Accounting:
- aaa server

what do aaa server do and how they keep our digital transactions safe and reliable?
- Authenticating people
  - aaa server conatc domain controller when user intiates authentication request
  - domain controller - a specilized server responsible for managing user acocunts and authentication within a windows domain env
- Authetincating systems
  - aaa framework with 802.1x authenticates devices in a network
  - each dev must have a valid certificate on its end point
- Authorization models
  - define the scope of permissbile activites
  - creates controlled env
  - mitigates risk associated with unauthorized access
- Accounting
  - capture essential details such as username, timestamps, ip addres, accessed resosuces, actions perfoemd
  - used for real-time monioring, histoical analysi, gerate reports for compliance/trobleshttoing
- AAA protocols - RADIUS, Diameter and TACACS
  - access control and accountability
  - login in uswr/devices are stored in a database
  - RADIUS - Remote authentication dial-in service
    - network security -
    - clients : wireless access points, routers, switches
    - cleints fwd authentication req to RADIUS server
    - this secret ebtwween radious clien and server safegards exchange of data
    - integri of authenication proces
  - Diameter
    - succesof or radius
    - modenr netw tech 4g, 5g infra
  - Terminal access controller Access control system - tacacs+
    - cisco
    - routers, switches, firewalls

Gap Analysis:
a stratic process to avaluates current secu proactices against established sec standards, regulations and insudtry standards
identify gaps between current sec posture and desired state of security
- assessment - current sec measures, policies, procedures and technologies
- benchmarking - comparing and marking
- identification - areas where sec measures fall of the desigred or req-level
- prioritization - rank the gaps based on potential impact and likelihood of exploitation
- remidation strategy - enhance org sec posture by creating actionalby remdiation strategy to close the identifiyed gaps
gap analysis is an iterative process
changing threat landscape

**Zero Trust**
- imp of data and control planes in networking
- ZT challges the asusmption of inhert trust within a netw
- seperation of data and control planes chaglles tradiional assumption of data dn control planes shud be tightly coupled
- data planes - effient mvement of info
- control panes - manages the inteligce behind data rotuing, netw health , device configura
- enhances cyberse by verify access at every step
- regardless of their location
  - secure netw demands distinct roles

- policy admin, implicit trust zone - data flows
  - control plane - uses subject.identity with company policies to decide which user/dev can access the new - this cntralization is needed regulate access, moniotr activ, swiftly repsond to emerging threats
  - adaptive identity
    - no static roles/permissions
    - dynamically adjust access based on various signals such as user behavi,location, dev charactists,
    - minimize the risk of unauth activ, and seamless user exp
  - threat scope reduction
    - minimize exposed attack surface
    - redicng the attackable code base
    - emporiwng rigorus patch mgmt
  - policy driven access control
    - automate the enforment of these diretcives
    - sytematic approach of access rights
    - elemniates the risk of human errro
  - policy admin
    - execue decison by policy engine to control access
  - policy engine
    - determins who gains access using policy set by org sec team
    - evalauets all paraments, data collected by siem and then communicates its deciso topolicy administrator
  - policy enformenet point
    - sec checkpint follow the tules set by poli admin
    - ensure only authorized user gets access
    - prevents protenal breaches
    - ultimate deci maker

The Data Plane:
- the data plane in cyber security is the operational core responsible for actual movement and forwaridg of data ackets within a netw
- focuses on executing tasks such as - routing, switching, pkt fwding based on predefined rules/policies
- ensures secure transmi between devi in netw
- subjects - entities who initiate data comunica
- systems - collective infra, devices, resource respon for processing, forwarding data packets
  - implicit trust zones
  - internal network zone
  - demilitarized zone DMZ - neither trused nor fully trusted
  - external netw zone - internet and otehrs .. WAN

policy engine looks at company polies and threat intelligence data to control access to the newt per user basis


Physical security:
- bollards - formiddable barrier for vehicular threats
- access control vetibule
- fencing
- video surveillance
- security guard
- access badhges
- lighting
- visitor logs
- sensor technologies - real time threat detection with minimal human intervention
  - infrared - heat - identif hman/animal for ditance meausrement and obkct/animal/human detection
  - pressure - touch - movement - pressure changes, reliable indicator of movement
  - microwave - moving objects - detect changes i frequency to detect motion 
  - ultrasonic - sound waves - see aorund all around corners - challenging envs

policy enforcement point sits in the data plance controlling access to resources

_Deception and disruption technology_
to understand adversaries' evolving tactics - decieve and disrupt
- honeypot
  - sec teams trying to find attack methods, set up web with lower sec similar to legitimate web
  - sec team monitors the attack methods and can prevent future attacks
  - another reason to set up honeypoyt as decoy so that real web server is not attacked
  - **attracts attackers and analyze   their attack methods**
- honeynet
  - study and analyze malicious activities
  - a grp of honeypots like a network
- honeyfile
  - lure an attackers curiosity - sensitive file name
  - **bait used to identify when attacker opens the file**
- honeytoken
  - decoy data hold no value
  - **detec and track unautorized access**
- fake information
  - dns sinkhole - deliberately send to differnt address instead of desired destination
  - fake telemtery where we identify and attack, but return fake data

Notes:
 non repudiation - aymmetic key
 audit trails - compreenisve record of user ctivities and system actions

 ### Explain the importance of change management process and the impact to security
 <u>hello</u>




  
