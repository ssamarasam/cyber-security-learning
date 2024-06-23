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











  
