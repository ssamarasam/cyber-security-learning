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


   


