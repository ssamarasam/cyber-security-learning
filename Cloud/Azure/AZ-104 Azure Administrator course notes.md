### AZ-104 Azure Administrator course

### Virtual machine service
resources created a spart of new VM resource
- VM
- Network interface
- disk
- virtual network
- network security group

Notes:
- subscription
- enable conenctions RDP from NSG - by adding new inbound rules for http-80
- delete resources when not needed - consider all related resources created
- create budget alerts - set budget amount and create alert to trigger at the specied % of resource already used

VM size series:
d-series-  general purpose compute
e-series - memory intense apps
h-series - high perf computing VMs


linux vm
-sudo apt-get update
- sudo apt-get install nginx  -> a web server

- generte pri-key - will be downlaoded as part of VM creation

- use puttygen to extrat the private key
- from putty - ssh - credentials - import the private key - set ip to connect to the linux vm
- reset pwd - reset ssh keys also

subscription restriction:
usage + quotas:

### Azure VM - Disks:
- OS disks
- Data disks
- temporal disks - not a amanaged disk - data will be lost when vm restart - data just used for temporary purpose like caching

data disks;
- 3 replicas
- throughputs - upload per second 1000mb/s
- IOPS - read/write operations
- ultra disks, premium dds, std HDD
- cost avries based on throughputs/iops  or disk categories

demo:
create vm without adding any disk - just leave the default
- vm created with c drive with 126gn and a temporary storage of 16gb  (check by connecting win VM machine by RDP )
- go to VM resource -> Disks -> OS disks will be there already -> Data disks -> create and attach new disk -> name, pre-ssd, size -20Gigs -> SAVE  
- connect via RDP
- go to server manager
  - file and storage services
  - disks
  - new 20gb will be visible with the partition name "unknown"
  - right clikc and initialize
  - right click - click New Voilume - next next - assign Drive letter
 
### restarting or stopping VM
- restart - data on temporary disks remains alomng with data on ON disks and data disk
- stop/deallocate - data on temporal data dissk will be erased - data on os and data disk will remain as it is

### Servcer side Disk encryption
- encryption is carried out with platform managed keys
- customer managed keys - disk encryption sets

### Azure key vault service
- resources - key vault
- create key vault
- enter details
- retention days after deletion
- permisison model - rbac , vault access policy
- create

- go to resource
- keys
- secrets

### Disk encryption set
-> key vault
 - keys -> generate/import -> name, key size, create it
 - go to VM resource -> Disks (already SSE with PMK - platform amaneged keys)
 - go to Disk encryption Set
   - create button
   - subscription, name
   - encr at customer managed key
   - choose key vayult
   - chosse the VM key and version
   - revie amnd create
  
   - go to the Data disk of your resos
   - click ENcryption
   - in key management -> current set as platform amanged key
   - change can be made when in deallocated status or unatatched sttaus

  - go to VM resos
  - stop the VM

  - go to disk -> encrytpion -> change the key mgmt to customer managed key- disk encrption set
  - if error, go to "disk encryption set" - grant the relavant permissions - click the msg itself to automatically grant the permissions to the keyvault

Note: changing form customer managed key to platform managed key might not work - it may work in futur azure updates


### Azure disk encryption:
- for OS level encryption
- create VM
- go to DISK section
- select "craete and attack a new disk"
- name, size
- key management - platform managee key
- ok
- review and create it

- got to VM
- DISKS -> Addiional settings -> DIsk to encrypt (os disks or os/data disks)
- can be able to select the encr key stored in the keyvauult
- select key, version, save
- slect Dployment failed ->
- go to key vault
  - select Access policies -> selecte the USER -> EDIT button -> under keys -> select all of "cryptogra;phic operations" -> next and save
  - go to access configuration -> resource access -> azure disk encr for volume encr(already selected)
  - go to keys -> create new encr key -> generate -> name , 4096 create
  - go to VM -> DISKS -> Addional settings -> OS and data disks -> chosse vault , key, version
  - for windows server 2022 key supported size is 4096
 
### Data disk snapshot
- point in time
- create  a file in the data disk of VM-1 - RDP -> allocate disk in server manager before creating a file
- go to a data disk resos -> create SNAPshot -> name, revie and create

- create a new VM
- it will have OS level disk alone currently
- go to the snapshot created already -> select "Craete New Disk" -> revie and create -> new managed dis is created
- go to new-vm -> select "Attach existing disks"
- chosse the new disk and SAVE
- go to new VM amchine using RDP
- connect via RDP
- new DISK will be already exisitng in the new mahcine without Initializing it from Server Manager


