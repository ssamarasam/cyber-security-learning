# AZ-500 Azure Security Technologies

**Foundational information**
- Solid foundation of Active Directory Domains
- RAS, DMZ, Virtualization concepts
- Azure AD to Azure Entra

**Managing Identities**
- Directory services - Azure AD, Entra
- Create and manage a managed identity for Azure resources
- Manage internal and external users in Azure
- Manage administrative units
- Hands on - create a user

**Manage secure access by Microsoft Entra**
- *IM - Previledged Identity Management*
  -- technology which allows to manage, control, monitor access to resources in the org
  -- Resources - Microsoft Entra, Micorsoft 365, Microsoft Intune
    - giving temporary access to someone to performa any action
    - principle of least rpivilage
    - just in time access
    - time bound
    - *Microsoft Entra Priveledged Identity Management* - assign roles and select time for duration of access - assigned user has to do MFA and activate it to gain access
- *Conditional Access Policies*
    - signals
    - ip location, device, applications, login time,
    - Decisions - block acces ot grant | require mfa, pwd reset and more
    - *Hands on*
        - Microsoft entra id -> Security -> Conditional access
        - New: name, assignments, target resources (cloud apps), conditions(user risk, signin-r, insider-r, device platforms, location, client apps), Grant (block, grant - req mfa, auth strength, dev to marked as compliant, ms entre hybrid dev, req approved client app,  req app protection policy, pwd change), sessions - use app enforced restrictions, cond acc app control, signin frequency, custo continuous access app ctl, persitent browser session --> Enable policy: Report only, On, Off
  - *Entra Identity protection* - mitigate and analyze threats - p2 license
      - Entra ID - Security - Identity protection
          - sign-in risk policy - meidum, high, low - block, req mfa
          - user risk policy - user actions, flag as user risk  - assignments - users/exclude  - Block access / Grant (pwd change)
      - Risky users - review the details, dismiss or block the user
      - Risky workloads
      - Risky sign-ins
      - Risk detection
      - Users at risk detected alerts - setup alerts to be sent to email of admin
  - *Passwordless authentication*
      - authenticator, hardware token
  - *Configure Access reviews* (when one user moves to other or left, access must be reviewd to revoke access)
      - Microsoft Entra id -> Identity Governance -> Access Reviews --> New access review -> select teams, or guest users - select reviewers to take action of access  - select recurrance of review  -> monthly/others to get notifictaion to review the access of users

**Command Line tools**
- *PowerShell*
    - ISE tool
    - commands: get, set, remove, start, stop, get-service,
    - e.g: start-service -name winrm
    - e.gL to remote into another machie -> Get-service - ComputerName CLIENT68, Enter-PSSession -ComputerName CLIENT68
    - e.g: Get-process - ComputerName CLIENT1, CLIENT2
    - Piping -> taking output of one command and input to another command
    - e.g: Get-process - ComputerName CLIENT1, CLIENT2  | out-file c:\\process\test.txt
    - e.g: get-help Get-EventLog
    - e.g: Get-EventLog -LogName Security -Newest 10
    - e.g: et-EventLog -LogName Security -Newest 10 | Format-List
    - >e.g: Get-EventLog -LogName Security -Newest 10 | Format-List | Out-File c:\Security-log.txt
    - cd/  --> dir sec*.txt --> notepad .\Security-log.txt
    - use $ to declare variable
- *Connecting PowerShell to Azure*
    - Azure commands from powershell gallery | Get-command -Noun *AZ*
    - powershell gallery.com
    - Install-Module -Name Az
    - NuGet and private repo warning - yes
    - Get-command -Verb connect
    - Connect -AzAccount -> provide username and pwd for Azure login in the popup
- *Working with Azure via PowerShell*
    - Get-command -Verb get -Noun *user*
    - Get-AzADUser - to list all ad users
- *Azure Cloud Shell* -  powershell and azure cli (bash)
- Azure CLI - install and use it in the powershell
 
**Manage Application access**
- *Integrate SSO and Identity providers for authentication*
    - Microsoft Entra id -> External identities -> All Identity providers  --> setup external identityes(google, fb, saml/wb)
- *Create an App registration*
    - Entra id --> App registration --> New (name, who can access this app or api? )
- Set up permissions for the app to read/access resources
    - Entra id --> App registration --> select app --> API permissions --> Request permission --> delegate (signed in), application permissions(without a signedin user)
    - Permission concent --> Enterprise application -> select app > grant Admin consent/user consent
- *Manage API permissions to Azure Subscriptions and resources*
    - app registrations - API permissions -> can able to remove perssions / revoke admin concent
- *Configure an authentication method for a service principal*
    - app registration --> select app --> Authentication --> (redirect urls, platform configurations, logout url)
 
**Manage Access Control**
- *Visualizing role permissions for management groups, subscriptions and more*
    - Management group(root) can have sub management groups underneath --> Subscriptions(allows to pay for the resources) --> Resource groups(containers to group the resources) --> Resources
    - each level, each element mentioned abouve has IAM tied to it
- *Interpret role and resource permissions*
    - Role
        - Name (e.g: owner, contributor, blowb owner)
        - id
        - actions (list of actions allowed)
        - NoActions - list of excluded actions
        - DataActions
        - NoDataActions
    - ENtra -> Roles and administrators -> create custom role and can assign i to someone
    - go to resource group, select it, select IAM and can add roles to it

**Implement advanced network security**
- *Secure the connectivity of hybrid networks*
    -  Azure boation
    -  Azure firewall
    -  on prem will go via VPN gateway --> Azure fireall --> Spoke (where VMs resides)
    -  outside on prem will go thru Azure botion --> Azure firewall --> spoke
    -  Azure monitoring gets feed from almost everything even from on-prem
 
- *Create and configure virtual networks and subnets*
    - Create resource group - vNetGroup
    - go to Virtual Network -> select the resource group -> new name for VN : vNet1 -> set the ip address 10.1.0.0/16
        - add one subnet as part of the VN creation -> Add subnet: Subnet1A, 10.1.1.0/24 (0 to 255 are allowed)
    - go to resource group, select the VN created under it.. it will show the subnet also -> create more subnets : 10.1.2.0/24
    - Create more Virtual networks and its subnets under them
    - the subnets within the virtual network can able to talk to each other(10.1.1.0 can communicate to 10.1.2.0), but vNet1 cannot communicate to vNet2
- *Secure the connectivity of Virtual networks*
    - Network Security Group - NSG
    - Application Security Group - ASG
    - Subnet can have one NSG
    - VMs can have many vNIC - eeach one can be tied with one NSG
    - to avoid tying NSG for each vNIC, a VM can be tied with one ASG to solve the issue because of one NSG allows in nic and other NSG also should be same for the other NIC
    - go to resource group -> create NSG
    - go to NSG
        - set the inbound rules
            - the lower the priority-number, higher the priorority
            - if higher number has deny rule, if the lower number has allow rule, allow rule will be considered as it is the top priority
            - or we can create inbound/outbound rule for specific ip address
        - if we allow RDP it ill throw warning that RDP is allowed for open traffic for testing.. for production we must use VPN gateway or others
        - also we can associate multiple subnets from different virtual networks as part of the same resource group.
    -  
