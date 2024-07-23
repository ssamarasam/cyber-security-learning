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

### Azure AD roles
- roles who has access only to active directory activities only
- azure rbac roles are for azure resources

### Azure AD roles - user admin
- login with userA
- go to azure active directru
- users - all suers
- can see other users, but cannot able to create "new user"
- go to admin account
- select the userA
- click "assigned roles"
- under "active assignments"
- add assignment
- select "user administrator" role
- scope type = directory
- next
- assignment type = Active
- enter justifications
- click "assign"

- go to default directry
- "roles and admins"
- click the "user admin"
- under active asignments, you can see "userA"



- now userA has "new user" option enabled

  Note: custom role
- can create a custom role under default directory
- can start from scrat or clone from exiring roles

### Azure AD groups
- create userB and userC
- create a group groupB and asisgn owner as userB
- login as userB
- userB can able to add mebers to groupB
- login as admin
- cannot remove owner from groupB untile new owner is assigned to groupB - so one owner must be prsent for a group


### Inviting an external user
- admin account user AD
- users
- new guest user
- "invite user"
- name, email address
- add message and INVITE
- can see the user in users  as guest user

- guest user will get email
- accept the invitation
- no access to any resos as of now
- as a normal user, he can be provided with varius access

### group naming policy
- naming policy for microsoft 365 group in azure ad
- go to ad - groups
- naming policy
- blocked words" - download th csv file and upload the file back
- group name policy - set particular prefix or particular suffix
- naming policy does not apply to certain directory roles such as Global administrator or user administrator



### Application registration
- to make an application to use the resosuce securely
- register the pplication in AD - application object and service principal will be craeted
- then give access to service pricipal to use the required resos

### Application registration - instalong postman
- download postman for win64
- install postman and signin

### app registration - azure ad application object
- use api call to get the user details from azure directory
- so some authentication must be neede in azure ad and  authorization is needed to get the users details
- 1. register an application in azure ad
  2. provide permissions

- go to AD
- app registrations
- new registration
- name- postman
- register
- applciation registered with the necessary details - check the postman application overview
- name, application id, object id, directory,

- go to API permissions
- default persion wa salready there- microsoft graph api - user.read permission, type - delegated
- remove the above permissions
- add a permisison
- chosse "micorosft graph service"
- chose application permission if you want to run on behalf of the applications
- go down to user
- user.readALL - select this permission
- add permission
- click "grant admin consent for default directory" - click YES
- so postman tool can make direct call to fetch the users list with the help of the assigned permission

### application registraton - calling the graph API
- call th eauthorization endpoint using the application credentials and get the access token
- using access token, app can access the resos - short lived
- go to overview of the app postman
- click endpoints
- OAUTH 2.0 token endpoint v2
- copy the url
- go to post man
- POST - url
- select body
- click - www-form-encoded
- key "grant_type"
- value "client_credentials"
- key scope - https://graph.microsoft.com/default
- client_id
- clicnt_secret  (generate a pwd for the application - go to certificates and csecrets - client secrets -> new client secret -> descrition : secret  - click add
- copy the value and pste it in the client secret value
- click SEND in postman
- access token is received int he response
- postman - GET https://graph.microsoft.com/v1.0/users
- headers: Authorization - Bearer $access-token
- info about all of th user is received in the response
- DELETE the postman application after this exercise
- 


### install Visual studio community edition
- install web aspdotnet and azure development tools

### 40: Azure AD - application registration - .net
- download the resos from az500 udemny course
- extract the zip
- go to application files inside it
- open vscode as administrator
- open a project or solution
- go to the extrated flder
- find and select - webapp----.sln file
- open appsettings.json - make sure application is integrated with active directory
- info abt application object
- go to AD
- go to 'app registration'
- new registration
- name- webapp
- redirect uri - web based
- url: https://localhost:44321/signin-oidc
- create application

- go to API permission of webapp
- it has the default api permisison - user.read - signin and read user profile
- type as delegatedadmin consent - no
- go to authentication
- check the signin url
- copy and put the same in "logout url" and change signin to signout-oidc
- enable "ID tokens"
- SAVE

- now to to vscode - appsettings.json
- you need to provide the client id and tenent id
- so go to AD again - overview
- copy the client id and tenent id from AD overview and past it in the appsettings.json file
- RUn the project locally
- it will open the local host and open the azure portal login page
- get userA signin
- consent screen will be opned for the permisisons requested
- accept it
- loggedin with showing the user detail
- signut

### sign-inlogs and audit logs
- go to AD
- click signin logs
- all llog details of all user logged in - both user signins and service pricipal signins
- check audit logs now
- e.g someone has done user managment, application management - those details will be there
- can download or export the logs on continuous basis
- add disgnostics settings
- select log categories and "destination details " to send to LOG analytics workspace , or archive to storage acct, event hub, partner solution


### Enterprise applications
- AD has enterprise applications
- for example an org might have DROPBOX for business acocount and might need to create seperate loginc for dropbox
- but using AD, we can use single identity for azure as well as for dropbox
- also using SSO
- integration available via enterprise applications
- go to AD's Enterprise application
- click - New application
- browse azure AD gallery
- see the most popular apps
- like github
- whatveer the pricing you sleect that has support with AD also
- dropbox also shuld support authentication from azure AD

- when you regsiter an enterprise app, it will craete a enterprise application object in AD
- note: all apps registred via "app registrations" will appear in enterprise applications also


### Assigning a user to an Enterprise Application
- myapps.microsoft.com
- see the applicatiosn that are asisgned to the user
- how to make an app visibilt ot he user in myapps.microsoft.com
- go to enterprise applications
- go to DROPBOX
- go to "users and groups"
- add a user - select userA
- now if userA login to myapps, then he will be able to see dropbox in his page
- if SSO is anabled, userA can directlya ccess dropbox without logiging in again
- admin acct - go to enterprise app - dropbox - select "single sign on"
- enable sso

### enterprise application - important properties
- go to dropbox properties
- enabled for users  to signin - YES - so same azude dire credentials can be used to login for dropbox
- visibile to users? - YES - for myapps portal

### enterprise application - Self service
- allow users to request access to an application (instead of assigning users with app)
- they will be automatically added to a group if they request is approved and app is assigned
- approval required?
- select approvers
- role

1. create a group dropbox-grp
2. select a owner- userA
3. create
4. go to group - dropbox-grp
5. go to owners in that
6. userA should be there
7. go to dropbox enterprise application
8. go to suers and groups
9. remove particular user
10. go to self service
11. YES - useres to request access
12. select the grp dorpbox-grp
13. YES - require approval
14. select approiver - userC (new)
15. SAVe
16. login myapps from any user
17. clcick - request access - new apps
18. select dropbox for bussines - click ADD
19. so the approver woll be replaced by userC from userA since we gave userC in the self service


### Managing applications in Azure AD
Azure Ad roles
- application administrator - allows all aspects of enterpise apps,app registrations, application proxy settings
  - ability to grant consent for delegated and application permissions
  - user will not be added as the powner when creating new application
 
- cloud application admin
  - NOt app proxy settings
 
- Application developer
  - can create app registrations - is users can register application is set to NO
  - can grant persmissons to consent on ones behalf, when users can consent tpo apps  accesing company;s data on theri beha;lf is set to NO
  - but the user will be assigned as the powner of the application
  


