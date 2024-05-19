
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

Data loss prevention:
- 