### Shared disks for multiple VMS
- create  anew VM
- create and attach disk - check the max number of shares
- select share count number - eg 2
- review and create

- create new vm-2 -> attach an exisitng disk - the old disk will be appearing eher - select that
- review and create

- when u login Vm1 and initialize, new volume - craete  new file
- login vm-2 , init, new vol, - you will not see the already created file - for that some OS level software must be installed to felect the changes created in one VM to apprear on the another vm which shares the same disk

### custom script extensions
- script to run when the VM is laucnhed first time
- to install some apps
- script to be stored in azure storage acocunt or in github
- max exec time is 90 mins
- dont specify user input commands
- no reboot commands

1. create a new storage acocunt
2. COntainers
3. upload the script file\
4. craete  new VM -> inbound port rule - cjhoose http-80
5. go to advanced  -> Extensions -> Select an extension to install ->  search "custom script extension" and select it ->
   - next
   - browse the file from storage
   - choose the script container - choose the file
   - select
   - create
   - go to resousr -> copy ip, paste it in browerse - we can see the IIS already loaded (insted of going to VM and then isnatll it there) 

other way:
- connect VM RDP -> server manager -> add roles and features -> select web server


for Linux:
- advanced - custom script for Linux
- in command -> write the name of the file of the script " sh install_wb.sh" - review and create

### 34: Linux virtual Machines - Cloud Init
- install packages in linux
- .yml - a markup language - can specify config for cloud init
- create new vm - enable http-80 and rdp(already) - advanced: "custom data and cloud init"

#cloud-config
package-upgrade: true
packages:
   - nginx


### 35: VM - Boot diagnostics
- create new VM - windows
- go to Monitoring:
  - boot diagnostics: enable with managed storage account - review and create
- go to VM
- under HELP section -> boot diagnostics - refresh if need3d, check serial log

### 36: VM - run command
- go to "RUN COMMAND"
- it allows to execute various commands without going to vm
- remotely execute PS scripts in run command


### 37: confidential computing and Azure dedicated host

confidential host:
- a apsecial type of hardware included in the cpou hardware
- DCsV2 series
- enclave
- intel SGX tech
- open enclave software dev kit
- confidential consortium framework

azure dedicated host:
- dedicated host for a particular customer
- not shared to anyone
- chares based on the dedicated host/physical server - not based on the number of VM running inside it
- can control the maint events that are initiated on the azure platform

### run command:
    import-module servermanager
    add-windowsfeature web-server -includeallsubfeature

### Redeploying your VM
- if vm is not boarded ar not able to connect
- - stop and start may bring the vm from the same physical server
  - reploy - VM will be migrated to new Azure host - lost data from temporal drive
  - no losing of data from c drive
 
- if Vm is in failed state,
  - Reapply
  - 

### Availability Sets
- fault domain - networking and power - 3 
- update domain  - microsoft maintenance updates - 20

### Lab - availability set
- create a new VM
- availability zone:
  1. availbility zone
  2. VM scale set
  3. **Availability set**
  4. create new -"app-set"
  5. fault domains
  6. update domains
 - review and create
 - go to resosurce
 - check the new "availability set " resource app-set
 - VM1
   - fault domain 0
   - update domain 0
  - create new vm and choose the already created availability set "app-set"
  - now check the availability set app-set
  - app-set will show both vms under it
  - vm1 - f-0, u-0
  - vm2 - f-1, u-1

if we add more vm, then it will have 0, 0 
if we delete app-set, we will get error since VM shoudl be deleted first before availability set deletion

### Availability Zones
- multiple data centers spread across diff places within a region
- no cost for using availzbilty zone
- but cost for VMs
- cost for data transfer between availability zones
- create new VM
- availability options - availability zone
- availabiulity zones - Zone 1
- no seprate availability zone resource - it just map the VM as part of zone 1


### Azure Virtual machine scale sets
- create an identical set of VMs to host an app
- vertical scaling - increasing the size of ram, cpu
- horizontal scaling - multiple machines hositng a machine
- create a 'virtual machine scale set ' resource
- number of VMs can increase or decrease based on demand

### lab - VM SS
- search scale set in marketplace
- Create a new Virtual machine Scale Set
- Name, region, A-zones, orchestration mode - uniform, security type - std
- instance details - ubuntu
- networking: network interface-  edit, allow selected ports- 22-ssh, enable public ip address - OK button
- load balancing - azure load balancer or app-gateway or none
- scaling - 1 as part of VMSS
- scaling policy - manual
- review and create

