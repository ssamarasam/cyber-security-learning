
# General Security Concepts

Threat - anyting that could harm, loss, damage or compromise to IT systems
Risks
Vulnerability

Confidentiality
- encr
- access controls
- data masking - obscurng data inaccessibile (like hiding 12 digits oif card number)
- physical sec measures
- training awareness

> confidentiality -> encryption

Integrity:
- data accuracy
- trust
- system operability
1. hashing - hash digest /   digital footprint
2. digit sig - using users private key, ency and hash it
3. checksums - during transmit 
4. access controls
5. regular audits

> integrity -> hashing

Availability
- ensu business conti
- maintain cus trust
- upholding an org's reputation

**redundancy**
- server redudancy
- data redu
- netw redun - if one netw path fails, can travel thru other route
- power redun

> Availability -> redundancy

Non-repudiation - undeniable proof of their action
- digital signature - hashing the msg with digitally signed and encr the hash digest with the users private key using asymmetric encryption
1. confimring the authenticity of digital transactios
2. ensuring integrity
3. providng accountability

> Non repudiation-> Digital signature

Authentication:
mthods:
- something you know
- you are
- you have
- you do
- somwehere you are

why?
- prevent unauth access
- protectuser data and privacy
- ensure resource validity - valid/authenticated users only can use allowed resouces - network and cloud

factors
- knowledge factors
- location
- pocession
- inherence
- action


Authorization
- role based, rule based, attributes based controls to determine permissions
1. protect sensitive data
2. maintain system integ in org
3. create more streamined user exps

authorization - set of rules/policies - used to dictate what actions user can perform once verified

Accounting:
- a sec measure that ensures all user activities are prope tracked and recorded
- monitoring and logging the actions of users
- provides tranparency, security and acocuntability
- robust accounting system
  - audit trail
  - rgula compliance
  - forencis analys
  - reosrce optima
  - user accontability

  how?
  - syslog serves
  - siem
  - network anaysi tool

  Security control categories:
  1. technical controls - soft/ward tech tools to protect
  2. managerical controls - adminitrative controls - strategic planning and governance side of security
     - risk assessments
     - security policies
     - training pgms
     - incident response startegies
  3. operational controls - involves procesudes and meausers designed to toretct data on a day to day basis and govenrd by intrenal process and human actions
     - backup procedures
     - acocunt reviews
     - user training pgms
  4. physical controls
     - physical secu
     - survial camer
     - shredding of sens data
     - sec guards
     - lock doors

  security control types:
  1. preventative controls - firewall
  2.   deterrent controls - waring signs
  3.   detective controls - ids, seim
  4.   corrective controls - fixing sys, quqrentine malwares
  5.   compensative controls - lower secured or legacy os.. but with use of vpan, we can add security
  6.   directive controls - pocicies
 
  Gap analysis:
  - current and desired performamnce
  - 1. scope of analys
    2. gather data on current state of org
    3. analyze data toidentify gaps
    4. develop a plan to bridge the gap

  1. technical gap analysis
  2. business gap analysi - business process wher they feel shoft compared to desired plan

 priotitize gaps
 
  plan of action and milestone - POA&M
  - outlines the spci meausre to address vul
  - alloca resos
  - set up timelines fo each remediation task

Zero trust:
1. control plane - identty and who gets access and how
   - adaptive identity - udneatnd user behavio, loca, activ
   - threat scope reduction - limit user acces, limit attck surface
   - policy driven access control - devlop, amange, enfore plocies , rules
   - secure zones - isolated env with a netw to house sens data
2. data plane - ensures that policies and rpocedurs are properly executed
   - subkect /system
   - policy engine
   - policy admin
   - policy enforment point


### Threat actors

Motivation:
- data exfiltration
- blackmail
- espionage
- war
- philosophical or political beliefs
- service disruption
- financial gain
- ethical reasons
- revenge
- disruption or chaos

Threat actor attributes
based on - origin 
- internal or extrenal
- resources or funding
- level of sophistification and capability
  - low - lowest skilled - script kiddies
  - high -


unskilled attackers
- taget small companies
- initiate DDoD attacks
- opportunistic
- tool - use tools like low orbit ion cannon
- lacks tech knowledge to craete or modify malwares
- gaining recog or for thrill
note: APT - advanced persistant threatds


hacktivists:
- indi/grps use their tech knowlege to promota  cause ror dive social chane instead for personal gain
- techiniques:
  - web defacement - electorinic graffiti - actr of vandalism
  - ddos - verwhelming a web to cause service disruption
  - doxing - public release of private info of an indi or an org
  - leak of snstive data
  - ananumus
  - lulsec - 50 days of lulz
 
Organized crime:
- sophisticated / well structred enti levegares resos and etch skills for ilicit gain
- use:
  - custom malware
  - ransomware
  - sophisticated phshing campaings
  - exploit emerging tech like - crupto, dark web, celluar collection devices
  - engage in variory o ililict activities like
    - data breaches
    - identify threft
    - ransomware attacks
    - online fraud
  - for financial gains but can be hired by anyone - fin7, carbanok
 
Nation-state actors:
- govt sponsored but kept a s seperate entity so that govt can deny their involment
- false flag attack - attack orchestrated in a way that it appears to originate from differnt source or group
- techniuqs
  - creating custom malware
  - using zero day exploits
  - becoming an advanced persistant threat
  - (nation state ctor - APT due to their long term persistance and stealth)
  > APT - prolonged and targeted cyber attack - in which inrtuder gets unathu access and remains undetected  for an extended period of time - trying to steal data or monitor netw activities rather than cuase immedite damage
  - why they attack?
    - gather inteligence
    - disrupting critical infra
    - inflicining political process
  - they also do cyber esponinage to steal intellectual property or gain competive advantage in competteive industries
  e.g: stucknet worm
   - malw used to sabotage iranians nuc pgm
 
insider threats 
- internal emp , contarctor , or anyoen who has access and knowleg about itrenal infra
- extensive access - like admin
- insiedr attacj forms
  - data theft
  - sabotage
  - misuse of access privileges
