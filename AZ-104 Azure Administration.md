# AZ-104 Azure Administration certification prepration

## Manage Identities and Governance in Azure

**Micorsoft Entra ID**
- MS' multitenant cloud based directory and identity management service
- support user access to resources / apps (internal resouces, MS 365, azure portal, saas apps, cloud apps developed by the org
- SAML, Qauth, Open ID, WS-Federation
- SSO, Connecting on-prem ad to entra to manage identities
- *Key components of MS Entra ID:
    -  Identity
    -  Account
    -  Microsoft Entra Account
    -  Azure tenant(directory) - directory represents a single org
    -  Azure subscription

**AD DS - Active Directory Domain Service**
- Windows Server based Active Directory on a physical or virtual server
- Certificate Services CS
- Light weight directory services  LDS
- Federation Services FS
- Rights Management Services  RMS

- AD is primarily a directory service - a database which stores and provides access to resources in a network env
- MS Entra is a full identity solution - primaritly built for internet based apps like http, https proticosl such as saml, ws-federation, open id, qauth(for authorization)

things to consider:
- identity solution
- communication protocols - http/https protocols
- federation services
- flat structure - users and groups - no OUs and group policy objects GPOs
- managed service - manage users, groups, policies -

Microsoft entra editions:
- free - user, group management- on-prem directory synchronization, basic reports, sso on azure, ms365, saas apps
- premium P1 - + hybrid users to access on-prem , cloud - dynamic groups administration, self service grp mgmt, cloud write back capabilities, ms identity manager, on-prem identity and access mgmt, self service pwd reset for on-prem users
- premium P2 - + conditional access, PIM(monitoring, just in timeaccess)

Microsoft Entra self service pwd reset - SSPR
- entra account with global administrator privileges  to manage SSPR options
- things to condier for SSPR:
    -   password reset - properties -> none, selected, all
    -   consider who can reset their pwds
    -   consider authentication methods - OTP, security questions
    -   combine many options

## Configure user and group accounts

**User Accounts**
- cloud or on-prem
- internal or external user

- 1. cloud identity - defined in ms entra-id. admin and other user accounts. defined for ms-entra org or for extrenal ms-entra instance. cloud identity is removed from primary directory, then it will be deleted
  2. directory-synchronized-identity - on-prem identity - can be connected to entra via MS-entra-connect to bring these accounts to azure. Source for these accounts is windows server active directory
  3. guest-user: defined outside azure. other cloud providers, ms-xbox acocunt. Invited user. useful when external vendors/contractors need to access your azure resources.

Things to consider:
1. where users are defined
2. support for extrenal contributors - guest user- revoke access when no longer required
3. combination of user accounts: directory-synchronized identity user accounts and cloud identitties defined in your ms-entra structure or for user defined in external entra instance


ways to add user accounts:
1. azure portal
2. ms 365 admin center
3. ms-intune admin console
4. azhure cli

cloud identity accounts:
- new user account
      - display name: john smith
      - associated user acocunt name: john.smith@companydomain.com
- global administrator or user administrator - can preset profile data
- non admin users: can set theor own profile data

thiings to consider to manage user acocunts:
1. user profile data
2. restore options for deleted accounts - upto 30 days
3. gather account data - signin / audit log  to analyze and improve the infra

Create bulk user accounts: via azure portal or azure powershell
- users -> bulk operations -> bulk create users 1. dcsv template - 2. edit 3. upload
- only global/user administrators
- templates can eb downloaded frm MS entra admin center

things to condsider for creating/deleting bulk users
1. naming conventions
2. initial pwd
3. strategies for minimze errors - after upload, bulk operations results page will show the errors (user already existing, etc)

**Create group accounts**
1. security groups
   - manage access to a group iof users
   - apply the same permissions for all the members
   - rather than adding permissions for each member
2. MS 365
   - shared mailbox, calendar files, sharepoint
   - add ms365 groups to enable grou member access to external guest users outside of entra org

access rights:
1. assigned: add specific users
2. dynamix user: dynamix member ship rules to dynamically add or remove users from the groups. member attributes. azure reviews the dynamix group rules for the directory. when member attribute doesnt meet, it will automatically remove th euser from group
3. dynamic device: only for security group. dynamix rules.

**Create Administrative Units**
creating many admins with different set of admin privileges based ont he need
for e.g: engineering department admin, help-desk-admin. each will have differnt set of administrative privileges

1. create a role that has specific admin privileges e,g engg dept for entra users
2. create adminisistrative unit for engg dept
3. assign engg dept students only to this adminitrative unit
4. add the engg dept IT team to the role along with its scope.. so they can manage engg dept only

Things to consider:
1. management tools - azure portal, powershell cmdlets, ms-graph
2. role requirements in zure portal - accoridng to role privileges. in azure portal, onky global admins or priviledged role admins can manage AUs
3. scope of administrative units - recognize the scope of an AU - members and admins of an AU can exercise theie default user permissions to browse other users, groups, resources outside of their AUs.

## Configure Subscriptions

**Azure Regions**
- represents a geo area which contain one or more datacenters
- 60/140 countries
- flex and scale to bring apps closer to users
- preserve data residency , comprehensive resiliency options

Region pair:
- to support always-on-availability of azure resources within same geo
1. physical isolation - 300 miles seperation
2. platform provided replication - geo redundant storage - auto replication to region pair
3. region recovery order - one region is prioritized to recover during a broad outage
4. sequential updates - rolling updates minimizes downtimes, bugs, logical failures
5. data residency

things to consider region/region pairs:
1. resouce and region deployment
2. service support by region - service availability
3. services that dont require region
4. exceptions to region pairing
5. benefits of data residency

- azure global infrastructure - search by country,regions or product

**Implement azure subscriptions**
- help you organize access to azure resources, help you control how azure resource usuage is reported, billed and paid
- eg: dev subscription, test and prod
- every service belongs to one subscription
- can have different billing and payment configuration
- multiple subs can be linked to one azure acct
- billing for one azure serives is done on a per-subscription basis
- programmatic operations for a cloud  service ight req a subscription-id

Things to consider:
1. types of azure acocunts needed - entra/directory or MS account
2. multiple subscriptions based on project, structure, need
3. dedicated shared services subscriptions - ensure all common network resources are billed together and isolated from otehr workloads - azure expressroute and virtal WAN
4. access to resouces - each subs linked to ms entra id and gets authenticated with entra before they access resources

obtain a subscription:
1. enterprise agreement - upfromt monetary commitment
2. microsoft reseller - buy azure thru open licensing platform
3. microsoft partner 
4. personal free account

Identify azure subscription usage:
free, pay as you go, enterprise agreement, student

**Implement MS Cost Management**

MS cost management:
- support for administrative billing tasks
- manage billing access to costs
- monitor and control azure spending and optimize your azure resource usage


Things to know:
1. Microsoft cost management shows org cost with usage patterns with adv analytics. negotiated prices, factor in reservation, azure hybrid discounts, predictive analytics
2. reports - usuabe based costs - internal, extrenal, azure market place charges, understand spending / resource use, fid anamolities, taxes, reservations cost might not be visible in reports
3. uses azure management groups, budgets, recommendations - how u might reduce costs
4. use portal, or  apis for export automation, integrate cos data with ext systems/process. automated billing reports, scheduled reports

Things to consider Microsoft Cost Management:
1. cost analysis - aggegated costs, accumulates cost over time
2. budget options - help prevent cost thresholds or limits surpassed
3. recommendations - idle resource, optimization recommendations
4. export cost management data to analys with extrenal systems using csv export


**Resource Tagging**
- apply to resources to logically organize into categories
- sorting, searching, managing and analysing
- name/value : server: production or test
- can view consolidated billing based on tags

Things to know:
- tags applied to resource groups are not inherited by the resources in the resource grp
- name/value
- max 50 for each resource group/resources

things to consider:
- search on tag data  for searcing resources by tag/value
- finding related resources
- grouping billing data by tags
- create tags programattically by using azure powershell/cli

e.g tag:   status: temp -> to store temporary resources so that we will plan to delete the resources by seeing the tag names

**Apply cost savings**
- reservations - pre paying reservation discounts upto 70% of pay-as-you-go billing without affecting anything
- azure hybrid benefits - license - software assurance - migrating to azure - azure hybrid benefits saving calculator to determine your savings
- azure credits - 
- azure regions
- budgets
- pricing calculator

## Azure Policy / Management groups

- ensure resource compliance
- service enables you to create, assign, manage policies to control or audit the resources
- enforce different rules, so they are compliant with corporate stds

**Create Management groups**
- container to manage access, policy, compliance accross subscriptions
- provides a level of scope and control over your subscriptions

Things to know:
- root group / top-level management group
- subscriptiptions inherit the condisiotns applied to the management group its under
- six levels of depth
- RBAC is not enabled for mgmt grp operations by default

Things to consider:
- custom hierarchies and groups
- policy inheritance - retrict regions at manag group.. so resouces cant be created in those retricted regions
- compliance rules
- cost reporting

create management groups:
Azure policy -> management groups -> create -> id(can submit commands using mgmt id), display name


**Implement Azure Policies**

Things to know:
- enforcement rules and compliance - enable exiting or create custom policies. evaluation.
- apply policies at scale - multiple policies - policy initiative - control accross org 
- perform remediation - real-time remidiation - remediation on exising resources
- exercise governance - implement governance ( support multiple teams, manage subs, stdarzie and enfore how cloud resource are configures, manage regu compliance, cost, security, design consistancy)

Things to consider:
- deployable resources - specify type of resouces to deploy sing azure policy
- location restrictions - specify locations 
- rules enforcement - complaince rules, configuration settings, enfore a required tag and define allowed values
- inventory audits - use azure policy with azure backup service and run inventory audits

**create azure policies**
- compliance conditions for a resource
- one or more policyes are comines to intiative definition to control scope of policies and evaluate the compliance of the resources

step1 - create policy definitiion - built in or custom
- express a condition to evaluate and the action to apply when conditions are met
- eg: prevent VM to be deployed if they are xposed to public ip address

step2 - create an initiative definition
- set of policy definitions
- to ensure resources are compliant with securty regulations

step 3- scope the initiative definition
- azure policy lets control how the intitiative definitions are applied to resouces in your org
- can limit the scope of an initiative definition to specific management groups, subscriptions and resources

step4 - determine compliance
- after assigning, we can evaluate the state of compliance of all our resorces
- individual resource, resorsce grps, subs within a scope can be excempted from the polices to affect them
- they cshould be handled individually for each assignment

**Create Policy Definitions**

examples of few built in defs
- allowed vm machine size SKUs
- allowed locations
- configure azure device update for IOT hub accounts to disable public network access access

azure -Policy -> +Policy definition(def location, name, description, category(new/existing)

**Create initiative definition**
e.g:
- audit machines with insecure pwd secuity settings
- configure windows machine to run Azure monitor agent and associate them to a Data collection rule
- configure Azure defender to be enabled on SQL servers

**Scope the initiative defition**
policy - Assignments -> Assign Initiative -> select the affacted subs, resource groups

**Determine compliance**
- Policy -> Compliance (compliant or non-compliant)

## Configure role based access control - RBAC
?? discretionary access control
?? mandatory access control

**Implement role based access control**
- RBAC determines what operations specific users can do on specific resources
- Azure RBAC is an authorization system built on ARM - provides fine grained access management of resources in azure

- application, user, group

Azure RBAC concepts:
- security principal - any object that request access to resources (user, group, service principal, managed identity)
- role definition - reader, contributor, owner, user access admin
- scope - the boundary for the requested level of access / how much access is granted - management grop, subscription, resource grp, resource
- role assignment

Things to consider:
- requestors
- roles
- scope of permissions
- built-in or custom definitions

**Create a role definition**
- consists of a set of permissions - defned in a JSON file - has permission sets
    - actions
    - notActions
    - dataActions
    - assinableScope - list the scopes where a role definition can be applied

  Things to know:
  - Azure RBAC provides built in- we can create custom
  - Owner built in role has the highest level of access privileges
  - AssinableScope permissions for a role can be a management group, subscription, resource group, resource

[ " * " ] , /*/read, /*/delete

Role scopes:
- / represents a scope as a role available for assignment for all requestors
- '/subs/lwj0nn97-nbygv-dvb', '/subs/bbbj-jndjdvjbdc' --> two subs are assigned
- can restrict to network group part of a subscription also - '/subs/sbjbvjd-ksdjbvkjvbhwg-87cbwdbjvjkdwbv/ResourceGroups/NetworkGroup


Things to consider when creating roles:
- using built in roles
- creating custom roles
- limiting access scope
- controlling changes to data
- applying deny assignments

**Create a role assignment**
- process of scoping  a role definition to limit permisisons for a requestor(user, group, service principal, managed identity
- e.g: contributor(role definition with actions, notActions) is assigned to Marketing group for a resource group(pharma sales)
  - so Marketing group can manage only pharma sales with the allowed permissions defined the role defintion
  - role definition + who + resource group

**Compare Azure roles to Microsoft Entra roles**
1. classic subscription administrator role
2. Azure role based access control RBAC roles
3. Microsoft Entra roles

**Apply Role based access control**
- ENtra admin roles are set at root level
- Azure RBAC roles provide granural access mgtmt for resources and can be aplied at multiple levels such as root, management, subs, res-grp, res

**Fundamental Azure RBAC roles**
1. Owner - all acces even to delegate access. sys admin, co-admin are all assigned the owner role at the subs scope
2. Contributor - can create /manage all res. cannot grant access to others
3. Reader - can view exising azure res
4. User Access administrator - can manage user access to azure resources

## Configure Azure resources with tools

using tools, admin can
- deploy hundres of resources at a time
- configure indi sevrcies using scripts
- viewing rich reports acress usage, cost, health and many more
  
**use azure portal**
https://portal.azure.com
- search reso, svc, docs
- manage resources
- customize dashboards
- acces cloudshell
- reciev notifications
- documentations

**Use Azure CloudShell**
- browser based command line tools for bash and powershell

features:
- file mounting temporary
- integrated graphical text editor - base don Monaco editor
- authenticates automatically to resos
- temp host per user basis
- times out after 20 mins of inactive state
- *requires resource group, storage account and Azure file storage*
- persists $HOME using a5 gb image held in your file share
- permissions are set a s regular linux  user in bash

**use Azure PowerShell**
- can be added to Windows Power shell or powershell core
- add the azure specific commands
- e.g: New-AzVM resosurce group name, name, image
- can be access via azure cloud shell or can be installed in windows, macos, linux
- two modes - interactive mode or scripting mode (multiple commands)

Az Module:
- Azure powershell module containg cmdlets to work with azure features
- resources
- storage
- vms
- entra id
- containers
- machine learning

lab:
1. create resource group
2. create managed disk
3. configure managed disk

powershell
$location = (Get-AzResourceGroup -Name gkbf-whbvbv-wmdndbd).location
$rgName = 'gkbf-whbvbv-wmdndbd'
New-AzResourceGroup -name $rgName -location $location


diskConfig - location, createOption, disksizeGb, sku
diskName = 'az104-03c-disk1'

New-AzDisk
    - ResourcegroupName
    - diskname $DiskName
    - Disk $DiskConfig

New-AzDiskUpdateConfig  -disksizegb 64 | update-AzDisk resourcegroupName, diskName

(Get-AzDisk resgrpname, diskname).sku  -> returned StandardLRS

New-AzDiskUpdateConfig  -Sku PremiumLRS| update-AzDisk resourcegroupName, diskName

**Use Azure CLI**
- command line tool , bash, administrative tasks
- e.g: restart a vm:   az vm restart -g myResourceGroup -n MyVM
- via azure cloudShell or can be locally installed in any os
- interactive or script
- supports cm.exe and bash
- commands in the CLI are structured into groups and subgroups
- find the commands to manage storage blog
  - az find blob
  - az storage blob --help

## Azure Resource Manager
- to manage resources
- resource locks
- move resources from one resource group to another
- track resource limits

Benefits:
- enables you to work with all related resources as a group
- deploy, update, delete all resources for your solution in a single, coordinated operation
- templates
- security, auditing, tagging features

1. consistant management layer
   - to perform tasks thru cli, powershell, portal, REST APi, client SDKs,
   - Azure Resource manager API
   - API request -> ARM service(authenticates, authorizes) -> ARM rotes the request to appropriate resource providers

Benefits:
- deploy, manage, monitor all resos as a grp rather than handling individually
- repeatedly deloy your solution in a consistent state
- manage ionfra thru declarative statements rather than scripts
- can able to define the dependancies between resosuces, so they are deployed in correct order
- RBAC acces control natively integrated to management platform
- apply tags to logically organize within the subs
- view cost by tags

Guidance:
- define/deploy infra thru delcrative rather than imperative commands
- define all deployment and config settings in templates. no manual steps
- run imperative commands to manage .. start/stop app
- arrange resos with the sam liefcycle in a resos-grp and tags for organizeing resos

**Azure Resource Terminology**
- resource
- resource group
- resource providers
- template
- declarative syntax

resource provider:
- format: {resource provider}/{resource type}
- e.g: Microsoft.KeyVault/vaults

**Create resource groups**
- when you deploy thru templates and if it fails, the output of the job will show what failed, why failed
- we can fix and redeploy the resouces
- if you want to deploy a third resource, the existing 2 resos will not be affected(incremental approach)

consideration:
- resos can exist in one resos grp
- cannot be renamed
- can have resos of many diff types/svs
- can have resos from many different regions

Creating resource groups:
- all resos in a resos-grp shoudl be in the same life cycle. else move the resos to other resos grp
- each resos can be in one resos grp
- can add/remove resos from resos grp anytime
- can move resos from one resos grp to other
- can contain resos from different regions
- can be used to scope access control fro administrative actions
- a resos can interact with another resos which is in differnt resos group but a different life cycle. for e.,g: web accessing a database

when creating resos-grp, location must be provided for compliance reasons . resos grp stores metat about the resources.

**Create Azure Manager Locks**
- to prevent accidental deletion of a resource
- can associate the lock a subs, resorce grp, resource
- locks are inherited by child resources

type:
- read-only - prevent any changes to the resources
- delete - prevent deletion

only the Owner or user access admin can create or delete management locks

**Reorganize Azure Resources**
- move resos from one resos-grp to another resos-grp within a subs or to new subs
  - when moving, source and target groups will be locked(cannot add, update, delete resources) but resources will be available to use
  - check for limitations
  - when you move the resource, dependancies also should be taken carre. when you move a VN, you must move its gateway resos 
  - go to resos group --> select *Move* -> choose the option to move
 
**Remove resources and resource groups**
- when deleting resos grp, all the resos within it will be deleted
- sometimes resos from other grp might depend the resos - caution

using powershell to delete resos grps: prompts for confirmation, returns no output
Remove-Az-ResourceGroup -Name "ConstosRg01"

can move individual resosurce or move from delete option of resource

**Determine Resource Limits**
- azure lets you view resos usage against limits - to track current usage, plan for future use
- subscription --> usage + quotas -> view the usage
- limits can be increased
- if you are maximum limit, it cannot be increased

## Configure resources with Azure Resource Manager templates

- azure templates
- azure templateschema components
- azure template parameters
- azure quickstart templates

- ARM templates define the resource manager templates in deployment

Template benefits:
- templates improve consistency
- help express complex deployments - dependancy mapping
- reduce manual error prone tasks
- are code - IaC
- promote reuse
- are linkable with other templates
- simplify orchestration - deploy all of your resouces and skip multiple manual operations

**Azure Resource Manager Schema**
below are the json key elements
- $schema *- locates the version of json schema file- 
- contentVersion *- describes the version of template
- parameters - values to customize the deployment
- variables - json fragments to simplify template language expressions
- functions - user defined functions that are available within the template
- resources *- resource types that are dpeloyed/updated in the res-grp
- outputs - values that are returned after deployment

**ARM template parameters**

"parameters": {
    "<parameter-name>": {
    type
    def-value
    allowed values
    minValue
    maxValue
    minLen
    maxLen
    metedata : {
        description: "jfn"
    }

}

e.g: 
"parameters": {
    "adminUsername": {
    "type": "string",
    metadata: {
        "description": "bjkbv"
    },
     "adminPassword": {
    "type": "securestring",
    metadata: {
        "description": "bjkbv"
    }
}

## Fundamentals of comuputer networking
- network protocols and standards
- differences between WAN and LAN
- TCP/IP
- IP addresses, Ports
- how these concepts apply to azure

**Network types and topologies for internet based network**
- PAN
- LAN
- MAN
- WAN

PAN:
- networking needs around an indi
- phone to a bluetooth speaker
- network standards: bluetooh, IEEE 802.15

LAN:
- networking needs around a single location
- office, school, hospital, airpost
- privately owned and needs authentication/authorization to access

MAN:
- networking capabilities between two differnt locations within a city/metropolitan area
- secure connection between each lan joined to MAN

WAN:
- networking capabilities between two different geographical locations
- WAN links multiple LAN -> super network
- use VPN to manage the connect between diff LANs

Network topology - physical composition of a network
- bus
- ring
- mesh
- star

other standards:
- ethernet
- fast ethernet
- gigabit ethernet
- 10 gigabit ethernet
- terabit ethernet

Networks in Azure:
- Auzre Virtual network
- connectivity services
  - vpn connection via Azure gateway
  - dedicated connection thru Azure ExpressRoute(secure point to point service)

**Types of network devices to use when you build a network**

network standards:
- network protocols  provide a unified method foc communication
- network standards govern the hardware and software that uses them
- 802.11 - wireless LAN
- 802.15 bluetooh
- 802.3 ethernet

network infra:
- repeaters
- hubs
- bridges
- switches
- routers

all devices depend on ip address or mac to deliver data on the network

mac - media access control 
- unique identifier assigned to every network enabled device at the time of manufacture
- burned-in, ethernet hardwarre, physical address
- aa-bb-cc-dd-ee-ff-gg
- aa-bb-cc -> refers to manufacturers Organizationally unique idenfifies OUI
- ff-ff-gg -> refers to device id

repeater
- two port device - repeats the network signal when netw devices are distant from each other
- it doesnt modify the signals

bridge
- divides a network into network segments and filter and fwd data packets between these semengs
- uses mac to identify the destination and reduce unncessary traffic on netw segments

Hub
- multip port repeater on a netw
- connestc more than one device structure he layout of netw
- operate at one speed whci is the speed of the slowest netw deice connected to it
- types:
  - fast ethernet - class1 class II
  - dual speed

Switch:
- combines the functionality of bridge and hubd
- segment networks and intereprent/filetr data to send directly to dest netw device
- full duplex mode - can able to send and revice data to and from a netw devices at the same time
- features:
  - adjust the speed of inbound packet witht he outbound speed
  - support power ever ethernet
  - other moduels can be attached - port mirroting, packet sniffers, ids

Types of ethernet switch:
- unmanaged
  - no config capability
  - switch happens automtaically
  - small home, small office envs
- managed
  - able to configure
  - thru cli which uses telnet or ssh, remote console, web interface
  - config options
    - Qos - priority
    - Virtual LANs - craete logical grp of devices
    - STP Spanning tree protocol - build alternate network routes when cable/device fails to build resiliency
    - port mirroring - use with network analyzer to diagnose netw issues/problems - exports copy of netw traff to single port
    - bandwidth rate limiting - control bandiwth used by specifc ports
    - MAC address filtering - control the deicves can be sued to access swicth based on mac address
    - SNMP client - configure SNMP with your network monitoring tools
  - sub-types of managed switches
    - smart - halfay ebtween unmanaged, managed switch - only web interface - only can manage port mirroring, virtual LANs, bandwitth rate limiting
    - enterprise - fully managed switch service

router:
- connect mutiple networks together and provide internet access
- also called gateway
- fwd decisons based on IP address
- def gateway IP address
- Interconnectvity:
  - routers in interconnected networks maintains routeting table - has he preferred routes
  - start of authority of all network devices in its network
  - routing information is shared between routers using  a routing protocl called BGP - Broder Gateway Protocol
- Types:
  - Access Routers - simple rotuing - home or small offcie
  - Distribution routers
    - compile routing data from multiple routers
    - more sigifincant memory and power
    - hold vast quantiies of routing info
    - usd to manage the QoS scross a WAN
  - Edge routers
    - opeatres between local network and other networks
    - or local netw and internet
    - come with firewall to improve security
    - act as gateways and to filter traffic and route it inernally or exte based on packet headers
    - hanld DHCP and DNS services
  - Core Routers
    - enterprise routers for diff geo lcaton
    - higher bandwidths
    - fewer features than edge routes
    - pri focus to minize packet loss and congestion
    - pkt fwding to edge routers

Wireless Routers:
- all routing capabilities and provide wirelss acces point fuctions
- build wiress local area network
- not same as wireless modem which converts signal from ISP into the one thats usable in the network
- uslaly wireless modem comes with combine router to craete privatre home or office network


Azure options: - to help with routing and managing netwok traffic
- Azure Hub Spoke
  - its a reference architecture
  - the hus is usually a Azure Virtual Network - acts as a connection point between on prem and cloud
  - each spoke is a virutla network connected via a peer network
  - connections ebtween on prem and lcoud can be made using VPN gateway or Azure ExpressRoute
 
- Azure ExpressRoute
  - a dedicate circuit proivded by a third party partner between on-prem and cloud uses higher bandwith than a regular VPN gateway connection - super resilient connection
 
**Network Protocols**
- set of conditons or rules to specify how netw devices commuicate on a given netw

Network address 
- mac - identifier on a hardware level
- ip adresss - on a logical or sftware level

data packet:
- a unit of data that two devices on a network send eaqch other
- raw data
- headers
  - sender/dest address
  - size of pkt
  - protocol used
  - packent number
- trailer
  - deals with error checking

datagram:
- refers to data packet where the delivery of data cannot be guranteed - data packets of unreliable service

routing:
- mechanism where the data packets goes form one dive to otehr deive on differnt networks

protocol categories:
- network communication protocol
- network security protocols
- network management protocols

Network communication proocols:
- establishing and maintaining communication between devices
- foundational protocols - logincal transmisison of data over the network
  - Transmission control protocol
    - send data securely and across ip based network
    - reliable
    - communication oriented protocol
  - Internet protocol
    - addressing of data packet
    - adds header
  - user datagra protocol
    - connectionless protocol
    - unreliable
    - dont verify that the recieptnet device recieved the data
remaining protocls are type based
  - HTTP uses TCP/Ip to deliver web page content from server-  handle download /uplod from remote servers
  - FTP transfe files between diff computers on anwtework
  - POP3 - Post office protocol3 - used by email client to recive email - uses TCp for the managemnt of emeil delivery
  - SMTP - Simple Mail Transfer Protocol - send email - uses TCP
  - IMAP - interactive mail access protocol - more power than pop3 and smtp - used to manage sigle mailbox on and email server

Network Security Protocols:
- uses enctryption and cryp[tographic principles to secure messages

SSL - secure Socket layer
 - std encr and security protocol
 - provides secure conn between your computer and a target comuter or device accessed over internet
TLS - Transport layer security
 - sucecssor to SLL- more robust security encr protocol
 - designed to stop message forgery and eavesdropping
 - typiclaly used to rotect wbe based, email voip, instant msging
HTTPS:
 - secure version of http protoc, by ussing ssl or tls
Secure Shell SSH
 - is a cryptographic network security protocol provices a secure connection accross a network
 - ssh is designed to support command line exeuon of instructions and reote authenticaltion
 - FTP uses many ssh functions for file transfers
Kerberos:
 - validation protocl provides roubst authentication fo clnt serevr based applications using secret key cryptography
 - it assum all endpoints in network are insecure
 - constany enforces strog encr for all communications and data

Network management protocol:
- focus on sutainability of netw by looking at faults and performace
- monitoring and reporting

1. simple network management protocol - SNMP
   - internet protocl which allows for the collection of data from devices on our network and mgmt of the dvices
   - devics has to support snmp protocol - swithes, routers, lapos, desktops, printers
2. Internet control message protocol - ICMP
   - protocls included within internet protocol suite ips
   - allows deivces to send warning/erros mesags with operational details such as sucecs or faily of connection request or if srvice is unreliable

*Ports*:
- logical construct that allows the routing of incoming messages to specific processes
- particular port for evey typoe od ips
- communication protoclos such as tcp or udp assignes these port numbers
- first 1024 pots are well known ports - reserved for common srvices
- remainging higher number are ephemeral ports , unresrved, used by dedicated applications

- internet assigned numbers authority IANA manages allocation of ports, regional assignement of ip address and dns root zones
- well known ports, registered ports, dynamic/private ports

  22 - secure shell ssh
  25 - smtp pro for email rotung
  53 - dns
  80 - http
  443 - https
  123 - ntp


  Innternet Protocol Suite or TCP/IP suite:
  - collection of communication protocols
  - abstract, layerd netwroking ref model
  - used tosend recive data on internet and similar networks
  - TCP/IP model and OSI Model

  Monitoring networks in Azure:
  1. azure network watched - to view data packets
  2. network performmnce monitor
  3. perforamnbce monitor

  
  












   


