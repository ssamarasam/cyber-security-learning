# AZ-500 Azure Security Technologies


### Azure Active directory
- microsoft clod based identity provider


### Azure AD tenant and subscription
- the subscription needs to trust the AD
- multi tenant will have different subscription and multiple directory will be created for each tenant


### Security defaults
- go to AD --> properties
- "manage security defaults" - default "yes"
- extra level security enable by default - like MFA
- when selecting "no", you must select the reasons to enable SAVE  like my org uses conditional access


### Creating user in AD
- users - New user
- user name, domain name
- name
- custom pwd
- the user needs to change the pwd after the first login using this admin created pwd
- pwd restrictions - length of 8
- groups - no
- role - user
- create user

- go to the created user
- check the principal id to login
- check the proiperties - can edit or delet the user
- click resources in a new tab
- select sign in with a different account
- sigin in with the created credentials
- it will promt to change the pwd
- resources wont be there since access needs to be given

### Create a group
- ad - groups - new
- security or microsoft 365
- name "internal admin"
- membership - assigned
- can add members here istself
- create hte group
- go to the group and add the new member created already to the grp

### create a MS365 group
- micorsoft 365
- ms365grp
- assignbed / dynamic
- create grp

### Dynamic groups
- azure ad premium p2 is needed
- create a new user
- create a new security group - locationgrp - dynamiz user- add dynamic query -
- city contains "new"
- go to the two users and update the location with New York and new york
- go to the group - can see the 2 users added dynamically
- rules are NOT case sensitive


### Custom domains
- when creating azure acocunt, by default user gets the default microsofy dpomain useremail.onmicrostf.com
- purchase a domain in godaddy
- go to ad
- select - custom domain name
- add custom domain
- custom domain name added
- add a record within your extrnam dmain provider form the details show when you add the domain
   - record type - txt / mx
   - alis or host name
   - destination or point of address
   - ttl
   - go to dodayy
   - add a record
   - TXT
   - @ as host name
   - txt value = ms=ms..iuhuh
   - ttl - 1 hour
   - SAVE
   - it will take some mins so AD can verify that the record is added in the domain provider
  - go to AD custom domain name
  - select VERIFY
  - domain verified
  - it will show both default and new domains
  - select the domain and "Make it as PRIMARY domain"
  - if we create new user, we can see both domain names
 
### Azure AD licenses
- azure ad pricing
- default - 0
- office 365 - free
- p1 - $6
- p2 - $9
- go to azure AD
- license - azure ad free
- go to licenses section in ad
- all products
- Try or BUY
- activate the free trial for p2 - for 30 days
- 100 licenses comes with ti
- after 30 days you will NOT be charged
- logout and login after 30 mins to check p2
- go to license, you see p2 and 100 licenses

### Restroing users and groups
- go got deleted users and restore the user within 30 days
- go to delted groups and restore the MS365 group within 30 days
- Deleted Security groups CANNOT be restored

### What goes into the deployment of an Azure VM
- when creating a Azure VMN, below are created as well
  1. vm
  2. virtual network
  3. OS disk
  4. data disk can be added
  5. public ip address
  6. Network security group
 
  - allr esource are part of resos group
  - and resosurc grp is part of a subscription
 
### create a VM
- creata a resos
- VM
- select subcription
- create resos grp
- select image windowd
- size D2s
- admin account credentials
- leave the inbound port rules which has RDP 3389 by default
- in the NEtworking
- create a new network
- review and create
- create
- in a new tab, open "all resos" - select the VM
- connect using RDP

### create a storage account
- create a storgae acct
- subs
- resos grp
- uniq name
- perf - std
- redun - Locally LRS
- reviee an create
- create


### RBAC
- users to acces resos wihin a subscription after authentication


### Role nbased assignments - reader role
- create a new user A
- open all resos in another tab
- in another tab, login with the new user A
- new user CANNOT see any of the resos
- go to all resos using admin acocunt
- goto a VM resousr
- select Access Control (IAM)
- Add role assignment
- see the inbuilt roles
- chosse the "reader" role and chosse NEXT
- assign access to "user grp or service principal"
- select member - A
- review and assign
- there ytou see, you are gic9iv access at the scope of the subscriptpon and the selected VM
- click "review and assign"
- select "role assignments :" inthin Access control(IAM)
- can see the reader role with the user-A for VM resos

- user A can not able to see app-vm resos
- but cannot see the details liuke pib ip addr
- because these are seperate resosr - like pub ip is a separate resos, virtual network/sunet is a seperate resos


### Role based assignments - resource group level
- click the resource grp - app-grp
- go to Access control IAM
- add role asisgnment
- chosse the reader role again and select the user-A
- the scope is at subscripton/resos-grp level
- go to resosucr visualizer
- now user-a can see all resos

### role based asisgmentes - subscription level
- go to azure subscripton-1 which has 2 resos group and iunderneath some resos like azure storage acocunts
- select Access control IAM
- add role asisgnments
- reader role
- select user-A
- scope - subcroioon level
- now user-A can see all the resos part of the subscription

### role based asisgnments - controibuotor role
- user-A go to app-=VM resos
- select STOP
- no access
- go to app-grp resos grp
- access control-IAM
- add role asisgments
- search " virtual machine contributor role"
- chosot that and select userA
- assign
- now userA can able to restart/stop VM

### role based asisgnments - controibuotor role
- userA open app-VM
- add role assignment - disabled
- admin account
- app-vm
- access control, IAM
- add role assignment
- chosse - user accesa  administrator
- select userA
- scope at VM level
- review and assign
- now userA can see "add role assignment" enabled

### Custom role
- go to resos grps
- go to one of the resos grp - app-grp
- ACcces control
- Add" custom role"
- custom role name - can clone a exisitng role and can modify it
- or start from scratch********
- or start from json
- next
- add permisisons
- search virtual machoine
- chosse ms-compute and see various permisisons
- ms-compute - read, restart th emahcine, stop the machine
- ADD
- next
- assignable scope: resosur group level
- see the enitre json generated
- next
- create
- cleick "roles" in access control-IAM of resos grp
- you can see the new role created - RoleA
- go to VM resos, access control - add role assignmnet to any user for the new role - RoleA
- 
- 