- motivations?
  - financial gain
  - revenge
  - carelessness / lack of cyber sec awareness/best rpatices like newbie
eg. snowden, twiietr attack of 2020

Shadow IT:
- the use of IT sys, device, apps, svs with the excilt org approval (stealth it, clinet it, shadow it)
- shadow it:
  - use of perosnl devices fo waork purposes
  - installation of unapproved softw
  - use of cloud servi not pporv by org

eg:
- usb
- ext hdd
- keyboard
- wired mouse
- netw adapter


They may bring wide range of vulnerabilities as thier life cycl is not managed by an org

potenal data breaches, non compliance with regu and sys disrp

- plusgins
- extension
- byod

- use of google drive, dropbox without the knowlge of org is also shadow IT - can lead to data leakage oif not properly managed

Threact vectors and attack surfaces:

Threact vector:
- the means or pathway by which an attacjer can gain unauth access to netw, compu to deliver mali payload or carry out an unwanted action

Attack surace:
- encompasses all various  ponts wher an unauth user can enter data or extract data from an env
- sum of all vuls and entry pooints and attacker could exploit


threat vector as how of an attack
attack surface is the aware of the attack

if atack surce is netw, to sigificant imcrease sec posture of netw
- restict access
- removing unne soft
- disabling unsued protocols

Threat vectros in enterprises:
- messages
- images : stegno attack - embeding mali code within pixels
- files
- voice calls
- removable devices - baiting - leaving usb with mali code
- unsecure netws
  - wireless - evil twins - mimic the legitimate wireless access points
  - wired - mac address cloing, VLAN hopping
  - bluetooth - blueBorne(vul attack pspread malware, on path communi to intercept communi), blueSmack( a type of ddos attack, crash dev and make inoperable)

threat vector - means or pathway by which an attacker can gain unautorized access to a computer or a network to deliver a maicious payload  or carrty out an wunwanetd action
attack surface - excompasses on al th various points where an attacker can enter data or extract data from an env

Outsmart threat actors:

TTPS - tactics, techniques and procedures
deception and disruptive techniques - to undertand the TTPS of an attack by attackers
- deisgned to mislead, consife, divert attackers fromc ritical assesta while similtaneoly detecting and neutralizeing threats

1. honeypots
   - decoy sys - allow accatakers to understand attackers' methods, motives and TTPs
   - can be used against insider threats to detech internal fraud, snooping and malpractice
   - emulation app to simulate actival netw or application
   - designed to log all inetraction/ transaction to provide values insigtes to the threat landscape
   - instal in screened subnet or osilated segment - easyf or attackers
3. honeynets - grp of honeypots to mimic an entire netw including orters, swicthes and other new devices - but can end up a s dowside sward since an attacker can learn the how the newt architure is made in the org
4. honeyfiles
   - decoy file placed with a syste m to lure  in potential attackers
   - shoud, apprea contain valueable information to make attacker to go aftr the data
   - set us a s trap - IDS inform sec team and some file whic have embedded code allows them to enumurae the attackers network once the file is open
   - unique embedded file to help track the file if it is stolen or copied
6. honeytokens
   - peice of data or resource with no legitimate data to use but can be monitored for access or use
   - fake user accout, url, a dummy database record,
   - if honeytoken is used or access - clear indication of potential security breach is likely occuring
   - particulatrly sueful fodetcing insider threats
   - any inetarction with them is suspicous
  
Other techniques in decpeion/distrptiv tech:
- using bogus dns entries
- creaing decoy directories
- generating dynamic pages  to stop web scraling
- using port triggering - to hide services
- spoofing fake telemtry data - during adetcted netw scan


### Physical Security
Fencing - prevent people
Bollards  - prevent vehicles

Attacking physical security with brute force:
- forcible entry - breaking
- tampering with sec devices - tamper deives - soltion: reduct device at multiple places
- confronting sec professional - 
- ramming a barrier with vehicle

Surveillance systems
- a security perosnall or sensors and cameras
- 1. video
     - motion detection
     - night vision
     - facial recog
     - remote access thru smartphone/computer
    wired/wireless
    CCTV:
    - indoor/outdoor
    - Pan Tilt Zoom PTZ - can aletr the direction of camera
    where?
    - data center
    - telemcoom closets
    - entrance or exit
   shoudl be acapable of identifiying intrustion using ML
  
  3. sec guards
  4. lighting
  5. sensors
     1. infrared - low light, heat identyfy human animal 
     2. microwave - detetc movemts emiting microwave pulses and meausringt he ferlction of moving objects - large ares - sometimes prone to be false alarms
     3. pressure - activate whn a specief amt of weight is detected on the sensor that is embetted on a mat or floor - identy unauth entries in spec areas and alert owners
     4. ultrasonic sensors - meause the refle of ultrso waves of movig objects - aumtomated doors or detectmovement in indoor env
    

Bypasing surveillance systems
1. visual obstruction - paint ballon on camera
2. blidng sensors and cameras - hig h power falsh light, heating up room to damage infrared sens
3. acoustic interferarance - loud noise, music
4. elctro magtnei interfe - EMI generatros, jammers to distupt the radio frequencies
5. physicl env attack

sotuoion:
- tamper alrms
- backup powe ups
- encr frequencies


Access control vetibue 
- two door system - elctronically controlled - only one door can be opend at a given time
- opens the second door when the first door is open
- autheic, identy, access
- prevents piggy backing, tailgating
- RFID id cards - radio frequency identification
- NFC - near field communication
- magnetic strips - legacy (like back on the credit card)
- action is logged
- access based on role
- audit trail to log user actions
- sec guard at access contro, vesibule as visual detrrent and also to reponse immediate concenrs
  - visual asistan
  - assitance
  - check identity
  - response

Door Locks:
- pad locks with key
- pin locks
- wireless locks  using nfc
- biometric
  - false accecptance rate
  - false rejection
  - equal erorr rate ERR
    - calle as  croosver error rate CER - meaure effectiveness of a biometric system
  - MFA
