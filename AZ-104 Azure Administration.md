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
- exercise governance - 



   


