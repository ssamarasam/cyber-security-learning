# SC-900 Microsoft Certified: Security, Compliance and Identity fundamentals

## Resource: Micorsoft learn documentation

### Describe Security and Compliance concepts


**Shared responsibility model:**
IaaS
PaaS
SaaS

customer:
information and data
mobiles and pcs
accounts and identities

**Defense in depth:**
1. physical layer
2. idneity and access layer
3. perimeter
4. network
5. compute
6. application
7. data

**CIA triad:** Confidentiality, Integrity and Availability

**Zero trust model**
identity
devices
network
infra
apps
data

1. verify explicitly
2. least priviledged access
3. assume breach


**Encryption and hashing**
- symmetric
- asymmetric
- encr at rest, transit and in use(enclave for cpu, ram)
- hashing + salting

**GRC concepts**
- governance
- risk
- compliance
  - data residency
  - data sovereignty
  - data privacy
 

  ### Describe identity concepts
  - authentication AuthN
  - authorization AuthZ
 
  **Identity as the primary security perimeter**
  - 4 pillars:
    1. administration - creating, management/goveneance of identities - users, devices, services or anything
    2. authentication
    3. authorization
    4. auditing - tracking, govenrance of identities


**role of an identity provider**
- identity provider - creates,   maintains, manages, identity info while offering authentication, authorization and auditing services
- info thats used to authenticate a user is stored and managed centrally by identity privider
- idneity sus[picous activities,   reduce malicious attacks, establish authorization policies, monotir user behaviour
- client - idnetity provider - srver
- sso
- federation

**Directory services and Active Directory**
- dir serice stores directory data and makes it available for netw users, administrators and apps
- AD DS - activie directory DOmain Services:
  - stores infor about members of the domain, inclduing domains and users, verifies their credentials, define theoir acecss rights
  - a server running the AD-DS is called Domain Controller
 
  - microsoft entra id - IDaas - identity as a service - active directory based identity solutions - on prem, cloud
 

**Federation**
- access across org or domain boundaries by establishing trusted relationships between respective domains identity provider


### Capabilities of Microsoft Entra

**Function and identity types of Microsoft Entra**
- cloud based identity and access management system
- can be sync with  on-prem active dir, other dir services, ur used a sstand alone service
- securely enable personal devices, mobiles, tablets and enable collaboration wiht business partners/ customers

identity secure score:
- how aligned you are with MS best practice recommendations for security
- tailored to specific config
- measure your identity sec-posture
- plan identity sec improvements
- review the sucess of improvements

terms:
- teneant:
  - instance of ms entra
  - single orgnincluding prg objects - users, grousp, devices, apps registrations
  - security and administrative boundary to manage and control access to resos, apps, devices and services
 
- directory:
  - microsoft entra directory or microsoft entra tenent
  - logical container within a ms-entra tenent - hols and organizes various resources and objects
  - directory - a database or catalog  of identities and resosuces associated with an org;s tenent
  - a ms-entra tenant consist of only one directory

- multi-tenant:
  - org with multi tenant
  - org with multiple subsidaries which operate independantly
  - org's that merge or acquire companies
  - multiple geo-boundaries with various residency regulations and more

- can setup mfa to access resos
- add sso
- provide APIs - allow personalized app experiences using exising org data
- subs to azure serices, ms-365, dynamics 365 automatically have ms-entra-id

**Types of identities**
categoroes:
1. people
2. physical devices
3. software based objs - workload identities

**user**:
how they authenticate?
- internal authentication
- external
**user-type**
- guest
- member

User:
1. internal member -
2. external guest - consulatants, vendors, partners - autnehticates using extrenal ms-entra acct or social media acct
3. external memeber - orgs consists of multi tenants - member level access
4. internal guest - orgs who collobaorate with distributors , vendors, - set uo internal guest - b2b collaboration - use their own credentials- alowing extrenal identity provider to manage authentication and account life cycle

Workload identities: - software workload
- applications and service principals
- service principal - an identity for an application
- app must be registered with ms-entra to delegate its identity and access functions
- after registration a service principal is created in each ms-enyra tenant where the app is used

managed identities:
- type of service principal -automatically managed in ms-entra-id eliminate the need for developers to manage credentials
- provide idnetities for use to connect to azure resources that support ms-entra without any cost

1. system assigned:
   - tied to one resources - live in resources life cycle, gets deleted when resources gets deleted
2. user-assigned:
   - standalone azure resos
   - assign it to one or more instances of azure resources - multiple VMs
   - scenario - when multiple VMs need same set of permissions
   - deleting resources doesnt impact user-assigned identity


Device:
- device identity gives admin they can use when making access or config decisions
1. MS entra registered devices - for byod - registered device can access org resources without requiring an org acocunt to sign in
2. ms entra joined - device joined to ms-entra-id thru an org account, which si then used to sign into the device - generally owned by org
3. ms-entra-hybrid-devices - devices from on prem act dir acn be joined to ms-entra - requiring org acct to signin

regsitiering and joining dveices allows to use SSO to access cloud resos
devces that are  ms-entra joined beniefit from sso to resources /apps that rely on on-prem active dir

Microsoft intue - MDM and MAM - mobile application management

Groups:
- if several identieis need same level of acces - then can create a group
- group to asisgn permissions and access to resources for zero trust
1. security - manage user and  device access to shared resos
   - requires MS_entra admin role to create security groups
2. Micorsoft 365:
   - distribution groups - used for grouping users accoridng to colloboration needs
   - access to shared mailbox, file sharepoint sites,
   - memebrs can be users and , users outside of org also, no need of admin role

can be configured manual or dynamic 
dynamic membership rules to automatically assign or remove identities

**Hybrid identity**
- on-prem and cloud

accomplished by inter directory provisioning and synchronization
- when a user is already in Active directory is provisioned into Microsoft entra id
- making sure identity infor is matching between active directory and cloud

method:
- ms-entra cloud sync using ms-entra cloud provisiong agent
- provides a light weight inter directory  rpovisning experience that acts as a bridge between ms-entra-id and active directory
- org needs to deploy the agent in their on-prem or IaaS environment
- provisong config is stored in ms-entra and managed as part of service

SCIM - System for cross domain identity management
- a std used to automate the exchange of user or grp identity information between identiy domains such as entra

ms-entra cloud sync agent uses SCIM to provion and deprovison users/grps

**External identities**
- providng acces to org resources to extrenal users
- Micrsoft entra external ID
  - b2b collaboration
  - b2b direct connect
  - ms-entra external id for customers - preview
  - ms-entra multi tenant organization
 
  B2B collaboration:
  - enables emp of an org to collabotae with ext users - letting them use prefered identity to sign into ms-apps or org;s enterprise apps
  - guest users
  - they use their home org's or identity provider
  - we check guest user's eligibility for b2b collaboration
    1. invite users to b2b using the entra acocunts, social ids
    2. use self service signup usef flow to let ext users to signup
    3. use ms-entra entitle amangement - identity governance feature  -lets you manage identity and access for ext users at scal by automating access request workflows , access assignments, reviews and expiration
   
  user obj is created in the same directory- allows to assign permisisons


B2B direct connect:
- allows to conenct with extrenal ms-entra orgs using teams shared channel
- not represented in ms-entra directory
- can be viewd in Teams shared channle or monitored in Teams admin center
- two was trusted relationship
- when 2 orgs enable b2b direct connect, they authneticate from their home org and recive token from resource org

- enable teams connect shared channel - lets you colloborate with extrenal users ffrom multiple orgs for chat, calls file sharing, app-sharing
- 1. within teams, a shared channel owner can searchf ro allowed users from ext org, add them to shared channel
  2. ext users ca access resources without having to swicth org to sign in with diff account. can access file thru teams. cross tennt access settings wil bemange truted relation with extrnal users inblund as well as outbound
 
Micorosft entra external id for customers - preview:
- new MS's Cusomter identify and access management solution - CIAM
- with ms-entra ext id, create a distint tenant follows the std MS-entra tenant module , but configured for customers
- 1. SSO with social and extrenal identities - usernam/pwd, otp, email
  2. signup and signin pages to your apps
  3. add company brnading to signup page - customer can securely access all the apps using single identity
  4. provide slef service account management


Multi-tenant organization:
- more isntance of ms-entra id
- multiple clouds or multiple geo boundaries
- one way synchronization called cross tenant synchronization



### Authentication capabilities of MS-entra id

Authentication methods:
- password
- phone - sms - primary, voice call veririfcation - secondary
- OATH - open authentication - seocndary - for sspr or ms-entra mfa
  1. software oath token
  2. hardware oath tokens
- passwordless
  - biometrics with windows hello for business
  - fido2 security key
 
windows hello for business; - pri + seocndary
- replaces pwd with string two-factor authentication on devices
- combination of key or certificate tied to device and something that person knows-pin or biometic, to cryptographyically sign data to send to identity provider - the IDP verifies and authenticates the user - can be used as secondary form of authentication when verutying during mfa

fido2 - fast identity online
- open std for passwordless authn
- incorporates web authentication standard webAuthN - supported by ms-entra
- usb devices, blutooth or nfc also
- primary + seocndary

MS-authenticator-app - pri
- can be used as a software token to geneate oath verification code

Certificate based authentication:
MS entra CBA - certitifcate based authN - allow to authnticate directly with x.509 certificates against their ms-entra identity
- for apps and browswer signins
- cba is only as a pri form of pwdless authN
- x.509 certificates are part of PKi, digitally signed documents - bind an identity - user, org, website



**MFA**
- know
- have
- you are

Security defaults and MFA:
- basic identity sec mechanisms recommneded by MS
- 1. enforcing mfa for users
  2. forcing admins to use mfa
  3. requring all users to complete mfa when needed
 
SSPR:
- reduce it support
- more productive
- admin can roll our changes
- includes robust sec-logs available from api, enabing data t be imported to a SIEM
- enabled for SSPR by admin
- sec questions for secdnary
- admins cant sue sec questions, they have otehr mfa options
- password write back to on-prem active directory without a delay
- email notificatiosn after sspr
- all global admisn will be notified when SSPR is used on a admin account

**Password protection and management capabilities:**
- reduces the risk of using weak pwds
- detects and blocks weak pwds and weak terms
- default banned pwd lists are applied t all users in a tenant
- custom abnned also can be defined
- when user restes, these listss will be checked
- mfa for pwd protecion

global banned pwd list:
- mainted by ms-entra id protection team
- with all varients created using algo - s to $

custom banned pwds list:
- org name, location as pwds
- focused on specif terms like
  - brand names
  - product names
  - locations
  - comapny ehadqrters
  - comapsny speci terms
  - abbreviations used in comapny
 
custom abnned willbe compbined with global banned list

banned pwd list are feature of ms-entra p1 and p2 licensing

Proetcion against password spray:
- real wrld teleterty daa
- weak pwd banning

Hybrid security:
- admisn can integ ms-entra pwd protection within an on-prem act-dir env
- component installed on act-dir willrecive banned lists from ms-entra and perfocm checks 

### Access management capabilities of MS-entra

**Conditional access**
- implemented thru policies - craeted/managed in ms-netra-id
- conditonal policys analyses signals from user, location, device, apps and risk to automate decisions for authorizng access to resos
- if-then statements
- if user belong to a  certain gro, then mfa needed
- conditional access policies are applied after first factor authentication is completed

conditional access policy components:
1. assignments:
- which signals to use
- who, what, where, when
- logically ANDed
- 1. users and groups
  2. cloud apps or actions - netgartin of defencder for cloud - control over access and activities
  3. condtions: where and when -
     1. sign-in risk
     2. user risk
     3. devices platform
     4. ip location info
     5. client apps
     6. filters for devices


2. Access controls
   - block access
   - grant access
     - with no extra controls
     - with mfa
     - with a pwd change
     - with a specif complaince policy requirements
       
   - session - using session control, enable limited exp within specific cloud apps
     - use signals from ms-defender for cloud apps to block download, cut, copy, print for sensitiev docs
     - signin freq
     - application enforced restrictions
     - limited or full exp based on device state

**MS entra roles and RBAC**

built in roles;
1. global admin
2. user admin
3. billing admin

custom roles:
- define the role defining with permisnions
- assign the defention to user or group

Categories of MS entra roles:
1. ms entra specific roles - user admin, app admin, groups admin,
2. service specif roles - grant permissions to amaneg features within the specif servuce- echange admin,ntune admin, sharepoint admin, teams admin
3. cross service roles -
   - sec admin grant access to ms365
   - complaince admin grant access to ms365 compliance center, exchange
  

MS entra RBAC - ms entra resosurces susch as users, grps, apps
Azure RBAC - vms, storage using ARM

### Identity protection and governance capabilities of Microsoft entra
identity protection - protecting org's identities agaist risk and potential vuls
identity governance - balacing identity security with user productivity that can be justified and audited
- protecting, monitoring and auditing access to critical assets
- ms-entra id governance
- PIM
- capabilties of ms0entra protection
- permissions mgmt

**MS Entra id governance**
- govern the identity lifecycle
- govern access lifecycle
- secure priviledged access for administration

identity lifecycle:
- no-access, join, move, leave
- hr system - workday or SuccessFactors
- p1, p2 offers cloud based hr system
- ms-identity manager imports records from on-prem hr systems such as SAP-HCM, Oracle Ebusiness , Oracle Peoplesoft


Access Lifecycle:
- users need diff access during their org's life
- automate thru technologies such as Dynamic-Groups - enable attributed based rules to determine access
- they will be added to grp or removed babsed on the rules they satisfy at that time


Priviledged access lifecycle:
- admin rights - protential misuse - governance is required for that
- MS entra PIm


**Access reviews**
- ms entar access reviews manage - grp memberships, access to enterprise apps, role assignment
when access review?
1. too many users with priviledge roles
2. business critical data access - compalince to regularly confirm and ask why they need this access
3. to maintain policy exception list - excpetions are reviewed regularly
4. ask grp owners to confirm thye still need guest users in their grps
5. have reviews occur periodically

Manage user and guest user access with access reviews:
- make changes or rmeove access after access review completion and based on the results

Multi stage access reviews:
- three review stages
- at the end , access is revoked for denied users
- enable complex workflows to recertification and audit requirements calling for multiple reviewers to attest access for users in a paricular sequence
- design more efficient reviews for yout resources owners by reducing the number of decicions each reviewer is acocuntable for

- admins can track progerss as the reviewers complete their process
- can stop a review before completion
- but access changes hdul happen after access review completion only

- manual or autpo apply changes to remove access from a grp membership or aapplication assignement exceptt for a dynamic grp that originates on on-prem - in those cases, hanges must be directly applied to grp


Entitle management:
- who can request access
- who must approev the access
- when does access expires
- managing access for extrenal users

access packages: who can request, who must approve, expiration

1. delegate the creation of access packages to non-admins
2. managing extrenal users - b2b ccount in your dir will be automatically removed when their access expires


MS entra terms of use:
- rpesented to all suers
- before they access data or app
- sensite data
- recuuring schedule
- user attrbutes changes
- presenting terms to all users

- pdf format
- conditional access policies are used to require terms of use statement being displayed
- admins can view who accepted or denied the terms

**Capabilities of PIM**
- manage , control, monitor access on ms-entra resources - ms-entra, azure, ms online services such as ms-365, intune
- mitigates the risk of excessive, unnecessary, misused access permission
- requires jsutification why want access and requires mfa to activate

1. just-in-time
2. time-bound
3. approval
4. visible
5. auditable

use PIm with
1. ms-entra roles
2. azure roles
3. pim for grps - justintime membership and just-in-time owenership . pim for groups goven access to  ms-entra roles, azure roles, azure sql, key vault, intune, application roles and third party roles

workflow:
1. assign: members or ownser, scope to resos, assignment tyep - eligible or active duration
2. activate - eligible roles must activate with a reason why they need access
3. approve or deny - delegated approvers recieve this request
4. extend or renw - users have to eten if needed or renew if its already exired but needed

Audit:
pim audit history to see role asisgments,activations for upto 30 days for lal priviledged roles


**MS-entra ID protection**
- id protection tool
  1. automate detection and remediate identity based risks
  2. insvestigate risks using data from portal
  3. export risk data for further analysis
 
Detect risks:
1. sign-in risks
   - ananymous ip
   - atypical travel
   - unfamiliar signin properties
   - ms-entra threat inteligence for unusual signin or known attack patterns
  
2. user risk
   - anomalous user activity - suspicious
   - user reported  suspicios activity
   - leaked credentials
   - ms-entra threat intelligence
  
Investigate risks:
three reports;
1. risk detections
2. risky users
3. risky sign-ins

remidiate:
1. automated remdiiation using policies
2. unblock users
3. risk based conditional access policies willbe anbled to to require mfa, string pwd, pwd reset
4. manual - thru portal, api, ms-defender

Export:
- ms graph based api to siem
- log analytics workforce, archived data to storage acct streamed to event hubs, solutions

Workload identity;
- app/serice principal
- cant perform mfa
- no formal life cycle process
- no to store credentials somewhere

- mage these risks by prviding workload identity risk detections acrsoss signin behaviour and other IOCs

**MS entra permissions amangement**
- cloud infra entitlement mgmt - CIEM
- provides comprehensive visibility and control over permissions for any identity and any resource in ms-azure, aws, gcp
- discover - remiediates - monitor
- zeror trust
- multi cloud access visibility
- monitors unused or excessive access permissions

discover - ustomer assess risks by evalauting gap between permissons granted and permisisons used
  - cross cloud permissions discovery - granular and normalized metircs for aws, gcp, azure
  - Permissions creep index - pci - evalautes the level of risk associated with the unused or excessive perms acrross your identities and resos. how much damange identities can cause based on the permissions they have
  - permission usauage analytics -
 

remidiate: 
- right size perms based on usuage, grat new perms on demand, automate just-intime access for cloud resos
- automated deletion if unsed for 90 days
- perms on demand - on needed babssi - time bound


monitor:
- detect anomalous activities with ML powered alerts and generate detailed foresiic reports
- get compreghesicve visibility
- automate lease pri access - usalaytics to ensire identities have right perms at right time
- unifiy access policies across IAAS platforms - consistent sec-policies


**MS entra verified ID**
- managed verifiable credentials service based on open stds
- automates the verification of identity credentials and enables privacy protected interactions betw orgs and users
- issuer
- user
- verifier
- data registry


## Capabilities of Microsoft's security solutions

### Core Infrastructure security services in Azure

**Azure DDOS protection:**

DDOS attacks:
1. vomumetic attacks
2. protocol attakcs
3. resouce/application layer attacks

Azure ddos protection: protects ate layer-3 network layer and layer-4 transport layer
- alwyas-on traffic monitoring
- adapting real time tuning
- ddos protecion telemtry, monitoring and alerting - integrate logging with azure event hubs, azure monitor logs, azure storage for advanced analaysis via azure monitor diagnositics interface

supports 2 tier:
1. ddos network protection - proetcts resosuces in virtual network, plus advanced capabilities including logging, alerting and telemetry
2. ddos ip protection - pay-per protected ip model
   - doenst include valuse added services such as ddos rapid response support, cost protection, discounts in WAF
  

**Azure Firewall**
- managed, cloud based network security serice
- threat protectio for resosusrs, workloads running in azure
- deploy in   any virtual netw
- bets approach is centralized so that all traffic to cloud or on prem passes thru Azure firewall - to centrally control traffic - across all subscriptions
- scale up to the usage
- netw traffic is subjected to the configured firewall rules when you route it to the firewall  as the subnet default gateway

Key features:
- 3 sku - standard, premium, basic
- built in high availability and availability zones
- network and application level filtering - ip, port, rpotocol - fully qualified domain name filetering for outboundhttp/s traffic and network filtering controls
- outbound SNAT and inbound DNAT to communicate with interenet resos
- multiple public ip address
- threat intelligence
- integartion with azure monitor

**Web application firewall**
- makes sec mgmt simpler
- improeves response time to secu threat
- pacting a known vul at one place instaed of at each application
- gives app admins a better assurance of protection
- protects web apps from ddos attacks occur at application layer - http floods


**Network segmentation in Azure**
- reasons for segmentation
  - grp related items/resources - fpor maint workloads
  - isolation of resos
  - governance policies
 
  - zero trust/layer approach
  - defense in depth
 
  Azure Virtual Network - Vnet
  - enables orgs to segment their netw
  - can multiple VNs per region, subs, multiple smaller network(subnets) within each VN
  - no traffic allowd across VNETs  inbound to the VN
  - communications needs to be explicitly provisioned
 

**Azure Network Security Groups - NSG**
- filter netw traffic to/from from Azure resources in an azure virtual network
- only one NSG to each virtual network subnet/network interface in a virtual machine
- same nsg can be associatd to many diff subnets/network interfaces

Inbound/outbound sec rules
- evaluated by poriotiry using five info points
- source
- source port
- dest
- dest port
- protocol
- azure create a set of 3 inound, 3 outbound baseline rules which cannot be removed - but can be overriden with new rules with higher priorities

properties in each rule - one or more of these below:
1. Name - adminAccessOnlyFiler
2. priorority - lower numbers processed before higher numbers - when traffic matches a rule, processing stops. any other rules with lower priority (higher numbers) will NOT be processed
3. source or dest - ip address, ip addr range, app-sec-grp, service tag, 
4. protocol
5. direction
6. port range - individual or range of ports
7. action - allow/deny

e.g inbound:
1. port 400 can be allowed
2. allow servicetag-VN to any
3. denyAll

**Azure Bastion**
- if deve;loper or admins want to connect VM remotely - then azure bastion without using ip, or open rdp, ssh 
- no need to expose open ssh or rdp ports outside
- enables to connect to  all VMs in the VN using secure ssh/rdp
- dont need apub ip, agent or special software
- per Virtual Network basis, not per acocunt/subs or Virtual machine - with suppoirt for virtual network peering
- from browser/portal
- PAAS
- platform managed PAAS

Benefits:
- rdp/ssh directly from azure portal
- remote session using TLS and firewall tarversal for rdp/ssh - html5 based
- no pub required on azure VM - connects using rpivate IP
- no hasstle managing NSGs
- protection against port scanning
- hardening in one place to protect againts zero day exploits

- two avaialable SKUs - Basic and Standard


**Azure Key vault:**
- cloud service for securely storing and acecssing secrets
- 1. secrets management - tokens, pwds, API keys, other secrets
  2. key management solution - create and control the encrption keys used to encrypt your data
  3. certificate management - tls, ssl certificates

  tier:
  1. standard - encryo with software key
  2. premium - inclusded HSM - hardware security module protected keys

  why key vault?
  1. centralize application secrets - uses key vault object idneitier for applicatios to get the keys from vault -0 url format
     -   standard - https://{vault-name}. vault.object typoel object-name, object-version
     -   premium - https://{hsm-name}. vault.object typoel object-name, object-version
  2. securely stores secrets and keys - authorization is needed
     - provided by Microsoft Entra / Azure RBAC or key vault access policy
  3. monitor access and use - enable logging for ytour vaults
  4. simplified administration of application secrets
     - replicate content of key vbault in secondary region easily
     - provide azure std administration options via portal, azure cli or powershel
     - automate certain tasks on certificates such as enrollment or renewal from Public certificate Authorities - CAs

### Security management Capabilities in Azure


**Microsoft Defender for Cloud**
- a cloud native application protection platform - CNAPP
- policies and security initiatives
- CAPABILITIES:
- - devsecops
  - cloud secutiry posture management - cspm
  - cloud worklods protection platform - cmpp
 
1. devsecops:
   - protects code management platform
   - code pipelines
   - get insights into developement environments security posture form a single location
   - multi cloud and muliple pipeline envs
   - security practices
  
2. CSPM:
   - monitors/assess ytour cloud and on-prem envs and alerts sec team for configuration changes or anything
   - proper config and deployment
   - tools and setrvices to monitor
  
3. CWPP:
   - security controls to protect the workload
   - indicates the nature and severity of threats so you can plan for response
   - implements ecureity practices
   - proactive secuity principles
  
  
**Security Policies and initiatives improve cloud security posture:**
- azure policy - rule about specific security condition
- security initiative - grp of azure policies fo r apsecific goal
  - assign them to a scope of resos
  - mgmt grps, subs, resosurce grps, resources

MS defender applies security initiaties to subscriptions - may contain or ore more security policies
- sec admins can build their own sec inititives
- default : Micorosft cloud secutiy benchmark - automatically assigned when you enable Microsoft defender foc cloud on your subscription

Micorosft cloud security benchmark: MCSB
- MS authored set of guidelines for security and complianace - best practices, recommendations
- bulit from CIS - center of Internet security  and NIST  with a focus on cloud security
- its a excel sheet with the below colums
  1. id -
  2. control domain - high level desc of feature or activity that needs to be addressed - e.g - idenity management, priviledged acces, inci resp, endpoint security, network security, data protecion
  3. Mapping to industry frameworks - CIS< NISt, PCI DSS<
  4. recommendation - for each control domain, many distictnt recommendations - NS1, NS10
  5. Azure guidance - how -> technical fatures or ways to implement the controls in azurelike using NSG or ASG
  6. AWS guidance -
  7. links - info ron implemenattion relate to azure or aws


  MSCB in Defender for cloud:
   - ms defender continuos asses the hybrid cloud envs and analsye the risk factors accoridng to MSCB
   - regulatory compliance dashboard in MS defender - reflects the status of compliance with the mscb and any other stads you applied to your subs

Security recommendation:
- recommendations on how to mitigate issues or congif issue sfound form the assesing oif our clodu
- recommendations based on the chosen intiatives and the mscb intiiative
- when something is not compliant, then the rcomendations will be presnted  - to secure or harden your resos
- e.g -
  - a short desc of the issue
  - remediation steps
  - the affected resources
 

**Cloud Security Posture Management - CSPM**
- provides hardening guidance - efeicintly and effectivly improve your security
- visibility of your current security situation

1. Secure Score
   - asses all cross cloud resouscres for security issues - azure , aws and gcp
2. Hardening recommendations
   - based on identified secuiry misconfigurations
   - grouped into logical security controls - reflects your vulnerable attack surfaces
3. Defender CSPM plan options
   - foundational multi cloud CSPM is free with asset discovery, continuos assessment and secu-recommendations for posture hardening, cpomplaince with MSCB and secure score
   - optional defender CSPM plan - offers advanced posture managment capabilities and tools to asses ytour secu cpmlaince with a wide range o benchmarks, stds and any custom sec policies


**Enhanced Security of Microsoft defender for cloud**
- a pillar cloud security is cloud workload protection

defender plans:
- MS Defender for servers
- app service
- storage
- SQL
- kubernetes
- container registries - azure resource manager based registries
- key vault
- Resource manager
- DNS
- open source relational protections

features:
- comprehensive EDR
- vul scanning
- multicloud security
- hybrid security
- threat protection alerts
- track compliance with a range of records
- assess and application controls - allow/deny lists, ml powered recommendations, just-in-time conntrolled acecss amanagment ports on azure VMS
  - blobk malware and other unwanted applications using ml - wllowlist, deny lists
  - reduce netw surfce - JIT, controlled access managmt ports, protocols
  - reduce brute force and other attacks


**DevOps Security Management**
- development and operations
- unite people, process, tech in application planning, development, delivery,  and operations
- defender for devOps console - allows you to manage your connected DevOps Environements amd provides ytoutr secteams with a high level overiview of duscovred issues that may exist within them

Defender for DevOps:
- across multi pipeline envs
- protect apps and resources from code to cloud across multi-pipeline envs siuch as github and azure DevOps
- findings help remediate code

Key capabilities:
- unified visibility into DevOps security posture -
- strengthen clodu resosurce cponfigurations throiught the development lifecyel - enable security of IaC templates
- prioritize remediation of critical issues in code


### Security capabilities of Microsoft Sentinel

SIEM - collect data, trigger alerts
SOAR - Security Orchestration, Automation and response - initiates resposnse workflows for automated response for incidents

MS-Sentinel:
- collect
- detect
- investigate
- respond

connect sentinel to your data sources:
- DEFENDER XDR SOLUTIONS, ms-365

workbooks
- monitor data using ms sentinel integration with azure monitor workbooks
- visualize data

analytics
- built in correlation rules
- build your own
- ml rules

Manage incidents in ms-sentinel
- standard incident response
- playbooks

SOAR using playbooks
investigation

Hunting - MITRE framwwork
- custom detection rules
- bookmarking

Notebooks:
- jupier notebook for analytics
- custom python query for analyis
- visualization

Content hub:
- centralized location to discover and manage out-of the box packaged solutions
- ms-sentienal content or ms-sentinel api
- out of the box content

Microsoft Security Copilot:
- response at machine speed
- generative AI security product
- prompt bar allows sec-analysts to ask questions in natual lang
  1. security posture management - infor on anything that exposes org' data dn provides mitigation techniques to protetc against those vuls detected
  2. incident reponse - provide infor on source of incident, response and remediation steps, single plane of glass - pulls data form defender, sentinel
  3. security reporting
 
- data is protected by comprehensive enterprise compliance and security controls
- your data is not used to train the foundational AI


## Threat Protection with Microsoft Defender XDR

### MS Defender XDR services
- detection, prevention, investigation and response
- networks, apps, endpoints, emails
- detects lateral movement
 XDR suits protect:
1. Endpoints with msdef for endpont
2. assets with defender vul management
3. email and collaboration with msdef for office 365
4. identities with msdef for identities
5. applications with msdef for Cloud Apps

MS defender threat intelligence:
- inside ms defender portal
- helpos streamline sec-analyits triage, inci response, threat hunting, vul mgmt workflows,
- aggregates and enriches critical thret infor in an easy to use interface


### MS defender for office 365
- preset sec-policies
- threat protection policies
- reports
- threat investigation and response capabilities
- automated investigation and response capabilities

- plan1 - exchange online protection eop , known attacks, volume based - email and collaboratoion tools such as sharepoint - malware, phishing, BEC
- plan2 - post breach ivestigation, hunting, response, automation, training simulation




### MS defender for endpoints
- network resos, laptops, phones, PCs, accesspoints, routers and firewalls
- 1. endpint behavioural sys - collection
  2. cloud sec analytics -translates signal into insights
  3. threat intelligence
 
features:
1. core defender for vul mgmt
2. attack surface reduction
3. next gen protection
4. endpoint detection and response
5. AIR automated investigation and remediation
6. MS secure score for devices
7. Micorsoft threat experts
8. management and APIs - expose entities and capabilities thru a std ms-entra id based authentication and authorization

- plan1 and plan2

### MS defender for cloud apps
- protection for SaaS apps
- tradiotnal cloud - CASB - cloud access security broker
- 1. Fundamental CASbs - cloud app usuage, shaodow IT, infor protection, copmpliance
  2. SSPM - SAAS Security posture mgmt
  3. advanced threat protection - enabled by ms defended extended detection and response
  4. app- to app protection - extending core threat scenarios to OATHu enabled apps thta have permissons to critical data and resos

**Discover SAAS apps:**
- identify -
- assess - more than 90 key risk indicators - asses your orgs apps security and compliance
- manage - set policies to monitor apps for aunusual activtiites, anamolus behaviour

**Information protection:  which data is stored and who is acecssing it**
- scan files containing sensitive data
- 1. apply sensitive level
  2. block downdloads to a unmanaged device
  3. remove external collaborators on confidential files
- can be integrated with Micorosoft purview which enables out of the box data classification types in their info protecion policy anc ontrol sensitve infor with DLP features

**SAAS Security Posture Management - SSPM:**
- defender for cloud apps helps by surfacing misconfigs and recommending specific actions tpo strengthen the sec posturefor ech connect app
- recommentsdations ar ebased on CIS - center for internet security
- automatically provides sspm data in ms secure score for any supported and connected app

**Advanced threat protection**
- offers bulit in AAC adaptive access control which provides UEBA user and entity behaviour analysis and help mitigate attacks going laterlly compromsing end points
- directyly integrated into ms defender XDR, correlating detection and response signals XDR form ms defender suite - proivdes inci-level detection, investigation and powerfiul resp capabilities
- gives SOC teams compolete kill chian visibility and improves overall efficiency and effectivity


**App to App protecion with app governance:**
- OAuth - open std for teoken based authentication and authorization - enables   user account info to be used by thrid party serices whitout exposing pwd
- often have excessive permissions
- defender for lcoud apps closes the gap on OATH security, ptotect inter app data exchange with application governance
- watch for unused apps and monitor current and expired credentials to goven the apps used in your og and maintain app hygiene


### MS defender for identity
- collect signals form active directory
- 1. monitor user, entity, behaviour, activities - learning based analytics
  2. protect user identities and credentials stored in AD - secu reports and user profile analytics - identity user / devices who uses clear text pwds - protects AD FS (federation sevrices) by detecting on-prem attacks and proivides visibility in authn events generated by ad-fs
  3. identify and investigate sus activities and adv attacks across the cyberattack kill chain
     - reconnaisance - idntity rogue users and atatckers attempts
     - compromised credentials - identity attempts to compormise creden, rute force attacks
     - lateral movements - gaining other user acocunts inside the netw
     - domain dominance - highlighting attacker behaviour if domain dominance is achieved, thru rmeote code execution on th edomain controller or other methods
  5. provide clear infor on  a simple timeline for fast triage
  6. investigate alerts and user activities
     - only importnat security alerts - reduce alert noise
     - real-time organizational attack timeline
     - defender for identity attack timeline view/intellience of smart analytics

### MS defender vul mgmt
- visibility, intelligent assessments , built in remidiation tools for windows, macos, linux, andorid, ios, network devices
- prioriizes vuls
- continus deliver and monitoring
- risk based inteleigent prioritization
- remediation and tracking


continious asset discovery and monitoring:
- cnsolidated inventories - soft apps, digital certificates, hardware, firmware, browser extensions
  1. visibility into software and vuls
  2. network share assessment - netw share config
  3. browser extension assessments - info on extension's permissions and associated risk levels
  4. digital certificates assessment - identity certs before they expire and detect potential vuls due to weak signature algorithms
 
risk based intelligent prioritization:
- ms threat intelligence, breach likelihood predictions, business contexts, device assessments - priotirizte biggest vuls
- single view of prioritized recommentdations with critical details, CVEs and exposed devices - help quickly remediate vuls on most assets


Remediation and tracking:
- remediation requets to it in MS-intune form a specific security recommendation
- block vul app - mitigate
- alternate mitigations - config changes to reduce risk on soft vuls
- real-time remediation status - real-time monitoring of the status and progress of remeidation actitivies across org


dashboard insights:
- view exposure score and ms-secure score for devices + top recommendations, soft vuls, remdiationactivites and exposed devices
- correlate endpoint detection and response with endpoint vuls and process them
- select remeiation action and track the remediation tasks
- select exception actipons and track them


### MS defender Threat Intelligence - TI
- keyword, artifact, CVE search
- intel explorer  -with articles
- Defender TI articles:
  - actionable content and key indicators of compromise to help users take action
  - insight into threat actors, tooling, attacks and vuls
  - descripotion - 
  - public indicato rs - poreviously published indicators related to this article
  - defender TI indicators - indicators that defenders Ti's reseacr team found
- vul articles:
  - cve search
  - descriton of cve, list oif affacted compoonnets, tailored mitigation procedures and startegies, related intelligcen articles, ref in deep/dark web and other observations
  - defender ti priority score, sevrity indicator based on cvss
 
- data sets:
  - tradtional - whois, ssl certs, subdomains, dns, reverse dns and services
  - advanced - trackers, componentshost pairs, cookies - collected from observing the DOM or web page crawled
 
- reputaion scoring and analyst isights:
  - repu scores of host, domain, ip address - to udnerstand they are tied to malicious or suspicous infra
 
### MS defender portal
- RBAC based - cards will appear based on that
- should be on oiff these - global admin, security admin, security operatoir, secutrity reader
- incidents and alerts
  - ms365 serviuces generat;es alerts - corelatted oincidents in xdr
    1. full stoiryof the attack, inslcuing all the laerts, assets, rediation tasks
    2. all the alerts related to that incident
    3. all the assets
    4. all the automated investigations triggered by the alerts in the incident
    5. all the support evidence and response
- hunting:
  - custom detection rules
  - query based threat hunting tool lets proactively isnpect events in your org to locate threat indiacors / entities
  - can be atomated to repond tpo sec breaches, misconfigured machines, and pother findings
 
- Threat intelligence:
  - threat analytics - in-product threat intelligcen solution from expert ms-security researchers  to assist sec teams track and respond emerging threats - hightlights the reports that relavant to your org
  - intel profiles - curated content organized by thret acors, their tools and nown vuls
  - intel explorer - access exising dendetedn TI contentdescribed inthe previous unit

- Secure score:
  - representaion of comanys sec posture
  - higher the score., better the protections

note:
secure score in ms-defender is measure of secuiry posture of your azure subscriuptions
secure score in ms-defender xdr  - sec post of org across apps, devices and identities

Learning Hub:
-   official documentation form miscorost securiy blogs, ytoutube, learn

Reports:
- genarl sec report
- can be bracnhed into specuifc endpoint, emails, collaboration
- dynamically genared based on workload config


Permissions and roles:
- access to XDr is configured  with ms-entra global roles, or by using cusotm roles


## Capabilities of Microsoft Compliance Solutions

### Service trust portal
1. certifications, regulations and stds
2. reports whitepapers, artifacts
3. industry and regional resos
4. resources for your org


### Microsoft privacy principles
1. customer control
2. transparency
3. security
4. strong legal protecions
5. no content based targetting
6. benefits to you

### Microsoft Priva
1. priva privacy risk management - snapshot view of personal data your porg stores in ms365
   - exchange online
   - sharepoint online
   - ondrive
   - ms-intune
  
2. priva subject rights request
   - data subject access request - dsr or dsar
   - provides workflow and automation , collaboration capabilities for helping you search data, renew findings, collect appropriate files and produce reports


## Compliance management capabilities in Microsoft Purview

### MS Purview Compliance portal
- provides tools and data to understand and manage an org's compliance needs
- should be ms365 customer with the below roles
  1. global admin
  2. complaince admin
  3. compliance data admin
- the portal contains several cards
1. complaince manager card
  - to manage compliance
  - provdes risk based compliance score - measures towad completing the recommendatiosn to reduce risks associated with data protection and regulatory stds
  - providews workflow capabilities and built-in-control mapping to help you efficiently carry out improvement actions

2. Solution catalog - collections of inetegarted solutions to manage ened to end complaince scenarios
   - information protection and governance - 
   - privacy
   - insider risk management
   - descovery and response

3. active alerts card
   - most active alerts with link to check the details
  
Navigation:
- left side
- with access to
- complaince manager
- data classification
- alerts
- reports
- policies
- data connectors - import non ms-data to ms365


### Compliance manager
- to manage compliance requirements of an org
- from taking imnventpory of data porotection risks
- to magaing the complexities of implemneting controls
- staying current with regulations and certifications
- reporting to auditors

provides:
1. prebuilt assesmnts based on regional/indus regus and stds - can do custom assessments spe if to org
2. workflow capabilities to complete risk assessments
3. step by step improvement actions to help meet regus and stds - some actions are managed by MS and admins get notifications on th0ose actions/audit results
4. complaince score for compliance posture

Key elements fo compliance manager activities - to assign test, monitor complaince activities
1. Controls
   - a req of a regu, std or policy to assess and manage system config, oirg policies and people to meet specift reqirement, regu or std, regulation
   - tracks the below
     1. ms managed controls
     2. customer controls
     3. shared controls
    
    - comiliance manager continuously aessess controls by scanning thru ms365 env and detecting your settings, continuously detecting and and automatically updating your technical action stat
  
2. Assessments
   - grouping of controls from a specif regu, std, por policyt
   - compelting actions within an ass helps meet req of sts, reg or law
   - e.g. bring org ms365 settings in line wiht iso 27001 reqs
   - contains sveral componnets that are in scope  ms-managed ocntorols, customer/your controls., shared controls, and assessment score - shows progress towards reaching the complinece req
  
3. Templates
   - templates for admins to quicly create assessments
   - customize as per need / org req
  
4. Improvement actions:
   - recommended guidance to align wiht data protection regus and stds
   - can be assigned to users to do implementation and testing work
   - admin scan store documentation updates, record status updates, notes wihtin the oimporevement actions
  
**Benefits of compliance manager:**
1. translating complivcated regus, std, company policies in simple lang
2. providng access to large variety of pout of box assesmnts an dcustom assemnt needed
3. mapping regu controls with impevembt actions
4. provindg step by spetp guidnace on how to implement soltiuons to meet regu req
5. helping admins/users to rpiotorixze complaince actiuons with a score

Overall compliance ,manager helps org iun completing actions to meet complaince req to  reduce risks around data porotection and regu stds

### Use and benefits of compliance score
- progres
- current posture
- prirotize

- calculated using scores assigned to actions
  1. your improved actions - actions that org is expected to manage
  2. ms actions - actiosn that ms manages for the org
 
**actions are categorized into:**
1. mandatory
2. discretionary

**Sub categories:**
4. preventative
5. detective
6. corrective


Orgs accumulate points when the actions are completed - complaince score is the percentage representing all the actions completed, compared with the ones  outstanding


## Information protecion, data life cycle management and data governance capabilities in Microsoft Purview

### Know your data, protect and govern ypour data

MS-purview information protection - discovers, classifies, protects senstive and busines critical data thorught its lifecycle across your org
- proivdes tools to know your data, protect and prevent data loss

MS-purview data life cycle management - manages content lifecyel using soltions to import, store and classify busines scritical data so you can keep what tou need and delet what you dont- capabalities to govern data for complinace and regu reqs

infor proetcion and data lfcye mgmt works together to classify, porotect, givern your data where it lives and wherever it goes

1. know your data - tools : trainable classfiers, activity explorer, content epxlorer
2. protect your data - excr, acess restrictions and visual marking
3. prevent data loss - detect risky behavious and prevent accidental overshairng of sensitive infor - data loss prevention ploicies, endpint data loss prevention enable orgs to rpevent data loss
4. govenr your dtaa: - retention policies, retention labels, records amanbgemt


### Data classification capabilities of the compliance portal
- manual
- automatd pattern recognition like senstive information types
- machine learning


SIT - sensitive information types
- pattern based classifiers
- ms purview has built in patterns
- custom sit
  - for employee ids and project numbers
 
- support fo EDM - exact Data Match

Trainable classfiers:
1. pre-trained classifiers - ready to use
   - resumes, source code, harrasment, profanity and threat (five pretrained classifiers to use)
  
2. custom trainable classfifiers
   - provide samples (seeding) and test the predictions of classification
   - org based classification like invoices, cusotomner records, contracts

at this time, classfiers will only work with items that are NOT encrypted

**understand and explore the data**
- overview secion of data classfication pane in complaince portal
  - number of items classified as sensitive infor and which classificatiosn they are
  - details on the locations of data based  on sensitivity
  - summary of actions that users are taking on senstive content across the org
 
admins can use content and activity exploreer to gain deeper understsnidng and can guide their actions

**Content explorer:**
- under data classification pane
- visibility into the content that ahs been summarixzed inthe overview pane
- highly restricted as it makes us posisble to read the scanned files
- roles: content explorere list viewer and content explorer content viewer
- can a get a currnet snapshot of conet that has bene classified across org - exchange, onedrive, sharepoint


**Activity explorer:**
- visibility into what contnet has been discovered and labeled and where the content is
- possible to monitor whats being done with label content across org
- visiblity into document level actvities like lable changes, label downgrades,
- fileters - label, users, file types, activities
- helps to evalate controls are placed and effective
- activities that can be analyzed:
  1. file copied to removable media
  2. copied to netw share
  3. labell e applied
  4. lable changed
 
- fileters :
  - locatiuon
  - user
  - sensitivity label
  - retention label
 
### Sensititvity labels and policies
lables:
- customizable - personal, public, confidential, highly confifdential
- clear text - APPS AND SERVICES CAN read it and apply their own protective actions
- persistent- lableis stored int he metedata of email or document. lable moves wiht the ocntent inclduing the proetcion settings and this data becomes the basis for applying and enforicng policies

only label can be applied at a time to a item

can be cofnifgured to:
- encrypt
- mark the content - watermarks, headers/footers
- apply the label automatically
- protect content in containers such as sites and groups - doenst apply automatic labelling - but protects content by controlling access to the container where documents are stored
- extend senstitve lables to theird party apps and services - the ms purview protecion SDK allows theird party apps/services to read sensitivity labels and apply protecion settings
- classficy content without using protecion settings -  - to generate reports and   view activity data  for sesitive content


**Lable policies**
- once sensitivity labels are created, it then needs to be published to specific users / grps sot hat it eill be nabled in their office apps and sensitivve lables avcn be applied to documents or emails
enables admisn to:
- chosse the users and grps that can see the labels
- apply a default label
- require justifications for label changes
- require users to aply the label - mandatory
- link users to custom help pages

once sensitive label is applied to docu or email , any configured protection settings for that label are enforced on that content


### Data loss prevention
- apply dlp policy to implement data loss prevention- identity , monitor and automatically protect
- deep content analysis - analyzed for primary data macthes to keywords, regular exps, internal function valdiuation, secondary data matches
- ml algos, other methods to detect conent thta matches your DLP policies

**Protective actions of DLP policies**
- dat at rest, transit or in use
1. show apop up  or warning aboyt sensitive data access
2. block the sharing with override option with customer justification
3. vblobk the sharing without overidng option 
4. data at rest, sensit items - locked and moved to secure quarentine locations
5. for teams chat, senstive data will not be displayed

**DLP policy infomration:** 
- predefined templates or custom policy
  1. chose the typoe of data to monitor
  2. choose adminitrative scoping - adminitrative units
  3. chosse the location where the policy can be applied
  4. choose the conditions that must be matched for a policy to be applied
  5. choose the practive actions to take when the policy conditions are met
 

**End point data loss prevention**
- audit and manage users take on senstive itmes stored in win10, 11, macOS devices
- - create, renaming, coping to externam media, printing, cassing via unauth apps/browsers
 
  - activity explorere help on users activity on sessitive documents
 
**Data loss prevention in Microsoft teams**
- in teams chat or channel messages
- block shairng of senstive data by blobking and displaying a warning or tip in the chat
- select "what i can dp" and take appropriate action -0 can oveedir with justitication as well


### Retention policies and retention labels
- retain only
- delete only
- retain adn then delete

retention policies
- site / mailbox level / container level
- retention settings dont travel when documents are moved out but a copy is kept stored in a secure location

retention label
- document/folder level
- settings travel
- can be automatically applied when codnitions met
- support disposition review to review content beofr i6s permantly deleted

- single retention label can be include in multiple retention label policies
- retention label policies specifiy the locations to publish the retention lables - same location can be include in multiple retention label policies


### Records management
- labeling content as record
- establish retenion and deletion policies within record level
- triggening event based retention
- revieng and validating disposition
- proof of records deletion
- exporting info about disposed items

when content is labeld as record:
- restrictions are put in place to block certaina ctivities
- activities are logged
- proof of disposition is kept at the end of the retren period


regulatory record:
- cant be relabled or label cannot be removed
- retention period cannot be shortened


use cases:
- enabling admins/users to manually apply retention and eletion actions for documents/emails
- automatically applying retention and deletion actions to doc/emails
- enabling site admins to set default
- enabling users to automati apply to emails using outlook rules


### Microsoft Purview Unified Data Governance Solutions

Data map - metadata about enterpirse data, data discovery
Data catalog -
- search
- automate tagging of data assets to glosary terms
- visually trace the lineage of  data assets

Data estage insights:
- what data is actively scnanned
- where sens data is
- how it moves

data policy:
- manage access to data sources and datasets securely at scale
- categorization:
  1. data owner policies - grant acces directly in ms purview by creating data access policy theu policy management app in ms purview governance portal
  2. devops policies - grant access to database system metadata instead of user data - simplyfy access provisonng for it operations and security auditing personal - they can grant - not deny access
  3. self service data access policies - allwos data consumer to request access to dataset and once its approved augenerated policy will provide the access - currently supported for containers, storage accounts and folders, files

 Data sharing:  - preview
 - to securely share data within org or corss orgs with busines partners and cusotmers wihtin just clicks
 - data providers can centrally manage and motoru data sharing relationships and revoke sharing at any time
 - data consumers can acces received data with theoir own analytics tools and turn data into insights

## Insider risk capabilities in MS Purview


### Insider risk management
- enable org to detect, investigate and act on risky and malicious activities
- priciples:
- 1. transparency - balance bwteeen user privacy and org risk with privy by design achitecture
  2. configurable - configurable policies based on industry, geo, busines grps
  3. intgerated - integrated workflows access ms-purview soltuions
  4. actionable - provdes insights to enable user notifications, data investigations and user investigations
 
  Insider risk management workflow:
  1. policies - what risk indicators are examined in ms365 using policies
  2. alerts - alerts dashboard
  3. triage - needs review status
  4. investigate - case dashbord  - user acitvity, content explorer case notes
  5. action - sending notifcation when employee accidently  or inadvertenly violate policy conditions - more serious case - escalating to other stakeholders to eDiscovery(premium) in ms-purview
 
data theft, intentional/unintenional data leaks, offensive behavior or more

### communication compliance
- detct, capture, act on inappropriate messageswhich leds to potential data sec or compliance incidents
- commu compliance avlautes text and image based messages in teams, viva engage, outlook, whatsapp - inappro sharing of data, offensive lang, harrasing lang, threatning, potenail regu violations
- RBAC,  - removing msg from teams / notifng senders pr protentially inappropriate conduct
- workflow:
  configure, investigate , remediate, MONITOR

  - ENABKES SCANNING FO EMAILS , TEAMS, EXCHANGE, ONEFDRIVE
 
  important complaince areas wher communication complaince policies assit with revieing msgs:
  1. corporate policies - ethical stds
  2. risk management - scna unautho communication abt projects which are confidential - auistions, earnings disclosure
  3. regulatory compliance - regu complaince to monito insider tading, laundring bribery 


## eDiscovery and Audit capabilities in MS Purview
 - identity , collect , audit infor for legal , regu oir business  reasons

**eDiscovery solutions in MS purview**
- process of identityfing and deleivering info that can be used as evidence in legal cases
- exchange online, onedrive,m teams, ms365 grps, yammer teams, mailboixes sites
- identity, hold., export content found in mailboxes and sites


eDiscovery Solutions:
1. content search - search and export in loacal computer
2. eDiscovery Standard - craete edisocvery cases and assign edisco managers to specif cases - lets you assoictae seacherches and hold on contnet locations relavant to the case
3. eDiscovery Premium - end to end workflow to identify, preserve, collect and review, analyze, report, export content responsible to your org internal or external investigations

member of the ediscovery manager role grp in ms prucive complaince portal


### Audit solutions in MS purview - for breaches across ms365
- audit std
- audit premium



























