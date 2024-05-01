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
- PIM - Previledged Identity Management
  -- technology which allows to manage, control, monitor access to resources in the org
  -- Resources - Microsoft Entra, Micorsoft 365, Microsoft Intune
    - giving temporary access to someone to performa any action
    - principle of least rpivilage
    - just in time access
    - time bound
    - *Microsoft Entra Priveledged Identity Management* - assign roles and select time for duration of access - assigned user has to do MFA and activate it to gain access
- Conditional Access Policies
    - signals
    - ip location, device, applications, login time,
    - Decisions - block acces ot grant | require mfa, pwd reset and more
    - *Hands on*
        - Microsoft entra id -> Security -> Conditional access
        - New: name, assignments, target resources (cloud apps), conditions(user risk, signin-r, insider-r, device platforms, location, client apps), Grant (block, grant - req mfa, auth strength, dev to marked as compliant, ms entre hybrid dev, req approved client app,  req app protection policy, pwd change), sessions - use app enforced restrictions, cond acc app control, signin frequency, custo continuous access app ctl, persitent browser session --> Enable policy: Report only, On, Off
      