- cipher lock - mechanical locking systems uses push buttons, often numberrd and requris the correct combination to be entered for access

Access Badge Cloning:
- vulnerability of able to clone access badges to bypass your authentication systems
- copy of data from an RFID or NFC card to another card or device
- 1. scanning
  2. data extraction
  3. writing to a new card
  4. using cloned access badge

hw to prevent?
1. implement advaced encr in card based authen systems
2. MFA
3. regularly updated securty protocols
4. educate the users
5. implement the use of shielded wallets or sleeves wih rfid access badges
6. monitor and audit the access logs


### Social Engineering
- the art of exploiting human psychology to gain unautho acesss to systems, data or physical spaces

Motivational triggers used by scial engineers:
- social engineers use these below factors to gain trust or achive their intended action
1. authority
2. urgency
3. social proof - if soemthing isused by many or if some page is liked by many and friends, we think thats legitimate  - psychological phenomenon - if a social engg forces one guy to post something, hten it goes to another to anther a slegitimate one by one - e.g signing up a course which has 100,000 reviews and likes of it
4. scarcity - psychological pressure when they belive a prod is limited or in short supply , poeple act quickly 
5. likablity - associate with being nice, friendly, socially accepted by others
   - sexual attraction
   - pretending to be a friend
   - common interest
7. fear - a great motivator like ransomware. if you dont do what i tell you, then this wll happen (Fear and authority)

Impersonation: as a social engg attack
1. impersonation
   - adversary assumes the identity of another person to gain unautho access
   - attacker might intimidate as other and gain trust
   - 1. unautho acess
     2. disruption of serv
     3. complete sytem takeover
2. Brand impersonation
   - attacker pretends to represent  a legitimate company or brand
   - attacker may use brnad logos, legitimate kind of emails, web pages, online rpesence to make people believe whom they clim to be
3. Typosquatting
   - attacker registers a domain name similar to popular wbe site but contain typograhical errors
   - url hijaking or cyber-squatting
   - user who mispell urls and it might lead to mali websites and become victorms of their typosquatting
   - companies may register original url and also mispelled url to protect users
4. watering hole attack
   - an attacker attacks a commonly used website or service and then wait for users to use those attacked services to capture those user's details
   - like animals wait near water source for their prey to come and drink water and then attacks the animals
   - to prevent these, orgs must keep their systems up to date
  

Pretexing:
- is way to give some amount of information that seems true so you will give us more information to fill in the gaps

Phising attacks:
1. phishing
   - email represnting a legitimate personal to gain trust, or to click mali link, or to download mali attachment
   - sent to mass group of individuals
   - spray and prey
3. vishing
   - voice phishing
   - betetr approach than email phsing.. ike a abnk repres call
5. smishing
   - SMS phishing
   - link via sms, urgency
7. whaling
   - a form of spear phishing targetting high profile individuals CEOs CFOs - 
8. spear phishing
   - targetted form of phishing - specific grp of individuals or orgs - attackers gather info and send personalized emails - higher level of customization - higher success rate
   - target users
9. business email compromise
   - if attacker compromises one email acocunt, then use that account to affect otehr email acocunts or making employees to do their inted action using the trust of compromised account

preventting phishing attacks:
- anti phishing campaigns - trainings to eployees
  - generic greetings
  - spelling and grammer mistakes
  - spoofed email addresses

  comonly used key indicators:
  - urgency
  - unsual reqs
  - mismatched URLs
    - word based email
    - html based email show display text and hides url. hover on it to see real url address
  - strange email addresses
    - display email address
    - real email address by cliking it
  - poor spelling and grammar


techniques:
- conduct trainig
- recog phsing attempts
- report suspicious messages

Conducting an anti-phishing campaign:
- free program - Trend Micro : phish insights

Frauds and Scams:
fraud:
- the worngful or criminal depction to steal infor from user

Identity fraud: identity theft
- the use of another persons's PI without authorization to commit a crime ro to decive

Scam:
- a fradulant or deceptive act or operation

Influence campaigns'
- misinformation:
  - inaccurate infomation share unintentionally
  - false info shared without harmful intent
  - by mistakes
  - e.g. gagling small amoyt of chlorine water could prevent covid virus spread
 
- disinformation
  - intentiona spread of fals information to decive or mislead
  - to manipulate public opinion
  - spread discord
  - or undermine trust and isntitutions
  - e.g. spreading rumours about opposite parties for election campaign


### Malwares
- any software that is designed to infiltrate a system , damage without the user's knowledge or consent
- Threat vector - a specific method used by an attacker to infilitrate victim's machine (how they are plan to break into the system)
  - unpacted software
  - installing code
  - phishing campaign
  - other vulnerabilities
- attack vector - a means by which an attacker gains access to compu to infect the system with malware (how they are break into system and affect the system)

unguarded neighbour hood is thret vector
walking the home, picking the lock, open the door -> attack vector (vulnerabilities that could be exploited)

unpactched vulnerability is threat vector  
wannacry malware- scan amchiens to find vulnerabilities

Types:
- Viruses - damage sys
- Worms - replicate themselves
- Trojans - look like legitimate software and gains unauth access once executed
- ransomware - malware which encrps and locks systems and iut gets a ransom amount to get the encr key
- zombies - a compromised system
- botnets - network of compromised system used for varilos mali activities to run phishing campains and many others
- backdoors
- logic bombs
- keylogger - malware that captures all key in activities to capture credentials and sensitive data
- spyware - resides in systems and sends data to attackers without user's knowledge or consent
- bloatware

Virus: (req user to perform an action - open a file)
- boot sector
- macro
- program
- multiparte - boot sector + program
- encrypted
- polymorphic - adv version of encr virus - rewrite the virus code each time its executed to avoid detection
- metamorphic - rewrite its entirely before it infects the system (more adv vs of polym)
- stealth - its a technique used to prevent the detection of virus - also it prevents the virus's activities like encr of data, paylod execution 
- armored - layer virus to avoid detection
- hoax

