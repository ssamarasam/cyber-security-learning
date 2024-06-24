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
   
  user ppbj is created in the same directory- allows to assign permisisons







