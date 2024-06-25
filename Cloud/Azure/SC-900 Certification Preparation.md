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
  - logical container within a ms-entra tenent - hols and organizes various resos and objects
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
- provide idnetities for use to connect to azure resos that support ms-entra without any cost

1. system assigned:
   - tied to one resos - live in resos life cycle, gets deleted when resos gets deleted
2. user-assigned:
   - standalone azure resos
   - assign it to one or more instances of azure resos - multiple VMs
   - scenario - when multiple VMs need same set of permissions
   - deleting resos doesnt impact user-assigned identity


Device:
- device identity gives admin they can use when making access or config decisions
1. MS entra registered devices - for byod - registered device can access org resos without requiring an org acocunt to sign in
2. ms entra joined - device joined to ms-entra-id thru an org account, which si then used to sign into the device - generally owned by org
3. ms-entra-hybrid-devices - devices from on prem act dir acn be joined to ms-entra - requiring org acct to signin

regsitiering and joining dveices allows to use SSO to access cloud resos
devces that are  ms-entra joined beniefit from sso to resos /apps that rely on on-prem active dir

Microsoft intue - MDM and MAM - mobile application management

Groups:
- if several identieis need same level of acces - then can create a group
- group to asisgn permissions and access to resos for zero trust
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
- providng acces to org resos to extrenal users
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
  2. ext users ca access resos without having to swicth org to sign in with diff account. can access file thru teams. cross tennt access settings wil bemange truted relation with extrnal users inblund as well as outbound
 
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



