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

