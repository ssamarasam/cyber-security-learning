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

1. internal member -
2. external guest - consulatants, vendors, partners - autnehticates using extrenal ms-entra acct or social media acct
3. external memeber - 
4. internal guest - 