Worms: 
- a mali soft like a virus - can replicate itself without any user interaction
- it scans network, find vuls and spread one netw to another
- e.g Nimda, confliker

Trojan - 
- software looks like liegitimate software but comes with mali code and executes once the software is executed
- and takes oevr the system or get remote access
- create backdoors to use the victim's system

Remote Access Trojan
- trojan wich provides remote controlof victim's machine


Ransomware:

how to avoid?
- conduting regular  backups
- installing regular software updates
- providing security awareness training
- MFA


Botnets
- netw of compromised systems(zombies) controlled remotely by mali actors
- use the processing, memory,. storage, networking capabilities of our system without our concent or knowledge
- used to perform tasks using remote commands

command and control mode: C2 node
- responsible for managing an coordinating he activities of other nodes or deivces within a network using one's comuter
- which will make all activities happens at victims machine
- attacker uses C2 note to control the botnets

- ddos attack can be performed via botnets(using comproevmized 100000 zombies and attack one's server to cause DDoS - send too much load and the server goes to offline
- crypto mining as they use processing ower of zombie
- using zomies and its procesisng power, they break thru differnt encr schemes
- attackets ypicllly use 20 to 25% of victims processing power to avoid detection

Rootkits: - hiding malware activities and maintaining priviledged access to a system
- soft deisgned to gain adminitrative level of control over a given comuter without being detected
- root or adminitrative level of permission
- differnt ring levels of permisisons
- ring 0  - kernal - deep - hightest level of permiiosnl which have acces to os, hardwares
- ring 1  - over leayer of ring zeoro which has admin privileges of ystem
- rootkit tries to go to ring 0 as well and anyti virus cant detct the rootkits easily as it resides or takes over hightest permisson
- designed to dig deeply into the OS
- DLL injection  -  is a technique used to run arbitrary code within the address space of  another process by forcing it to load dynamic link library
- DLL provides data and code to many process needed by os and loaded up at runtime
- this DLL works as SHIM
- SHIm - softw code that si placed by two  components to intercept one process

- to detect rootkit installation, boot the system using external hard drive and scan the system y=using good ani-malware soltion

Backdoors & Logic bombs:

backdoor
- placed in coputer system to bypass the normal security and authentication functions fo the systems designed by systems original programmers for their own use like miantaing the system

easter egg:
- insecure coding pratices sued by programemrs to prvide a joke or gag gift to the users
- thse ara ddiional unnecessary code may bring vuls

Logic bomb - mali code instered into program and will only execute when certain conditons are met


Keylogger:
- software or hardware based - computers and mobiles


preventing ideas:
- updates
- anitvirus
- training
- excr keystringing systems
- physical check is hardware keylogges is isntalled

spyware & bloaware:
- listens and send data to maliactors
- istalled?
  - bundled with other soft
  - instaleld thru mali web
  - when clikcing deceptive pop-up ad
- slow down sys , perf as ist is continusly using ur system gathering info about you
- always read EULA - end user licensing aggreement

Bloatware
- any softw thats pre isntalled on a new compu or smartphone
- watstes storage space
- shopws down perf of devices
- introuces new vuls to sstems

remove:
- manually remove it
- bloatware removal tools
- perofm clearn OS installation

Malware exploitation techniques:
1. fileless malware - used to create a procss in system memory without relying on local file systm of infected host
   - levae limited evidence or traces as it will delete all the items after executing
   - dificlt to be identified by ani-malware/virsus systems
   - stage1. dropper or downloader   - when suer cliks/downloads, mali soft is instaleld ( these use light weight shell code)
  
dropper - a spcif malware type designed to intiate or run other malware forms within a payload or infgected host
downloader - retrioves additional tools post the intial infection faciliated by dropper 
shellcode - emcompasses light weight code meant to execute on a given target

stage2: downloader 
- download and unstall remote acces strojan to conduct and command control on victim machine

action on objectives phase :
- threat actors will exuet their primary objectives  - data exfiltration, encryption

concealment:
- used to help the threat actir for prolonged access  to a sys by hind their tracks, erasing log files, and hiding any evidence of their mali activities

techiques:
- code injection
- masquerading
- dll injection
- dll slideloading
- process hollowing

Living of the land
- try to exploit stad system tools to conduct mali activities or intrusions

Inidcations of malware attacks:
1. account lockouts
2. concurrent session utiliztion
3. blocked content
4. impossible travel - acocunt is used/accessed in two or more geographical locations which isimporrible to travel in short time
5. resource consumtpion - crypto mining, cpu utilization
6. resouec inaccessability
7. out of cycle logging - logs at odd hours
8. misisng logs
9. published and documented attacks

### Data Protection

- is a process of safe guarding important information from corruption, compromise or loss

Data classification - category based on org's value and the sensitive of data when its disclosed (Data owner decides this)
- sensitive data - loss of security
- overclassifyling data leads to protecting all data at high level

1. commercial business
   - public
   - sensitive - minimal impact if released - like org' fin data or course content before published
   - private - data within the org - relates to individual entity
   - confidential - trade secrest, source codes, intellectual rpoperty that affects org if disclosed - only approved personalls can read or 3rd parties under an NDA
   - critical - too valuable - credit card numbers
3. government
   - unclassified
   - sensitive but uclassified
   - confidential -serious effect
   - secret - serous damage
   - top secret - data that would damange national security if disclosed, might contain blue prints for variuoys systems
  
  life cycle of data - org must have polices for their data - how they store, how long they store - how are you going to destry when not needed
  - colelct
  - retain
  - dispose

consider legal and govement regulaions

Data Ownership:
- process of identyfing the person resoonsible for the CIA and the privacy of the information assets
1. data owner - senior exce role - has responsiilty for maintaing the CIA of the information asset - label the asset and ensre it is protected with the appropriat controls
2. data controller - entiry who controls the purposes, methods of data storage, colelction and usage and for guranteeing the legality of processess - holds acocuntability for any breaches of privacy and cannot delicate this repon to another party
3. data rpocessor - grp / indiv to hel data controler for collecting, storing, analyze data
4. data steward - role focused on the qualityf of  data and the associated meta data - working for data owner - make sure data is approper labled an classified
5. data custodian -   handling the mgnt of sys on which data assets are stored - system admin whoc enforeces acecss control, encry and backup recovery measyres that protect data
6. data privacy officer - role respo for overisght of any kind of provacy related data like PII, SPI, PHI,
   - they ensure we follow all the regulaoty legal complaince, frameworks - data sovernity 

Data States:
1. Data at rest - data stroed in databases, file sys and other sys
   - encryption of data atrest
     - full disk encr
     - partition encr
     - file encr
     - volume
     - database
     - record
2. Data in transit/motion
   - SSL / TLS - cryptographic protocols designed to provide secure commnic over a compu network
   - VPN - tech that creates secure connection over a less secure network(internet)
   - IPsec - internet protocol securityprotocl suite used to seucre IP communications by authenticating and encrytping each IP pkt  in a data system
  
3. data in use
   - data in the process of creation, retirved, updated or deleted
   - security
     - application ;level
     - access controls
     - secure enclaves
     - intel software guards
    
Data Types:
- regulated data - PI, SPI, PHI   - regulated by laws
  - GDPR, HIPPA
- trade secrtes - type of comfidetial business infor rovides a companywith competive advantage
- intelectual property - creation sof the mind, innovations, designs, symbols - patents, copyrights, trademarks
- legal information - data related to legal proceedigs, contracts or regu compliance
- financial information -  data rlated to org's financial transactions  , slaes rec, invices, ban atements - subject to PCI DSS
- human readble data - texts, spreadhseets
- non humand readable data -  soft are to interpret - binary code or machine language

Data Sovereignty:
- conept that digital information is subject to the laws of the country in which it is located
- GDPR for euroian citicans data proetction


Securing Data:
- geographical restrictions - geofencing - confy with data seoveringty laws - rpeven unauthoaccess form high risk locations
- encryotion
- hashing
- masking
- tokeniztion - replaces sensitv data with non sensitve substitutes such as tokens
- obsfucation - making data unclear or uninteligible making ti difult oto understand for unauth users
- segmentation
- permission restrictions
the perimeter of the netw
Data loss prevention:
- set up to monitor data of a system, while in use, transit, at rest in order to detect any attemps to steal data
- software
- hardware

1. endpoint DLP system (can be st as prevent or detection mode) similar to IPS or IDS but this is specifically for data
   - a piece of softw installed on a workstationor laptop to monitor the data thats on that computer
  
2. Network DLP system
   - placed on the perimeter of the netw to detect the data in transit
3. storage DLP - encryted or watermarked
   - installed in server of the data center and inspect data on server while it is at rest
  
4. cloud based DLP system
   - offered a s SaaS - part of cloud service and storage needs


### Cryptography
- cyrptgraphy
- encryption
- hashing
- pki

Symmetric vs Asymmetric:

Symmetric Algo: private key
- encr algo, where the sender and reciver must know the same shared private key
- like a physical key for a lock to open and lock using the same key and same copy of key should be shared to everyone who has access
- since same share key is used by multiple, non-repudiation cannot be performed and confidentialit is at risk

Asymmetrick algo: public key
- encr algo wher diff keys are used to encrypt and decrypt the data
- one key to encr,
- another key to decr
- common algo - diffie hellman, RSA, eliptic curve cryptography ECC

Hybrid implementation:
- utilize asymmet encr to seculy transfer a private key that can be used wth symmertric encr

Stream cipher
- uses keystream generatro for bit by bit encr sing XOR function to create cipher text
- suited for securing real time communication data streams - streaming audio or video
- uses symmetric alog uses same key for both encr and decr
- hardware based solutions

block cipher:
- divides data into blocks and encrypts them
- softe based solution
- 64, 128, 256
- if less than the block size, additional data will be attached

Symmetric Alogorithms:
- DES, 3DES
- IDEA
- AES
- BLOWFISH
- TWO FISH
- RIVEST CIPHERS - RC4, RC5, RC6

DES - Data Encryption Standard
- uses 64 bit key and 8 bit used for parity
- each msg will be broken down into 64 bit blocks and pushed thru 16 rounds of transpostion

3 DES:
- uses 3 different keys to encrypt, decrypt and encrypt to generate a stronger cipher text

IDEA - Inetrnational data encr algorithm
- used in PGP - pretty good privacy suite tools

AES - Adv Encr Standard:
- symmetric block cipher  uses 128 bit, 192 or 256 bit blocks and matching encr key size to encry plain text to ciphertext
- rinjdal algo/cipher

Blowfish
 - uses 64bit blocks and variable length of encr key to encrpt

Twofish:
- 128 bit block and uses 128, 192, 256 bit key

RC cipher suite:
- dropped

RC4 - Rivest cipher 4
- symmetric
- variable key from 40 to 2048 bits - used in SSL and WEP
- symmteirc 64bit - 128 bit key

RC5 -symm block cipher -  key size upto 2048 bits

RC6 - stronger than RC5


Asymmetric algorithms:
- does not req a shared key - public key - isnce that is available to all public openly
- encrypt and decypt data using two different pair of keys - public and private key
- public key cryptography provides
  - CIA and non repudiation
- data encryptted using receiver's public key
- hash digest - msg encyprted with senders private key as a digital signature to confirm the sender - integrity of the message

diffie hellman:
- asymmetric
- used for key exchange inside creating a VPN tunnel establishment as part of IPSec
- key exchange of any kind over the internet

RSA - mathemeitcl difficlty of factoring large prime numbers
- used for key echange encr and difital signatures
- helps to proetct privat, pub key pairs
- key size between 1026 and 4096

Elliptic curve cryptography:
- mobile devices - hevily used
- algebrai strcture of elliptical curves
- ecc with 256 bit key is equal to RSA with 2048 bit key
- more ffiecnt than RSA
- 1. ECDH
     - ecc version of the popular diffie hellman key exchange protocol
  2. ECDHE
     - EPHEMERAL - uses a diff key for each portion of the key establishment process
  3. ECDSA - EC Digital signature algo
     - used for public key encr algo for  us giv digital sig

> ECC - mobile devices and low poer computing devices

Hashing:
- one way cryptographic function which converts data into a fixed value

MD5:
- creates a 128 bit hasg value unique to the input file

SHA-221 to SHA512:
- creates uptp 512 bit hasg value

RIPEMD - RACE integrity Primitive Evaluation Message Digest
- 160, 256, 320 bit versions

HMAC - Hash based message authentication code
- used to check the message integrity and authnticity is good
- usually combined with other algo HMAC-MD5, SHA1, SHA256

Digital Signature
- creating a hash file and then taking that result hash digest and encrypting it with a private key

DSS Digital security standard
- relies upon a 160 bit message digest created by digital secuerity algo

code signing - using digital sig for sharing other types


Increasing Hash Security:
two common attacks:
1. pass the Hash Attack
   - hashng techniq allws the attacker to  authenticate instead of user's plaintext pwd
   - since hashes ate stored in database and used for authentication instaed of direct plaintext pwds
   - MIMIKATZ - provides the ability to automate th process of harvesting the hashes and conducting the attack
3. Birthday attack
   - occurs when a attacker is able to send 2 diff mesg and results in same identical hash digest - collision
   - birthday paradox - 2 people n the random grp may have same bday
   - if another word brings the ame has value as pwd, then attacker can use wrong owd to login your system since the hash value of wrong owd and priginal pwd isame which is used for authenticating
   - Key Strecthing technique
     - used to mitigate the weaker key by increasing the time needed to crack it
   - salting - add random data into one way cyprographic hash to protect against pwd cracking techniques
     - dictionary attack - attacker tries every word from a predefined list
     - rainbow tables - precomputed tables for reversing cryptographic hasing - these are rendered ineffective agaunst salted hashing 
   - Nonce - number used once
     - often random number is added to pwd based authentication pocess
  - limting the failed login attempts

Public Key infrastructure
- uses asymmetric public ey encr
- involved certificate authority to provide tjey
- Key escrow to store the cryptographi keys
- creatses a secure channel between user and web server

when a broswer enters usrl, the server gets a certificate from CA and sends to browser
using web server's public key, a secure SSL/TLS connection is made to transfer the data 

Digital Certificate:
- digitally signed electorinc  document tht binds  a public key with user's identity
- x.509 protocol inside PKI
- inlcudes the name, email addres, even the public key , all infor abut CA too

1. wild card certificate / single user certificate for a full domain

subject alternate name - SAN field
- to use one certificate for multiple domains

2. Single sided certificate
   - only reqs the server to eb validated
  
3. Dual sided certificate
   - reqs both the server and user to be validated
   - twice the processing power
   - only used in high security envs

4. Self signed cert
   - certificate signed by the own identity instead of CA
   - level of truct is low
  
5. Third part cert
   - digital cert issues and signed by a trused certificate authority CA
  
6. Root of trust
   - each cert is validated using the concepot of rrot of trust or chain of trust
   - e.g: Verisign, Amazon, google, cloudFare
7. Certificate Authority
   - trusted third party who is going to issue these digi certs
  
8. Registration authority
   - reqs id info from user and fwds to CA to create digi certs
9. cert sighing req - CSR
    - a block of encoded text to requet for digi cert
    - contains - org name, dmain name, locality, country
9. cert revocation list
    - list of certs revoked by CA .. may be due to breaches
  
10. OCSP - Online Certificate Status Protocol
    - allws to determine the revocation status of any digi cert usng its serial number
    - lacks encr / security

11. OCSP stapling
    - allows cert holdet to get OCSP record   from server at regular intervals
    - this happens commonly in SSL/TSL handshake

12. Public key pinning
    - allws https web to resisis impersonation attacks fro who are tryoing to provide fradulant certs
   
13. Key escrow
    - recomened atleasy 2 admin when a key is taken out of key escrow
14. key recov agent
    - soft that allows restoration of lost  or correct key to be performed
  

Blockchain:
- a shared immutable ledger for recording transactions, tracking assets and building trust
- public ledger - a record keeping system that   maintains participants identities in a secure and anonymus format
- every action is securely logged using hashing
- smart contracts: self executing contracts where the terms of agreement and conditions are directly written into code
- provides transperancy, reduces fraud
- clear and indispute record of all transactions,

- permissioned blockchain(by ibm) - used for busines stransactions - promotes new level of trust and transparency using this immutable public ledger

Encryption tools: - to protect enterprise networks and system
- TPM
- HSM
- SECURE ENCLAVE
- Key management system

TPM - Trusted platform module ( like a personal vault)
- dedicated microcontroller designed to secure hardware thru integrated cryptographi keys
- BitLocker encryption feature in Windows OS
- securing the cryptograhic keys inside the isolated hardware, we add an additional layer of security agaisnt softare based attacks

HSM - Hardware security Module: ( high security Bank vault)
- physical device - safegards and amanagees digi keys, pri for mission critical situations, finalnical trans
- hardwa sec module which performs encr operatiosn withn a tamper profof env
- reliable choid for sensitive operations
- not only itgneretaes cryptog keys, provides acceletared cyprograioc functions

Key management system:
- a machanism to maange the life cycle of keys
- from creation, storing till deletion

Secure enclave:
- coprocessor integrated with main processor of some devices deisgned with the sole process of ensuring data rpotection
- isolates the coprocessor from main processor for protection of data
- e.g: secure enclave from apple iphones store the face id or finger pirnt id.. even the deice is compromised, these data are not touched and will be available for the authorized sole person


Obfuscation:
- steganography
- tokenization
- data masking

steganography - covered writing
- all about concelling a message within another, so that the very existence of the message is hidden
- a practice of hiding secret data withn ordinary non-secret files or messagesto avoid detection
- pri goal is prevent the suspicion that any hiddent data is isnide at all
- embedding data inside an image
- frequently used alongside of encr for extra layer of security
- stylesuxx.github.io/steganography
- hid inside another message, image or anything

Tokenization:
- techniq in data protection that involves substituting senstve data elements with non sestitvte equivalents called tokens which have no meaningful value
- mapping will be stored in org

Data masking:
- used to proteect data   by ensuring tht it remains recognizable but does not include any senstive info
- while mainting data authenticity usability
- aletering customer data for using in test regions without exposing any genuine information
- e.g. masking first 12 digits of crdit card

Cryptographic attacks:
- techniques and strategies that adversaries use to exploit vulnerabiulities in cryptographic systems with the intent to compromise CIA of data

- downgrade attacks
- collision attacks
- quantum computing


Downgrade attacks:
- version rollback attack - force a system into using weaker or odler cryptographic standard than what its curently utilizing
- to explout known vulnerabilities and weakness in those older protocols that are addressed in newer or more secure versions

POODLE attack - Padding Oracle on Downgraded Legacy Encrypotion attack - targetted SSL v3.0

Collision attack:
- aims to find two differnt inputs that produce the same hash output
- hashing is commonly used for data verification and integrity
- collision is a vulnerability in hashing

Quantum computing:
- a computer  that uses quantum mechanics to genrate amnipulate quantum bits qbits in order to access enormous processing power
- quantum communication -  a communcations network that relies on qbits made of photons(light) to send multiple combinations of ones and zeroes simultaeneously  which resulst in   tamper resistant and extremely faster communications
- QBIT - a quantum bit composed of elctrons and photos that can represent numerous combinations of ones and zeores  at the same time through superposition
- cryptoraphy can be taken down by using a quantum computer

- key exchanegs are using asymmettric communications
- using PKI

Post quantum cryptography:
- a new kind of cryptographic algo that can be impleted using todays' comuters but can be impervious to attacks from future quantum computers

- increase key size to increase the number of permutaions for brute force  - works well with using symmetric algo like AES

- post quantum resistant algorithms
  1. lattice based cryptography
  2. super singular isogeny key exchange
 
  NIST recommends
  - CRYSTALS Dilithium
  - FALCON
  - SPHINGS+
      
### Risk Management

- a fundamental process that involves identifying, analyzing, treating, monitoring and reporting risks

Risk assessment frequency:
- the regularity with which risk assessments are conducted within an org

1. ad-hoc - conducted as needed often in response to any incident or situation that has the potential to introduce new risks or change the nature of existing risks - natural disaster or incident - may be repeated if similar situations arise 
2. recurring - conducted at regular intervals, annually, quarterly, monthly - SOPs of an org - to regularly analyze and manage risks effectively
3. one-time - conduted for specific purposes and not repeated  - often associated with new project or change - new it system, undetraking a major constrction project, or planning significant org changes
4. continuous - ongoing monitoring and evaluation of risks - enabled by tech to conitnuosly monirot threats and risks

varies depending on the needs of org and types of risks involved within the  organization

Risk identification:
- recognizing potential risks that cpould negatively impact an org's  ability to operate or acheive its objectives

risk identification -> business impact analysis and determine key metrics
1.   Recovery time objeective RTO
2.   Recovery point objective RPO
3.   mean time to repaid MTR
4.   mean time between failures MTBF

tECHNIQUES USED IN RISK IDENTIFICATION:
1. brainstorming
2. cheklists
3. interviews
4. scenario analysis

Business impact analysis  BIA
- proces that involves evaluating the protential effects of disrption to an org's business functions/processes  

RTO - max acceeptable length of time that can elaps before the lack of a business fuction severly impacts the org
- target time, it must be restored to avoid unaccecptable consecquences
- e.g 2 hrs of downtime can be toletared befoe the impact on sales and customer satisfaction becomes severe

 RPO - max acceecptable   amount of data loss measured in time
 - point of time that data must be restored to resume business operations
 - e.g: a fin instutation can toetare uptp 15 mins of no data and must be restored within 15 mins to resume its operations

MTR - avg time requried to repair a componet or sys
- e.g 4 time to repair a machine back to operation

MTBF - avg time between failures
- its a meausre of reliability of a system or component
- avg time beet failures
- higher MTBF - incidactes a system tht failes less frequently - sign of a reliable and well maintained system

Risk Register:
- risk management - involving identification and assessment of uncertainities that may impact objectives
- risk register - risk log - a doc detailing identified risks including their desc, impactlikihood and mitigation strategies
- may resumble heat map risk matrix
- 1. risk description
  2. risk outcome
  3. risk impact - 
  4. risk level - combineing impact and likeligood - high, low, med
  5. risk likelihood - high , med , low
  6. cost - financil impact - potential expenses it it occurs or cost of mitigation
 
  Risk tolerance / Risk Accecptance:
  - refers to an org or indivi willingness to deal with the uncertainity in pursiuit of their goals
  - max amout of risk they are prepared to accept
  - tolerating/accepting risk - no countermeasures are defined because the level of risk doest not justify the cost or because there will be unavoidable delays befoe the countermeasures are deployed - simply the og chooses to not do anythingabt the risk
  - risk appetite -> org's willingness to embrace or retain sepecific types and evels of risk to fullfill its  strategic goals
  - 1. expansionary - org is open to taking more risk in the hopes of achieving greater returns
    2. conservative - less risk
    3. neutral - balance between risk and return
   
  Key risk indicators
  - predictive metrics used by org to signal risking risk levels in diff parts of enterprise
  - barometr for forward-looking view of future portential risk and often associated with org's risk appetite
  - provides a early wanring system for potential risk to proactively manage risk

  Risk owner
  - PERSON OR GRP RESPONSIBLE OR MANAGING THE RISK
  - monitoring, mitiga, upding risk register
 
Qualitative risk analysis:
- a method of assesing risks bansed on the portential impact and the likelihood of their occurance
- likelihood based on past exp, statitical analysis or expect decision
- impact - poten conse - cost time, quality, other critial metrics
- low, medium, high

Quantitative risk analysis - 
- objective and numerical evaluation of risks
- probablitic analysis of poten future events and typiclaly sued in ficnacial, safety and schedulng decisons
- performed using it key components
- 1. singel loss expectancy  SLE = value of asset * exposure factor
  2. Annualized rate of occurance ARO (once in 5 years is = 1/5 = 0.2)
  3. Annuzlized Loss expectancy ALE = SLE * ARO
  4. Exposure Factor EF
 
  Exposure factor
  - proportion of an asset that is lost in an event


Risk management strategies:
- transfer - risk sharing  - insurance /  contract indemnity clauses
- risk acceptance
  - excemption - certain small busines smight be excempt from certain reporting requirements
  - exception - provision that permits a party to bypass a rule or req  in certain conditions
- risk avoidance - strategy of altering plans or approoaches to completely eliminate certain risk - choosing operating a company in a diff country where laws works
- risk mitigation - implementing measures to decrease the likelihood or impact of a risk

Risk monitoring and reporting:
- ongoing monitoring
- 1. residual risk
     - likelhood or impact after implemeing mitigation, transference or acceptance measures on the initial risk
  3. control risk
     - how much less effective a sec-control has become over time
    
- risk reporting - a process of communicating imfo abut riskmgmt activities
  - infomed decison making
  - compliance
  - risk mitigation
  - stakeholder communication
 
  Third party vendor risks:
  - potential security and operational challenges introduced by external vendors, suppliers/service providers

Supply chain risks:
  1. hardware
  2. software - propeprly licensed , scanned , vul assessments
  3. managed service providers
     - org that provide a range of tech services and support to business and other cases like SaaS
     - evalaute data sec measures
     - ensure C and I
     - access cyber sec protocols
     - resp to sec breach
    everything must undergo a supply chain audit - not just cost effeicncy - perfm, sec, commit are all important

Supply chain attacks:
-attack that involves targetting a weaker link in the supply chain to gain access to a pri target
hardware:
chop washing - repackging the contents of a micro chp with a less expensive or or one with malware
some devices with malware brings backdoor

deliberate embedding of rootkits within devices by overseas suppliers

software:
- netw monitorng and mgmt soft - Solarwinds

chops act - to manuf chips within us broders to prevent prorein made malware contained ones - semiconductor suppli chain
- MSPs - managed service providers 
1. vendor due deligence
2. regi monito and audits
3. educat and collab
4. incorporating contarctual safeguards - to maintain sec stds

Vendor assessment
- a process that org implement to evaluate the sec, reliabil and perf of externam systems
- vendors - business or orgs that rpovides good and services to an org
- suppliers - indi involved in the produciona nd deliver of  products or parts of products
- MSPs - indivs hired by companies to manage IT services on behalf of an org

methods:
- penetration testing - reviw vendor audit clause - the right to audi clause grants org to evalauet vendors
- internal audit - evndors own self asseesment to evauate their patcicesagant industry std or org's reqs
- independant assessment - evaluation condyted by 3rd party entities that hav no stake in the org's or vendor's operations
- supply chain analysis - dive dep into evdors supply chain and assess the security and reliability of ech link

Vendor selection and monitoring:
- due diligence - rigorus evaluation goes beyond credentials
  - fin stability
  - operational history
  - client testimonials
  - on the groudn practices
- conflict of interest
- vendor questionnaires
  - data redun measures
  - security rpotocols
  - uptime gurante
  - disastar rec plans
- rules of engagement - temrs of inetraction
  - communication protcols
  - data sharing =policies
  - negotiation boundaries
 
- moniroting - perdiodic evaluations
- feedback loops -two way feedback sharing

contracts and aggreeements:
- clear boundries and guidelines
- foundation stone of most bsiness relationships

1. basic contract
2. SLA
3. Memorandom of agreement MOA - outlines roles/resps of involved parties
4. Memorandum of understanding MOU - declation of mutal intent - les binding
5. MSA - recurring , engament details, ayment term, confidentialty clause
6. Stament of work SOW - sppeficy details of specifi project - deliverabl, timeleins, milestoes - indepth details of certain sevreice or projecr
7. NDA - commitment to privacy - ensures sensit info share reminas confidential between both parties
8. Business partnetship aggreement BPA - two enties decides to pool their resouces for mutual profit - rofit shareng, exit strategies and more - Joint venture aggreement JV  


### Governance and compliance

governance
- strateic leadership , structures and prcessess that ensure an organization's IT  infra aligns with its business objectives
- key decison about risk mgmt, resos allocation, perf measurement
- establishing a stretegic framework that aligns with org's objectives and regulatory requirements
- this framw includes the rules, resps and proctices that guide an org in achiving its goals and managing its IT resos
- direcly influces the creation of and implemention of org's guidelienspolicies, std, and procedures
- shaping the path an org should follow - risk guideleins and reommended approach handling varios situations
- instrumental in policy development
- creating high level guideleins - outlines the org commitment and intentions toward certain actions suc as data protection or ethical conduct
- Monitoring and Revision when tech shift and givernance must adapt with latest changes and regulatory changes

Governance structures:
- boards - board of directrors oversee the management of an org
- committees - subgroup of boards - aduit committee, governance comm, secu-comm
- governement entities - they establish lay and regulations that ogrs must comply with
- centraliuzed and decentralized structures
  - centralized - decison making authority is concentrated at the top level of management - consistant decision making and clear lines of authority - slow to respond to local needs - large corp use centralized  to ensure consitant policies accross org
  - decentralized - distributes decison making authority throught the org - quicker decion making and greater response to local or departmental needs but can lead to inconsistancies


Polices:
- accecptable use
- info sec
- business conti
- disaster reco
- incident response
- SDLC
- change mgmt

