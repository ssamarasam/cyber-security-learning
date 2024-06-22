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