- go to new scaleset resource
- check isntances - 1 instance running as of scale set
- go to all resos, see the below resos
  - virtual network
  - NSg
  - network watcter
  - scaleset
  - not seeing any ip or VM
  - VM is reprsented as an instance here
 
  Scaling conditions:
  - go to sclaset resos
  - select "Scale"
  - manual or custom
  - scale mode: metric or  isntance count
  - metric - add rule
  - min, max, default
  - set thr ule
  - based on coidntion increase the count - scale out
  - decrease the count - scale IN
  - SAVE
 
trigger stress in Linux to test the VM scaling OUT / IN
connect linux using ssh - putty
- sudo apt-get update
- sudo apt-get install stress
- sudo stress --cpu 1000
- control Z to strop the stress tool

Exam question:
- when VM scales out by adidng more VM, will the apps get installed in all new VMs automatically?
  - NO:
    options:
    1. custom script extensions
    2. use images which have application set already on it  and scale set could set the VM based on the image

- combine CPU percentage oif all current VM gpoes up to the specified point only, the new SCALE OUT (increase) option will trigger. its just not based on one of the VM gets more CPU pertencege up
- check Autoscal concepts in learn-MS
- click the rulk - cool down period: (5): time to give the application load across the current and newly added VM machines
  - time for new VM to stablise
  - duroing cool down time, no sclaing operations will be performed
  - time for entrire infra to stablize itself with the addition of new machines
 

### 51: Azure VMSS - orchestration modes
orchestration mode: flexible(achive high availability at scale with identifcal or multiple  machine types_  - earlier : uniform
- creatre new VMSS  with flexible
- go to scaleset:
  - instances ->  instance in creating state
- go to resosucres:
- - see the below resos which you can see only via flexible option and not in uniform
  - 1. netw ointerface
    2. Virtual machine
    3. disk
   
  - so we can manage these resos seprately using flexible option
 
  - create a ne "VM" - in the availability optio n select " virtual machine scale set" - chosse the a;lready created scale set "app-set"
  - go to scale-set app set -> two VMs are there
 
### 52: VMSS- Custom script Extensions
- create a VMSS using windows
- go to networking - edit network interface - allow selected ports - rdp-3389 and http-80 - enable public ip address - ok
- scaling - initial isnace count as 2
- review and create

- go to storage acocunt
- go to containers
- go to scrip container
- upload the new powersheel- file to install IIS webserver and craete a defauilt.html page with computer info

- go to scaleset
- instances - 2 shud be running
- click extensions + applications --> Add -" search "custom script extension" - next -> chosse the uploaded script from storage account
- custom scrip is added as part of the scale set
- script can run on both the machines(instances) that are part of scale set
- latest model: no i scale set - which says no changes made to the isntances which was applied to VMSS
- so custom sctript is not yet ran till now
- cleick on both instance and clecik "upgrade" to apply the change from the custom script extension -? clcik yes

- we can make this a stupomatiuc proces
- by going to "upgrade policy" of VMSS resos
- go to upgrade policy - currently se as "Manual"
- 

Virtual machine images:
- Azure compute gallery - create an image and place as part of it
- image definition
- image version
- 1. specialized VM images - with user  and machine infor
  2. generalized Vm images - user infor will be removed before image creation


1. create  a windows vm
2. add a custom script extension toinstall IIS and a defalt.html
3. go to resos, networking - add invound rule to accetp http-80
4. go to resos -overview -->  select "CAPTURE"
5. share it to gallery option
6. gallery details --> create new - companygallery
7. select **spcialized** / generalized
8. target vm image defintion --> create new -> name: webimage - ok
9. version number 1.0.0
10. review and create
    ------
12. go to all resos
13. we can see the new image 1.0.0 and also computegallery, also imagedefiniton - webimage
----
14. go to webimage defintion - vm image definition
15. craete a VM
16. newVM
17. image: companygallery/webimage/
18. no ability to mention admin account details since it is specialized iamge, it ahs the admin details already created by the source VM
19. create VM
20. got to new vm resos, take ip and go to browser, default.html will be working - soruce vm computer name is embedded
21. connect vm using rdp
22. go to server manager
23. select - local Server
24. click computername which ahs the old src name
25. click- change
26. "newVM"
27. restart now
28. rdp - windows-c/ inetpub/wwwroot/default.html - still old name - change it to new name




















